---
layout: post
title: "Das Freifunk Netz wird aufgeteilt"
date: 2018-12-16 12:00:00
categories: community
---

Freifunk Karlsruhe ist in den letzten Jahren stark gewachsen, und ist dabei an seine Grenzen gekommen.
Deswegen haben wir uns entschieden das Freifunk Netz in mehrere kleinere Domains aufzuteilen.
Das passiert in den nächsten Wochen vollkommen Automatisch.

<!--*-->


## Domains

Auf der Karte findet ihr eine Übersicht über unsere Domains. Die Domains haben wir in Karlsruhe an den Statistischen Bezirken in der Stadt orientiert, im Umland vor allen an den Postleitzahlen. Kleine Ausnahmen bestätigen dabei die Regel.

Benachbarte Domains, welche in gleiche Farbe teilen sich ein gemeinsames Netz und können somit deswegen miteinander meshen. Mit der feineren Aufteilung innerhalb einer Farbe ist es in Zukunft deutlich einfacher doch feiner Domains zu erstellen.


## Firmware Update & Automatische Migration

In kürze werden wir die Firmware 0.6.2 als Stable veröffentlichen.
In dieser Firmware gibt es mehrere Neuerungen.
Schon seit Firmware 0.6.0 wird man beim Setup bereits gefragt in welche Domain man den Knoten aufstellen wird.
Zusätzlich beinhaltet die Firmware 0.6.2 nun auch eine Automatische Migration.
Das heißt das euer Knoten sich automatisch die korrekt Domain von unseren Gateways zuweisen lassen.

Dafür ist es notwendig das wir die ungefähre Position des Freifunk Routers kennen. Da das leider bei vielen Routern nicht der Fall ist beziehen wir automatisch die BSSID und Empfangsstärke benachbarter WLAN-Netze von den Knoten und nutzen diese für eine temporäre Lokalisierung der Knoten. Diese Daten werden dabei nicht gespeichert.


Für Knoten aus der Ortenau, Pforzheim, oder Hohenlohe änder sich bei der Auswahl der Domäne zudem die SSID auf die der jeweiligen Community. Eine Separate Firmware ist damit nicht länger notwendig.


## FAQ


### Was ist mit bestehenden Mesh-Netzen?

Wir beachten bereits bestehende Mesh-Verbindungen und behalten diese auch während der Migration bei. Für den Fall dass ein Mesh zwischen zwei Knoten in über mehrere Domänen lappen würde, so werden beide Knoten in die gleiche Zieldomäne zugeordnet.

### Was ist nach der Umstellung zu beachten?

Für Freifunk Nutzer ist eigentlich nichts weiter zu beachten, Freifunk funktioniert einfach weiter. Allerdings ändern sich die IP-Adressen des Freifunk-Knotes selber. Die neue IP-Adresse nach der Umstellung kann auf unserer Karte in Erfahrung gebracht werden.
