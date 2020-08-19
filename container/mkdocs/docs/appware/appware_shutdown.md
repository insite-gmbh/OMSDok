# Die AppWare des OMS
## Shutdown-Menü

![Shutdown-Menü](./ShutdownOptions.png?raw=true "Neustart-Optionen")]

### Konfiguration zurücksetzen

Verwirft alle gespeicherten Konfigurationsinformationen, die der Bootstrapper beim Start heranzieht (im Wesentlichen sind das die URLs für das Config- und das Update-WebAPI des OMSConfigService). Der Bootstrapper versucht daraufhin neue Konfigurationsinformationen über einen UDP-Broadcast von einem OMSConfigService zu bekommen. Solange läuft die AppWare mit der bestehenden Konfiguration weiter. Sobald der Bootstrapper neue Konfigurationsdaten ermittelt hat, übernimmt er diese und startet die AppWare neu.

### Update installieren
Forciert die Installation eines ggf. vorhandenen Updates der AppWare. Wenn ein Update bereit steht, beendet der Bootstrapper die AppWare, installiert das Update und startet die AppWare anschließend neu. Sollte keine Update bereit stehen, gibt die AppWare eine entsprechende Fehlermeldung aus.

### Herunterfahren
Startet das OMS neu.

