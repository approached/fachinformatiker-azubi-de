---
title: Proxmox 
---

# Proxmox

Proxmox ist eine Virtualisierungsplattform.

## Festplatte vergrößern

Host:
qm resize [VM_ID] [DISK_NAME] +[SIZE_INCREASE]G
qm resize 301 scsi0 +2G

Guest:
fdisk -l
parted

## Fertige image nutzen

Vorbereitung:
VM erstellen
Festplatte löschen

wget https://cloud.debian.org/images/cloud/bookworm/latest/debian-12-nocloud-amd64.qcow2
qm importdisk 302 debian-12-nocloud-amd64.qcow2 local-lvm

Festplatte Bus umstellen auf Sata
SSD Emulation: AN
Discard: AN

Option:
Boot-Reihenfolge: sata0 einschalten
sata0 nach oben schieben

SSH aktivieren:
dpkg-reconfigure openssh-server

Quelle: https://www.youtube.com/watch?v=k6-miz1Tb80
