---
title: Welche Ports sind offen
---

# Welche Ports sind offen

Wenn man raus finden möchte welche Ports gerade am lauschen sind, kann
man dies folgt heraus finden.

    root@v-debian:~# netstat -an | grep LISTEN
    tcp        0      0 0.0.0.0:993             0.0.0.0:*               LISTEN
    tcp        0      0 127.0.0.1:3306          0.0.0.0:*               LISTEN
    tcp        0      0 0.0.0.0:587             0.0.0.0:*               LISTEN
    tcp        0      0 0.0.0.0:143             0.0.0.0:*               LISTEN
    tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN
    tcp        0      0 0.0.0.0:465             0.0.0.0:*               LISTEN
    tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN
    tcp        0      0 0.0.0.0:25              0.0.0.0:*               LISTEN
    tcp        0      0 0.0.0.0:443             0.0.0.0:*               LISTEN
    tcp6       0      0 :::993                  :::*                    LISTEN
    tcp6       0      0 :::587                  :::*                    LISTEN
    tcp6       0      0 :::143                  :::*                    LISTEN
    tcp6       0      0 :::465                  :::*                    LISTEN
    tcp6       0      0 :::22                   :::*                    LISTEN
    tcp6       0      0 :::25                   :::*                    LISTEN

tcp und tcp6 ist die splittung von IPv4 und IPv6.

## Standardisierte Ports

-   993 IMAP with TLS
-   3306 MYSQL
-   587 SMTP
-   143 IMAP
-   80 Webserver
-   465 SMTP
-   22 SSH
-   25 SMTP
-   443 Webserver with TLS

siehe <https://de.wikipedia.org/wiki/Liste_der_standardisierten_Ports>
