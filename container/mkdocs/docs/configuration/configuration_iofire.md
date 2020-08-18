# Konfiguration des OMS
## IO-Konfiguration Feueralarm
![Feueralarm](./iofire.PNG?raw=true "Feueralarm konfigurieren")

Auf dieser Seite kann ein Hardware-Eingang als Feueralarm-Signal festgelegt werden. Im Falle eines Feueralarms wird die FTS-Leitsteuerung in den Status "Feueralarm" (normalerweise STOP) versetzt.

Allgemeine Informationen zu der Digital-IO eines OMS finden Sie [**hier**](./configuration_iogeneral.md).

Die Bedienelemente von links nach rechts:

### Eingang
Hier wird der Eingang für das Feueralarm-Signal aus der Liste der vorhandenen Eingänge ausgewählt. Wenn der ausgewählte Eingang in Folge gelb hinterlegt erscheint, dann wird er bereits an anderer Stelle (Auftragserzeugung oder Torekonfiguration) verwendet und muss dort erst freigegeben werden.

### Entprellzeit
Die Entprellzeit in Millisekunden, für die ein Eingang ein stabiles Signal liefern muss, um als gültiger Status bewertet zu werden. 

### Fallende Flanke
Hier mit wird festgelegt, ob der Feueralarm mit einer steigenden/positiven Signalflanke (offen -> geschlossen, 0 -> 1, aus -> an) oder mit einer fallenden/negativen Signalflanke (geschlossen -> offen, 1 -> 0, an -> aus) als anstehend bewertet wird. Per default ist die Checkbox angehakt, d.h. der Feueralarm steht nach einer negativen Signalflanke an.

## Speichern der Änderungen nicht vergessen!

**Die Änderungen auf dieser Seite werden erst mit einem Klick auf den Button "ÄNDERUNGEN ÜBERNEHMEN" aktiv!**

Als Bestätigung erscheint für einen kurzen Moment ein grünes Fenster mit dem Text "GESPEICHERT" und der Anzahl der Feueralarme, die über das OMS ausgewertet werden (aktuell entweder 0 oder 1).

## [Übersicht zu den Digital IOs des OMS](./configuration_iogeneral.md)
