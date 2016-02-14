Ein Blackboxtest testet ein Programm ohne dessen interne Logik zu kennen.

# Äquivalenzklassenbildung

Die Definitionsbereiche der Ein- und Ausgaben einer Funktion werden zerteilt in Klassen, in denen jeder Wert zu dem selben Verhalten führt. Dann reicht es pro Äquivalenzklasse einen Wert zu testen, beziehungsweise alle Kombinationen von Äquivalenzklassen.

Zusätzlich ist es nützlich, Grenzwerte zu testen, da diese oft fehlerträchtig sind. Grenzwerte liegen an den oberen und unteren Rändern einer Äquivalenzklasse, einmal innerhalb und einmal außerhalb.


# Entscheidungstabellentest

![Beispiel einer Decision Table](/decision-table.png)

Siehe [A Guide to Decision Tabbles](http://reqtest.com/requirements-blog/a-guide-to-using-decision-tables/)


# Modellbasierter Test

Der Zustand eines Sytems hat Einfluss auf Ausgaben. Der Zustand eines Systems bestimmt sich aus den vorherigen Eingaben. Zustandsmodellbasierte Tests weisen konfomität eines Testobjets zu einem Zustandsdiagramm nach und testen nicht-konfomrante Benutzung.

Folgende Arbeitsschritte sind nötig:
1. Erstellung des Zustandsdiagrammes
2. Prüfung auf Vollständigkeit
3. Ableiten des Übergangsbaumes für modellbasierten Konformanztest
4. Erweitern des Übergangsbaumes für modellbasierten Robustheitstest
5. Generieren der Ausführungsfolgen und Ergänzen der Nachrichtenparameter
6. Ausführen der Tests und Überdeckungsmessung

Ein **Zustandsdiagramm** ist eine Tabelle mit allen möglichen Zuständen als Spalten, allen möglichen Ereignissen als Zeilen und den Folgezuständen im Tabellenkörper.

Ein **Übergangsbaum** fängt mit dem initial-Knoten an und wendet alle möglichen Übergänge an, bis jeder Zweig jeweils in einem final-Knoten endet oder sich ein Zustand wiederholen würde. Dann werden noch Fehler-Knoten für nicht-mögliche Übergänge angehangen.

Nun können Tests generiert werden: jeder Zweig ist ein Test.
