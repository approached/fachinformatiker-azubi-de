---
title: RAR - UNRAR
---

# RAR - UNRAR

In Linux kann man das proprietäre Archivformat *Rar* ebenfalls nutzen.
Für das packen benötigt man das Paket **rar** und für das entpacken der
rar Dateien das **unrar** Paket.

## Packen

Die Syntax für das Packen eine rar Archiv lautet wie folgt:

`rar a <archiv> <file1> [file2] usw.`
`rar a CSS-File.rar online.css style.css print.css`

Möchte man die Datein mit Passwort verschlüsseln dann gibt man folgende
Option mit:

`rar a CSS-File.rar -h online.css style.css print.css   oder`
`rar a CSS-File.rar -hp online.css style.css print.css`

Der Unterschied zwischen h und hp ist. Das bei hp ebenfalls der Header
verschlüsselt ist. Das bedeutet man nicht mal rein schauen welche
Dateien sich im Archiv befinden.

-   Möchte man Ordner Rekrusiv also auch die Dateien und Ordner die sich
    befinden Packen, dann packt man die Option `-r` hinzu.
-   Möchte man keinen Passwort Eingabe durchführen sondern direkt in der
    Anweisung angeben, dann geschieht das folgender maßen.

` rar a CSS-File.rar -r -hpMEINGEHEIMERPASSWORT /etc/ /var/www/`

Dies kann in automatische Script gut eingebaut werden.

## Entpacken

Das Entpacken einer rar geht folgendermaßen:

`unrar x test.rar`

## Backup Script

Mittels diesem Script kann man easy Passwortgeschützte Archive erstellen
und diesen dann übertragen.
