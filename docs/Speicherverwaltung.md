---
title: Speicherverwaltung
description: 
published: true
date: 2022-02-09T13:07:06.084Z
tags: 
editor: markdown
dateCreated: 2022-02-01T16:56:53.386Z
---

# Speicherverwaltung

Unter Speicherverwaltung versteht man die Verwaltung eines realen
Speicher und virtuellen Speicher. Dabei werden Dateien von dem
Betriebssystem zu dem realen Speicher ausgelagert. Später wenn die Daten
benötigt werden, dann werden die wieder eingelesen.

## Reale Speicherverwaltung

Die Reale Speicherverwaltung wird als physikalischer Hauptspeicher
benutzt. Hinzu wird der Swapping Speicherplatz genutzt und gilt als
*Hintergrundspeicher*. Swapping speicher kann nicht größer als der
Hauptspeicher dabei sein.

## Virtuelle Speicherverwaltung

Bei der Virtuellen Speicherverwaltung wird der Speicherbedarf virtuell
entkoppelt. Das bedeutet das der Adressraum über den realen Speicher
hinaus reicht.

Einlagerungstrategien  

-   demand paging (Seiten werden bei Seitenfehler gespeichert)
-   pre-paging (bevorstehen Seiten die in der Zukunft benötigt werden,
    werden gespeichert)

Auslagerungstrategien  

-   FiFo (First in first out)
-   Random (Zufall)
-   Least recently used (Längste ungenutzte Seite wird ausgelagert)

### Paging

Beim Paging läuft zwischen dem Hintergrundspeicher und dem Hauptspeicher
ein interner Transfer.

### Page Fault

Bei einem Seitenfehler ist der Zugriff auf den Hauptspeicher nicht
möglich. Dabei blockiert ein Prozess die Seite er geladen ist, bevor er
weitermachen kann.