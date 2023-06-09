---
title: Unterschiede zwischen IPv4 und IPv6
description: 
published: true
date: 2022-02-09T13:25:11.770Z
tags: 
editor: markdown
dateCreated: 2022-02-09T13:25:10.656Z
---

# Unterschiede zwischen IPv4 und IPv6

**IPV4** sowie **IPV6** sind *Internet Protokolle* zum übertragen von
Daten. Das IPv6 wurde in der Zeit von 1995-1998 Hergestellt. Man hat
bemerkt, dass man mit dem Adressbereich von IPv4 in Zukunft nicht
auskommen wird. Der IPv6 wird zum heutigen Standard und löst viele
Probleme. Zusätzlich zur Erweiterung des Adressbereichs ergeben sich
weitere Vorteile.

## IPv4 und IPv6 Vergleich

<table>
<thead>
<tr class="header">
<th></th>
<th><p>IPv4</p></th>
<th><p>IPv6</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IP-Adressen</p></td>
<td><p>2<sup>32</sup></p></td>
<td><p>2<sup>128</sup></p></td>
</tr>
<tr class="even">
<td><p>IP-Adressen als Zahl</p></td>
<td><p>4.294.967.296</p></td>
<td><p>340.282.366.920.938.463.463.374.607.431.768.211.456</p></td>
</tr>
<tr class="odd">
<td><p>Network Address Translation (NAT)</p></td>
<td><p>ja</p></td>
<td><p>nein</p></td>
</tr>
<tr class="even">
<td><p>Dynamic Host Configuration Protocol (DHCP)</p></td>
<td><p>ja</p></td>
<td><p>nein (bei kleinen Privaten Netzwerk notwendig)</p></td>
</tr>
<tr class="odd">
<td><p>Netzwerkadresse</p></td>
<td><p>ja</p></td>
<td><p>nein</p></td>
</tr>
<tr class="even">
<td><p>Broadcast</p></td>
<td><p>ja</p></td>
<td><p>nein</p></td>
</tr>
<tr class="odd">
<td><p>Adressen Aufbau</p></td>
<td><p>4 Blöcke mit jeweils 8 Bit (Dezimal)</p></td>
<td><p>8 Blöcke mit jeweils 16 Bit (4 Hexadezimal)</p></td>
</tr>
<tr class="even">
<td><p>Private Netzwerkadressen</p></td>
<td><p>Class A - 10.0.0.0–10.255.255.255 Class B -
172.16.0.0–172.31.255.255</p>
<p>Class C - 192.168.0.0–192.168.255.255</p></td>
<td><p>fe80::/8</p></td>
</tr>
<tr class="odd">
<td><p>Localhost</p></td>
<td><p>127.0.0.1</p></td>
<td><p>::1/128</p></td>
</tr>
<tr class="even">
<td><p>URL-Notation</p></td>
<td><p>http://192.168.0.1:8080</p></td>
<td><p><a
href="http://%5Bfda2:c496:7232:adf7:0:0:0:1">http://[fda2:c496:7232:adf7:0:0:0:1</a>]:8080</p></td>
</tr>
</tbody>
</table>

## IPv6 Vorteile und Nachteile

Vorteile  

-   Größerer Adressbereich
-   Kein NAT
-   Kein DHCP (IP wird mittels einer Autoconfiguration vergeben)
-   Schneller als das IPv4 Protokoll (Header ist aufgeräumt, es werden
    keine Prüfsummen berechnet sowie Packetierung)
-   IPv6 ist automatisch verschlüsselt (IPsec)

Nachteile  

-   Unübersichtliche Adressen
-   Mac Adresse kann global sichtbar gemacht werden, somit ist die
    Privatsphäre ist gefährdet (bei Deaktivieren von Privacy Extension)
    
## Unterschiede im Detail

**IP-Adresse**

Mit IPv6 stehen so viele IP-Adressen zur Verfügung, dass man jedem
Pflasterstein auf der Welt eine IP-Adresse zuweisen kann. Wenn man
bedenkt, dass jedes Smartphone, Kühlschrank, Körperwage oder
Heizungskörper bald **Online** sein wird, dann ist dies definitiv
Notwendig.

Im ersten Moment wirken die IPv6 Adressen sehr merkwürdig und kommen uns
ziemlich lang vor. Aber das wird sich mit der Zeit ändern.

**Network Address Translation (NAT)**

Endlich kein **NAT** mehr in IPv6. Nie wieder mehr Port Weiterleitungen
einrichten. Jeder Rechner ist mit dem Internet Verbunden. Das bedeutet
das man dann verstärkt auf Firewalls setzen wird. Die meistens Rechner
sind von Haus aus mit Firewalls ausgestattet.

Falls der Bedarf an NAT besteht, dann kann NAT trotzdem eingesetzt
werden. Dieses bietet sich meistens nur für Firmen an.

**Dynamic Host Configuration Protocol (DHCP)**

Im Normalfall muss kein DHCP-Dienst mehr betrieben werden. Dies
geschieht voll automatisch mittels **IPv6 Autokonfiguration**.

Bei Bedarf kann man jedoch einen DHCPv6 Dienst betreiben. In kleinen
privaten Netzwerk wird es immer noch notwendig sein!

**Netzwerkadresse und Broadcast Adresse**

Diese zwei Adressen werden nicht benötigt. Die Broadcast Adresse spricht
alle unterlegenden Router auf *ff02::2* an. Die Netzwerkadresse leitet
sich ab von der IPv6 Adresse auch genannt Prefix.

**URL-Notation**

IPv6 Adressen schreibt man in eckigen Klammern. Das Trennzeichen
*Doppelpunkt* wird für den Port verwendet.

-   IPv4 - http://192.168.0.1:8080
-   IPv6 - [http://\[fda2:c496:7232:adf7:0:0:0:1][1]\]:8080

## IPv6 im Detail

-   Localhost ::1/128
-   Private fe80::/8
-   Multicast ff00::/8
-   Broadcast ff02::2
-   Öffentlicher Block 2000::/3
-   DHCP Autoconfiguration fe80::/80 (Falls keine Internetverbindung
    besteht)

## IPv6 Schreibweise

Die nullen müssen nicht unbedingt hingeschrieben werden.

`Ohne Nullen`  
`2001:db8:53fc:a:df70:5dc:10d`

`IPv6 komplett`  
`2001:0db8:53fc:000a:df70:05dc:010d`

Leere nuller Blöcke kann man weglassen.

`Gekürzte Adresse`  
`2600:c::273:fd:1`

`IPv6 komplett`  
`2600:000c:0000:0000:0000:0273:00fd:0001`

Das Kürzen wird mit Doppelpunkt eingeleitet und ist nur einmal erlaubt.
Bei mehrfacher Nutzung kann die richtige IPv6 Adresse nicht abgeleitet
werden.

  [1]: http://%5Bfda2:c496:7232:adf7:0:0:0:1    