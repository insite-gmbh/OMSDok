# Die AppWare des OMS
## Auftragserzeugung und -überwachung

Nachdem ein Auftrag durch Drücken eines Soft Keys angestoßen wurde, wird dessen Status durch verschiedene Farben und Symbole auf dem Soft Key angezeigt:

![Auftrag eingereiht](./OrderSoftKeys8Queued.png?raw=true "Auftrag zur Bearbeitung eingereiht")

Diese Darstellung und der rechts unten auspoppende Text zeigen, dass "Auftrag 1" zur Bearbeitung an die FTS-Leitsteuerung übergeben wurde (Status "queued" - "eingereiht").

![Disponierter Auftrag](./OrderSoftKeys8Dispatched.png?raw=true "Auftrag wurde an Fahrzeug disponiert")

Ein grüner Soft Key zeigt an, dass der Auftrag einem Fahrzeug zugeteilt wurde (Status "dispathed" - disponiert).

**Wenn es zu keinem Fehler kommt, wird die Statusanzeige nach einer gewissen Zeit wieder blau (= fertig) und der Benutzer kann den selben Transportauftrag erneut auslösen. Wann der Auftrag in "fertig"-Status wechselt, hängt von dem Transporttyp des Auftrags ab:**

* Transporttyp **Abtransport**: Auftrag wird fertig gemeldet, nachdem die Last **geholt** wurde.
* Transporttyp **Antransport**: Auftrag wird fertig gemeldet, nachdem die Last **gebracht** wurde.

![Fertiger Auftrag](./OrderSoftKeys8New.png?raw=true "Auftrag wurde fertig gestellt und kann neu ausgelöst werden.")

## Verzögerungen bei der Bearbeitung
Manchmal werden Fahrzeuge an der reibungslosen Bearbeitung von Aufträgen gehindert (z.B. durch Störungen im Verkehr) und es kommt zu Verzögerungen. In diesem Fall wird der Soft Key gelb hinterlegt:

![Auftrag verzögert](./OrderSoftKeys8Delayed.png?raw=true "Auftragsbearbeitung verzögert.")


## Navigation
## [Zurück zur Hauptseite der AppWare](./appware_main.md)
## [Zurück zur Hauptseite](../README.md)