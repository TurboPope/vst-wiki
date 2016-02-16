Softwaremetriken dienen als Indikator von Softwarequalität und für Priorisierung der QS-Aktivitäten. Fehleranfälligkeit korreliert mit **Komplexität**, also soll Komplexität mit Metriken erfasst werden.


# Zyklomatische Komplexität

Gibt an, wie viele *unabhängige* Pfade (duplizierte Pfade ignorieren) in einem Kontrollflussgraphen existieren. Wird berechnet durch **McCabe-Formel**:

```
c = edges - vertices + 1
```

* `c` Zyklomatische Komplexität
* `edges` Die Anzahl der Kanten im Kontrollflussgraph
* `vertices` Die Anzahl der Knoten im Kontrollflussgraph

Bei mehreren Endpunkten wird die Formel um die Anzahl der Endpunkte `p` wie folgt erweitert:

```
c = edges - vertices + p + 1
```

Äquivalent: Alle Verzeigungen zählen und 1 addieren. Switch-cases zählen auch jeweils als 1, aber pro Switch wird 1 abgezogen.

Nach McCabe ist eine zyklomatische Komplexität größer als 10 nicht tolerabel.


# CK (Objektorientierte Metriken-Suite)

CK ist eine objektorientierte Metriken-Suite, vorgeschlagen von **Chidamber & Kemerer**.

* **Weighted Method Complexity** (WMC): Summe der Komplexitäten der Methoden einer Klasse
* **Depth of Inheritance Tree** (DIT): Anzahl der Superklassen
* **Number of Children** (NOC): Anzahl der Subklassen
* **Kopplung von Klassen** (CBO): Anzahl der Methoden und Variablen, die eine Klasse von einer anderen Klasse nutzt
* **Reaktion einer Klasse** (RFC): *wat*
* **Lack of Cohesion of Methods** (LCOM): *wat*
