# Einführung
Dass ein Fehler auftritt muss nicht an falschen Anweisungen liegen, sondern kann auch von vorher falsch berechneten, referenzierten Werten hervorgerufen werden.

Idee: Testen der Interaktion zwischen Anweisungen, die Wert einer Variablen berechnen (definieren), und Anweisungen, die diesen Variablenwert benutzen (referenzieren).

Ein **Datenflussgraph** ist ein Kontrollflussgraph, bei dem jeder Knoten drei zusätzliche Mengen speichert:
* **DEF**: Menge der Variablen, die im Knoten definiert werden
* **UNDEF**: Menge der Variablen, die im Knoten undefiniert werden
* **REF**: Menge der Variablen, die im Knoten referenziert werden

# Alle Definitionen
Jede Variable die definiert wird, wird auch einmal referenziert.


# Alle DR-Interaktionen
Ein **DR-Weg** (Definition-Referenz-Weg) ist ein Weg, an dessen Anfang eine Variable definiert und an dessen Ende diese variable referenziert wird. Das Kriterium **Alle DR-Interaktionen** fordert, dass ein solcher Weg für jede Variable existiert, die definiert wird. Es fordert also in Erweiterung zu Alle Definitionen, dass die Referenz nicht nur existiert, sondern auch erreicht wird (für die Testfallmenge).


# Alle Referenzen
Eine Erweiterung von [Alle DR-Interaktionen](#alle-dr-interaktionen). Immer wenn von einem `REF`-Knoten mehrere Kanten ausgehen, müssen diese alle mit in den Testfluss dazugenommen werden.


# Kontextüberdeckung
*pls halp*


# Alle DR-Wege
*durr*


# Alle Berechnungs-/Entscheidungs-Referenzen
Unterscheidung, ob eine Referenz in einer Berechnung oder in einer Entscheidung stattfindet.
