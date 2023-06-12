---
title: Linux
---

# Linux

Verschiedene Themen im Bereich Linux.

-   [OpenLDAP](./OpenLDAP)
-   [Vim](./Vim)
-   [Apache](./Apache)
-   [Tar](./Tar)
-   [Partitionieren](./Partitionieren)
-   [Mount](./Mount)
-   [Cronjob](./Cronjob)
-   [Dpkg](./Dpkg)
-   [Find](./Find)
-   [Linux Grep](./Linux_Grep)
-   [Git Tutorial](./Git_Tutorial)
-   [RAR - UNRAR](./rar-unrar)

## Shell

-   History löschen (gespeichert unter ~/.bash\_history)

`history -c`

-   Benutzer abmelden

`root@mail:~# who`
`root     pts/0        2014-06-13 10:52 (192.168.178.55)`

PTS Session abmelden

`skill -KILL -v pts/1`

Mehrere Benutzer mit User abmelden

`skill -KILL -u root`

Nachricht senden

`echo "Microsoft gives you Windows.. Linux gives you the whole house" > /dev/pts/1`

Architektur:

`dpkg --print-architecture`

Paket anzeige: dpkg -l | grep libzip

## User

Benutzer erstellen (mit der -m option, wird Heimatverzeichnis erstellt):
`useradd -m username`

Benutzer erstellen mit einem anderen Heimatverzeichnis:
`useradd -m -d /opt/secret username`

Passwort ändern:
`passwd username`

Einloggen mit dem Benutzer:
`su - username`

Benutzer löschen:
`userdel username`

Benutzer löschen mit seinem Heimatverzeichnis:
`userdel -r username`

## SSH Client

SSH Key erstellen:
`ssh-keygen -t ed25519 -C "your_email@example.com"`

authorized_keys Datei erstellen:
```
mkdir ~/.ssh
touch ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys
```

SSH Key hinzufügen (z.B. auf dem Server):
`echo ssh-ed25519 AAAAC3NzaC1lZDI1N[....] >> ~/.ssh/authorized_keys`

Login testen ohne private/public key:
`ssh -o PubkeyAuthentication=no -o PreferredAuthentications=password hans@1.1.1.1`
## SSH Server

Der SSH Server läuft standard gemäß mit dem Port 22. Aufgrund von bots ist es empfehlenswert den Port zu ändern. Man kann hierzu einen Port zwischen 30000 und 65535 wählen. Das geht wie folgt:
```
vi /etc/ssh/sshd_config

Eintragen/Ändern folgende Zeile:
Port 33322

Neustart:
/etc/init.d/ssh restart
```
