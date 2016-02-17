# UML Profile
The following options exist for defining modelling languages (an **UML extension**) within MOF:

* Definition of new meta model (not necessarily extension of UML, but could be)
* Heavy-weight extension: uncontrolled extension of UML meta model
* Light-weight extension: controlled extension of UML meta model with stereotypes, called **UML profile**

UML is a general-purpose modeling language

* UML can be adapted to become a domain-specific language (DSL)
* Domain-specific adaption of UML is called **UML Profile**
* Domain-specific extensions are indicated by stereotypes
* Notation: «stereotype»

An **UML profile** is a lightweight, domain-specific **UML extension** using stereotypes.

[Erneut geklaut aus einer anderen Zusammenfassung](https://github.com/TurboPope/we-wiki/blob/master/software-engineering/modeling.md#uml-profiles-and-extensions)

* **Stereotypen** spezialisieren Benutzung von Modellelementen
* **Tagged values** fügen {tag=value} Paare zu stereotypisierten Elementen hinzu
* **Constraints** verfeinern die Semantik eines stereotypisierten Elements (Können durch OCL ausgedrückt werden)

Ein UML-Profil sammelt diese Informationen


# UMLSec
**UMLsec** kann benutzt werden, um Sicherheitsanforderungen in normale UML-Modelle einzubauen. Sind diese vollständig und werden bei der Implementierung berücksichtigt ist das System *mehr oder weniger* sicher.

*Unten folgt eine Auflistung von Stereotypen mit einer generellen Beschreibung. Stereotypen können in verschiedenen Diagrammarten vorkommen und haben dort eventuell leicht unterschiedliche Bedeutungen. Daher folgt darauf eine Auflistung der relevanten Diagramme mit einer Beschreibung, welche UMLsec-Elemente in ihnen vorkommen können und was sie dort speziell bedeuten.*

*Die Informationen sind extrem ungeordnet und inkosistent. Außerdem lassen sich manche Konzepte, die nur für eine Diagrammart gezeigt wurden, anscheinend auch auf andere Diagramme übertragen.*

## Stereotypen
Aus dem tollen Diagramm:

* `«data security»` Stellt sicher, dass die Sicherheit auf der Verhaltensebene gegeben ist *(was auch immer das heißt)*
* `«secure links»` Stellt sicher, dass die Sicherheitsanforderungen in den verschiedenen Teilen eines *Verteilungsdiagramms* konsistent sind.
* `«secure dependency»`: Stellt sicher, dass die Sicherheitsanforderungen in den verschiedenen Teilen eines *Klassendiagramms* konsistent sind.
* `«critical»`: Markiert Objekte oder Subsystem-Instanzen, die kritische Daten enthalten
* `«secrecy»`: Niedrigste "Sicherheitsstufe"
* `«integrity»`: Mittlere "Sicherheitsstufe"
* `«high»`: Hohe "Sicherheitsstufe"
* `«encrypted»` Kommunikations-Art im Deployment-Diagramm
* `«Internet»` Kommunikations-Art im Deployment-Diagramm
* `«wire»` Kommunikations-Art im Deployment-Diagramm
* `«LAN»` Kommunikations-Art und -Knoten im Deployment-Diagramm
* `«smart card»` Kommunikations-Knoten im Deployment-Diagramm
* `«POS device»` Kommunikations-Knoten im Deployment-Diagramm
* `«issuer node»` Kommunikations-Knoten im Deployment-Diagramm

In der Wildnis encountered:
* `«fair exchange»` fordert, dass eine Transaktion so durchgeführt wird, dass ein Betrug verhindert wird
* `«call»` *Siehe Klassen-Diagramme*
* `«send»` *Siehe Klassen-Diagramme*
* `«rbac»` *Siehe Aktivitäts-Diagramme*

## In Aktivitäts-Diagrammen
* `«fair exchange»`. Hier können auch noch Aktivitäts-Mengen für Anfang (`start`) und Ende (`stop`) der Transaktion, die gesichert werden muss, angegeben werden. Wird eine Start-Aktivität ausgeführt muss anschließend eine zugehörige Stop-Aktivität ausgeführt werden.
* `«rbac»` Erzwingt rollenbasierte Zugriffskontrolle im durch das Aktivitätsdiagramm spezifizierten Geschäftsprozess. *Keine Ahnung wie das funktioniert.*

## In Klassen-Diagrammen
* `«secure dependency»`: Stellt sicher, dass `«call»`- und `«send»`-Abhängigkeiten zwischen Klassen Sicherheitsanforderungen ({secrecy}, {integrity}, {high}) für versendete Daten respektieren.
* {secrecy}, {integrity}, {high}: Tagged-Values für Klassen. Die Values sind Mengen von Methoden, für die diese "Sicherheitsstufe" gelten muss
* `«call»`- und `«send»` existieren zwischen Methoden ("Nachrichten" in den Folien). Sind zwei Methoden so mit einander Verbunden und wurde einer der Methoden einer Sicherheitsstufe zugeordnet muss die andere gleich zugeordnet sein.
* `«critical»`

## In Paket-Diagrammen (Package Diagrams)

## In Komponenten-Diagrammen

## In Sequenz-Diagrammen

## In Zustands-Diagrammen (State Charts)

## In Anwendungsfall-Diagrammen (Use Case Diagrams)
* `«fair exchange»`

## In Verteilungs-Diagrammen (Deployment Diagrams)

Es geht darum festzulegen, welche Aktionen einem Angreifer nicht möglich sein dürfen. Diese können sein:

* `delete` (Verbindungen)
* `read` (Verbindungen)
* `insert` (Verbindungen)
* `access` (Knoten)

Threats<sub>A</sub>(s) oder besser `get_threats(angreifer, verbindung_oder_knoten)` ist eine "Funktion", die in dem arkanen Wissen von UMLsec nachschlägt und sagt, welche Aktionen dem gegebenen `angreifer` auf dem gegebenden `knoten` bzw. der gegebenen `verbindung` möglich sind.

*Hier ist zumindest ein Teil dieses arkanen Wissens für den "Standart-Angreifer" der vermutlich der einzige ist, den man für die Klausur kennen muss:*

| `stereotyp` | Threats<sub>default</sub>(`stereotyp`) |
| ----------- | -------------------------------------- |
| Internet    | {delete, read, insert}                 |
| encrypted   | {delete}                               |
| LAN         | {}                                     |
| smart card  | {}                                     |

Die Sicherheitsstufen geben an, welche Aktionen dem Angreifer nicht möglich sein dürfen:
* `«high»`: Der Angreifer darf nichts
* `«secrecy»`: Der Angreifer darf nicht lesen (`read`)
* `«integrity»`: Der Angreifer darf nichts einfügen (`insert`)

Wenn irgendwo im Diagramm ein Datenaustausch stattfindet, wird mit einem Stereotypen wie `«Internet»` angegeben, über welchen Kanal dieser stattfindet. Sollen die Verbindungen sicher sein (`«secure links»` im Kopf des Diagramms) muss man prüfen, ob die von den Sicherheitsstufen der Verbindungen festgelegten Aktionen dem gegebenen Angreifer bei dieser Verbindungsart möglich sind.

### Alternative, informelle Erklärung
> ich kanns dir auch einfach grad schnell erklären

> deine verbindungen zwischen den komponenten sind ja mit stereotypen markiert

> also sowas wie `<<LAN>>` `<<Internet>>`

> er hat dann ne funktion gemacht die Threat_A(x) funktion, die übernimmt als x einen solchen stereotyp und gibt aus welche angriffe möglich sind wenn es sich um einen angreifer A handelt

> secure link ermöglicht es dir verbindungen zwischen artefakten mit `<<integrity>>` `<<secrecy>>` oder `<<high>>` zu markieren

> und es gibt da eigentlich nur 3 bedingungen

> wenn eine verbindung mit `<<secrecy>>` markiert ist, dann darf kein angriff mit read möglich sein, also darf threat_A(x) nicht "read" enthalten

> wenn eine verbindung mit `<<inetgrity>>` markiert ist, dann darf kein angriff mit insert möglich sein, also darf threat_A(x) nicht "insert" enthalten

> wenn eine verbindung mit `<<high>>` markiert ist, dann darf kein angriff möglich sein, also darf threat_A(x) nicht nichts enthalten

> das ist alles... hauptsache der macht das mega dumm und umständich
