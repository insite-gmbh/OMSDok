# Netzwerk konfigurieren

Die Netzwerk-Konfiguration besteht aus 2 Teilen:  

1. Verbindung mit dem WLAN herstellen (Einstellen der SSID, Security-Verfahren und Passwort).  
2. Einstellen einer statischen IP-Adresse im WLAN.

*Das OMS ist für WLAN-Betrieb vorgesehen, lässt sich prinzipiell aber natürlich auch an einem kabelgebundenen LAN verwenden. In diesem Fall entfällt der 1. Schritt und die statische IP-Adresse muss für die (kabelgebundene) Netzwerkkarte eingestellt werden.*

## Beenden der Oberfläche der AppWare
Nach dem Hochlauf startet die AppWare automatisch im Vollbild-Modus und überdeckt so die Betriebssystem-Oberfläche. Das ist so gewünscht - das unterliegende Betriebssystem soll dem Endanwender verborgen bleiben. Um die AppWare zu beenden, müssen Sie auf der angeschlossenen Tastatur die Tastenkombination  

    Alt + F4 

drücken. Das Fenster der AppWare schließt sich und Sie können auf die GUI des Raspbian-Betriebssystems zugreifen. 


## Öffnen eines Terminals

Die Einstellungen werden in einem Terminalfenster vorgenommen. Dieses öffnen Sie über das Terminal ("LX-Terminal") am oberen Fensterrand.

![Terminal](./1 Terminal.png?raw=true "Terminal öffnen")

*Das sog. Prompt (hier "pi@futaraspi:~ $") kann bei Ihrem System abweichen.*

## WLAN konfigurieren 

Um das WLAN zu konfigurieren, starten Sie das Raspberry-Konfigurationsprogramms "raspi-config".

Geben Sie nach dem Prompt folgenden Befehl ein:

    sudo raspi-config

![raspi-config](./2 RaspiConfig.png?raw=true "Raspberry Konfiguration starten")

Das Proramm heißt eigentlich nur "raspi-config". Mit dem vorangestellten Befehl "sudo" sagen Sie dem System, dass Sie dieses Programm als Superuser ausführen möchten. Entsprechend fragt Sie das System anschließend nach dem Superuser-Passwort. Wenn Sie dieses richtig eingegeben haben, erscheint die text-basierte Oberfläche des Konfigurationsprogrammes.

![raspi-config-main](./3 RaspiConfig.png?raw=true "Raspberry Konfiguration Hauptmenü")

Bewegen Sie die Markierung wie gezeigt auf den Punkt "Network Options" und drücken Sie die Eingabe-Taste (Select).

![raspi-config-wifi](./4 RaspiConfig.png?raw=true "Raspberry Konfiguration WiFi")

Hier wählen Sie "N2 Wi-fi" und Sie gelangen in die erste Eingabe-Maske für die SSID des WLANs.

![raspi-config-ssid](./5 RaspiConfig.png?raw=true "Raspberry Konfiguration SSID")

Geben Sie hier die SSID des WLANs ein und drücken Sie die Eingabe-Taste (OK). Danach werden Sie aufgefordert, das WLAN-Passwort bzw. die "Passphrase" einzugeben:

![raspi-config-wlanpwd](./6 RaspiConfig.png?raw=true "Raspberry Konfiguration WLAN Passwort")

Geben Sie das Passwort ein und drücken Sie die Eingabe-Taste (OK). 

Beenden Sie das Raspberry Konfigurationsprogramm und Sie landen wieder im Prompt des Terminals. Lassen Sie dieses geöffnet, Sie brauchen es gleich wieder.

**Damit ist die WLAN-Konfiguration abgeschlossen.**

## IP-Adresse einstellen

Da sich das OMS gegenüber dem OMSConfigService mit seiner IP-Adresse identifiziert, muss das OMS eine eindeutige (statische) IP-Adresse haben. 

*(Wenn Sie das OMS in einem Netzwerk mit DHCP-Server betreiben und gemeinsam mit der IT-Abteilung des Endkunden sicherstellen können, dass jedes OMS immer die gleiche IP-Adresse zugeteilt bekommt, können Sie diesen Schritt auch überspringen.)*

### Name der Netzwerk-Schnittstelle ermitteln

Um die Konfiguration der Netzwerk-Schnittstelle vorzunehmen, muss deren Name ermittelt werden. Dieser wird in Folge benötigt. 

Geben Sie dazu den Befehl

    ifconfig | less

im Terminal ein und drücken Sie die Eingabetaste. 

![ifconfig-wlanpwd](./7 ifconfig interface name.png?raw=true "ifconfig um den Schnittstellen-Namen zu finden")

Das "Pipe"-Symbol (senkrechter Strich) bewirkt, dass die Ausgabe des Programmes "ifconfig" an das Programm "less" übergeben wird. "less" unterteilt die meist umfangreiche Ausgabe von ifconfig in mehrere Bildschirmseiten, die Sie durch einen Druck auf die Eingabetaste weiterschalten können.

![ifconfig-locenxb](./8 ifconfig enxb.png?raw=true "Schnittstellen-Name finden")

Auf der obigen Seite finden Sie den Namen der kabelgebundenen Netzwerkkarte. Er beginnt mit "en" ... wenn Sie dann Eingabe drücken, kommen Sie zur letzten Seite der Ausgabe von ipconfig:

![ifconfig-locwlan](./9 ifconfig wlan0.png?raw=true "Schnittstellen-Name der WLAN-Karte finden")

Der Name der Netzwerkschnittstelle ist in diesem Fall (und wahrscheinlich in Ihrem Fall auch) "wlan0".

### Einstellungen der Netzwerk-Schnittstelle anpassen

Nun müssen wir in einer Konfigurationsdatei eine Änderung vornehmen. Die Datei heißt "/etc/dhcpcd.conf" und wir verwenden den "nano"-Editor. Da die Datei nur als Superuser bearbeitet werden kann, müssen wir nano im Superuser-Modus starten. Der vollständige Befehl lautet also:

    sudo nano /etc/dhcpcd.conf

![nano-dhcpcd](./10 nano etc_dhcpcd.conf.png?raw=true "Nano mit Konfigurationsdatei öffnen")

Nano zeigt nun die besagte Konfigurations-Datei an:

![nano-dhcpcd](./11 oben dhcpcd.conf.png?raw=true "Nano mit geöffneter Konfigurationsdatei")

Blättern Sie mit den Pfeiltasten ganz nach unten und geben Sie für die jeweilige Netzwerkkarte die entsprechenden Konfigurationswerte vor. 

**Sie müssen das nur für die Schnittstelle "en..." oder die Schnittstelle "wlan0" machen, je nach dem, ob Sie WLAN oder kabelgebundenes LAN verwenden.**

Für wlan0 geben Sie ein:

    interface wlan0
    static ip_address=x.x.x.x
    static routers=y.y.y.y
    static domain_name_servers=z.z.z.z


x.x.x.x ist die statische IP-Adresse des OMS, die Sie vergeben müssen.
y.y.y.y ist die Router-/Gateway-Adresse, sofern es im Netzwerk einen gibt.
z.z.z.z ist die Adresse eines DNS-Servers.

Die letzte Einstellung ist wenig relevant, da das OMS keine Zugriffe auf Rechner über einen Hostnamen tätigt. Auch der Router/Gateway ist in der Regel irrelevant, wenn sich die Leitsteuerung und der OMSConfigService im gleichen Netzwerksegment befinden, wie das OMS.

Hier ein Beispiel für eine identisch Konfiguration beider Netzwerk-Karten:

![nano-dhcpcd](./12 setup dhcpcd.conf.png?raw=true "Neue Konfigurationswerte")

Überprüfen Sie die Änderungen auf Schreibfehler und speichern Sie dann mit "Strg+O" die geänderte Datei. Danach beenden Sie nano mit "Strg+X". Beide Befehle sehen Sie auch unten in der Menüleiste des Editors.

Um die Änderungen wirksam werden zu lassen, müssen Sie das System neu starten. Dazu geben Sie ein

    sudo reboot

![nano-dhcpcd](./13 sudo reboot.png?raw=true "Neustart des Systems")


Nach dem Neustart sollten Sie Verbindung zum WLAN haben und in der Lage sein, andere Rechner im Netzwerk "anzupingen". Auch das können Sie über das Terminal mit dem Befehl "ping" überprüfen:

    ping a.b.c.d

a.b.c.d ist die bekannte IP-Adresse eines Rechners im Netzwerk.

**Damit ist die Netzwerk-Konfiguration abgeschlossen.**





























