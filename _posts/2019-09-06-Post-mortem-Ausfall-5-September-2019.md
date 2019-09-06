---
layout: post
title: "Post-mortem Ausfall 5. September 2019"
date: 2019-09-06 19:30:00
categories: community
---

Am 5. September 2019 gab es einen größeren Ausfall der Freifunk-Karlsruhe-Infrastruktur, welche nahezu alle Services von Freifunk Karlsruhe und Freifunk Westpfalz (welche unser Backbone mitnutzen) betraf. Erste Probleme machten sich um die Mittagszeit bemerkbar, grundlegende Dienste wurden um ca. 23:00 wiederhergestellt, wenige Dienste konnten erst im Laufe des 6. Septembers wiederhergestellt werden.

### Was ist passiert?
Zum Beginn der Störungen wurden Broadcast Storms im Netzwerk eines anderen Anbieters beobachtet, welche aus ungeklärter Ursache zu Problem auf einem userer Switches führte: Der betreffende Switch begann, einen großen Anteil aller Pakete auf allen Ports zu verlieren, hoher Packet Loss im (nahezu) gesamten Netzwerk war die Folge.
<!--*-->
Der Upstream-Port zum betreffenden Anbieter wurde als erste Hilfsmaßnahme physikalisch ausgesteckt, die Symptome blieben jedoch bestehen. Auch ein Reboot des Switches konnte das Problem nicht lösen.
Gegen 17:00 Uhr fiel die Entscheidung, den Switch auszutauschen. Ersatz wurde kurzfristig aufgetrieben und konfiguriert, was ca. bis 21:00 gedauert hatte. Ab 21:00 wurde der alte Switch ausgebaut und durch den neuen Switch ersetzt. Einige Konfigurationsänderungen mussten vor Ort durchgeführt werden, bis die Konnektivität wieder komplett hergestellt war.
Da die Hosts des VM-Clusters an besagtem Switch angeschlossen waren und zur persistenten Speicherung auf das verteilte Ceph-Dateisystem setzt, welches dadurch ebenfalls vom Ausfall betroffen war, musste zusätzlich Zeit in die Recovery des Clusters investiert werden. Während die meisten Services im Anschluss wieder gestartet werden konnten, kam es bei einigen wenigen VMs zu einer Korruption der virtuellen Festplatte. Betroffene VMs wurden am morgen des 6. Septembers aus einem Off-Site Backup wiederhergestellt.

### Welche Schritte wurden unternommen?
Eine erste Analyse zeigte schnell, dass der Switch hohen Packet Loss verursachte. Als erste Gegenmaßnahme wurde der Uplink, von welchem wir annehmen er würde die Probleme verursachen, physikalisch ausgesteckt. Nachdem dies zu keiner Verbesserung führt wurde ein Reboot des Switches durchgeführt. Als auch dies nicht zu erfolg führt wurde schnell die Entscheidung getroffen, den Switch unmittelbar auszutauschen.
Nach Inbetriebnahme des neuen Switches wurde unmittelbar die Recovery des Ceph-Dateisystems gestartet.

### Was lernen wir daraus?
Bei Freifunk handelt es sich um eine ehrenamtliche Tätigkeit, welche auf Grund fehlender finanzieller Mittel auf die Nutzung gespendeter Hardware angeweisen ist. Der betroffene Switch war alt und sollte mittelfristig ausgetauscht werden, Ersatz stand jedoch noch nicht bereit. Um die Fehleranalyse zu vereinfachen wäre ein Monitoring des Switches eventuell nützlich gewesen, wobei auch das Monitoring selbst vom Ausfall des Switches wahrscheinlich unmittelbar betroffen gewesen wäre. Während nahezu das gesamte eingesetzte Setup redundant aufgebaut ist stellen die Switches momentan einen Single Point of Failure da, welcher sich im Zuge des Ausfalls gänzlich manifestierte. Zukünftig könnte der Einsatz redundanter Switche möglicherweise Ausfälle wie den voliegenden verhindern, die Komplexität eines solchen Setups ist jedoch unwahrscheinlich höher als die der aktuell eingesetzten Lösung. Es sollte darüber evaluiert werden, ob es Sinn macht, die VM-Hosts direkt miteinander zu verbinden (z.B. in Form eines redundanten Rings), damit der Ausfall einer Netzwerk-Komponente zukünftig keine Probleme im Kontext des verteilten Ceph-Dateisystems mehr verursachen kann. Auch haben wir zu Zeit keinen Vollständigen zweiten Standort der einen Ausfall des ersten Standots komplett abfangen könnte.