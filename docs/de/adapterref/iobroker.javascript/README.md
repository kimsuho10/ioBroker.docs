---
BADGE-Number of Installations: http://iobroker.live/badges/javascript-stable.svg
BADGE-NPM version: http://img.shields.io/npm/v/iobroker.javascript.svg
BADGE-Downloads: https://img.shields.io/npm/dm/iobroker.javascript.svg
BADGE-Tests: https://travis-ci.org/ioBroker/ioBroker.javascript.svg?branch=master
BADGE-NPM: https://nodei.co/npm/iobroker.javascript.png?downloads=true
chapters: {"pages":{"de/adapterref/iobroker.javascript/README.md":{"title":{"de":"no title"},"content":"de/adapterref/iobroker.javascript/README.md"},"de/adapterref/iobroker.javascript/blockly.md":{"title":{"de":"Inhalt"},"content":"de/adapterref/iobroker.javascript/blockly.md"}}}
---
Der javascript-Adapter dient dazu komfortabel Skripte zu erstellen, editieren und zu verwalten.


## [](https://github.com/ioBroker/ioBroker/wiki/ioBroker-Adapter-javascript#konfiguration)Konfiguration


![Einstellungsmenü Javascript Adapter](img/javascript_Einstellungen-Javascript.png)
   Die eigentliche Konfiguration besteht aus der Eingabe von zusätzlichen zu ladenden npm-Module (durch Komma getrennt), sowie der Geo-Koordinaten, die für diverse Berechnungen benutzt werden sollen. Um die Koordinaten zu erhalten, kann man z.B. _google maps_ ziemlich weit aufzoomen und an der gewünschten Stelle anklicken. Die Koordinaten werden dann angezeigt. Nach dem Speichern muss der Adapter noch über die rote Play-Taste aktiviert werden aktiviert werden.

* * *

## Bedienung

Bei der Installation wird ein weiterer Reiter _Scripte_ in der _Admin_-Oberfläche gezeigt. Hier wird ein neuer Ordner angelegt indem auf das (+) in der Symbolleiste (roter Kreis) geklickt wird.  Ein neues Skript wird über das "leere Blatt"-Icon links davon angelegt. Ein Fenster öffnet sich und fragt den Namen und Speicherort in der Ordnerstruktur ab. 
![Javascript Adapter](img/javascript_Javascript-Adapter.png)


### Ordner- und Dateiliste

Die Ordnerstruktur kann nach eigenem Wunsch angelegt werden. Der Speicherort hat keine Auswirkungen auf die Funktionalität des Skriptes. Neben der Baumstruktur gibt es eine Listenansicht. Ein Suchfeld erleichtert das Wiederfinden von Skripten. Damit ein Skript läuft, muss es links in der Ordnerstruktur durch klick auf den roten _Play_-Knopf aktiviert werden. Zum Stoppen auf den grünen _Pause_-Knopf drücken. Für jedes Skript wird ein neues Objekt angelegt. Es trägt den Skriptnamen mit dem Zusatz `_enabled` und liegt im Ordner `javascript.Instanz.ScriptEnabled`. Das Objekt zeigt mit (`true/false`) an, ob das Skript läuft. Der Zustand kann auch gesetzt werden, um das Skript ein-/auszuschalten. Skripte, die im Ordner _global_ gespeichert wurden, sind globale Skripte. Diese werden intern vor jedes andere Skript kopiert, also vorher abgearbeitet. Somit lassen sich globale Funktionen auf mehrere Skripte anwenden. Variablen in globalen Skripten können in anderen Skripten benutzt werden. Aber Achtung: Jedes Skript hat seinen eigenen Variablen-Raum. Man kann Variablen in globalen Skripten also nicht dazu benutzen um Werte zwischen Skripten auszutauschen. Dazu müssen zwingend Objekte (States) genutzt werden.  

### Editor

Nach dem Anlegen öffnet sich rechts der Editor für _Javascript_. Einige Beispielskripte finden sich [hier](http://www.iobroker.net/docu/?page_id=2786&lang=de).

#### Name

Hat man vorher einen Namen vergeben, wird dieser hier angezeigt und kann geändert werden.

#### Speicherort

In diesem Dropdown werden alle angelegten Ordner angezeigt. Zur Zeit sind sie in der chronologischen Folge ihrer Erstellung sortiert.

#### Enginetyp

hier kann ausgewählt werden, ob mit der _javascript_ oder der _coffeescript_ engine gearbeitet werden soll.

#### Log

Rechts unten findet sich das Log-Fenster für die Ausgabe aller das markierte Skript betreffende Logs. Die Logs werden nach dem Abspeichern/Neustart des Skriptes angezeigt.

* * *

## Tipps

### Backup

Um Skripte im Zweifel wiederherstellen zu können, sei die Sicherung per _Copy & Paste_ empfohlen.

### Test-Instanz

Es hat sich bewährt, zum Testen von neuen Skripten, eine weitere Javascript-Instanz anzulegen und das Skript in dieser Instanz zu starten. 
Hinter dem Skriptnamen lässt sich per Dropdown die gewünschtes Instanz einstellen. 
Sollte im Skript ein schwerwiegender Fehler sein, beendet sich nur diese zusätzliche Testinstanz, nicht die Produktivinstanz. 

![Instanz Javascript Adapter wählen](img/screen.jpg)

## Changelog

### 4.6.22 (2020-07-30)
* (Apollon77) catched some more file errors in mirror logic

### 4.6.21 (2020-07-28)
* (Apollon77) catched some more file errors in mirror logic (Sentry IOBROKER-JAVASCRIPT-2X, IOBROKER-JAVASCRIPT-3C)

### 4.6.20 (2020-07-26)
* (Apollon77) make sure 0_userdata.0 objects/states are not overwritten on createState 

### 4.6.19 (2020-07-26)
* (Apollon77) Prevent wrong errors when setting "null" values for states
* (Apollon77) Prevent potential crash when no typings could be found (Sentry IOBROKER-JAVASCRIPT-2T)
* (Apollon77) catch an error in mirroring functionality( Sentry IOBROKER-JAVASCRIPT-2V)
* (Apollon77) make sure names are handled correctly if they are not strings (Sentry IOBROKER-JAVASCRIPT-2Y) 
* (Apollon77) make sure invalid schedules can not crash adapter (Sentry IOBROKER-JAVASCRIPT-31)
* (Apollon77/paul53) Allow "deleteState" with full javascript.X object Id again (from same instance only)
* (bluefox) Revert changes for sync getState, because "on change" detection is broken 
* (AlCalzone) Several issues with Typescript, Typings and virtual-tsc optimized and fixed
* (bluefox) Store JS in browser cache by enabling serviceWorkers
* (Apollon77) prevent multiple script restarts on fast file content change for mirroring or fast object changes

### 4.6.17 (2020-05-25)
* (bluefox) Fixed error with warnings collapsed blocks
* (Apollon77) optimize Sentry error reporting to prevent false positives

## License

The MIT License (MIT)

Copyright (c) 2014-2020 bluefox <dogafox@gmail.com>,

Copyright (c) 2014      hobbyquaker