---
title: SQL Distinct
description: 
published: true
date: 2022-02-14T21:03:40.278Z
tags: 
editor: markdown
dateCreated: 2022-02-14T21:03:39.219Z
---

# SQL Distinct

Werte die Mehrfach auftreten, können mittels **DISTINCT** so angezeigt
werden, das nur **ein Wert** erscheint.

Beispiel: Man hat eine Tabelle *Name* mit den Werten: *Schröder, Meier,
Meister*

Falls man nun bei diesem Beispiel einen SQL DISTINCT anwendet, dann wird
der Wert **Schröder** nur einmal ausgegeben! Die SQL-Abfrage müsste so
aussehen:

*SELECT DISTINCT name FROM Kunden;*

## Problem mit mehreren Werten {#problem_mit_mehreren_werten}

Falls man mehreren Spalten ausgeliefert haben möchte mit einem Wert,
führt dieses zu Problem. Nehmen wir an man möchte folgende SELECT haben:

`SELECT name, DISTINCT geburtsjahr FROM personen;`

Nach dieser SELECT abfrage bekommt man fehlerhafte Ergebnisse angezeigt.
Den Personen die im Gleichen Geburtsjahr geburtstag haben, werden
hierbei nicht berücksichtigt.

Lösung: Um die identischen Werten in mehrern Spalten zu unterbinden
benutzt man ein *GROUP BY*. Die SQL Syntax würde, dann wie flogt
aussehen: SELECT name, geburtsjahr FROM personen *GROUP BY name,
geburtsjahr*;

## Sonstiges

SQL-Konstrukte wie:

`SELECT DISTINCT name, DISTINCT geburtsjahr FROM ..`

führen zu Fehlermeldungen. Weil die Spalte *name* und *geburtsjahr* nur
Teilmengen liefern!