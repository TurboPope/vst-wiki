# Einführung
Statische Analyse beruht nicht auf ausführung des Programms. Es gibt viele Wege Code statisch zu analysieren:

* Compiler
* Quellcode-Überprüfer (*Linter?*)
* Überprüfung von Richtlinien (bei Modellen)
* Metriken wie Lines of Code und Zyklomatische Zahl
* Kontrollfluss-Analyse
* Datenfluss-Analyse

Ziel ist es, Anomalien zu finden. Diese können, müssen aber keine Fehler sein.


# Kontrollfluss-Analyse
* Manuelle oder automatische Prüfung des Kontrollflussgraphen auf Verständlichkeit und Anomalien
* Suche von Vorgänger- und Nachfolgerlosen Anweisungen in Vorgänger-Nachfolger-Tabelle


# Datenfluss-Analyse
* **ur-Anomalie** (undefined-read) Referenzieren einer nicht-initialisierten Variablen
* **du-Anomalie** (define-undefine) Nicht-Verwendung einer Variable
* **dd-Anomalie** (define-define) Überschreiben des Wertes einer Variablen ohne sie vorher zu referenzieren

Manuelle Analyse kann hier bei komplexeren Programmen sehr schwierig sein.


# Symbolische Ausführung
Statt mit konkreten Werten zu testen, werden "symbolische Werte" (wie Variablen in der Mathematik) zur Ausführung benutzt.

> In computer science, symbolic execution (also symbolic evaluation) is a means of analyzing a program to determine what inputs cause each part of a program to execute. An interpreter follows the program, assuming symbolic values for inputs rather than obtaining actual inputs as normal execution of the program would, a case of abstract interpretation. It thus arrives at expressions in terms of those symbols for expressions and variables in the program, and constraints in terms of those symbols for the possible outcomes of each conditional branch. (*Quelle: [Symbolic execution bei Wikipedia](https://en.wikipedia.org/wiki/Symbolic_execution). Enthält auch ein gutes Beispiel.*)
