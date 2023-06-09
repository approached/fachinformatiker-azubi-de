---
title: Linux Grep
description: 
published: true
date: 2022-02-16T21:11:43.867Z
tags: 
editor: markdown
dateCreated: 2022-02-16T21:11:42.798Z
---

# Linux Grep

## Beispiele

Nur **Einstellungswerte** anzeigen.

`grep -v "#" awstats.example.de.conf | less`

Leere Zeilen entfernen

`grep -v "#" awstats.example.de.conf | grep -v '^$' | less`

In allen .php files nach dem Suchword "&lt;? " suchen

`grep -r --include=*.php "<? " .`