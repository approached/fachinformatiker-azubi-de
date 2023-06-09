---
title: Datenbank
---

# Datenbank

Hier kommen alle Informationen über Datenbanken.

## Fragen

**Wie funktioniert eine Replikation?**

Zuerst wird ein Abbild erstellt und auf andere DB repliziert. Soblad
Daten verändert werden, dann wird dies Synchronisiert.

**Wie verhält sich die Referentielle Integrität beim löschen?**

Wegen der Dateninkonsistenz ist das löschen nicht problemlos möglich.
Zuerst muss man alle Beziehung in Form der Fremdschlüssel
löschen/ändern. Erst dann kann der Datensatz gelöscht werden.

**Was ist ein Inner-Join?**

Bei einem Inner-Join werden zwei Tabellen zusammengeführt. Sobald die
Kriterien erfüllt sind, werden dann nur die Daten ausgegeben, wo der
Bezug vorhanden ist.

**Was hat ist mit Left- sowie Right-Join gemeint?**

Es wird alle Selektiert von der linken/rechten Tabelle. Es muss dazu
kein übereinstimmender Bezug/Wert vorhanden sein. Bei einer Selektion
von Artikel und Artikelgruppen, wird z.B. alle Artikel ausgegeben auch
wenn die in keiner Gruppe zugeordnet sind! (siehe
<http://www.bjoerns-choice.de/archives/20>)

**Was ist eine Procedure?**

In mehreren Datenbanksystemen kann man Prozedure (Methoden) erstellen.
Dadurch ist eine gewisse Sicherheit als Performance Verbesserung
möglich.

**Was ist ein Trigger?**

Ein Trigger löst eine Funktion nach einem Insert, Update oder Delete
aus. Diese Funktion prüft letztendlich ob die Aktion erlaubt ist oder
nicht. Falls es erlaubt ist, wird die Aktion ausgeführt ansonsten nicht.

**Was ist mit einer Transaktion gemeint?**

Die Daten sollen bei der Aktion vollständig ausgeführt werden oder im
Fehlerfall abgebrochen werden.

-   Gestartet wird eine transaktion mit *beginn*
-   Übernohmen mit *commit*
-   Änderungen zurücknehmen mit *rollback*

**Was ist mit Persistenz gemeint?**

Die Daten werden sind stehen Persistent (Dauerhaft) bereit. Es handelt
sich nicht um einen flüchtigen Speicher, sodass nach einem Stromausfall
die Daten Persistent (Dauerhaft) verfügbar sind.

**Was ist mit dem Acid Prinzip gemeint?**

siehe unter [Wikipedia](http://de.wikipedia.org/wiki/Transaktion\_(Informatik)#ACID-Prinzip)

## Shell

```sql
show databases;
use mysql;
show tables;
describe user;
```

## Weiteres

-   [SQL Statements](/SQL_Statements)
-   [SQL Distinct](/SQL_Distinct)

## Mysql Create Database {#mysql_create_database}

1\. Einloggen

`mysql -u root -p`

2\. Datenbank erstellen

`create database fachinformatiker_azbui;`

3\. Übersicht der Datenbanken

`show databases;`

## Create user {#create_user}

Show user:

`select user, password, host from mysql.user;`

Show databases;

`show databases;`

Create user;

`CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'user_password';`

Grant permission to database:

`GRANT ALL PRIVILEGES ON database_name.* TO 'database_user'@'localhost';`

Grant all databases permissions:

`GRANT ALL PRIVILEGES ON *.* TO 'database_user'@'localhost';`

Show permissions:

`SHOW GRANTS FOR 'database_user'@'localhost';`

Remove permissions:

`REVOKE ALL PRIVILEGES ON database_name.* TO 'database_user'@'localhost';`

Drop user:

`DROP USER 'user'@'localhost'`

Save changes:

`FLUSH PRIVILEGES;`

Change password:

`ALTER USER 'newuser'@'localhost' IDENTIFIED BY 'new_password';`

## Mysql SQL Import {#mysql_sql_import}

Import einer SQL Datei mittels der Shell

`mysql --default-character-set=utf8 -u root -p < 2011-02-23_19h51m.Mittwoch.sql`

Import zu einer bestimmten Datenbank

`mysql -u root -p DATA-BASE-NAME < import.sql`

Import ohne entpacken

`gunzip < db.sql.gz | mysql -u root -p DATA-BASE-NAME`

## Mysql Root Passwort ändern {#mysql_root_passwort_ändern}

Wenn Sie für den Benutzer **root**,das Benutzerpassword änder möchten:

`mysqladmin --user=root --password=oldPassword password newPassword`

Sollte Sie keine Shell haben dann können Sie dies benutzen:

`UPDATE user SET Password=PASSWORD('newPassword') WHERE user='root';`\
`flush privileges;`

## Mysql Datenbank sichern {#mysql_datenbank_sichern}

Für die Shell

`mysqldump -u root -pMEINPASSWORD --all-databases | gzip -9 > db.sql.gz`

Eine DB

`mysqldump --default-character-set=utf8 -u root -pMEINPASSWORD --databases mydbname | gzip > db.sql.gz`

Eine DB - Plain ohne gzip

`mysqldump --default-character-set=utf8 -u root -pMEINPASSWORD --databases mydbname > db.sql`

DB Transfer

`mysqldump --databases mydbname --single-transaction --compress --order-by-primary –u root -pMEINPASSWORD | mysql --host=hostname –-port=3306 –u root -pMEINPASSWORD`

## Mysql Administrieren {#mysql_administrieren}

Auflistung jede Datenbankgröße:

`SELECT table_schema "DB", SUM( data_length + index_length) / 1024 / 1024 `\
`"Size in MB" FROM information_schema.TABLES GROUP BY table_schema;`

Auflistung jede Tabellengröße der DB CHANGEME:

    SELECT table_name AS "Tables",
    round(((data_length + index_length) / 1024 / 1024), 2) "Size in MB"
    FROM information_schema.TABLES
    WHERE table_schema = "CHANGEME"
    ORDER BY (data_length + index_length) DESC;

## Clustering

Sobald man die Datenbank replizieren möchte versucht meisten folgende
Strategie:

-   Master (nur Schreibrechte)
-   Slave (nur Leserechte) Replziert
-   Replication <http://www.liquibase.org/quickstart.html>

## Docker

**Backup**
```shell
.sql file:
docker exec CONTAINER /usr/bin/mysqldump -u root -pPASSWORD DATABASE > backup.sql

.sql.gz file:
docker exec CONTAINER /usr/bin/mysqldump -u root -pPASSWORD DATABASE | gzip > backup.sql.gz

.sql.bz2 file:
docker exec CONTAINER /usr/bin/mysqldump -u root -pPASSWORD DATABASE | bzip2 > backup.sql.bz2
```

**Restore**
```shell
.sql file:
cat backup.sql | docker exec -i CONTAINER /usr/bin/mysql -u root -pPASSWORD DATABASE

.sql.gz file:
gunzip < backup.sql.gz | docker exec -i CONTAINER /usr/bin/mysql -u root -pPASSWORD DATABASE

.sql.bz2 file:
bunzip2 < backup.sql.bz2 | docker exec -i CONTAINER /usr/bin/mysql -u root -pPASSWORD DATABASE
```

### Postgres

**Backup**
```shell
.sql file:
docker exec --user postgres postgres pg_dump DATABASE > backup.sql

Custom:
docker exec --user postgres postgres pg_dump --if-exists --clean --no-owner --no-privileges --no-acl --schema=public --column-inserts --exclude-table-data 'public.assetindexdata' --exclude-table-data 'public.assettransformindex' --exclude-table-data 'public.sessions' --exclude-table-data 'public.templatecaches' --exclude-table-data 'public.templatecachequeries' --exclude-table-data 'public.templatecacheelements' --exclude-table-data 'public.cache' --exclude-table-data 'public.templatecachecriteria' DATABASE > backup.sql
```

**Restore**
```shell
.sql file:
cat backup.sql | docker exec -i --user postgres postgres psql DATABASE
```
