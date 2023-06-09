---
title: TCP und UDP
description: 
published: true
date: 2022-02-16T20:41:17.409Z
tags: 
editor: markdown
dateCreated: 2022-02-16T20:41:16.378Z
---

# TCP und UDP

UDP steht für User Datagram Protocol und TCP für Transmission Control
Protokolle . Beide Protokolle sind für den Austausch von Daten geeignet.
Beide Protokolle gehören zum [TCP-IP Model](/TCP-IP_Model).

Der wesentlich unterschied zwischen **TCP und UDP** ist: Das sie
unterschiedliche *Referenzdaten* haben. Das bedeutet TCP benötigt eine
Information ob Paket XY angekommen ist. UDP dagegen schickt einfach
Daten los in der Hoffnung das es Endverbraucher die Daten erhält.

Heutzutage wird UDP immer weiter Interessanter. VoIP oder IpTV setzen
grundsätzlich auf das Konzept von **UDP**. Die Haushalte verfügen
meistens höhere Bandbreiten. Sodass man davon ausgehen kann, dass die
Daten ankommen werden. Man benötigt keine **Metainformation** ob nun
tatsächlich das Paket angekommen ist.