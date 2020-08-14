# Konfiguration des OMS
## IO-Konfiguration Tore
![Tore](./iogates.PNG?raw=true "Tore konfigurieren")

Für jeden Hardware-Eingang kann auf dieser Seite festgelegt werden, ob und wenn ja, welche Art von Aktion in der FTS-Leitsteuerung angestoßen wird, wenn dieser Eingang seinen Status ändert. Bisher haben diese Aktionen die Sperrung eines Fahrursbereiches zur Folge. Als Aktion wird daher hier immer der Name des zu sperrenden Fahrkursbereiches angegeben. Das Incubed-System verwendet hierzu benannte "Resourcen", in BeeWaTecs BeeLoCCore-System werden im Fahrkurslayout benannte "Areas" definiert. 

Allgemeine Informationen zu der Digital-IO eines OMS finden Sie [**hier**](./configuration_iogeneral.md).

*(Das OMS1 in dem gezeigten Beispiel verfügt über 20 Eingänge, entsprechend werden auf dieser Seite normlerweise auch 20 Eingänge angezeigt, der Screenshot ist jedoch reduziert auf die ersten 6 Eingänge.)*

Die Hardware-Eingänge können auch für das Auslösen von Aufträgen oder den Feueralarm verwendet werden und stehen dann nicht mehr in der Torkonfiguration zur Verfügung. Ein bereits verwendeter Eingang wird gelb hinterlegt dargestellt. Im dargestellten Fall sind die Eingänge 1 und 2 bereis belegt. 

Die Torstatus werden in der AppWare visualisiert. Sie erscheinen auf der Oberfläche mit dem jeweils vergebenen Namen und sind grün (frei) oder rot (gesperrt) hinterlegt.

Für jeden Eingang gibt es eine Konfigurations-Zeile in der Tabelle. Die Spalten im einzelnen:

### Name
Ein sprechender Name für das Tor. Dieser wird in der AppWare verwendet um den Torstatus darzustellen.

### Aktion
Der Name des zu sperrenden Fahrkursbereiches. Dieser kann frei vergeben werden aber muss natürlich einer benannten Resource in FTS-Leitsteuerung entsprechen, sonst zeigt die Einstellung keine Wirkung. Im Idealfall hat der OMSConfigService die vorhandenen Resourcenamen jedoch bereits bei der FTS-Leitsteuerung angefragt und bietet sie über "auto-completion" zur Übernahme an.

Eine Konfigurationszeile ist gültig, solange hier ein Name eingetragen ist. Ein leeres Feld hat ein Löschen der Konfiguration für den jeweiligen Eingang zur Folge.

### Entprellzeit
Die Entprellzeit in Millisekunden, die ein Eingang ein stabiles Signal liefern muss, um als gültiger Status bewertet zu werden. 

### Fallende Flanke
Hier mit wird festgelegt, ob das Tor mit einer steigenden/positiven Signalflanke (offen -> geschlossen, 0 -> 1, aus -> an) oder mit einer fallenden/negativen Signalflanke (geschlossen -> offen, 1 -> 0, an -> aus) als geschlossen bewertet wird. Per default ist die Checkbox angehakt, d.h. das Tor ist nach negativer Signalflanke geschlossen.

## Speichern der Änderungen nicht vergessen!

**Die Änderungen auf dieser Seite werden erst mit einem Klick auf den Button "ÄNDERUNGEN ÜBERNEHMEN" aktiv!**

Als Bestätigung erscheint für einen kurzen Moment ein grünes Fenster mit dem Text "GESPEICHERT" und der Anzahl der Tore, die über das OMS ausgewertet werden.


## Navigation
## [Zurück zur Hauptseite der Konfiguration](./configuration_main.md)
## [Zurück zur Hauptseite](../README.md)