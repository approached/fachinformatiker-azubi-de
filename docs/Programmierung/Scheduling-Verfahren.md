---
title: Scheduling Verfahren
---

# Scheduling Verfahren

Es gibt viele verschiedene Scheduling Verfahren nachdem ein Prozessor
arbeitet. Ein Teil des [Betriebssystemes](./Betriebssystem)  (**Scheduling**) entscheidet
welcher Prozess verarbeitet wird.

Ein gutes Scheduling Verfahren zeichnet sich durch folgende Punkte aus:

-   Effizienz (Prozessor ist stets ausgelastet)
-   Fairness (Prozesse erhalten einen gerechten Anteil)
-   Durchsatz (Zeitintervall kann bei Bedarf erhöht werden)

Die bekanntest vier werden hier erklärt anhand diesem Auslastung
**Beispiel**.

<table>
<thead>
<tr class="header">
<th><p>Porzess</p></th>
<th><p>Ankunftszeit</p></th>
<th><p>Verarbeitungs</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A</p></td>
<td><p>0</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>B</p></td>
<td><p>2</p></td>
<td><p>6</p></td>
</tr>
<tr class="odd">
<td><p>C</p></td>
<td><p>4</p></td>
<td><p>4</p></td>
</tr>
<tr class="even">
<td><p>D</p></td>
<td><p>6</p></td>
<td><p>5</p></td>
</tr>
<tr class="odd">
<td><p>E</p></td>
<td><p>8</p></td>
<td><p>2</p></td>
</tr>
</tbody>
</table>

## First-come first-served

Das Verfahren *First-come first-served* arbeitet nachdem **FiFo**
Prinzip. FiFo steht für First in, First Out. Dies bedeutet das, dass
erste Pakete was kommt, geht als erstes wieder raus.

Es eignet sich für Lange Prozesse besser als für kurze.

<table>
<caption>Beispiel</caption>
<thead>
<tr class="header">
<th></th>
<th><p>1</p></th>
<th><p>2</p></th>
<th><p>3</p></th>
<th><p>4</p></th>
<th><p>5</p></th>
<th><p>6</p></th>
<th><p>7</p></th>
<th><p>8</p></th>
<th><p>9</p></th>
<th><p>10</p></th>
<th><p>11</p></th>
<th><p>12</p></th>
<th><p>13</p></th>
<th><p>14</p></th>
<th><p>15</p></th>
<th><p>16</p></th>
<th><p>17</p></th>
<th><p>18</p></th>
<th><p>19</p></th>
<th><p>20</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>B</p></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>C</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>D</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>E</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>

Beispiel

  [Betriebssystemes]: Was_ist_ein_Betriebssystem "wikilink"

## Shortest Remaining Time

Shortest Remaining Time hat die Eigenschaft Prozesse anhand der
**Verarbeitungszeit** zu verarbeiten. Dabei werden Prozesse
gegebenenfalls abgebrochen, wenn ein neuer Prozess rein kommt das eine
kürzere Laufzeit hat.

Der Nachteil bei diesem Verfahren ist, dass längere Prozesse verhungern
können (sie kommen nicht dran).

<table>
<caption>Beispiel</caption>
<thead>
<tr class="header">
<th></th>
<th><p>1</p></th>
<th><p>2</p></th>
<th><p>3</p></th>
<th><p>4</p></th>
<th><p>5</p></th>
<th><p>6</p></th>
<th><p>7</p></th>
<th><p>8</p></th>
<th><p>9</p></th>
<th><p>10</p></th>
<th><p>11</p></th>
<th><p>12</p></th>
<th><p>13</p></th>
<th><p>14</p></th>
<th><p>15</p></th>
<th><p>16</p></th>
<th><p>17</p></th>
<th><p>18</p></th>
<th><p>19</p></th>
<th><p>20</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>B</p></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>C</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>D</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>E</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

Beispiel

## Shortest Process Next

Shortest Process Next arbeitet so ähnlich wie *Shortest Remaining Time*.
Es hat ebenfalls die Priorität anhand der Verarbeitungszeit. Der
unterschied liegt jedoch am Abbruch. Shortest Process Next bricht den
Prozess nicht ab.

Der Vorteil liegt hierbei das kurze Prozesse schnell verarbeitet werden
und längere Prozesse werden verhungern.

<table>
<caption>Beispiel</caption>
<thead>
<tr class="header">
<th></th>
<th><p>1</p></th>
<th><p>2</p></th>
<th><p>3</p></th>
<th><p>4</p></th>
<th><p>5</p></th>
<th><p>6</p></th>
<th><p>7</p></th>
<th><p>8</p></th>
<th><p>9</p></th>
<th><p>10</p></th>
<th><p>11</p></th>
<th><p>12</p></th>
<th><p>13</p></th>
<th><p>14</p></th>
<th><p>15</p></th>
<th><p>16</p></th>
<th><p>17</p></th>
<th><p>18</p></th>
<th><p>19</p></th>
<th><p>20</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>B</p></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>C</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>D</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>E</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

Beispiel

## Round Robin

Round Robin hat sich als Scheduling Verfahren bis heute durchgesetzt und
wird vermehrt eingesetzt vor allem als load balancing. Round Robin wird
anhand eines Interrupt (ein **Zeitwert**) die Prozesse splitten. Danach
werden die Auufträge nach dem FCFS (First-come first-served) Muster
sortiert.

Alle Prozesse werden nach einem bestimmt Takt verarbeitet. Und es
existieren hierbei keine bevorzugte Prozesse.

<table>
<caption>Beispiel</caption>
<thead>
<tr class="header">
<th></th>
<th><p>1</p></th>
<th><p>2</p></th>
<th><p>3</p></th>
<th><p>4</p></th>
<th><p>5</p></th>
<th><p>6</p></th>
<th><p>7</p></th>
<th><p>8</p></th>
<th><p>9</p></th>
<th><p>10</p></th>
<th><p>11</p></th>
<th><p>12</p></th>
<th><p>13</p></th>
<th><p>14</p></th>
<th><p>15</p></th>
<th><p>16</p></th>
<th><p>17</p></th>
<th><p>18</p></th>
<th><p>19</p></th>
<th><p>20</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>B</p></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>C</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>D</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>E</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

Beispiel

q=3 (Zeitwert)
