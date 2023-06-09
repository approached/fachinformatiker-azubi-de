---
title: Tar
description: 
published: true
date: 2022-06-20T12:01:38.686Z
tags: 
editor: markdown
dateCreated: 2022-02-16T21:07:11.206Z
---

# Tar

Tar dient zum packen, entpacken und komprimieren von Datein. Es ist
vergleichbar mit dem Dateiformat **.zip**.

## Dateien entpacken

```shell
tar -xvfz file.tar.gz <Dateien-die-man-Entpacken-möchte>
```

-   x steht für extract (Extrahieren)
-   v steht für Verbose (Ausführungsmodus)
-   f steht für Filesystem (Dateiensystem)
-   z kompromierung - gunzip

## Dateien packen

```shell
tar -cvfz file.tar.gz <Dateien-die-man-Packen-möchte>
```
  
-   C steht für create (erstellen)
-   v steht für Verbose (Ausführungsmodus)
-   f steht für Filesystem (Dateiensystem)
-   z kompromierung - gunzip

## Dateien einzeigen

```shell
tar tfv file.tgz 
  
Mit Suche:
tar tfv file.tgz 'home/andreas/documents'
```

-   t steht für Ausgabeliste
-   f steht für Filesystem (Dateisystem)
-   v steht für Verbose (Ausführungsmodus)

Bei der Nutzung im Verbose Modus muss kein Trennzeichen angegeben werden. Außerdem erhält man im Verbose Modus die Anzeige der Rechte.
  
  
Man kann 

## bz - bzip2

bz2 ist vergleichbar mit gz (gunzip).

-   Packen: **bzip2 <Dateiname>**
-   Entpacken: **bunzip2 <Dateiname>.bz2**

In Verbindung von tar:

-   Packen: **tar cfvj <Dateiname>**
-   Entpacken: **tar xfvj <Dateiname>.bz2**