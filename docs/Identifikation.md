---
title: Identifikation UUID / CUID / GUID
---

# Identifikation

Die Identifikation von Informationen kurz **ID** gibt es verschiedene Arten. Häufige nutzung einer ID wird in der Datenbank genutzt.

## UUID / GUID

UUID steht für *Universally Unique Identifier*.

* Besteht aus 128 Bit (16 Bytes),
* Standanrd von RFC4122

> Beispiel: 672945a3-a2bb-42ef-bd42-8e045c9b34c4

## CUID

CUID steht für Collision-resistant ids. Die ID ist optiemiert für die horizantele Skalierung und binäry Suche. Der Hauptunterschied gegenüber UUID ist, dass weniger Informationen gespeichert werden.

Deswegen ist es leichtgewichtiger und performanter.

## GUID

GUID steht für Globally Unique Identifier. GUID ist von Microsoft die Implementierung von UUID.

## Quellen

* <https://de.wikipedia.org/wiki/Universally_Unique_Identifier>
* <https://de.wikipedia.org/wiki/Globally_Unique_Identifier>
* <https://github.com/ericelliott/cuid>
