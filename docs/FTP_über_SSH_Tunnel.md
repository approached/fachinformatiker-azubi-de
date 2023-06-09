---
title: FTP über SSH Tunnel
description: 
published: true
date: 2022-02-09T13:30:14.058Z
tags: 
editor: markdown
dateCreated: 2022-02-09T13:30:13.003Z
---

# FTP über SSH Tunnel

Das Tunnel über das Protocol *ssh* ist Problemlos möglich. Zuerst wird
der Tunnel Zugang in Putty erstellt.

Dabei muss man nur Source Port auf 21 stellen und den Punkt *Dynamic*
auswählen. Dann klickt man noch auf Add und man verbindet sich mit dem
Server. Schon ist der Tunnel von der Putty Seite eingerichtet.

![ssh_to_ftp_tunnel_putty.jpg](/ssh_to_ftp_tunnel_putty.jpg)

Im FTP-Client Programm FileZilla erstellt man nun ein Proxy nach diesen
Angaben. Danach verbindet man sich mit dem *FTP-Server* zu dem man eine
Verbindung aufbauen möchte mit den Zugangsdaten.

  ![ssh_to_ftp_tunnel_filezilla.jpg](/ssh_to_ftp_tunnel_filezilla.jpg)