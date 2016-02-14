# Whitebox Testing
Testverfahren basiert auf Analyse interner Struktur des Testobjekts.


# Kontrollflusbasiertes Testen
Ein **Kontrollflussgraph** veranschaulicht den Kontrollfluss eines Programms:
* **Knoten**: Block von Anweisungen im Programm
* **Block**: Sequenzielle Anweisungsfolge
* **Kante**: Möglicher Kontrollfluss
* **nstart** und **nfinal**: Anfangs- und Endanweisung eines Programms

* **Pfad**: Folge von Knoten und Kanten, die mit Startknoten beginnt und Endknoten endet.
* **Wege(P, T)** von Programm `P` mit Testfallmenge `T`: Menge der möglichen Pfade.

Testfallauswahl orientiert sich an Kontrollfluss des Programms. Vorgehen:
1. Festlegen, welche Pfade ausgeführt werden sollen
2. Ableiten, mit welchen Eingaben diese Pfade erzeugt werden können


# Anweisungsüberdeckung (C<sub>0</sub>)
Alle Knoten werden mindestens ein Mal besucht. Testwirksamkeit: Verhältnis Anzahl besuchter Knoten zu Anzahl aller Knoten.


# Zweigüberdeckung (C<sub>1</sub>)
Alle Kanten werden mindestens ein Mal besucht. Testwirksamkeit: Verhältnis Anzahl besuchter Kanten zu Anzahl aller Kanten.


# Grenze-Inneres Überdeckung
Jede Schleife muss genau einmal und mehr als einmal ausgeführt werden. `while`- und `for`-Schleifen müssen zusätzlich einmal nicht ausgeführt werden. Testwirksamkeit: Verhältnis Anzahl getesteter Schleifen zu Anzahl Schleifen.


# Pfadüberdeckung (C<sub>∞</sub>)
jeder Pfad muss mindestens ein Mal ausgeführt werden. Testwirksamkeit: Verhältnis Anzahl durchlaufener Pfade zu Anzahl Pfade.
