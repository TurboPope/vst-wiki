# Einführung
Viele Zusammenhänge beziehungsweise Einschränkungen können mit reinem UML nicht modelliert werden. Es wird eine formale, machinell einsetzbare Erweiterung benötigt.

Die **Object Constraint language** ist eine Logik-basierte Notation für solche Einschränkungen. OCL ist keine Programmiersprache und jeder Ausdruck ist Seiteneffektfrei. Ausdrücke sind im Allgemeinen deklarativ und beschreiben fortlaufende (**Invarianten**) oder vor- und nach-Bedingungen.

Ein constraint hat folgenden Syntax:

```
context <identifier>
<constraint-type> [<constraint-name>]: <condition>
```

* `context` ist ein Schlüsselwort
* `<identifier>` gibt das Modellelement an, zu dem das constraint gehört
* `<constraint-type>` gibt die Art des constraints an:
  * `pre` für Vorbedingungen
  * `post` für Nachbedingungen
  * `inv` für Invarianten
* `constraint-name` optionaler Name für Constraint
* `condition` boolscher Ausdruck für einzuhaltende Bedingung

**Invarianten** sind Bedingungen, die immer von allen Instanzen einer Klasse eingehalten werden müssen. **Vorbedingungen** (oder pre-conditions) müssen erfüllt sein, bevor eine Methode ausgeführt wird. **Nachbedingungen** (post-conditions) müssen nach Ausführen einer Methode gelten.

*Die Folien geben an dieser Stelle eine umfassende Einführung in OCL (mit Beispielen). Diese hier zu wiederholen ist sinnlos.*
