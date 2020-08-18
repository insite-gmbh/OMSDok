# Funktionsprinzip

## Download der "AppWare"

Die Applikation, die auf einem OMS ausgeführt wird, und die dazugehörige Konfiguration bezeichnen wir als "AppWare". 

Das OMS verfügt nach der Basisinstallation ab Werk lediglich über einen "Bootstrapper", welcher die AppWare von dem OMSConfigService bezieht. Der OMSConfigService ist in der Regel auf einem Konfigurations-Server im Produktions-Netzwerk oder einem (normalerweise nur temporär verbundenen) Inbetriebnahme-Laptop installiert.  

Der Download der AppWare erfolgt über HTTP, in der Regel über die im OMS eingebaute WLAN-Netzwerkkarte oder alternativ über Kabel. Um den OMSConfigService im Netzwerk zu finden, kann der Bootstrapper ein UDP-Broadcast auslösen, der vom OMSConfigService entsprechend beantwortet wird.

![Verbindung zum OMSConfigService](./OMSOverview.png?raw=true "Verbindung zu einem Server mit OMSConfigService")


Updates der AppWare werden ebenfalls von den OMS vom OMSConfigService heruntergeladen.

## OMS-Konfiguration
Ein entscheidender Teil der AppWare ist die geräte-spezifische Konfiguration des OMS. Der OMSConfigService führt dazu eine Liste mit IP-Adressen der zum Einsatz kommenden OMS und ordnet anhand dieser Liste die individuellen Konfigurationsdaten dem jeweiligen OMS zu.

Details hierzu finden sich in 
[Konfiguration des OMS](../configuration/configuration_main.md)
.

Neben den Hardware-Eigenschaften (Anzahl E/A etc.) und beispielsweise der Zuordnung von FTS-Aufträgen zu GUI-Buttons wird in der Konfiguration die URLs des **Konfigurations-WebAPIs** und des **Update-WebAPIs** festgelegt.

Diese sind bei einem neu installierten OMS nicht bekannt oder können sich während des Laufzeit des Projektes auch einmal ändern.

## Bootstrapping
Beim allerersten Start hat das OMS noch keine Konfiguration und kennt daher die IP-Adresse des Konfigurationsservers noch nicht. Weiterhin kann es nach Netzwerkänderungen dazu kommen, dass die bisher verwendete IP-Adresse nicht mehr gültig ist. In diesen Fällen versucht der Bootstrapper den OMSConfigService durch einen UDP-Broadcast im Netzwerk zu finden. 

Bei einem Neustart des OMS führt der Bootstrapper die folgenden Schritte durch:

![Bootstrapping der AppWare](./BootstrapperFlow3.png?raw=true "OMS Bootstrapping der AppWare")


Der Bootstrapper bleibt auch nach dem "initialen" Download der AppWare aktiv. Damit sind nach einem Neustart des OMS jederzeit Updates der AppWare möglich. 

### Probleme durch den Broadcast
Theoretisch kann es passieren, dass mehr als ein OMSConfigService im Netzwerk aktiv ist. Der Bootstrapper verwendet die Daten, welche derjenige Service zurückliefert, der zuerst auf den UDP-Broadcast antwortet. Theoretisch kann das zu einer Fehlkonfiguration des OMS führen. 

**Achten Sie daher darauf, dass nur *ein* OMSConfigService im Netzwerk aktiv ist und dass der aktive Service die richtigen Konfigurationsdaten für das OMS bereit hält.**

## Mehrere OMS im Netzwerk
Jedes OMS ist eindeutig durch seine IP-Adresse identifizierbar. Die Konfiguration wird - wie oben bereits erwähnt - dieser IP-Adresse im OMSConfigService zugeordnet. Bei größeren Anlagen empfiehlt es sich, den OMSConfigService auf einem dauerhaft verfügbaren Server zu installieren, sodass Änderungen an der AppWare an zentraler Stelle vorgenommen werden können. Durch einen Restart des OMS bzw. dem Auslösen der Funktion "Update installieren" über dessen GUI, können die OMS schnell und einfach aktualisiert werden.

## [Funktionsprinzip der OMS AppWare](./working_principle_appware.md)

