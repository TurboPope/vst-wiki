# Einführung
> Ein Geschäftsprozess ist eine Menge logisch verknüpfter Einzeltätigkeiten (Aufgaben, Aktivitäten), die ausgeführt werden, um ein bestimmtes geschäftliches oder betriebliches Ziel zu erreichen. (*Quelle:* [Wikipedia](https://de.wikipedia.org/wiki/Gesch%C3%A4ftsprozess))

Es sollen Geschäftsprozesse modelliert werden. Die Notation soll domänenspezifisch sein und die Kommunikationslücke zwischen Fachabteilung und Softwareentwicklern überbrücken. Des weiteren soll sie die Automatisierung von Geschäftsprozessen unterstützen.

# EPK Notation
*[Wikipedia](https://de.wikipedia.org/wiki/Ereignisgesteuerte_Prozesskette#Symbole_und_Syntaxregeln) fasst das ganz nett zusammen:*

> Die **Ereignisgesteuerte Prozesskette** (EPK) ist eine grafische Modellierungssprache zur Darstellung von Geschäftsprozessen.

![Einfache EPK](/epk.png)

Topologisch sind Prozessketten gerichtete Graphen ohne Schleife. Die Knoten sind Entitäten einer Organisation, Methoden eines Prozesses oder Hilfsknoten der Strukturierung. Die Kanten sind Informationsflüsse. Feedback oder Iterationen werden in diesem Ablauf nicht visualisiert. Die Prozesse der Kette münden in einem gemeinsamen Geschäftsziel.

* Ein **Ereignis** ist ein Zustand, der vor oder nach einer Funktion auftritt. Das Symbol für ein Ereignis ist sechseckig. Im obigen Beispiel: "Auftrag ist angenommen".
* Eine **Funktion** (Prozess) ist eine Aktion oder Aufgabe, die auf ein Ereignis folgt. Funktionen werden durch Rechtecke mit abgerundeten Ecken symbolisiert. Im obigen Beispiel: "Auftrag prüfen".
* **Konnektoren** dienen zum Aufspalten oder Vereinigen des Kontrollflusses. Es stehen die drei Konnektoren UND, ODER und XOR zur Verfügung, die jeweils in einem kleinen Kreis mit dem entsprechenden Symbol dargestellt werden.
* **Prozesswegweiser** sind Hinweise auf andere Prozesse. Sie werden durch ein Rechteck symbolisiert, hinter dem sich ein Sechseck verbirgt.
* **Informationsobjekte** stellen Dokumente oder sonstige Datenspeicher dar. Das Symbol für ein Informationsobjekt ist ein Rechteck. Beispiel: "Kundendatenbank"
* **Organisationseinheiten** (Symbol: Ellipse, die vor dem linken Rand eine senkrechte Linie enthält) symbolisieren Rollen oder Personen, die für den Prozess verantwortlich sind. Organisationseinheiten werden per durchgehender Linie mit Funktionen verbunden. Beispiele für Organisationseinheiten sind "Kunde" oder "Marketingabteilung".

Hierbei sind Organisationseinheiten und Informationsobjekte Symbole der erweiterten Ereignisgesteuerten Prozessketten (eEPK). Der Informationsfluss zwischen den einzelnen Symbolen wird durch Pfeile dargestellt. Funktionen und Ereignisse besitzen genau einen eingehenden und einen ausgehenden Pfeil (Ausnahmen: Bei Anfangsereignissen geht keine gerichtete Kante ein, bei Endereignissen geht kein Pfeil hinaus). Falls mehrere Ereignisse zu einer Funktion führen sollen, so müssen Konnektoren (zum Beispiel UND) vorgeschaltet werden.

Aufgrund der Denkweise, dass Ereignisse passiv und Funktionen aktiv sind, gilt: Ein Ereignis darf nicht über einen OR- oder einen XOR-Konnektor zu zwei Funktionen aufgespaltet werden, da ein Ereignis über keine Entscheidungsgewalt verfügt.


# EPK Werkzeuge
* ARIS (Architektur integrierter Informationssysteme) *ist eigentlich kein Tool aber wir tun so* ([Wikipedia](https://de.wikipedia.org/wiki/ARIS))
* **ADONIS** is a Business Process Analysis (BPA) tool supporting business process management [...]. It allows business process modeling using **BPMS** notation and [BPMN 2.0](https://en.wikipedia.org/wiki/Business_Process_Model_and_Notation), process analysis, simulation, evaluation as well as publishing and process automation with BPMN 2.0 XML (BPMN DI) and XPDL.
