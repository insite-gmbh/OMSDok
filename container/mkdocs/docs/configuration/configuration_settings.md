# Konfiguration des OMS
## Einstellungen eines OMS

![Einstellungen](./settings.png?raw=true "Einstellungen")

Die Bedienelemente von oben nach unten, links nach rechts:
* OMS LÖSCHEN
  
  Entfernt das OMS aus der Liste der konfigurierten OMS. 
  
  **Dieser Vorgang lässt sich nciht rückgängig machen!**

* Name

  Legt den Namen des OMS fest.

* Typ

  Legt den Typ des OMS fest. Zur Eingabe des Typs gibt es eine Dropdown-Liste mit vordefinierten Werten. 

  **Die Auswahl des Typs ist nicht beliebig. Die Firma BeeWaTec liefert ein OMS mit einer bestimmten Hardware-Ausstattung. Wenn die Hardware-Ausstattung nicht mit dem hier selektierten Typ übereinstimmt, kann es passieren, dass die AppWare auf dem OMS nicht lauffähig ist *oder* dass die Fähigkeiten der Hardware nicht vollständig genutzt werden.**

  Informieren Sie sich vorher, welchen Typ von OMS-Hardware Sie konfigurieren.

  Derzeit gibt es 4 Varianten:
    * OMS Standard (4 Eingänge, 4 Ausgänge)
    * OMS Extended (20 Eingänge, 20 Ausgänge)
    * OMS F Standard (4 Eingänge, 4 Ausgänge, Funkmodul, ohne Display)
    * OMS F Extended (20 Eingänge, 20 Ausgänge, Funkmodul, ohne Display)

  Die Ausstattung wird in einer Textzeile angezeigt.

* Anzahl Soft Keys

  Neben einem Anstoß durch digitale Hardware-Eingänge können Aufträge auch über Soft-Keys auf dem Touch-Panel des OMS erzeugt werden. Die Anzahl der Soft-Keys hat Auswirkungen auf das Layout des GUI der AppWare, jeweils 4 Stück werden in einer Reihe dargestellt, bis zu 16 Soft Keys können dargetellt werden. Die Einstellung hier hat lediglich Auswirkungen auf die Größe der Konfigurationstabelle. Weitere Informationen zur AppWare finden Sie [**hier**](../appware/appware_main.md).

* IP-Adresse
  
  Hier legen Sie die IP-Adresse des OMS im Netzwerk fest. Das OMS frägt beim Hochlauf oder auf eine Benutzereingabe hin beim OMSConfigService per http seine AppWare an. Der OMSConfigService verwendet die IP-Adresse des anfragenden OMS um die Konfigurationsdaten des OMS in seiner Datenbank zu suchen um sie anschließend an das OMS zurück zu senden.
  
  **Die IP-Adresse muss innerhalb des aktuell ausgewählten Projektes eindeutig sein, sonst kann der OMSConfigService die AppWare nicht an das OMS übertragen.**


## Navigation
## [Zurück zur Hauptseite der Konfiguration](./configuration_main.md)
## [Zurück zur Hauptseite](../README.md)