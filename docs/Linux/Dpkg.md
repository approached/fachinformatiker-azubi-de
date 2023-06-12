---
title: Dpkg
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
