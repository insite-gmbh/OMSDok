# Konfiguration des OMS
## Konfiguration Soft Keys

![Aufträge](./softkeys.PNG?raw=true "Aufträge für Soft Keys konfigurieren")

Auf dieser Seite kann für jeden Soft Key festgelegt werden, ob und wenn ja, welche Art von Transportauftrag in der FTS-Leitsteuerung erzeugt wird, wenn der Benutzer den jeweiligen Button auf dem OMS Touchscreen betätigt. 

*(Das OMS1 in dem gezeigten Beispiel verfügt über 16 Soft Keys (einstellbar in den Einstellungen), entsprechend werden auf dieser Seite normalerweise auch 16 Soft Keys angezeigt, der Screenshot ist jedoch reduziert auf die ersten 6 Soft Keys.)*

Für jeden Soft Key gibt es eine Konfigurations-Zeile in der Tabelle. Die Spalten im einzelnen:

### Holen-Ziel, Bringen-Ziel

Die Zielnamen können frei vergeben werden, im Idealfall hat der OMSConfigService die vorhandenen Ziele jedoch bei der FTS-Leitsteuerung bereits angefragt und bietet die vorhandenen Ziele über "auto-completion" zur Übernahme an.

### Auftragstyp
Hier sind die Einstellungen "Abtransport" oder "Antransport" möglich. Die Einstellung hat keine Auswirkung auf die Generierung des Auftrags in der Leitsteuerung. Vielmehr wird sie verwendet, um den aktuellen Auftragsstatus in unterschiedlicher Art und Weise anzuzeigen. Mehr dazu unten.

### Auftragsname
Dem erzeugten Auftrag kann hier ein Name gegeben werden, der dann u.a. in der Meldungsliste der AppWare verwendet wird. 

**Eine Auftragskonfiguration ist nur gültig, wenn der Name ausgefüllt und nicht leer ist.**

## Speichern der Änderungen nicht vergessen!

**Die Änderungen auf dieser Seite werden erst mit einem Klick auf den Button "ÄNDERUNGEN ÜBERNEHMEN" aktiv!**

Als Bestätigung erscheint für einen kurzen Moment ein grünes Fenster mit dem Text "GESPEICHERT" und der Anzahl der Aufträge, die für das OMS definiert sind.

## Anzeige des Auftragsstatus
Der Status eines Auftrags wird direkt über die Farbe des Soft Keys / Buttons auf dem GUI der AppWare angezeigt. Die Darstellung des Status hängt vom Auftragstyp (Antransport oder Abtransport) ab. Wie und welche Status visualisiert werden finden Sie im Kapitel zur  [**AppWare**](../appware/appware_main.md).


## Navigation
## [Zurück zur Hauptseite der Konfiguration](./configuration_main.md)
## [Zurück zur Hauptseite](../README.md)