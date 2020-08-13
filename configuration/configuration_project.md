# Konfiguration des OMS
## Projektverwaltung

Innerhalb eines Projektes wird die Konfiguration der verschiedenen OMS einer FTS-Anlage gespeichert. Dies beinhaltet folgende Informationen:

* Die Datenbank-Datei, in welcher die Konfigurationsdaten für dieses Projekt abgespeichert sind.
* Alle OMS mit ihren jeweiligen Konfigurationen, die innerhalb des Projekts verwendet werden. 
* Welche Art von Leitsteuerung in diesem Projekt verwendet wird.
* Die IP-Adresse der Leitsteuerung.

**Die Auswahl eines Projektes hat eine gewisse *Sonderstellung*, da sie direkten Einfluss auf die vom OMSConfigService bereit gestellten Konfigurationsdaten für die OMS hat. Wie im Abschnitt [Funktionsprinzip](../working_principle/working_principle_main.md) beschrieben, ordnet der OMSConfigService die Konfiguration für ein OMS anhand dessen IP-Adresse zu. Es ist nun möglich, dass es ein OMS mit der IP x.x.x.x sowohl in Projekt A als auch in Projekt B gibt. Der OMSConfigService greift immer auf das aktuell eingestellte Projekt zurück! ** 

Streng genommen machen mehrere Projekte nur auf einem Inbetriebnahme-Laptop Sinn. Auf einem dauerhaft beim Kunden installierten OMSConfigService sollte **genau ein Projekt** angelegt und dieses **immer** ausgewählt sein.

### Projektverwaltungs-Seite



## Navigation
## [Zurück zur Hauptseite der Konfiguration](./configuration_main.md)
## [Zurück zur Hauptseite](../README.md)