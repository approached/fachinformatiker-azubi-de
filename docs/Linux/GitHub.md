---
title: GitHub
---

# GitHub

GitHub ist ein Dienst zur Verwaltung von Softwareprojekten. Es wird hierbei die Versionsverwaltungssystem Git genutzt und das Projekt gehört Microsoft.

## Server deploy key benutzen

Damit man die Projekte auf dem Server *auschecken / einchecken* kann muss man einen eigenen Key extra erstellen.

1. Ed25519 key generieren:
```shell
ssh-keygen -t ed25519 -C "projectname@servername" -f /root/.ssh/projectname

Enter passphrase (empty for no passphrase): <EMPTY>
```

2. Config eintragen in `/root/.ssh/config` github:
```shell
Host github.com-projectname
        Hostname github.com
        IdentityFile=/root/.ssh/projectname
```

für Gitlab gilt:
```shell
Host gitlab.com-projectname
        Hostname gitlab.com
        IdentityFile=/root/.ssh/projectname
```
3. Github key hinzufügen:
```
cat ~/.ssh/projectname.pub
```

Gehe zu <https://github.com/username/projectname/settings/keys> und trage den Key ein.

4. Projekt auschecken
```shell
git clone git@github.com-projectname:username/projectname.git
```
