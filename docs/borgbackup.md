---
title: Borgbackup
description: 
published: true
date: 2022-03-17T10:16:26.427Z
tags: 
editor: markdown
dateCreated: 2022-03-16T16:20:21.044Z
---

# Borgbackup

BorgBackup (kurz: Borg) ist ein deduplizierendes Backup-Programm. Der Vorteil des Borg ist das es Komprimierung und authentifizierte Verschlüsselung kann. BorgBackup funktioniert ähnlich wie ein Git Repository. Man erstellt Verzeichnis/Repository und diesem Verzweichnis werden die Daten versioniert gespeichert.

## Quickstart

```bash
borg init --encryption=repokey /opt/test
borg create /opt/test::Monday ~/src ~/Documents
```

### Usage

List:
```bash
borg list ssh://u260001-sub1@u260001.your-storagebox.de:23/./borgbackup
```

List all files:
```bash
borg list ssh://u260001-sub1@u260001.your-storagebox.de:23/~/test::superserver-2020-01-31_00:42
```
List all files in path:
```bash
borg list ssh://u260001-sub1@u260001.your-storagebox.de:23/~/test::superserver-2020-01-31_00:42 opt/backup/store-mysql/
```

Restore path:
```bash
borg --list --progress extract ssh://u260001-sub1@u260001.your-storagebox.de:23/~/test::superserver-2020-01-31_00:42 opt/`
```

Restore file:
```bash
borg --progress extract ssh://u260001-sub1@u260001.your-storagebox.de:23/~/test::superserver-2020-01-31_00:42 backup/db00008151.sql.gz
```

## Notes

* [Automatisches Backup](https://borgbackup.readthedocs.io/en/stable/quickstart.html#automating-backups)