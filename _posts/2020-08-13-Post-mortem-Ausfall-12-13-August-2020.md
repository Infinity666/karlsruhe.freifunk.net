---
layout: post
title: "Post-mortem Ausfall 12. - 13. August 2020"
date: 2019-08-13 23:30:00
categories: community
---

Vom Mittag des 12. bis zum Nachmittag des 13. August 2020 war Freifunk Karlsruhe von einem Ausfall großer Teile der Infrastruktur betroffen. Konkret waren alle selbstgehosteten Services von Freifunk Karlsruhe und teileweise auch Freifunk Westpfalz betraf. Grund dafür war ein sogenannter Fibercut am 12. August, welcher bei Bauarbeiten nahe der Haltestelle Yorkstraße in Karlsruhe auftrat. Hierbei wurden beide Glasfasernstrecken, welche unseren Standort mit dem Internet verbinden, von einem Bagger durchtrennt. Erst am 13. August gegen 16 Uhr konnte die Störung behoben werden.

<!--*-->

### Weitere Details
Am 12. August 2020 war das Freifunk-Netz ab 13:13 Uhr nicht mehr erreichbar. Eine erste Recherche ergab, dass es sich um ein Problem unseres Carriers handeln müsse, da auch unser Out-of-Band-Zugriff sowie das separat gehostete Monitoring-System nicht mehr erreichbar waren. Gegen 14:30 Uhr erreichte uns die Information unseres Carriers, dass auch dieser seit ca. 13:15 Uhr beide Router am Standort nicht mehr erreichen kann und es sich um vermutlich um einen Fibercut handelt. Gegen 16:00 Uhr wurde der Fibercut von unserem Carrier bestätigt. Ein Störungsende war zu dem Zeitpunkt für die frühen Morgenstunden des 13. August 2020 prognostiziert.
Da sich der Firbercut anscheinend als schwerwiegender herausstellte als ursprünglich gedacht, konnte der Termin nicht gehalten werden. Die Glasaser-Verbindung wurde daher erst um 16 Uhr des 13. August 2020 wieder hergestellt.

### Welche Schritte wurden unternommen?
Nach der Bestätigung über die außerhalb unseres Einflussbereichs liegenden Gründe für den Ausfall seitens unseres Carrieres begannen wir mit der aktiven Kommunikation des Status via Twitter, da wir keine Möglichkeit sahen, kurzfristig den Zustand zu beeinflussen: [Twitter](https://twitter.com/FFKarlsruhe/status/1293527355152097280)
Noch am Abend des 12. August wurde evaluiert, ob wir den sich grade im Aufbbau befindlichen zweiten Standort in einem anderen Karlsruher Rechenzentrum kurzfristig in Betrieb nehmen können. Leider war dies keine realstische Option, da die Hardware vor Ort noch nicht vollständig ist und weitere Komponenten hätten besorgt werden müssen, was nicht in dem kurzen Zeitraum möglich war.
Nachdem selbst um 15:00 am 13. August noch keine funktionierende Verbindung und keine verlässliche Voraussage über das Störungsende vorlagen, wurden Notfallpläne für die Einrichtung einer Richtfunkstrecke als temporären Uplink angestellt. Hierzu wurde bereits Kontakt zu lokalen Einrichtungen aufgenommen, welche uns evtl. auf der Gegenseite hätten unterstützen können. Die Umsätzung der Pläne war frühestens für die Abendstunden angedacht, bis wohin die Störung jedoch behoben werden konnte.


### Was lernen wir daraus?
Die Qualität des von Freifunk Karlsruhe bereitgestellten Netzes ist stark von seinen Sponsoren abhängig. Aktuell haben wir nur einen Sponsor für die Außenanbindung am aktuellen Standort. Die Außenanbindung ist redundant ausgeführt; wir können selbst zum aktuellen Zeitpunkt nur über die Gründe spekulieren, warum die redundanten Glasfasern über die selbe Trasse geführt wurden.
Die einziege Abhilfe schafft in dieser Situation die Anbindung des Standorts über einen weiteren, unabhängigen Carrier, z.B. via Glasfaser-Verbindung in ein anderes Rechenzentrum oder durch Sponsoring von Transit direkt am Standort.
Weiterhin war es sinnvoll, externe Kommunikationskanäle (primär Twitter und IRC), welche nicht von der Störung betroffen waren, für die Kommunikation zu nutzen. Zukünftig möchten wir bei größeren Störungen auch via Mailingliste benachrichtigen.

Um die Netz-Qualität von Freifunk Karlsruhe langfristig zu erhöhen wird derzeit ein zweiter, vollwertiger Standort in einem anderen Rechenzentrum in Karlsruhe eingerichtet. Sobald dieser in Betrieb ist, sollten auch bei Totalausfall eines einzelnen Standorts das Freifunk-Netz selbst, sowie für den Betrieb zentrale Dienste, mit minimalen Einschränkungen weiterlaufen.

Die vielen Anfragen, welche wir auf verschiedenen Kanälen während der Störung erhielten, zeigen uns, welchen Stellenwert Freifunk in Karlsruhe hat, und wie viele Menschen unser Netz nutzen -- dies ist für uns eine große Motivation.

### Wie kann ich unterstützen?
Momentan betreiben wir das Netz auf Basis von Spenden und Sponsorings. Wenn du finanziell etwas beisteuern kannst freuen wir uns [über eine Spende](https://karlsruhe.freifunk.net/mitmachen/spenden/). Ebenfalls freuen wir uns über die Vermittlung von Kontakten zu lokalen Dienstleistern oder Institutionen, welche uns konkret unterstützen können, z.B. durch die Bereitstellung von Glasfaser-Strecken, L2-Transport, Transit oder Dächern hoher Gebäude für die Installation von Richtfunk-Equipment.

