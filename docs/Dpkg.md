---
title: Dpkg
description: 
published: true
date: 2022-02-16T21:10:00.914Z
tags: 
editor: markdown
dateCreated: 2022-02-16T21:09:59.589Z
---

# Dpkg

## Wo wird der Befehl ausgeführt

**which crontab**

    approach@tanja:~$ which crontab
    /usr/bin/crontab

-   Gibt Pfad der Auszuführenden Datei zurück.

## Suche installierte Pakete

**dpkg -S /usr/bin/crontab**

    akloos@artemis:~$ dpkg -S /usr/bin/crontab 
    cron: /usr/bin/crontab

## Listet alle Dateien des Paketes

**dpkg -L cron**

    approach@tanja:~$ dpkg -L cron
    /.
    /usr
    /usr/bin
    /usr/bin/crontab
    /usr/sbin
    /usr/sbin/cron