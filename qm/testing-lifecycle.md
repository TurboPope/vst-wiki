# Testen in Softwareentwicklungsmodellen
*Es gibt viele Ansätze Testen in den Entwicklungsprozess einzubauen, hier wird random das V-Modell zum tausendsten Mal erklärt.*

## V-Modell
![V-Modell, nicht völlig retardierte Version](/v-model.png)

Konstruktionsphasen:
1. **Anforderungsdefinition**: Sammlung von Anforderungen des Auftraggebers.
2. **Funktionaler Systementwurf**: Anforderungen auf Funktionen des neuen Systems abbilden.
3. **Technischer Systementwurf**: Entwurf der technischen Realisierung des Systems
  * Definition der Schnittstellen zur Systemumwelt
  * Zerlegung des Systems in Teilsysteme, unabhängig voneinander entwickelbar
4. **Komponentenspezifikation**: Definition von Aufgabe, Verhalten, innerer Aufbau und Schnittstelle für jedes Teilsystem
5. **Programmierung**: Jedes spezifizierten Bausteins in einer Programmiersprache

Testphasen:
6. **Komponententest**: Erfüllt einzelner Softwarebaustein für sich die Vorgaben seiner Spezifikation?
7. **Integrationstest**: Zusammenspiel von Gruppen von Komponenten wie im technischen Systementwurf vorgesehen?
8. **Systemtest**: Erfüllt System als Ganzes die spezifizierten Anforderungen?
9. **Abnahmetest**: Aufweisung der vertraglich vereinbarten Leistungsmerkmale vom System aus Kundensicht?

## Iterativ-inkrementelle Entwicklungsmodelle
Mit jedem **Inkrement** werden für die neuen Funktionalitäten neue Tests eingeführt. Alte Tests werden beibehalten und weiter als **Regressionstests** ausgeführt. Bekannte Modelle:

* RAD
* RUP
* Agile Entwicklungsmodelle:
  * XP
  * SCRUM
  * DSDM


# Teststufen

## Komponenten-Test
*Bezieht sich auf die Stufen 4 (Komponentenspezifikation) und 6 (Komponententest) aus dem obigen V-Modell.*

Erstellte Softwarebausteine vor (Test Driven Development) oder nach der Programmierphase einem systematischen Test unterziehen.

## Integration-Test
*Bezieht sich auf die Stufen 3 (Technischer Systementwurf) und 7 (Integrationstest) aus dem obigen V-Modell.*

Verbindet Komponenten und testet deren Zusammenspiel. Findet Fehlerwirkungen in den Wechselwirkungen mehrerer Komponenten. Noch nicht implementierte Komponenten sollen simuliert werden. Es wird zwischen 4 **inkrementellen Integrationsstrategien** unterschieden:

* **Top-Down**: Test beginnt (rekursiv) mit der Komponente des Systems, die weitere Komponenten aufruft
* **Bottom-Up**:  Beginn mit elementaren Komponenten des Systems, sukzessive (rekursive) Zusammensetzung
* **Ad-Hox**: Integration der Bausteine in der Reihenfolge ihrer Fertigstellung
* **Big-Bang**: Nachdem alle Softwarebauteile entwickelt und getestet sind, wird alles auf einmal zusammengeworfen

## System-Test
*Bezieht sich auf die Stufen 2 (Funktionaler Systementwurf) und 8 (Systemtest) aus dem obigen V-Modell.*

Überprüft die Erfüllung der spezifizierten Anforderungen vom Produkt. Es wird das gesamte System in einer dem Produktivsystem nahe kommenden Umgebung getestet.

## Abnahme-Test
*Bezieht sich auf die Stufen 1 (Anforderungsdefinition) und 9 (Abnahmetest) aus dem obigen V-Modell.*

Spezielle form des System-Tests durch den Kunden auf dem Produktivsystem.


# Test neuer Produktversionen
Während dem Einsatz der Software müssen oft noch Anpassungen oder Konfigurationsänderungen vorgenommen werden. In diesen Fällen müssen erneut **Regressionstests** ausgeführt werden.
