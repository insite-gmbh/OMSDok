# Konfiguration des OMS
## IO-Konfiguration Aufträge

![Aufträge](./ioorders.png?raw=true "Aufträge konfigurieren")

Für jeden Hardware-Eingang kann auf dieser Seite festgelegt werden, ob und wenn ja, welche Art von Transportauftrag in der FTS-Leitsteuerung erzeugt wird, wenn dieser Eingang seinen Status ändert. 

Allgemeine Informationen zu der Digital-IO eines OMS finden Sie [**hier**](./configuration_iogeneral.md).

*(Das OMS1 in dem gezeigten Beispiel verfügt über 20 Eingänge, entsprechend werden auf dieser Seite normlerweise auch 20 Eingänge angezeigt, der Screenshot ist jedoch reduziert auf die ersten 6 Eingänge.)*

Die Hardware-Eingänge können auch für das Sperren von Fahrkursbereichen (Tore) oder den Feueralarm verwendet werden und stehen dann nicht mehr für die Erzeugung von Aufträgen zur Verfügung. Ein bereits verwendeter Eingang wird gelb hinterlegt dargestellt. Wenn wie im dargestellten Fall Eingang 3 zur Auftragserzeugung verwendet werden soll, muss er vorher bei seiner anderen Verwendungsstelle (Feueralarm oder ein Tor) freigegeben werden.

Für jeden Eingang gibt es eine Konfigurations-Zeile in der Tabelle. Die Spalten im einzelnen:

### Holen-Ziel, Bringen-Ziel

Die Zielnamen können frei vergeben werden, im Idealfall hat der OMSConfigService die vorhandenen Ziele jedoch bei der FTS-Leitsteuerung bereits angefragt und bietet die vorhandenen Ziele über "auto-completion" zur Übernahme an.

### Auftragstyp
Hier sind die Einstellungen "Abtransport" oder "Antransport" möglich. Die Einstellung hat keine Auswirkung auf die Generierung des Auftrags in der Leitsteuerung. Vielmehr wird sie verwendet, um den aktuellen Auftragsstatus in unterschiedlicher Art und Weise anzuzeigen. Mehr dazu unten.

### Ausgang
Hier kann dem Auftrag, der über den jeweiligen Eingang erzeugt wird, ein Hardware-Ausgang zugeordnet werden, mit dem der Auftragsstatus über eine Leuchte visualisiert werden kann. Mehr dazu unten.

### Entprellzeit
Die Entprellzeit in Millisekunden, die ein Eingang ein stabiles Signal liefern muss, um als gültiger Status bewertet zu werden. 

### Fallende Flanke
Hier mit wird festgelegt, ob der Auftrag mit einer steigenden/positiven Signalflanke (offen -> geschlossen, 0 -> 1, aus -> an) oder mit einer fallenden/negativen Signalflanke (geschlossen -> offen, 1 -> 0, an -> aus) erzeugt wird. Per default ist die Checkbox leer, d.h. der Auftrag wird mit positiver Signalflanke erzeugt.

## Anzeige des Auftragsstatus
Wenn der Status eines Auftrags angezeigt werden soll, muss dem Auftrag ein Hardware-Ausgang zugeordnet werden. An diesen ist in der Regel eine Leuchte angeschlossen. Die Darstellung des Status hängt vom Auftragstyp (Antransport oder Abtransport) ab. Folgende Status werden damit visualisiert:

| Auftragsbearbeitungs-Status      | Auftragstyp     | Leuchte        |
| -------------------------------- | --------------- | -------------- |
| Auftrag erzeugt                  | egal            | ein            |
| Fahrzeug holt                    | Antransport     | ein            |
|                                  | Abtransport     | blinkt langsam |
| Fahrzeug bringt                  | Antransport     | blinkt langsam |
|                                  | Abtransport     | aus            |
| Fertig / Abgebrochen             | egal            | aus            |
| Verzögerung bei der Bearbeitung  | egal            | blinkt schnell |





## Navigation
## [Zurück zur Hauptseite der Konfiguration](./configuration_main.md)
## [Zurück zur Hauptseite](../README.md)