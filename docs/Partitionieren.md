---
title: Partitionieren
description: 
published: true
date: 2022-09-30T07:52:46.665Z
tags: 
editor: markdown
dateCreated: 2022-02-16T21:07:37.830Z
---

# Partitionieren / Formatieren

Alle Geräte / USB Sticks anziegen:
```sh
sudo blkid

/dev/mmcblk0p1: LABEL_FATBOOT="boot" LABEL="boot" UUID="C839-E506" BLOCK_SIZE="512" TYPE="vfat" PARTUUID="0cf2eefd-01"
/dev/mmcblk0p2: LABEL="rootfs" UUID="568caafd-bab1-46cb-921b-cd257b61f505" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="0cf2eefd-02"
/dev/sda1: UUID="c6e50cd0-975f-4bdb-8a18-bf8c2d763367" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="IntensoMega" PARTUUID="b8bf4306-2f08-4607-aace-8c3d3a4f6246"
/dev/sdb1: LABEL_FATBOOT="EFI" LABEL="EFI" UUID="67E3-17ED" BLOCK_SIZE="512" TYPE="vfat" PARTLABEL="EFI System Partition" PARTUUID="58d501a7-d40f-404e-a9f1-128532063865"
/dev/sdb2: LABEL="Micro400" UUID="6336-9729" BLOCK_SIZE="512" TYPE="exfat" PARTUUID="6bc425af-4619-4b39-96ed-f1050e37538d"
```

Alle Partionen anzeigen:
```
sudo lsblk

NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda           8:0    0   4.5T  0 disk
`-sda1        8:1    0   4.5T  0 part /usb
sdb           8:16   1 366.8G  0 disk
|-sdb1        8:17   1   200M  0 part
`-sdb2        8:18   1 366.6G  0 part
mmcblk0     179:0    0  59.5G  0 disk
|-mmcblk0p1 179:1    0   256M  0 part /boot
`-mmcblk0p2 179:2    0  59.2G  0 part /
```

Kompletten Stick löschen:
```
dd status=progress if=/dev/zero of=/dev/sdb bs=4k && sync  
```

Partion erstellen:
```
sudo fdisk /dev/sdb
```
1. Drücken Sie dann den Buchstaben `o`, um eine neue leere DOS-Partitionstabelle zu erstellen.
2. Eine neue Partition erstellen: Drücken Sie den Buchstaben `n`, um eine neue Partition hinzuzufügen. Sie werden aufgefordert, die Größe der Partition anzugeben. Wenn Sie sich nicht sicher sind, können Sie eine primäre Partition erstellen, wenn Sie dazu aufgefordert werden.

Partionen erstellen:
```
NTFS:
mkfs.ntfs -f /dev/sdb1

FAT32:
mkfs.vfat -f /dev/sdb1

exFAT:
mkfs.exfat -f /dev/sdb1
```

Partion prüfen:
```
fsck /dev/sdb1
```

Usb namen ändern:
```
ntfslabel /dev/sdb1 Micro
```
Für weitere Dateiformate siehe https://help.ubuntu.com/community/RenameUSBDrive.

USB Stick einbinden / mounten:
```
mount /dev/sdb1 /media/micro/
```

USB Stick abhängen / unmount:
```
umount /media/micro/
```