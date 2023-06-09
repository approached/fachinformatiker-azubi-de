---
title: Elektrotechnik
---

# Elektrotechnik

Elektrotechnik in der Zwischenprüfung als auch in der Abschlussprüfung
relevant. Meistens sind eins bis zwei Fragen in der Prüfung vorhanden.

## Ohmsches Gesetz

Bei dem Ohmsches Gesetz wird die Formel *URI* verwendet.

Formel: U=R\*I

Bedeutung:

-   U = Spannung - V (Volt)
-   R = Widerstand - Ω (Ohm)
-   I = Stromstärke - A (Ampere)

## Elektrische Leistung

Bei der Elektrische Leistung wird die Formel *PUI* verwendet.

Formel: P=U\*I

Bedeutung:

-   P = Leistung - W (Watt)
-   U = Spannung - V (Volt)
-   I = Stromstärke - A (Ampere)

## Leiterwiderstand

Formel: l=A\*R/roh

Bedeutung:

-   l = Leiterlänge - m (Meter)
-   A = Leiterquerschnitt - mm²
-   R = Widerstand - Ω (Ohm)
-   roh = Kupferleitung ( 0,0178 Ω\*mm² ) / m

## Stromdichte

Bei der Stromdichte wird die Formel *ISA* verwendet.

Formel: I=S\*A

Bedeutung:

-   I = Stromstärke - A (Ampere)
-   S = Stromdichte - A/mm²
-   A = Leiterquerschnitt - mm²

## Reihenschaltung

`#TODO`

## Parallelschaltung

`#TODO`

## Berechnung des benötigten Stromes einer USV

Reicht diese USV-Anlage für 10 Minuten aus?

Daten:

-   Akkuspannung: 12 Volt
-   Akkukapizität: 200 Ah
-   Leistung die er versorgen muss 20.000 W

<!-- -->

    t * P = Q
    10M * 20.000W = 200.000W

    I * U = Q
    200Ah * 60 (minuten) = 12000mAh * 12V = 144.000W

    Die Relation:
    200.000 - 10M
    144.000 - x

    x= 10 * 144.000 / 200.000
    x= 7,2M

Bei dieser USV recht der Strom bis zu **7 Minuten** aus.

[Akku Rechner]

## Stromkosten

-   Strompreis: 0,20€/kWh (Preis pro Stunde)
-   Computer: 400W
-   Dauer: ganzes Jahr

<!-- -->

    1000W - 0,20€
     400W - x

    x= 0,20 * 400W / 1000W
    x= 0,08€

    0,08 * 24 * 365 = 700,80€

  [Akku Rechner]: http://www.akkuline.de/akku-batterie-rechner-accu-calculator.aspx#Betriebsdauer
