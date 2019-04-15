---
layout: post
title: "Updates zum Thema Netz, Backbone, Firmware und Hardware"
date: 2019-04-15 15:00:00
categories: community
---

in letzter Zeit hat sich viel am Freifunk-Netz in Karlsruhe getan, eine ausführliches Update auf der Mailingliste steht bis jetzt noch aus - dies möchten wir hiermit nachholen!

## Netzaufteilung

<!--*-->

Wie bereits im Dezember auf der Webseite angekündigt wurden hinter den Kulissen viele Vorbereitungen für die Aufteilung des Netzes in verschiedene Domänen getroffen.

So wurden zwei neue Gateways für das Mesh Netz in Betrieb genommen, welche über einen sehr modernen Software-Stack verfügen. Die Hardware auf der wir die Gateways betreiben befindet sich komplett in unserer Colocation. Extern zugemietete Server werden nicht mehr benutzt.
Insbesondere der Saltstack mit dem die Gateways aufgesetzt, gewartet und betrieben werden wurde dabei komplett überarbeitet und verbessert.

Seit Firmwareversion 0.6.2 sind nun auch endlich (fast) alle Domänen in diese integriert, sodass diese auch genutzt werden können. Bei Updates auf diese (oder neuere) Firmwareversionen verbinden sich die Knoten standardmäßig noch mit den alten Albufer-Gateways. Eine andere Domäne wurde nur dann genutzt, wenn sie bei einer Neuinstallation ausgewählt oder manuel nachträglich geändert wurde.

In diesem Zuge wurden auch Domänen für die Ortenau, Pforzheim und Hohenlohe angelegt, sodass zukünftig alle Communities eine einheitliche Firmware nutzen können. Dadurch wird der Wartungsaufwand reduziert und Änderungen am Netz können schneller ausgerollt werden. Die SSID wird sich dadurch natürlich nicht ändern.

Zusätzlich enthält die neue Firmware eine Schnittstelle zu dem von Freifunk Darmstadt entwickelten Domain Director. Hierbei handelt es sich um eine Serveranwendungn, welche im lokalen Freifunk-Netz betrieben wird und den koordinierten und zeitlich abgestzimmten Umzug von einzelnen Knoten bzw. ganzen Meshes in eine andere Domäne erlaubt. So soll sichergestellt werden, dass Knoten über die neuen Domänen verteilt werden und keine Knoten im alten Netz zurückbleiben. Dies ist wichtig, da das alte Netz mittelfristig abgeschaltet wird. Die Zuordnung von Knoten zu Domänen erfolgt dabei über die Geoposition der Knoten.
Die Funktionalität, einzelne Knoten und Meshes umzuziehen, konnte von Freifunk Karlsruhe beigesteuert werden.

Seit Ende März verwenden wir den Domain Director, um nach und nach einzelne Nodes oder kleinere Meshes in die neue Infrastruktur zu migrieren.

Mit den deutlich kleineren Layer-2-Netzen und BATMAN-Meshes ist das Grundrauschen im Netz deutlich zurück gegangen und Freifunk in Karlsruhe ist so hoffentlich für alle ein Stück besser geworden.


## Backbone Netz

Auch das Backbone-Netzwerk wurde komplett überarbeitet: Herzlich Willkommen in AS202329! Freifunk Karlsruhe betreibt nun ein eigenes Backbone (IPv4 und IPv6) und erhält Transit von redundanten Upstreams.
Um dem neuen Standard gerecht zu werden haben wir darüber hinaus einen zweiten Core-Router in Betrieb genommen, sodass es bei Ausfall eines Routers zu keinen Einschränkungen kommen sollte.

## Firmware und Hardwareempfelungen

Mit der neuen Firmware können wir nicht nur endlich unser Netz aufteilen, es wird auch jede Menge neue Hardware unterstützt. Im Zuge dessen wurde unsere Seite mit Hardwareempfehlungen überarbeitet. Ihr findet dort Modell-Empfehlungen für verschiedene Anwendungsfälle und verschiedene Budgets.
Wir danken den Freifunkern aus Darmstadt für ihre herausragende Arbeit.

Auch unseren eigenen Hadware Pool haben wir entsprechend aufgefrischt:  Im Entropia halten Mitglieder eine Sammlung von AVM Fritzboxen 4020 und 4040 auf Lager, welche zum Selbstkostenpreis mit vorinstallierter Freifunk-Firmware erworben werden können.

Experimentell unterstützen wir Geräte von Devolo mit einem sehr guten Preis-Leistungs-Verhältnis. Diese können ebenfalls von Mitgliedern zum Selbstkostenpreis erworben werden.

Unser Ziel dabei ist es, allen einen möglichst günstigen Umstieg auf ein Modell zu ermöglichen, welches auch in den nächsten 5+ Jahren Unterstützung für die Freifunk-Firmware haben wird.


## Das Ende von 4/32

Die aktuelle Firmware ist gleichzeitig die letzte mit Unterstützung für 4/32er Geräte (Geräte mit 4MB Flash und 32MB RAM). Diese laufen nicht mehr zufriedenstellend mit aktuellen Firmwareversionen. Schon vor einiger Zeit haben wir daher begonnen, vom Einsatz dieser Geräte abzuraten und keine Installations-Images für diese mehr zur Verfügung zu stellen.

Aus diesem Grund wollen wir Vorsorge treffen: Neben der Unterstützung für viele neue und attraktive Geräte mit den neuen Firmwareversionen werden wir am 1.5.2019 damit beginnen, technische Maßnahmen zu ergreifen, welche die Verbindung neuer 4/32er-Geräte mit dem Netz verhindern.

Eine Liste an nicht mehr unterstützen Geräten findet ihr hier:
https://karlsruhe.freifunk.net/news/2018/05/28/eol-devices/

Zu dem Thema wird es noch einmal einen separaten Blogpost geben.

Bei Fragen könnt ihr euch gerne auf der Mailingliste oder im Forum (https://forum.ortenau.freifunk.net) melden.
Und sonst kommt doch mal wieder beim Treffen vorbei: https://karlsruhe.freifunk.net/kontakt/

Viele Grüße und bis bald
Simon und Julian
