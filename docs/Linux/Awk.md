---
title: Awk
---

# Awk

## Beschreibung

-   Awk ist ein Programmiersprache
-   Awk hat die Syntax von Unix
-   Das Paket in Linux, nennt sich *mawk*
-   Es dient zur Ausgabe von bestimmt Daten anhand einer Textdatei
-   Ebenso eigenen sich gut auch .csv Datein
-   Es wird fast ausschließlich mit Strings gearbeitet
-   Es wäre nicht verkehrt das Know-How zu haben von regulären Ausdrücken.

## Bespiele

### Einfache Ausgabe

Hier ein paar einfache Anwendungsbeispiele dazu, die man z. B. unter
Linux einfach in einer Shell eingeben kann:

    echo Hallo Welt | awk '{print $1}'

Die Ausgaben wird ein *Hallo* sein.

### Sonderzeichen

-   Für die Nutzung der Sonderzeichen wird der *Backslash* benötigt.
-   Das darstellen von Sonderzeichen mit einem Backslash ist in Unix
    eine Standard.

`cat final.csv | awk '{print "UPDATE geo_orte SET bundesland_code = " $2 " where plz = " $1 ";"}' | less`
`cat final.csv | awk '{print "UPDATE geo_orte SET bundesland_code = '\`*`"`` ``$2`` ``"'\`*` where plz = '\`*`"`` ``$1`` ``"'\`*`;"}' > final2.sql`

`ls -l  | awk '{print "ddrescue -v " $9 " /media/Track/"$9}'`

## Notes

-   Trennzeichen: --field-separator=";"
