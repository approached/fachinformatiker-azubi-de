---
title: Apache
---

# Apache

Apache ist ein *Apache Hypertext Transfer Protocol Server*. Das heißt es
ist ein Server-Dienst für das Protokoll **http**.

## Installation

Apache installiert man meistens als eine LAMP Umgebung. LAMP steht für
Linux, Apache, Mysql und PHP. Man kann sicherlich auch nur das Paket
Apache2 installieren, dann könnt ihr aber nur mit html Files umgehen.

Für das aufsetzen eine Standard LAMP Server benötigt man folgende
Pakete.

`sudo apt-get install apache2 php5 libapache2-mod-php5 mysql-server mysql-client php5-mysql`

Empfehlenwerte Pakete unter anderem:

`sudo apt-get install phpmyadmin awstats php-apc`

Um zu entwickeln:

`sudo apt-get install php5-xdebug phpunit`

## Mod Rewrite

Das Modul *Mod Rewrite* bewirkt folgendes: Man ruft die Url
localhost/Test auf und im Hintergrund wird eine PHP Datei aufgerufen,
das diesen Aufruf verarbeitet. Heutzutage in den meisten Scripte ein
muss.

`sudo a2enmod rewrite `
`sudo service apache2 restart`

## Apache Boost

Modul PageSpeed aktivieren:
<https://developers.google.com/speed/docs/mod_pagespeed/download?hl=de>

`a2enmod deflate`

Deflate komprimiert die Dateien bevor es losschickt. (Kostet mehr
Rechenleistung) <http://httpd.apache.org/docs/2.2/mod/mod_deflate.html>

`a2enmod expires`

Expires gibt die Cachedauer an, die der Browser nutzen soll.
<http://httpd.apache.org/docs/2.2/mod/mod_expires.html>

`a2enmod headers`

Passt den Http Header an.
<http://httpd.apache.org/docs/2.2/mod/mod_headers.html>

## Entwickeln

Bevor wir in unserer Lamp umgebung entwickeln können müssen wir erst ein
paar Sachen erledigen.

### WWW Verzeichnis einbinden

Zuerst fügen wir unseren Benutzer zu der *www-data Gruppe* hinzu.

`sudo usermod -a -G www-data `<benutzer>

Nun wechseln wir in der Shell Sitzung zu der Gruppe. Jede Datei die wir
erstellen wird zur Gruppe von www-data.

`newgrp www-data`

Nun bekommt das Verzeichnis passenden User und Gruppe

`sudo chown -R root:www-data /var/www`

Zum schluss die Richtige Berechtigung

`sudo chmod 774 /var/www/ -R `

Auf Wunsch kann man bevorzugte Gruppe einstellen

`sudo usermod -g www-data `<benutzer>

### Subdomains hinzufügen unter localhost

Sobald local auf seinem Rechner entwickelt. Möchte man mit Subdomains
arbeiten. Das hat den Vorteile das man nicht mit den Pfaden unterpfaden
Arbeiten muss. Statt http://example.de/**zend**/<Anwendung> kann man nun
http://**zend**.example.de/<Anwendung>

Virtualhost anlegen:

    <VirtualHost *:80>
        ServerName zf2-tutorial.localhost
        DocumentRoot /var/www/zend/public
        SetEnv APPLICATION_ENV "development"
        <Directory /var/www/zend/public>
            DirectoryIndex index.php
            AllowOverride All
            Order allow,deny
            Allow from all
        </Directory>
    </VirtualHost>

Quelle:
<http://framework.zend.com/manual/2.1/en/user-guide/skeleton-application.html>

Unter **localhost** muss man jedoch unbedingt einen Hosts Eintrag
durchführen!

`vi /etc/hosts`
`Letzte Zeile hinzufügen:`
`127.0.0`

 ## Apache2 als IPv6 betreiben

  pache2 beherrscht von Haus an IPv6. Das ganze funktioniert sofort nach
der DNS Zuweisung mittels einem AAAA. Sollte es nicht funktionieren
liegt ein Mangel in der Art der ganzen Konfigurationsstrategie vor.

## Testen

Testen ob die Seite als IPv6 anerkannt wird, kann man dieses Analyse
Tool verwenden: <http://ipv6-test.com/validate.php>.

Hört Apache2 auf den Port 80? Das könnt ihr mit den Befehl testen.

    root@h2157161:/etc/apache2# netstat -tulpn | grep :80
    tcp6       0      0 :::80                   :::*                    LISTEN      1083/apache2

## AH01630: client denied by server configuration - 403 Forbidden

  Ab der Apache Version 2.4 sind verschiedene Änderungen durchgeführt
worden. Falls du die Meldung **403 Forbidden** und im log *AH01630:
client denied by server configuration* stehen hast dann habe ich die
Lösung für dich.

Mit der neuen Apache Version 2.4 musst du Ordner Rechte geben. Wie z.B.:

    <Directory "/home/user/workspace">
        Options All
        AllowOverride All
        Require all granted
    </Directory>

## Notes

-   <http://httpd.apache.org/docs/2.4/upgrading.html>
