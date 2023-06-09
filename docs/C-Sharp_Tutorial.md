---
title: C-Sharp Tutorial
description: 
published: true
date: 2022-02-09T13:32:49.488Z
tags: 
editor: markdown
dateCreated: 2022-02-09T13:32:47.995Z
---

# C-Sharp Tutorial

C-Sharp (C#) ist eine Programmiersprache von Microsoft. Dieses basiert
auf das \[dot\].net Framework. Weiter Informationen gibt es [Hier].

## Beschreibung

Für das Programmieren mit **C#** wird ein Editor benötigt. Bestenfalls
sollte man das "Microsoft Visual Studio" oder eine ähnliche
Entwicklungsumgebung verwenden. Die Expressversion von Visual Studio ist
für 30 Tage kostenlos.

## Tutorial

### Vererbung

**Abstrakte Klasse**

        abstract class Tier
        {

            public String name = "";

            public Tier(String name)
            {
                this.name = name;
            }

            public virtual void Steckbrief()
            {
                Console.WriteLine("Name des Tiers: " + name);
            }

        }

**Implementieren von einer Abstrakten und einer Interface Klasse**

    class Landtier : Tier, IGeschwindigkeit
        {

            private int _ge;

            public Landtier(String Name, int ge)
                : base(Name)
            {
                geschwindigkeit = ge;
            }


            #region IGeschwindigkeit Member

            public int geschwindigkeit
            {
                get
                {
                    return _ge;
                }
                set
                {
                    _ge = value;
                }
            }

            #endregion

            public override void Steckbrief()
            {
                base.Steckbrief();
                Console.WriteLine("Geschwindigkeit: " + geschwindigkeit);
            }

        }

**Erben der Klasse**

        class Elefant : Landtier
        {
            public Elefant(String Name, int Ge) : base(Name, Ge)
            {
            }
        }

### Formatierung

**Label**

-   Labelinhalt löschen

Einen Text der im Label eingetragen ist kann wie folgt löschen.

`this.meinlabel.Clear();`

-   Label Auswählen

Einen Label kann man auswählen z.B. nach dem man es gelöscht hat
mittels:

`this.derlaber.Focus();`

**Formatierung**

-   Vom Label zur einer Variable

`double menge = Convert.ToDouble(this.menge.Text);`

-   Von einer Variable zu einem Label

`label.Text = Convert.ToString(menge);`

**Sonstiges**

-   Tabindex

Die Reihenfolge eines Formulars kann man mittels **Tabindex** steuern.
Dies lässt dort einstellen.

`Label > Eigenschaft > Tabindex > 1`

-   Programm schließen

Ein Programm kann man folgender maßen schließen.

`Close();`

## Handbuch

-   <http://openbook.galileocomputing.de/visual_csharp_2010/>
-   <http://openbook.galileocomputing.de/csharp/index.htm>

  [Hier]: http://de.wikipedia.org/wiki/C-Sharp