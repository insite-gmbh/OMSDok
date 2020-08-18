# Funktionsprinzip
## Funktionsprinzip der OMS AppWare

Die OMS AppWare stellt ein web-basiertes GUI bereit, für das folgende Funktionen mit der OMS Konfigurations-Oberfläche des OMSConfigServers konfiguriert werden kann:

* Transport-Auftragsgenerierung
     
  * Generierung von Abtransporten von Ziel A nach Ziel B
  * Generierung von Antransporten von Ziel C nach Ziel D
  * Definieren von Hardware-Eingängen zum Anstoß von Transporten
  * Definieren von Softkeys zum Anstoß von Transporten
  * Definieren von Hardware-Ausgängen zur Darstellung von Transport-Auftrags-Status 

* Fahrkurs-Sperren

  * Definieren von Hardware-Eingängen, die zur Sperrung bestimmter Bereiche des Fahrkurses führen. Z.B. für Brandschutztore.

* Feueralarm

  * Definieren eines Hardware-Eingangs, der ein Feueralarm-Signal bereitstellt. 

Damit die AppWare die entsprechenden Funktionen ("Generiere Auftrag", "Sperre Bereich A") auslösen kann, muss sie mit einer FTS-Leitsteuerung verbunden sein. Im Moment werden 3 unterschiedliche Leitsteuerungen unterstützt:

* Incubed
  * Leitsteuerung/FMS der Firma incubed
* BeeLoCCore
  * Leitsteuerung der Firma BeeWaTec
* Simulated
  * Simulationsumgebung der Firma BeeWaTec, nicht für produktive Anwendung.

Außer der Simulationsumgebung brauchen muss für alle Leitsteuerung eine IP-Adresse und Portnummer bekannt sein, unter der das jeweilige API der Leitsteuerung erreicht werden kann.

## Verbindung des OMSConfigServers zur Leitsteuerung

Der OMSConfigService versucht ebenfalls eine Verbindung zu einer Leitsteuerung aufzubauen. Damit können in der Konfigurations-Oberfläche diverse Listen automatisch ausgefüllt werden. Z.B. kann bei der Vergabe von Zielen oder Sperrbereichen auf eine Liste zurückgegriffen werden, die von der Leitsteuerung abgefragt wurde und damit garantiert, dass keine unbekannten Ziele oder Sperrbereiche verwendet werden.

## Übersicht

![Datenaustausch mit der Leitsteuerung](./OMSandCS.png?raw=true "Datenaustausch mit der FTS-Leitsteuerung")

## [Konfiguration](../configuration/configuration_main.md)
