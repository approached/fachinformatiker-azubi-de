---
title: Cronjob
---

# Cronjob

Für Wartungsaufgaben oder immer wieder kehrende Prozesse, benutzt man
*Cronjobs*. In Windows nennt sich das *Windows Task Scheduler*. Legt man
ein cron mittels **crontab -e** an, dann wird dies im Verzeichnis
`/var/spool/cron/crontabs/` gespeichert. Dieses sind Benutzerspezifische
Crons. Dies erfordert keine Benutzerangabe. Sprich man kann nicht
einstellen mit welchen User der **Prozess** gestartet wird!

Möchte man *Systemweite* Crons anlegen, dann passt man die Datei
**/etc/crontab** ein. Diese Datei wird mit root Rechten bearbeitet.

###### Syntax

Folgende Syntax wird für Cron genutzt.

    # m h dom mon dow user  command
    0 0 * * *  root /root/script.sh > /dev/null 2>&1 (Um 0:00 wird der Script gestaret)
    0,15,30,45 0 * * *  root /root/script.sh > /dev/null 2>&1 (Script wird jede viertel Minute ausgeführt)
    */5 *    * * *   root /root/script.sh > /dev/null 2>&1 (Jede 5 Minuten wird dieser Script gestartet)
    5    9-20 * * *  root /root/script.sh > /dev/null 2>&1 (Zwischen 9:05 und 20:05 wird jedes mal dieses Script ausgeführt)
    30   12   * * 0,4 root /root/script.sh > /dev/null 2>&1 (Am Sonntag und Donnerstag um 12:30 wird der Script ausgeführt)

-   **m** = Minute (0 - 59; oder Namen, siehe unten)
-   **h** = Stunde (0 - 23)
-   **dom** = Tag (1 - 31)
-   **mon** = Monat (1 - 12)
-   **dow** = Wochentag (0 - 7) (Sonntag ist 0 und 7; oder Namen, siehe
    unten)
-   **user** = Benutzer
-   **Command** = Shellscript

Hinter jeden Command muss ein Leerzeichen stehen!

### dow

0 Sonntag

1 Montag

2 Dienstag

3 Mittwoch

4 Donnerstag

5 Freitag

6 Samstag

### /dev/null

Mittels */dev/null* Struktur wird die Fehlerausgabe umgeleitet.

` * `**`/dev/null`**` = Bei Fehler, dann umleiten.`
` * `**`/dev/null`` ``2>&1`**` = Egal ob Fehler oder nicht, keine umleitung.`

Weitere Informationen finden man hier
<https://de.wikipedia.org/wiki//dev/null>

### Anacron

Bei PC die nicht durchgehend angeschaltet sind wird empfohlen ein
Anacron zu benutzen. Möchte man ein Backup anlegen (Beispiel um 20:15)
und der Rechner ist aus, dann wird die Sicherung nicht erstellt. Anacron
dagegen funktioniert anders. Hat man ein Cron verpasst, dann wird dies
später ausgeführt.

<https://wiki.ubuntuusers.de/Cron?highlight=Pw%20Tbaustell%20Zcronjob#Anacron-Anac-h-ronistic-Cron>
