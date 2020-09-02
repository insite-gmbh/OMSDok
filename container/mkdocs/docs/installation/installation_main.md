# Installation des OMS auf dem Zielsystem
Das OMS wird ab Werk mit vorinstallierter Software ausgeliefert. Diese beinhaltet das Betriebsystem, einen Bootstrapper und ggf. einen aktuellen Stand der AppWare.  Nach dem Hochlauf des Systems erkennt der automatisch gestartete Bootstrapper, ob eine AppWare installiert ist. Sollte das nicht der Fall sein, kann der Bootstrapper des OMS die AppWare von einem im Netzwerk erreichbaren OMSConfigService herunterladen. Hierzu ist jedoch eine funktionierende Netzwerk-Verbindung notwendig. Die Einrichtung der Netzwerkumgebung ist daher die einzige manuelle Konfiguration, die durchgeführt werden muss, sofern das OMS nicht bereits ab Werk korrekt konfiguriert wurde.

## Voraussetzung zur Einrichtung der Netzwerkumgebung


1. **Sie benötigen zwingend eine USB-Tastatur!**  
   Sie müssen das Gehäuse des OMS öffnen und die Tastatur an einen der freien USB-Anschlüsse des Touchscreen-Computers anstecken, so wie auf dem Bild (schwarzes USB-Kabel) zu sehen.  
   ![OMS](./OpenOMSKeybAttached.jpg?raw=true "Geöffnetes OMS mit angeschlossener USB-Tastatur")

2. **Sie müssen das Superuser-Passwort des Computers kennen!**  
   Die Netzwerk-Einstellungen, die Sie anpassen müssen, können nur vom Superuser verändert werden. Falls das Superuser-Passwort nicht im Inneren des OMS auf einer Etikette o.ä. vermerkt ist, wenden Sie sich bitte an BeeWaTec.

#### [Netzwerk konfigurieren](./installation_raspinwsetup.md)




