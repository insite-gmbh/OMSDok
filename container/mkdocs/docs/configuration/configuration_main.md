# Konfiguration der OMS AppWare

Ein OMS bezieht seine AppWare von dem OMSConfigService, der auf einem Rechner installiert und aktiv sein muss, der über das Netzwerk erreichbar ist. 

[Mehr dazu hier.](../working_principle/working_principle_main.md)

Der OMSConfigService bietet ein web-basiertes GUI, mit dem diese Konfiguration für alle kunden-spezifischen Projekte durchgeführt wird.
Jedes OMS hat innerhalb eines Projektes eine eindeutige IP-Adresse die als "Identifier" für die jeweilige Konfiguration dient.

## Start des GUI
Da das GUI web-basiert ist, reicht es aus, in der Adresszeile eines Browsers (bevorzugt Google Chrome!) die IP-Adresse des Rechners einzugeben, auf dem der OMSConfigService läuft. Per default verwendet das GUI den Port 5000.

In diesem Beispiel läuft der OMSConfigService auf dem Rechner mit der IP 192.168.0.134. Daher geben Sie in der Adressleiste des Browsers 

`192.168.0.134:5000`

ein und drücken die Eingabe-Taste. Mit den üblichen Funktionen eines Browsers ("Lesezeichen") können Sie die URL zu dieser "Webseite" speichern.

![URL-Zeile](./URL.PNG?raw=true "URL des GUI")

## Hauptseite des GUI

![Hauptseite](./MainPage.PNG?raw=true "Hauptseite des GUI")

### Projektverwaltung
Über den Menüpunkt in der rechten oberen Ecke (roter Rahmen) wechselt man auf die [**Projektverwaltung**](./configuration_project.md)

### OMS hinzufügen
Über den Menüpunkt in der linken oberen Ecke (grüner Rahmen) kann ein neues OMS im aktuellen Projekt angelegt werden. Es wird automatisch die Seite für die Einstellungen des neuen OMS angezeigt. Zu den Einstellungen folgt weiter unten mehr.

![Neues OMS angelegt](./NewOMS.PNG?raw=true "Einstellungen für neues OMS")

### Auswahl der bereits konfigurierten OMS
Die Liste auf der linken Seite (blauer Rahmen) zeigt die bereits für das aktuelle Projekt konfigurierten OMS ("Davids Laptop", "OMS1"). Die jeweiligen Untermenüpunkte können durch eine Klick auf die Pfeilsymbole (gelbe Kreise) geöffnet und geschlossen werden. Für das OMS1 sind hier exemplarisch alle Untermenüs zu sehen.

Erklärungen und Hinweise zu den einzelnen Menüpunkten finden Sie in diesen Dokumenten:

#### [Einstellungen eines OMS](./configuration_settings.md)

#### [Die Digital IOs des OMS](./configuration_iogeneral.md)
#### [IO-Konfiguration Aufträge](./configuration_ioorders.md)
#### [IO-Konfiguration Tore](./configuration_iogates.md)
#### [IO-Konfiguration Feueralarm](./configuration_iofire.md)
#### [Konfiguration Soft Keys](./configuration_softkeys.md)

