---
title: Router einrichten
layout: page
sub_menu: true
top_url: /mitmachen/
sub_weight: 4
permalink: /mitmachen/router-einrichten/
---

Diese Anleitung richtet sich an TP-Link und ZyXEL Geräte.
Solltest du einen Ubiquiti UniFi AP flashen wollen, findest du [hier](https://docs.karlsruhe.freifunk.net/firmware/unifi-ac/) die weitern Schritte.
Für einen AVM Router/Repeater findest du die nötigen Schritte [hier](https://fritz-tools.readthedocs.io/de/latest/).  


### Den Router anschließen


1. Lade das passende Erstinstallations-Firmware-Image für deinen Router [von unserer Seite](https://firmware.karlsruhe.freifunk.net) herunter.
2. Verbinde deinen Computer mit einem der gelben LAN-Anschlüsse des Routers.
3. Dein Computer erhält nun automatisch via DHCP eine IP-Adresse.

### Installiere das Freifunk-Image

1. Öffne das Webinterface deines Routers in deinem Browser.
2. Folge den Anweisungen im Handbuch deines Routers, um die Firmware zu aktualisieren.
3. Nutze nun das zuvor heruntergeladene Firmware-Image.
4. Warte, bis der Router wieder gestartet ist.

### Konfigurationsmodus

Dein Router sollte nun in den Konfigurationsmodus starten. Du erhältst erneut eine IP-Adresse per DHCP, dein Freifunk-Router ist nun unter [http://192.168.1.1](http://192.168.1.1) in deinem Browser erreichbar.

### Den Router konfigurieren

1. Wähle einen Namen nach dem Schema `ffka-Wahlname`, also bspw. `ffka-Kaesekuchen`.
2. Aktiviere das `Mesh-VPN`, um eine Verbindung mit dem Freifunk-Netz über das Internet herzustellen
3. Füge GPS-Koordinaten des Router-Standorts ein. Diese kannst du auf unterschiedliche Weisen erhalten:
  - Am PC: über [unsere Karte](https://karlsruhe.freifunk.net/karte/) (Zuerst Pin klicken, dann Doppelklick auf die Position des Routers)
  - Android: [GPS Status & Toolbox](https://play.google.com/store/apps/details?id=com.eclipsim.gpsstatus2)
4. Trage eine funktionierende Kontaktmöglichkeit ein. Deine Adresse wird ausschließlich zur Kontaktaufnahme durch uns genutzt und niemals an Dritte weitergegeben.
Nach einem Klick auf `Speichern und Neustarten` siehst du den Öffentlichen Schlüssel für den VPN-Zugang. Diesen sendest du bitte per E-Mail an [keys@karlsruhe.freifunk.net](mailto:keys@karlsruhe.freifunk.net).

	> &#35; ffka-Wahlname \\
	> &#35; lambda \\
	> &#35; a1:01:00:ab:cd:ee \\
	> key "f1d2d2f924e986ac86fdf7b36c94bcdf32beec15";


Danach startet der Router neu, sendet das WLAN `karlsruhe.freifunk.net` aus und versucht, sich per Mesh mit anderen Nachbarn zu verbinden. Falls du keine Mesh-Nachbarn hast, ist eine Verbindung mit dem WLAN-Netzwerk erst dann möglich, sobald sich der neue Freifunk-Knoten mit unserem `Mesh-VPN` verbunden hat.

Der Router ist jetzt im Normalbetrieb und nicht mehr unter der Adresse [http://192.168.1.1](http://192.168.1.1) erreichbar, für weitere Änderungen siehe [FAQ](/was-ist-freifunk/faq/).

### Den Router aufstellen
Als Standort empfehlen sich Fenster, Balkone oder Dächer. Je näher er der Außenwelt ist, desto wahrscheinlicher ist es, dass er für Passanten erreichbar ist und sich mit anderen Routern verbindet, um eine [Meshverbindung](https://de.wikipedia.org/wiki/Vermaschtes_Netz) zu bilden.

### Verbinde den Router mit dem Netzwerk

Wenn du deinen Internetzugang zur Verfügung stellen möchtest, verbinde jetzt den blauen WAN-Anschluss deines Freifunk-Router mit deinem vorhandenen Internetrouter. Möchtest oder kannst du das nicht, bist du auf andere Freifunker in deiner Nähe angewiesen, um eine Verbindung zum Freifunk-Netzwerk und ins Internet herzustellen.

### Fertig

Super, du hast es geschafft. Dein Freifunk-Knoten funktioniert jetzt und sollte, wenn du GPS-Koordinaten angegeben hast, in Kürze auf der [Karte](https://karlsruhe.freifunk.net/karte/) erscheinen.

Außerdem haben wir für dich einen [Beipackzettel](../..//images/freifunk_karlsruhe_beipackzettel_a5_du.pdf) vorbereitet, auf dem alle wichtigen Punkte noch einmal zusammen gefasst sind.
