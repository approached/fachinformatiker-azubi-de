---
title: OpenLDAP
description: 
published: true
date: 2022-02-16T21:05:03.123Z
tags: 
editor: markdown
dateCreated: 2022-02-16T21:05:02.087Z
---

# OpenLDAP

OpenLDAP ist eine strukturierte Datenbank. Mit strukturierte Datenbank
ist damit die Baumstruktur gemeint. **OpenLDAP** wird unter anderem für
folgendes genutzt:

-   Email (Postfix)
-   Samba (Netzwerk)
-   Userverwaltung
-   Windows Domäne

## Zugriff Kontrolle

Wenn ihr Zugriffe in der Konfiguration Datei einträgt ist es wichtig, in
welcher Reihenfolge die Einträge stehen! Hier einige Beispiele:

-   Beim User Peter hat man vollen Zugriffen. Aber nur User die
    Authentifiziert sind.

```
    access to dn="cn=peter,dc=example,dc=de"
            by users write
```            

-   Man darf über Attribut *street* überall verändern. Aber nur User die
    Authentifiziert sind.

```
    access to * attr=street
            by users write
```

-   Jeder User darf alles Lesen. Vorsicht Sambahash Passwort
    (Userpasswort) können auch anonymous User lesen.

```
    access to *
            by * read
```            

-   Alle User die in *ou=Users* vorhanden sind, dürfen in ihrem Email
    Verzeichnis *ou=virtual,ou=Email,dc=example,dc=de*, das Attribut
    mailDrop schreiben, wenn die objectClass = postfix ist!

```
    access to dn.regex="cn=([^,]+),ou=virtual,ou=Email,dc=example,dc=de$" attrs=mailDrop
            filter=(objectClass=postfix)
            by dn.regex="uid=$1,ou=([^,]+),ou=Users,dc=example,dc=de" write
            by * read
```            