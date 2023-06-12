---
title: Git Tutorial
---

# Git Tutorial

Git Projekt initialisieren

`git init`

Status Prüfen ob geänderte Dateien vorhanden sind

`git status`

Geänderte Dateien hinzufügen

`git add .`

Hinzugefügt Dateien Einchecken

`git commit -m "Config Datei angepasst"`

Was ist bislang passiert

`git log`

Um mehr Informationen anzuschauen

`git log --summary`

Bare Repository erstellen

`mkdir fachinformatiker.git`
`cd fachinformatiker.git`
`git --bare init`

Projekt auschecken

`git clone /opt/bare/fachinformatiker.git`

Entferntes Repository

`git clone user@host:/opt/bare/fachinformatiker.git`

Pushen

`git push origin master`

## Zurücksetzen der geänderten Dateein

Man unterscheidet zwischen zwei Arten von zurücksetzen. Einmal die
inszeniert (staged) Dateien:

`git reset -- foo.txt`

Und die nicht inszeniert (staged) Dateien. Das bedeutet die geänderte
Datei ist nicht eingecheckt/commitet.

`git checkout -- foo.txt`

## Letzte Änderungen zurücksetzen

Falls man einen Fehlerhaften commit erstellt hat, dann möchte man dies zurücksetzen. Dabei gibt es zwei Methoden:

1. Zurücksetzen die Dateien nochmal bearbeiten:
```
git reset --soft HEAD~1
```
2. Zurücksetzen und die Änderungen gehen verloren:

```
git reset --hard HEAD~1
```

Wenn man mehrere Versionstände zurücksetzen möchte kann dies einfach mit:
```
 git reset --hard efb5b3e8
```


## Git Apache Konfiguration

    <VirtualHost *:80>
            ServerName git.fachinformatiker-azubi.de
            DocumentRoot /opt/sites/git.fachinformatiker-azubi.de
            <Directory /opt/sites/git.fachinformatiker-azubi.de>
                    Options ExecCGI +FollowSymLinks +SymLinksIfOwnerMatch
                    AllowOverride All
                    order allow,deny
                    Allow from all
                    AddHandler cgi-script cgi
                    DirectoryIndex gitweb.cgi
            </Directory>
    </VirtualHost>

## GitLab

GitLab ist optimal, sobald man Git Repositorys selbst hosten will.

Empfehlungen

-   FeatureBranch sollte man 1:1 so übernehmen JiraTicket

## Weiteres

-   [Buch](https://git-scm.com/book/de/v2)
-   [GitWeb](https://git-scm.com/book/en/v2/Git-on-the-Server-GitWeb)
- <http://git-scm.com/book/en/Git-on-the-Server-GitWeb>
-   [GitLab](https://gitlab.com/)
-   [Git der Einfach Einstieg](https://rogerdudler.github.io/git-guide/index.de.html)
