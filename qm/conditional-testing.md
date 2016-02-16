# Einführung
Es werden stärkere Kriterien benötigt, die Teilbedingungen (**Prädikate**) berücksichtigen. **Bedingungsüberdeckungen**: Berücksichtigen Bedingungen in Schleifen und Auswahlkonstrukten zur Definition von Tests.

Das globale Beispiel sei hier `if (a || b || c) { ... } else { ... }`.


# Einfache Bedingungsüberdeckung (C<sub>2</sub>)
Jedes Prädikat in jeder Verzweigung muss einmal `true` und einmal `false` sein. Testwirksamkeit: Verhältnis Anzahl `true`-Prädikate plus Anzahl `false`-Prädikate zu Anzahl Prädikate mal zwei.

Beispiel: `{(0, 0, 0), (1, 1, 1)}`


# Zweig-/Bedingungsüberdeckung
Testfallmenge erfüllt Zweig-/Bedingungsüberdeckung gdw. sie C<sub>2</sub>-Überdeckung (atomare Bedingungsüberdeckung) und C<sub>1</sub>-Überdeckung (Zweigüberdeckung) erfüllt.

Beispiel: wie [Einfache Bedingungsüberdeckung](#einfache-bedingungsüberdeckung).


# Mehrfachbedingungsüberdeckung (C<sub>3</sub>)
Jede mögliche Wahrheitswert-Kombination der Prädikate aller Verzweigungen muss mindestens ein Mal erfüllt sein. Testwirksamkeit: Verhältnis Anzahl getesteter Kombinationen zu Anzahl möglicher Kombinationen (2<sup>Anzahl Prädikate</sup>)

Beispiel: `{(0, 0, 0), (0, 0, 1), (0, 1, 0), (0, 1, 1), (1, 0, 0), (1, 0, 1), (1, 1, 0), (1, 1, 1)}`


# Minimale Mehrfachbedingungsüberdeckung
Jede mögliche Wahrheitswert-Kombination der Prädikate aller Verzweigungen die eine Änderung des Wahrheitswerts des gesanten Ausdrucks hervorruft muss getestet werden. Testwirksamkeit: verhältnis Anzahl getesteter Kombinationen zu Gesamtzahl möglicher Kombinationen.

Beispiel: `{(0, 0, 0), (0, 0, 1), (0, 1, 0), (1, 0, 0)}`
