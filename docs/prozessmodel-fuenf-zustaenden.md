---
title: Prozessmodel mit fünf Zuständen
---

# Prozessmodel mit fünf Zuständen

In der Prozessverwaltung hat ein Prozessmodell fünf Zustände.

## Neu

Alle neue Prozesse landen unter dem Punkt **Neu**. Wenn das
Betriebssystem bereit ist, dann fügt er diesen Prozess in die Richtung
**Bereit**.

Die meisten Systeme haben eine Beschränkung der Anzahl bestehenden
Prozesse. Damit der Speicher nicht in die Kniee gezwungen wird.

## Bereit

Alle Prozesse die abgearbeitet werden landen unter Bereit. Das
Betriebssystem verwaltet die Prozesse anhand eines Interrupt, ein
Zeitwert. Das könnte z.B. so ablaufen das alle 3ms der Prozess
gewechselt wird.

Sobald also das Betriebssystem platzt zur Verarbeitung hat, dann fügt er
den Prozess zu den Bereich **aktiv** ein.

## Aktiv

Der Prozess wird hier abgearbeitet. Sollte der Prozess fertig sein
leitet das Betriebssystem zu den Bereich **Terminiert**.

Sollte der Prozess auf etwas warten, dann fügt er den Prozess in die
Bereich **Blockiert**. Er könnte vielleicht auf eine andere Berechnung
oder einer E/A-Operation.

## Blockiert

Sobald das Blockiert Ereignis eintrift z.b. E/A-Operation dann geschieht
eine Zustandsänderung zu **Bereit**. Dann kann nämlich der Prozess
erneut sich einreihen

## Terminiert

Der Prozess gilt als Fertig abgeschlossen.

## Quelle

W. Stallings: Betriebssysteme Prinzipien und Umsetzung, 4 überarbeitete
Auflage 2003, Perarson Studium
