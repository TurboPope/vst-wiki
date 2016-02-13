# Metamodellierung
Die UML-Notation muss selber formell definiert werden. Ein **Metamodell** ist ein Modell, das die Notation einer Modellierungsnotation definiert.

0. **M0: Informationsschicht**: Instanzen (*Zum Beispiel das Personen-Objekt `hans`*)
1. **M1: Modellschicht**: Modelle (*`hans` ist eine Instanz der Klasse `Person`*)
2. **M2: Metamodellschicht**: Metamodelle (*Die Klasse `Person` ist eine Instanz des Klassen-Metamodells*)
3. **M3: Meta-Metamodellschicht** Meta-Metamodelle (definieren valide Metamodelle)

"MOF is designed as a four-layered architecture. It provides a meta-meta model at the top layer, called the M3 layer. This M3-model is the language used by MOF to build metamodels, called M2-models. The most prominent example of a Layer 2 MOF model is the UML metamodel, the model that describes the UML itself. These M2-models describe elements of the M1-layer, and thus M1-models. These would be, for example, models written in UML. The last layer is the M0-layer or data layer. It is used to describe real-world objects." (*Quelle:* [Wikipedia](https://en.wikipedia.org/wiki/Meta-Object_Facility#Overview))

MOF ist logisch zirkulär: Es definiert UML-Modelle mit Klassendiagrammen aus der UML.


# UML-Erweiterungen
UML-Erweiterungen erweitern UML-Diagramme um fachliche Konzepte, bringen also domänenspezifisches Wissen auf die Modell-Ebene. Das hat den Vorteil, dass dieses Wissen nicht neu definiert werden muss, wenn man die Modelle für eine neue Implementation wiederverwendet. UML-Erweiterungen sind auf der Metamodellschicht (M2) definiert.

An UML profile is a lightweight, domain-specific UML extension using stereotypes. Ein UML-profil ist ein Paket aus Stereotpyen, Tagged Values und Constraints.

## Stereotypen
Spezialisieren ein Modellelement. Werden mit `«abc»` oder Symbolen notiert.

## Tagged Value
Fügt eine Menge von tag-value Paaren zu stereotypisierten Modellelementen hinzu (`{abc=d, efg=hi}`).

## Constraint
Verfeinert Semantik eines stereotypisierten Modellelements (z.b. mit OCL).


# Modelltransformationen


# Design Patterns
