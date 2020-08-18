# Konfiguration des OMS
## Die Digital IOs des OMS

Jedes OMS bietet eine bestimmte Zahl von digitalen Ein- und Ausgängen. Derzeit sind es - je nach Ausführung - 4 Ein- und 4 Ausgänge oder 20 Ein- und 20 Ausgänge. 

## Eingänge

Die Eingänge können 3 verschiedene Aufgaben übernehmen:

* Auftragserzeugung

  * jedem Eingang kann ein Auftrag zugeordnet werden
* Sperren von Fahrkursbereichen
  
  * jedem Eingang kann ein Fahrkursbereich zugeordnet werden

  * *wird derzeit ausschließlich für Bereiche um Brandschutztore verwendet*

* Auswertung eines Feueralarm-Signals (nur ein Eingang)


Über die Hardware-Eingänge können z.B. Taster oder andere Sensoren (z.B. zur Palettenerkennung) mit dem OMS verbunden werden und dann für den automatisierten Abtransport von Ware sorgen.

## Ausgänge

Die Ausgänge werden derzeit ausschließlich zur Anzeige der Status von Aufträgen verwendet. In der Regel werden dort Leuchten angeschlossen, es ist aber natürlich auch denkbar, diese Signale anderweitig auszuwerten.

Weitere Informationen dazu finden Sie auf [**dieser Seite**](./configuration_ioorders.md) unten.


Zur Konfiguration der Digital-IO finden Sie hier mehr Informationen:

#### [IO-Konfiguration Aufträge](./configuration_ioorders.md)
#### [IO-Konfiguration Tore](./configuration_iogates.md)
#### [IO-Konfiguration Feueralarm](./configuration_iofire.md)
