---
layout: post
title:  "Hinweis zu bevorstehendem Firmware-Update für Betreiber von virtuellen Maschinen"
date:   2018-01-07 00:00:00
categories: community
---

TL;DR:
Zur Zeit bereiten wir das Update auf Firmware-Version 0.5.0 vor, welches auf der aktuellen Gluon-Version 2017.1.x basiert. Die Images für x86-basierte Systeme, wie z.B. Virtuellen Maschinen oder Offloader, benötigen nun mehr Speicher als bisher. Dies führt bei Systemen, welche die neuen Speicherplatzanforderungen nicht erfüllen können, zu Bootloops nach dem Update. Davon betroffen dürften vor allem virtuelle Maschinen sein, da die virtuellen Disks standardmäßig in der Größe des installierten Images angelegt wurden, und damit in den meisten Fällen zu klein sein dürften.

Daher: __Bitte vergrößert die virtuellen Disks auf mindestens 273MB.__

<!--*-->

## Lange Version

Zur Zeit bereiten wir das Update auf die Firmware-Version 0.5.0 für alle Freifunk-Karlsruhe-Knoten vor. Die Firmware basiert auf Gluon __2017.1.4__, im Gegensatz zur bisher eingesetzten Version 2016.2.7 (in Firmware 0.4.2).

Die signifikanteste Änderung betrifft den _Wechsel von OpenWRT auf LEDE_ (seit kurzem wieder bekannt als OpenWRT). Dieser Wechsel führt dazu, dass die x86 images mehr Speicher benötigen, als dies bisher der Fall war: Lag die Größe der Images bisher bei ungefähr 55MB, __benötigen die auf Gluon 2017.1 oder neuer basierenden x86-Images nun mindestens 273MB__.

Da physikalische Systeme in der Regel sowieso mehr Speicher zur Verfügung haben, rechnen wir hier nicht mit größeren Problemen. Probleme könnte es jedoch bei Virtuellen Maschinen geben, da die Größe der virtuellen Disks oft auf die exakte Größe des initial installierten Images festgelegt wird - in diesem Fall also auf ca. 55MB.
Bei einem Update wird das installierte Image also mit einem Teil des neuen Images ersetzt, **was zu einer ungültigen Partitionstabelle führt. Dies wiederum kann zu einem Bootloop der betroffenen Systeme führen.** Dies kann nicht durch den Auto-Update-Mechanismus abgefangen werden.

Aus diesem Grund __bitten wir alle Betreiber von Virtuellen Maschinen, die Größe der virtuellen Disk entsprechend zu erhöhen__, z.B. auf 300MB. Weitere Informationen dazu können dem [Changelog von Gluon](https://gluon.readthedocs.io/en/v2017.1.x/releases/v2017.1.html) entnommen werden. Dort findet sich auch ein Beispiel, wie die Anpassung der Größe auf qemu-basierten Systemen durchgeführt werden kann.

Bei Fragen oder Problemen zögert bitte nicht, [mit uns Kontakt aufzunehmen](/kontakt/)!
