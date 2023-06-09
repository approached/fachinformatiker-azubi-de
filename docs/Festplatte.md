---
title: Festplatte
description: 
published: true
date: 2022-03-17T17:25:29.194Z
tags: 
editor: markdown
dateCreated: 2022-03-12T12:03:55.805Z
---

# Festplatte

## FAQ

**Warum sollt man kein FAT32 nutzen und stattdessen ExFat?**
FAT32 hat den Vorteil das es von jedem Betriebssystem gelesen werden kann. Der Nachteil jedoch ist die limitierte Dateigröße von 4 GB. Mit dem Dateisystem ExFAT lässt es sich umgehen. Aber achtung einiges ältere Geräte unterstützen es nicht z.B. Fritz.Box (Router) oder ein Autoradio. Für Linux muss ein Propritärer Treiber zusätzlich installiert werden.

## Zustand / Defekt prüfen

Mit [smartmontools](https://www.smartmontools.org/) kann man den Zustand der Festplatte prüfen.
```shell
brew install smartmontools
```

Schnelltest:
```shell
smartctl -t short -C /dev/sda
```

Status anzeigen:
```shell
smartctl -a /dev/sda
```

## Benchmark


Mit [amorphousdiskmark](https://www.katsurashareware.com/amorphousdiskmark/) einen Benchmark berechen.
```shell
brew install --cask amorphousdiskmark
```

## Linux CLI

Auflistung:
```shell
lsblk -f

or

parted -l
```
parted -l
parted /dev/sda mklabel gpt
parted /dev/sda mkpart primary ext4 0% 100%
parted /dev/sda name 1 MegaDriveDisk


Formatieren:
```shell
mkfs -t ext4 /dev/sdb1
```

Laben setzen:
```shell
e2label /dev/sdb1 MegaDriveDisk
```

GPT Aufteilung setzen:
```
apt install gdisk -y
gdisk /dev/sdb1
```
Weitere Infos siehe [GPT Konvortierung](https://www.explorelinux.com/convert-disk-mbr-to-gpt-on-linux/)


Oder via parted List/GPT/Formatieren/Label setzen:
```shell
parted -l
parted /dev/sda mklabel gpt
parted /dev/sda mkpart primary ext4 0% 100%
parted /dev/sda name 1 MegaDriveDisk
mkfs.ext4 /dev/sda1
```

Detail Information über die Festplatte auslesen:
```shell
smartctl -i /dev/sda
```

Festplattepartionsgröße anpassen:
```shell
resize2fs /dev/sda1
```


## Notes

* [Partitionen formatieren](https://snapshooter.com/blog/how-to-grow-an-ext234-file-system-with-resize2fs-)