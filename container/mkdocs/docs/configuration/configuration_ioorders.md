# Konfiguration des OMS
## IO-Konfiguration Aufträge

![Aufträge](./ioorders.png?raw=true "Aufträge konfigurieren")

Auf dieser Seite kann für jeden Hardware-Eingang festgelegt werden, ob und wenn ja, welche Art von Transportauftrag in der FTS-Leitsteuerung erzeugt wird, wenn der Eingang seinen Status ändert. 

Allgemeine Informationen zu der Digital-IO eines OMS finden Sie [**hier**](./configuration_iogeneral.md).

*(Das OMS1 in dem gezeigten Beispiel verfügt über 20 Eingänge, entsprechend werden auf dieser Seite normalerweise auch 20 Eingänge angezeigt, der Screenshot ist jedoch reduziert auf die ersten 6 Eingänge.)*

Die Hardware-Eingänge können auch für das Sperren von Fahrkursbereichen (Tore) oder den Feueralarm verwendet werden und stehen dann nicht mehr für die Erzeugung von Aufträgen zur Verfügung. Ein bereits verwendeter Eingang wird gelb hinterlegt dargestellt. Wenn wie im dargestellten Fall Eingang 3 zur Auftragserzeugung verwendet werden soll, muss er vorher bei seiner anderen Verwendungsstelle (Feueralarm oder ein Tor) freigegeben werden. Ein Auftrag wiederum gilt als "freigegeben", wenn sein Name leer ist.

## Konfigurationstabelle

Für jeden Eingang gibt es eine Konfigurations-Zeile in der Tabelle. Die Spalten im einzelnen:

### Holen-Ziel, Bringen-Ziel

Die Zielnamen können frei vergeben werden, im Idealfall hat der OMSConfigService die vorhandenen Ziele jedoch bei der FTS-Leitsteuerung bereits angefragt und bietet die vorhandenen Ziele über "auto-completion" zur Übernahme an.

### Auftragstyp
Hier sind die Einstellungen "Abtransport" oder "Antransport" möglich. Die Einstellung hat keine Auswirkung auf die Generierung des Auftrags in der Leitsteuerung. Vielmehr wird sie verwendet, um den aktuellen Auftragsstatus in unterschiedlicher Art und Weise anzuzeigen. Mehr dazu unten.

### Auftragsname
Hier kann dem erzeugten Auftrag ein Name gegeben werden, der dann u.a. in der Meldungsliste der AppWare verwendet wird. 

**Eine Auftragskonfiguration ist nur gültig, wenn der Name ausgefüllt und nicht leer ist.**

### Ausgang
Hier kann dem Auftrag, der über den jeweiligen Eingang erzeugt wird, ein Hardware-Ausgang zugeordnet werden, mit dem der Auftragsstatus über eine Leuchte visualisiert werden kann. Mehr dazu unten.

### Entprellzeit
Die Entprellzeit in Millisekunden, für die ein Eingang ein stabiles Signal liefern muss, um als gültiger Status bewertet zu werden. 

### Fallende Flanke
Hier mit wird festgelegt, ob der Auftrag mit einer steigenden/positiven Signalflanke (offen -> geschlossen, 0 -> 1, aus -> an) oder mit einer fallenden/negativen Signalflanke (geschlossen -> offen, 1 -> 0, an -> aus) erzeugt wird. Per default ist die Checkbox leer, d.h. der Auftrag wird mit positiver Signalflanke erzeugt.

## Speichern der Änderungen nicht vergessen!

**Die Änderungen auf dieser Seite werden erst mit einem Klick auf den Button "ÄNDERUNGEN ÜBERNEHMEN" aktiv!**

Als Bestätigung erscheint für einen kurzen Moment ein grünes Fenster mit dem Text "GESPEICHERT" und der Anzahl der Aufträge, die für das OMS definiert sind.

## Anzeige des Auftragsstatus
Wenn der Status eines Auftrags angezeigt werden soll, muss dem Auftrag ein Hardware-Ausgang zugeordnet werden. An diesen ist in der Regel eine Leuchte angeschlossen. Die Darstellung des Status hängt vom Auftragstyp (Antransport oder Abtransport) ab. Folgende Status werden damit visualisiert:

| Auftragsbearbeitungs-Status      | Auftragstyp     | Leuchte        |
| -------------------------------- | --------------- | -------------- |
| Auftrag erzeugt                  | -               | ein            |
| Fahrzeug holt                    | Antransport     | ein            |
|                                  | Abtransport     | blinkt langsam |
| Fahrzeug bringt                  | Antransport     | blinkt langsam |
|                                  | Abtransport     | aus            |
| Fertig / Abgebrochen             | -               | aus            |
| Verzögerung bei der Bearbeitung  | -               | blinkt schnell |


## [Übersicht zu den Digital IOs des OMS](./configuration_iogeneral.md)
