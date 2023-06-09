---
title: Linux Grep
---

# Linux Grep

## Beispiele

Nur **Einstellungswerte** anzeigen.

`grep -v "#" awstats.example.de.conf | less`

Leere Zeilen entfernen

`grep -v "#" awstats.example.de.conf | grep -v '^$' | less`

In allen .php files nach dem Suchword "&lt;? " suchen

`grep -r --include=*.php "<? " .`
