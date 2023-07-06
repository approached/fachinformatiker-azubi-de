---
title: Find
---

# Find

Mittels Find kann man bequem in der Shell suchen.

## Nach Dateinamen suchen

Es wird nach dem Dateien und Verzeichnisse mit dem Namen *Office*
gesucht.

`find . -name Office*`
`find . -maxdepth 2 -iname *chrome*`

## Nach Verzeichnisse suchen

Es wird nach dem Verzeichnis *EDV* gesucht.

`find / -name EDV -type d`

Es wird im Verzeichnis /etc nach dem Verzeichnis *ldap* gesucht.

`find /etc -name ldap -type d`

## Nach dem Inhalt in Dateien suchen

In jeder Datei wo der Begriff *office* auftaucht, wird dieses
aufgelistet.

`find . -type f -exec grep -qi "office" {} \; -print`

Möchte man z.B. ein **.hg** Repository Verzeichnis ausschließen
(Mecurial).

`find . -path '*.hg' -prune -o -type f -exec grep -qi "foo" {} \; -print`

Jede php Datei mit dem Tool php7cc verarbeiten

`find web/ -name "*.php" | xargs php7cc`

Suche in jeder php datei nach "$my\_variable"

`find . -type f -name "*.php" -exec grep -qi "$my_variable" {} \; -print`

## Zeige anzahl der Dateien an

`find . -type f | wc -l`
