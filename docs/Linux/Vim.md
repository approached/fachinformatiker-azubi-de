---
title: Vim
---

# Vim

Vim ist Texteditor das im Terminal genutzt. Es ist vergleichbar mit [Nano](https://wiki.ubuntuusers.de/Nano). Vim ist die weiterentwicklung von **vi** und eine es gibt noch einen erweiterten Editor (https://neovim.io/)[neovim]. Dieser hat erweiterte Funktionenen und der quellcode wurde optimiert.

## Cheatsheet

**Normal, insert, command**

| Modus   | Beschreibung                                                                                 |
|---------|----------------------------------------------------------------------------------------------|
| normal  | Für Navigation und Manipulation von Texten. In den Modus kommt mit mit Drücken der <kbd>ESC-Taste</kbd> |
| insert  | Der eigentliche Modus zum schreiben von Texten. Du kommst u.a. mit <kbd>i</kbd> in diesen Modus         |
| visual  | Hier wird ein Bereich markiert, um innerhalb diesen Bereichs etwas durchzuführen             |
| command | Die Command Line des Editors. Aus dem Normal-Modus mit : zu erreichen                        |
| Ex-Mode | Eigentlich für Batch-Verarbeitung und der Ursprung von vi                                    |

**Öffnen, speichern und beenden**

| Befehl        | Was passiert?                                                                                            |
|---------------|----------------------------------------------------------------------------------------------------------|
| :q            | Beendet den Editor. Sollte etwas nicht gespeichert sein, kannst Du in nicht beenden                      |
| :q!           | Beendet den Editor, auch wenn noch etwas nicht gespeichert ist (Datenverlust)                            |
| :w            | Speichert, aber beendet nicht. Mit :w Dateiname kannst Du entsprechend einen Namen zum speichern angeben |
| :w! dateiname | Speichert (und überschreibt auch falls es die Datei schon gibt), aber beendet nicht.                     |
| :wq           | Speichern und beenden. Ja ja, die coolen Leute drücken ZZ im normal mode.                                |
| :wqa          | Speichern und beendet auch alle Tabs. Eher für später interessant, da Du erst mal Tabs lernen musst.     |
| :e dateiname  | Öffnet eine Datei in einem weiteren Buffer. Ein Buffer ist eine Art weitere Layer im Editor.             |


**Suchen und Ersetzen**
| Befehl                           | Was passiert?                                                                             |
|----------------------------------|-------------------------------------------------------------------------------------------|
| :%s/suchbegriff/ersatzbegriff/g  | Sucht nach suchbegriff und ersetzt dies durch ersatzbegriff im aktuellen Dokument         |
| :%s/suchbegriff/ersatzbegriff/gc | Wie zuvor, aber man wird gefragt, ob es ersetzt werden soll                               |
| :%s/suchbegriff/ersatzbegriff    | Ohne dem /g wird nur das nächste passende Wort gesucht und ersetzt                        |
| :&#8203;s/suchbegriff/ersatzbegriff/g   | Suchen und Ersetzen nur in der aktuellen Zeile und auch hier ohne /g nur das nächste Wort |
| :set ignorecase                  | Suche nicht Case-Sensitive. Befehl wirkt nur in der aktuellen Session                     |
| :set smartcase                   | Zusatz zu ignorecase. Aber wenn ich Groß-/Kleinschreibung verwende dann diese beachten    |



**Buffer**
| Befehl   | Was passiert?                                                                                  |
|----------|------------------------------------------------------------------------------------------------|
| :bn      | Spingt zum nächsten Buffer. Du kannst mehrere Dateien offen haben in unterschiedlichen Buffern |
| :bp      | Springt zum vorherigen Buffer                                                                  |
| :bf      | Springt zum ersten Buffer                                                                      |
| :bl      | Springt zum letzten Buffer                                                                     |
| :buffers | Zeigt an, welche Dateien (Buffer) geöffent sind                                                |

**Bewegen im normal mode**
| Befehl/Taste | Was passiert?                                                                                                                    |
|--------------|----------------------------------------------------------------------------------------------------------------------------------|
| h            | Cursor nach links. Geht natürlich auch mit den Cursor-Tasten                                                                     |
| j            | Cursor nach unten                                                                                                                |
| k            | nach oben                                                                                                                        |
| l            | nach rechts                                                                                                                      |
| $            | Springe zum Ende der Zeile                                                                                                       |
| 0            | Springe zum Start der Zeile                                                                                                      |
| ^            | Springe zum ersten Zeichen der Zeile, also nach z.B. Leerzeichen                                                                 |
| gg           | Gehe zum Anfang des Dokuments                                                                                                    |
| G            | Springe zum Ende des Dokuments                                                                                                   |
| w            | Bewegt den Cursor zum ersten Zeichen des nächsten Worts. Dabei ist auch ein Sonderzeichen ein neues Wort                         |
| W            | Überspringt auf das nächste Wort nach einem Leerzeichen                                                                          |
| b            | Identisch zu w, nur rückwärts                                                                                                    |
| B            | Identisch zu W, nur rückwärts                                                                                                    |
| e            | Wie w nur ist des nun der letzte Zeichen des Wortes                                                                              |
| E            | Wie W nur ist des nun der letzte Zeichen des Wortes                                                                              |
| ge           | Wie b, nur rückwärts                                                                                                             |
| gE           | Wie B, nur rückwärts                                                                                                             |
| )            | Springt zum ersten Zeichen des nächsten Satzes                                                                                   |
| (            | Springt zum ersten Zeichen des letzten Satzes                                                                                    |
| }            | Springt zum nächsten Absatz                                                                                                      |
| {            | Springt zum vorherigen Absatz                                                                                                    |
| +            | Begt den Cursor zum ersten Zeichen der nächsten Zeile                                                                            |
| –            | Entsprechend den Cursor in die vorherige Zeile                                                                                   |
| H            | Springt mit dem Cursor zu ersten Zeile des sichtbaren Fensters                                                                   |
| M            | Gehe mit Cursor in die Zeile die sich in der Mitte des sichtbaren Bereichs befindet                                              |
| L            | Und entsprechend in die letzte Zeile                                                                                             |
| fx           | Gehe zum nächsten Zeichen x der aktuellen Zeile. f, würde zum nächsten Komma springen                                            |
| Fx           | wie fx, nur rückwärts                                                                                                            |
| tx           | Identisch zu fx, nur ein Zeichen dafür                                                                                           |
| Tx           | Identisch zu Fx, nur ein Zeichen danach                                                                                          |
| %            | Bewegen den Cursor zur nächsten Klammer, geschweiften Klammer oder Kommentar, die mit der aktuellen Cursorposition gekoppelt ist |
| 5            | Springt 5 Zeilen nach unten                                                                                                      |
| 5-           | Springt 5 Zeilen nach oben                                                                                                       |

**Bewegen im normal mode und im insert mode**
| Befehl/Taste  | Was passiert?                         |
|---------------|---------------------------------------|
| Cursor-Tasten | Gewohnte Funktion wie in jedem Editor |
| CTRL+u        | Halbe Seite nach oben springen        |
| CTRL+d        | Halbe Seite nach unten springen       |
| CTRL+b        | Ganze Seite nach oben                 |
| CTRL+f        | Ganze Seite nach unten                |


**Suche im normal mode**
| Befehl/Taste | Was passiert?                                                                                     |
|--------------|---------------------------------------------------------------------------------------------------|
| *            | Sucht nach dem nächsten Wort, welches sich unter dem Cursor befindet                              |
| #            | Das ganze rückwärts                                                                               |
| /suchbegriff | Suche vorwärts nach dem Wort Suchbegriff. Je nach Einstellung wird Groß-/Kleinschreibung beachtet |
| ?word        | Die Suche entsprechend rückwärts                                                                  |
| n            | Springe zum nächsten Suchbegriff der gefunden wird                                                |
| N            | Entsprechend wieder rückwärts                                                                     |

**Wie komme ich vom normal mode in den insert mode**
| Befehl/Taste | Was passiert?                                                            |
|--------------|--------------------------------------------------------------------------|
| i            | Geht in den insert mode, um Text zu schreiben                            |
| a            | Geht ein Zeichen weiter in den insert mode                               |
| I            | Springt zum ersten Zeichen der Zeile und geht in insert mode             |
| A            | Geht in insert mode bei dem letzten Zeichen der Zeile                    |
| o            | Fügt eine Zeile unter der aktuellen Zeile ein und geht in insert mode    |
| O            | Fügt eine Zeile oberhalb der aktuellen Zeile ein und geht in insert mode |
| cm           | Ersetzte das aktuelle Wort. Löscht das Wort und geht in insert mode      |
| cc           | Löscht die ganze Zeile und geht in insert mode. Wäre wie ddO.            |
| C            | Entfernt alles bis zum Ende der Zeile und geht in insert mode            |
| s            | Entfernt Zeichen unter dem Cursor und geht dann in inset mode.           |

**Löschen (im normal mode)**
| Befehl/Taste | Was passiert?                                                                                                    |
|--------------|------------------------------------------------------------------------------------------------------------------|
| x            | Löscht das Zeichen unter dem Cursor. Entspricht Backspace, was auch geht                                         |
| r            | Tauscht das Zeichen unter dem Cursor aus und bleibt dabei im normal mode. Beispiel ra macht ein a an der Stelle. |
| dw           | Löscht das Wort. Du kannst auch dW, db oder eine andere Kombination nehmen.                                      |
| dd           | Löscht die ganze Zeile                                                                                           |
| D            | Löscht alles ab dem Cursor bis zum Ende der Zeile                                                                |

**Kopieren und Einfügen (im normal mode)**
| Befehl/Taste | Was passiert?                                                                    |
|--------------|----------------------------------------------------------------------------------|
| y            | Kopiert den markierten Text (siehe v und V)                                      |
| yy           | Kopiert die ganze Zeile                                                          |
| yw           | Kopiert das Wort unter dem Cursor. Du merkst die Kombinationen wiederholen sich. |
| ynw          | Kopiert eine Anzahl n Wörter. 5yy würde 5 Zeilen Kopieren                        |
| y$           | Kopiert bis zum Ende der Zeile                                                   |
| p            | Fügt das kopierte unter dem Cursor ein                                           |
| P            | Fügt das kopierte vor dem Cursor ein                                             |
| J            | Fügt die aktuelle mit der nächsten Zeile zusammen                                |

**VISUAL MODE**
| Befehl/Taste | Was passiert?                                                                 |
|--------------|-------------------------------------------------------------------------------|
| v            | Visual mode, sozusagen Text markieren                                         |
| V            | Visual mode für ganze Zeile                                                   |
| o            | Bewegt Cursor im visual mode zwischen ersten und letzten Zeichen              |
| ~            | Ändert Groß-/Kleinschreibung der Auswahl. Also klein wird groß und umgekehrt  |
| »            | Ist wie Einrücken mit Tab-Taste. Entweder die Zeile oder alles im visual mode |
| «            | In die andere Richtung.                                                       |

**Groß-/Kleinschreibung**
| Befehl/Taste | Was passiert?                                                   |
|--------------|-----------------------------------------------------------------|
| g~           | Ändere Zeichen unterhalb des Cursors. Aus klein macht groß etc. |
| g~$          | Bis zum Ende der Zeile alle Zeichen ändern                      |
| g~~          | Aktuelle Zeile                                                  |
| gUU          | Ganze Zeile in Großbuchstaben ändern                            |
| guu          | Und die ganze Zeile in Kleinbuchstaben wandeln                  |

**Undo, Redo, Repeat**
| Befehl/Taste | Was passiert?                                                                                       |
|--------------|-----------------------------------------------------------------------------------------------------|
| u            | Undo                                                                                                |
| U            | Alle Änderungen einer Zeile zurücknehmen                                                            |
| CTRL+R       | Das Gegenteil von Undo, also Wiederherstellen                                                       |
| .            | Letzte Änderung oder löschen wiederholen. Zeile löschen und mit . wird nochmals eine Zeile gelöscht |
| ;            | Wiederholt letztes f, t, F, or T Kommando.                                                          |
| ,            | Wie ; nur in die andere Richtung                                                                    |


## Einstellungen

**Zahlennummerierung**

Die Zahlen-Nummerierung kann man folgenderweise anstellen.

`:set nu`

Und folgendermaßen ausschalten

`:set nu!`

**Suchen und Ersetzen**

`:%s/[Suchstring]/[Ersetzungsstring]/g`

**Löschen Von-Bis Zeile**

`:5,10d`

**Alle Zeilen Löschen**

`:1,$d`

**Zur letzter Zeile Springen**

`G`

**Dateien vergleichen**

`vimdiff package.json package_preact.json`

Zeichkordierung

Das Anzeigen der Zeichenkordierung geht wie folgt:

`:set func`

Das Setzen der Zeichenkordierung:

`:set fileencoding=utf-8`

## Einstellungen

-   vim Editor als Standard Editor einstellen

`update-alternatives --config editor`

-   Automatische Vim Einstellungen

<!-- -->

    vim .vimrc

    Einfügen:
    :syntax on
    :set nu

## Notes

- <http://www.linux-fuer-alle.de/doc_show.php?docid=29&catid=8>
- Basis installation: <https://schimana.net/2021/neovim-teil-1-grundinstallation-von-neovim-unter-macos/>
- Visual cheatsheet: <https://github.com/mattmc3/neovim-cheatsheet>
- Text cheatsheet: <https://devhints.io/vim>
- VIM Keyboard Shortcuts from tuxfight3r <https://gist.github.com/tuxfight3r/0dca25825d9f2608714b>
