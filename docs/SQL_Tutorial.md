---
title: SQL Tutorial
---

# SQL Tutorial

SQL steht für *Structured Query Language* und ist eine Datenbanksprache.

Dieses Tutorial bezieht sich auf eine **Mysql** Datenbank.

## Datenbank

### Create

Syntax:

`create database datenbankname;`

Beispiel:

`create database sqltutorial;`
`` create database `sql-tutorial`; (Sonderzeichen bindestrich) ``

### Drop

Syntax:

`drop database datenbankname;`

Beispiel:

`drop database sqltutorial;`

## Tabelle

### Create

Syntax:

    CREATE TABLE tabellenname
    (
       Spaltenname Typ Option
       [...]
    );

Beispiel:

    CREATE TABLE KundenTest
    (
       Vorname varchar (100)  NOT NULL,
       Nachname varchar (100) NULL,
       Beruf varchar (100),
       `Alter` int(11),
       Geburtsdatum date
    );

Alter wurde mit Sonderzeichen ausgestattet, weil es eine alter Funktion
existiert.

### Rename

Syntax:

    RENAME TABLE  tabellenname;

Beispiel:

    RENAME TABLE KundenTest TO Kunden;

### Drop

Syntax:

    DROP TABLE tabellenname;

Beispiel:

    DROP TABLE Kunden4;

### Insert

Syntax:

`INSERT INTO tabellenname (Spaltenname [...]) VALUES (Werte [...]);`

Beispiel:

    Kurze Version:
    INSERT INTO Kunden (Vorname, Nachname, Beruf, `Alter`, Geburtsdatum) VALUES ('Peter', 'Wurst', 'Bauer', '23', '2014-12-18');

    Lange und sichere Version:
    INSERT INTO  `sql-tutorial`.`Kunden` (
    `Vorname` ,
    `Nachname` ,
    `Beruf` ,
    `Alter` ,
    `Geburtsdatum`
    )
    VALUES (
    'Hans',  'Wurst',  'Fleischer',  '22',  '2014-12-18'
    );

### Select

Syntax:

`SELECT Spaltenname, [...] FROM Tabellenname;`

Beispiel:

`Select * From Kunden;`
`Select Vorname, Nachname From Kunden;`
`Select Nachname AS Name From Kunden;`

### WHERE

`` Select * From Kunden WHERE `Alter` > 22; ``

### BETWEEN

Select \* From Kunden WHERE \`Alter\` BETWEEN 20 AND 22;

### AND & OR

`Select * From Kunden WHERE Nachname = 'Wurst' AND Vorname = 'Peter';`

Hier kommt nur ein Ergebnis.

`Select * From Kunden WHERE Nachname = 'Wurst' OR Vorname = 'Peter';`

Zwei Ergebnisse

### LIKE

Syntax: SELECT Spaltenname, \[...\] FROM Tabellenname WHERE Spaltenname
LIKE 'MUSTER';

Muster

-   F\_k: Zeichenketten zwischen F und k
-   Mi%: Zeichenketten mit dem Anfang Mi
-   %on: Zeichenketten mit dem Ende on
-   %ss%: Zeichenketten die ss enthalten

Beispiel:

`Select * From Kunden WHERE Nachname LIKE 'W_st';`

### ORDER BY

Syntax:

`SELECT Spaltenname, [...] FROM Tabellenname ORDER BY Spaltenname, [...] ASC|DESC;`

Beispiel:

`Select * From Kunden ORDER BY Nachname, Vorname ASC;`

### IN Operator

Der IN Operator ersetzt den OR Parameter, kann jedoch nicht mit LIKE
funktionen genutzt werden.

`Select * From Kunden WHERE Vorname IN ('Peter', 'Hans');`

### GROUP BY

Ergebnismenge wird gruppiert. Dieser Befehl wird meistens in Verbindung
von AVG, SUM und Count usw. Verwendet.

`Select Beruf From Kunden GROUP BY Beruf;`

Zeigt alle Berufe an.

`Select Beruf, count(Beruf) AS Anzahl From Kunden GROUP BY Beruf;`

Zeigt die Berufe mit der jeweiligen Anzahl auf.

### HAVING

HAVING ist ein zusätzlich WHERE klause die es erlaubt nach einem GROUP
BY zu benutzen.

`` Select * From Kunden GROUP BY Beruf HAVING `ALTER` = 22; ``

### DISTINCT

Mittels Distinct wird die Redundanz reduziert.

`Select DISTINCT Nachname From Kunden;`

Weiteres [SQL\_Distinct](/SQL_Distinct)

### JOIN

Mittels einem Join können mehrere Tabellen Verbunden werden.

## Weiteres

-   <http://www.datenbanken-verstehen.de/datenbanken/sql-tutorial/>
-   <http://www.sql-lernen.de/>
