---
title: SQL Statements
description: 
published: true
date: 2022-02-14T21:02:59.718Z
tags: 
editor: markdown
dateCreated: 2022-02-14T21:02:58.152Z
---

# SQL Statements

## Select

Standard Abfrage:

`SELECT * FROM abteilung where id=1;`

## Insert

Standard Insert:

`INSERT INTO abteilung (abteilung, ort) VALUES ('Marketing', 'Büro hinten rechts');`

## Update

Standard Update:

`UPDATE abteilung SET abteilung='Lager', ort='erstes Buero' WHERE id=2;`

## Create Table {#create_table}

    CREATE TABLE taetigkeit (
    ID SERIAL,
    Bezeichnung varchar(255),
    Beginn varchar(255),
    Ende varchar(255),
    Dauert varchar(255),
    aufgabe integer,
    mitarbeiter integer,
      CONSTRAINT taetigkeit_pk PRIMARY KEY (ID),
      CONSTRAINT aufgabe_fk FOREIGN KEY (aufgabe)
      REFERENCES aufgabe(ID) MATCH SIMPLE
      ON UPDATE NO ACTION ON DELETE NO ACTION,
      CONSTRAINT mitarbeiter_fk FOREIGN KEY (mitarbeiter)
      REFERENCES mitarbeiter(ID) MATCH SIMPLE
      ON UPDATE NO ACTION ON DELETE NO ACTION
    );

Erklärung: id SERIAL = Es wird eine Seqenz eingeleitet (MYSQL
Auto_incroment)

CONSTRAINT taetigkeit_pk PRIMARY KEY (ID) = Hier wird der Primäre
Schlüssel defeniert

    CONSTRAINT mitarbeiter_fk FOREIGN KEY (mitarbeiter)
    REFERENCES mitarbeiter(ID) MATCH SIMPLE
    ON UPDATE NO ACTION ON DELETE NO ACTION

Es wird eine Referentielle Identität erstellt (Fremdschlüssel). Mit der
Tabelle mitarbeiter und der Spalte id. Außerdem sind Optionen
hinterlegt, keine aktion bei der löschung eine Datensatzes sowie keine
aktion bei einem update.

## Drop

`DROP TABLE abteilung;`

## Transaktionen

Transaktionen starten mit:

`begin;`

Transaktionen löschen (wiederherstellen)

`rollback;`

Transaktion übernehmen

`commit;`

## Übersicht der Tabellen {#übersicht_der_tabellen}

Eine Übersicht der Tabellen in der Datenbank kann man mittels:

`\d`

oder

`\dt`

bekommen. Dies Ausgabe würde ungefähr so aussehen.

                        Liste der Relationen
     Schema |            Name            |   Typ   | Eigentümer 
    --------+----------------------------+---------+------------
     public | _syncinfo                  | Tabelle | postgres
     public | _systemmapping             | Tabelle | postgres
     public | crm_bankverbindungen       | Tabelle | postgres
     public | crm_communication          | Tabelle | postgres
     public | crm_contactpersons         | Tabelle | postgres

Eine Tabelle Übersicht zu bekommen ist auch möglich

`\d hr_abwesenheit`

## SQL UPPER and LOWER Functions {#sql_upper_and_lower_functions}

Wandelt die Zeichen in groß oder klein um.

    SELECT UPPER('Upper'),LOWER('Lower')

    UPPER('Upper')  LOWER('Lower')
    --------------  --------------
    UPPER           lower 

## Typumwandlung

plz::integer

    UPDATE geo_orte 
    SET bundesland_code = 'DE-SN' 
    WHERE plz::integer BETWEEN 01001 AND 01936;

## Zwischen

Werte müssen natürlich Integer Werte sein. Text werte sind dafür nicht
geeignet.

    UPDATE geo_orte 
    SET bundesland_code = 'DE-SN' 
    WHERE plz::integer BETWEEN 01001 AND 01936;

    oder

    plz >= 1001 and plz <= 1936
    
## Explain

Falls man ein SQL Befehl hat und nicht genau weiß was er anstellt so
kann ein explain helfen.

`EXPLAIN UPDATE geo_orte SET bundesland_code = 'DE-TH' WHERE plz::integer BETWEEN '07952' AND '07952';`

Mit Hilfe vom Explain lässt sich gut anschauen wie er diese SQL
Anweisung verarbeiten würde.

## Clear

Die Konsole kann mit dem Linux-Kommando clear bereinigt werden. Dafuer
muss mit in Postgresql der externe Befehl mit einem Ausrufezeichen (wie
im vi) eingeleitet werden.

`\! clear`    