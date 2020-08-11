# Funktionsprinzip
## Download der "AppWare"

Die Applikation, die auf einem OMS ausgeführt wird, und die dazugehörige Konfiguration bezeichnen wir als "AppWare". 

Das OMS verfügt nach der Basisinstallation lediglich über einen "Bootstrapper", welcher die AppWare von dem OMSConfigService bezieht. Der OMSConfigService ist in der Regel auf einem Konfigurations-Server im Produktions-Netzwerk oder einem (normalerweise nur temporär verbundenen) Inbetriebnahme-Laptop installiert.  

Der Download der AppWare erfolgt über HTTP, in der Regel über die im OMS eingebaute WLAN-Netzwerkkarte oder alternativ über Kabel.


Updates der AppWare werden ebenfalls von den OMS vom OMSConfigService heruntergeladen.

## OMS-Konfiguration
Ein entscheidender Teil der AppWare ist die geräte-spezifische Konfiguration des OMS. Der OMSConfigService führt dazu eine Liste mit IP-Adressen der zum Einsatz kommenden OMS und ordnet anhand dieser Liste die individuellen Konfigurationsdaten dem jeweiligen OMS zu.

Details hierzu finden sich in 
[Konfiguration des OMS](../configuration/configuration_main.md)
.

Neben den Hardware-Eigenschaften (Anzahl E/A etc.) und beispielsweise der Zuordnung von FTS-Aufträgen zu GUI-Buttons wird in der Konfiguration die 

  **IP-Adresse des Konfigurationsservers**

festgelegt.

Diese ist bei einem neu installierten OMS nicht bekannt oder kann sich während des Laufzeit des Projektes auch einmal ändern.

## Bootstrapping
Beim allerersten Start hat das OMS noch keine Konfiguration und kennt daher die IP-Adresse des Konfigurationsservers noch nicht. Weiterhin kann es nach einer Umstellung der IP-Adressen dazu kommen, dass die bisher verwendete IP-Adresse nicht mehr gültig ist. In diesen Fällen versucht der Bootstrapper den OMSConfigService durch einen UDP-Broadcast im Netzwerk zu finden. 

Bei einem Neustart des OMS führt der Bootstrapper die folgenden Schritte durch:

![Bootstrapping der AppWare](./BootstrapperFlow.png?raw=true "OMS Bootstrapping der AppWare")


Der Bootstrapper bleibt auch nach dem "initialen" Download der AppWare aktiv. Damit sind nach einem Neustart des OMS jederzeit Updates der AppWare möglich. 


![Bootstrapping der AppWare](./OMSOverview.png?raw=true "OMS Bootstrapping der AppWare")




## [Abschnitt 1](./working_principle_ch1.md)
## Navigation
## [Zurück zur Hauptseite](../README.md)