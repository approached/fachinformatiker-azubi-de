---
title: Rsync HowTo
description: 
published: true
date: 2022-02-09T13:31:00.426Z
tags: 
editor: markdown
dateCreated: 2022-02-09T13:30:59.023Z
---

# Rsync HowTo

Mittels dem Protokoll **Rsync** kann man komfortabel Daten abgleichen.
Dabei kann man dieses Protokoll nicht mit einem File-Transfer-Protocol
oder ähnlichem vergleichen. Es ist weit aus mächtiger. Rsync kann genau
feststellen welchen Änderungen z.B. in einer Textdatei geändert wurden
und kann damit als eine Art *Patch* liefern. Dadurch wird nur der Patch
übertragen, also nur die Textpassagen die sich geändert haben.

Das bedeutet das wenig Datenverkehr fließt und eine höhere
Rechenleistung angewendet werden. Somit ist das fortsetzen der
Dateiübertragung immer problemlos möglich.

## Dateien zum Server mittels SSH übertragen

In diesem Beispiel wollen wir unsere erstellten Dokumente auf eine
externen Server sichern.

`rsync -aPvze ssh document/ hans@server.com:document`

Die Parameter haben folgende Bedeutung:

1.  a kopiere Dateien mit den Optionen symbolische Links,
    Unterverzeichnis, Rechte (Benutzer, Gruppe und Besitzrechte), Zeiten
2.  P Fortschrittsanzeige und Fortsetzung beim Abbruch des Transfer
3.  v Verbose, zeigt alle Änderungen
4.  z Komprimiert die Daten vor der Übertragung
5.  e Ermöglicht die nutzung von der Remote Shell somit SSH

Sollten sich die lokalen Dateien verändert haben, dann möchte man die
gelöschten Dateien auch nicht mehr Besitzen.

`rsync --delete -aPvze ssh document/ hans@server.com:document`

Mittels **--delete** werden nicht mehr verwendeten Dateien gelöscht.

## Dateien vom Externen Datenträger A Datenträger B übertragen

Man sollte die Komprimierung in diesem Fall auslassen.

`rsync --delete -aPv /media/approach/Trick/ /media/approach/Track/`

## Ordnern von der Übertragung ausschließen

`rsync --delete --exclude=toDelete/ --exclude=Videos/damn/ -aPv /media/approach/Trick/ /media/approach/Track/`

Es besteht auch die Möglichkeit eine Datei mit den jeweiligen Ordnern
und Dateien anzulegen welche ausgeschlossen werden sollen.

## Code Snipet

Backup:

    rsync -rvptgluPEze ssh --delete --update --stats --bwlimit=30 user@server:~/ ~/