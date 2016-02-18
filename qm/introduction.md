# Motivation
Es ist aufgrund des Umfangs nicht sinnvoll jede mögliche Kombination von Eingaben für ein Programm oder eine Funktion zu testen. Zum realistischen Testen benötigen wir ein hohes Maß an Automatisierung und intelligente Werkzeugunterstützung.


# Definitionen

* **Validierung**: ob das System seinen Sinn erfüllt (richtigers System)
* **Verifizierung**: ob das System seine Anforderungen erfüllt (richtige Realisierung)

* **Fehler**: Abweichen von Ist- und Soll-Verhalten des Systems oder grobe nicht-Erfüllung einer Anforderung
* **Mangel**: Unvollständige Erfüllung einer Erwartung oder Anforderung

Eine **Fehlerhandlung (error)** einer Person führt zu einem **Fehlerzustand (fault)**, die eine **Fehlerwirkung (failure)** verursachen kann.

Beispiel:

* *Fehlerhandlung*: Jan vergisst, «secrecy» in seine Secure Dependencies zu schreiben
* *Fehlerzustand*: UMLSec greift nicht und die Daten sind nicht geschützt
* *Fehlerwirkung*: Der Standardangreifer kommt und hört sensible Daten ab


# Qualitätslenkung
Konstruktives QM duch Normen, Standarts, Projektleitung, Software-technik, Erfahrungsaustausch, Ausbildungsmaßnahmen und cetera.

## ISO 900x
**ISO 9000** ("Qualitätsmanagementsysteme - Grundlagen und Begriffe") erläutert prozessorient Grundlagen für Qualitätsmanagementsysteme und in Normenreihe ISO 900x verwendete Begriffe.

Eine **ISO 9001**-Zertifizierung bestätigt die Konformität des **Unternehmens-Qualitätshandbuchs** eines Unternehmens. Ein solches Zertifikat kann vom Kunden verlangt werden.

## Capability Maturity Model Integrated
*Siehe [Wikipedia](https://en.wikipedia.org/wiki/Capability_Maturity_Model_Integration).*


# Qualitätsprüfung
Analytisches QM von Prozessen, Ergebnissen, Dokumenten oder der Software selbst.

Testen erhöht indirekt:
* **Qualität**, da Fehler(zustände) vor Auslieferung entdeckt und korrigiert werden können
* **Prozessqualität**, da Fehler dokumentiert, analysiert und damit in Zukunft vermieden werden können
* **Vertrauen** in Qualität des Systems, wenn wenige oder keine Fehler gefunden werden

Frühes erfolgreiches Testen erfordert zwar initial mehr Aufwand, lohnt sich aber auf lange Sicht.

Ein **Testfall** besteht aus einem Eingabewert, einem Soll-Ergebnis, und Vor- und Nachbedingungen. Sind Soll- und Ist-Verhalten verschieden, liegt eine Fehlerwirkung vor. Ein **Testorakel** ist eine Informationsquelle für Sollergebnisse, zum Beispiel ein bestehendes System ([Was ist ein Testorakel?](http://www.karteikarte.com/card/1317237/was-ist-ein-testorakel)).
