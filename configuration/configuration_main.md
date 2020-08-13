# Konfiguration der OMS AppWare

Ein OMS bezieht seine AppWare von dem OMSConfigService, der auf einem Rechner installiert und aktiv sein muss, der über das Netzwerk erreichbar ist. 

[Mehr dazu hier.](../working_principle/working_principle_main.md)

Der OMSConfigService bietet ein web-basiertes GUI, mit dem diese Konfiguration für alle kunden-spezifischen Projekte durchgeführt wird.
Jedes OMS hat innerhalb eines Projektes eine eindeutige IP-Adresse die als "Identifier" für die jeweilige Konfiguration dient.

## Start des GUI
Da das GUI web-basiert ist, reicht es aus, in der Adresszeile eines Browsers (bevorzugt Google Chrome!) die IP-Adresse des Rechners einzugeben, auf dem der OMSConfigService läuft. Per default verwendet das GUI den Port 5000.

In diesem Beispiel läuft der OMSConfigService auf dem Rechner mit der IP 192.168.0.126. Daher geben Sie in der Adressleiste des Browsers 

`192.168.0.126:5000`

ein und drücken die Eingabe-Taste. Mit den üblichen Funktionen eines Browsers ("Lesezeichen") können Sie die URL zu dieser "Webseite" speichern.


## [Abschnitt 1](./configuration_ch1.md)

## Navigation
## [Zurück zur Hauptseite](../README.md)