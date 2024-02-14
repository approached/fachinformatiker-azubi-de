---
title: Welche Ports sind offen
---

# Ports

Die Ports im Bereich von 0 bis 1023 sind die Systemrelevant. Diese werden für standardmäßige, bekannte Netzwerkdienste verwendet. Sie sind auch eingeschränkt, so dass nur der Superuser in der Lage ist, sich an einen dieser Ports zu binden.

Die nächsten Portbereiche, insbesondere unter 10000, sind in der Regel immer noch Standardports für einige Dienste, aber sie sind nicht eingeschränkt. Einige gängige Beispiele sind 8080 (HTTP-Alternative), 8443 (HTTPS-Alternative) oder 1099 (Java RMI-Registrierung).

Der Portbereich von **32768 bis 65535** kann frei für eigene Anwendungen verwendet werden. Dieser Portbereich ist nicht weit verbreitet.

## Welche Ports sind offen

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
