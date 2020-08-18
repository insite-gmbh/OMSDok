# Konfiguration des OMS
## Projektverwaltung

Innerhalb eines Projektes wird die Konfiguration der verschiedenen OMS einer FTS-Anlage gespeichert. Dies beinhaltet folgende Informationen:

* Die Projekt-Datenbank, in welcher die Konfigurationsdaten für dieses Projekt abgespeichert sind.
* Alle OMS mit ihren jeweiligen Konfigurationen, die innerhalb des Projekts verwendet werden. 
* Welche Art von Leitsteuerung in diesem Projekt verwendet wird.
* Die IP-Adresse der Leitsteuerung.

**Die Auswahl eines Projektes hat eine gewisse *Sonderstellung*, da sie direkten Einfluss auf die vom OMSConfigService bereit gestellten Konfigurationsdaten für die OMS hat. Wie im Abschnitt [Funktionsprinzip](../working_principle/working_principle_main.md) beschrieben, ordnet der OMSConfigService die Konfiguration für ein OMS anhand dessen IP-Adresse zu. Es ist nun möglich, dass es ein OMS mit der IP x.x.x.x sowohl in Projekt A als auch in Projekt B gibt. Der OMSConfigService greift immer auf das aktuell eingestellte Projekt zurück! ** 

Streng genommen machen mehrere Projekte nur auf einem Inbetriebnahme-Laptop Sinn. Auf einem dauerhaft beim Kunden installierten OMSConfigService sollte **genau ein Projekt** angelegt und dieses **immer** ausgewählt sein.

### Projektauswahl

![Projektauswahl](./ProjectSel.png?raw=true "Projektauswahl-Menü")

Durch einen Klick auf das aktuell ausgewählte Projekt in der rechten oberen Ecke des GUI-Fenster öffnet sich das Projektauswahl-Menü. Ab dem zweiten Eintrag erscheinen die vorhandenen Projekte und können entsprechend aktiviert werden. Über den ersten Eintrag "Projekte verwalten" gelangt man auf die Seite zur Projektverwaltung, in welcher neue Projekte angelegt, existierende Projekte gelöscht und deren Daten verändert werden können.

### Projektverwaltungs-Seite

![Projektverwaltung](./projectmgmt.png?raw=true "Projektverwaltungs-Seite")

Durch die Eingabe eines neuen Projektnamens und anschließendem Klick auf "HINZUFÜGEN" wird ein neues Projekt angelegt. Für dieses und die existierenden Projekte können folgende Einstellungen vorgenommen werden:
* Typ der Leitsteuerung
  * Incubed
  * BeeLoCCore
  * Simulated (nur für Testzwecke)
* IP-Adresse und Port (default: 8888) der Leitsteuerung
  
  Die IP-Adresse wird von den OMS verwendet, um z.B. Aufträge und Fahrkurs-Sperren im FTS-System zu steuern (ohne Leitsteuerung ist mit einem OMS nichts anzufangen).

  Die IP-Adresse wird aber auch vom OMSConfigService verwendet, um in div. Listen (z.B. Ziele) vorhandene Namen bereit zu stellen um so die Eingabe zu vereinfachen und Fehler zu vermeiden.

* **Änderungen an den Projekteinstellungen müssen durch Klick auf das Disketten-Symbol gespeichert werden!**

* **Ein Projekt kann durch einen Klick auf das Papierkorb-Symbol gelöscht werden. Dies kann nicht rückgängig gemacht werden!**

Der Name der Projektdatei kann nicht verändert werden, sondern wird hier lediglich angezeigt.

 *Sie können sich den Dateinamen aus diesem Feld in die Zwischenablage kopieren, die Datei dann im Explorer lokalisieren und so vor größeren Änderungen eine Sicherungskopie anlegen.*  

