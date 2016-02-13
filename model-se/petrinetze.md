Jegliche automatische Verarbeitung von Modellen benötigt präzise Definition (des Ausführungsverhaltens). **Petrinetze** sind ein Ansatz für eine solche Modellierung.


# Syntax
Ein Petrinetz ist ein gerichteter Graph mit zwei Arten von Knoten, **Stellen** (Speichern von Informationen) und **Transitionen** (Verarbeitung von Informationen), und **Kanten**, die Stellen und Knoten alternierend mit einander verbinden.


# Ausführung
Als **Schalten** von Transitionen bezeichnet man das Übergeben einer Anzahl (es gelten Kapazitätsbeschränkungen) von **Marken** durch eine Transition von ihrer Vorgängerstelle zu ihrer Nachfolgerstelle. Eine Transition wird **aktiviert**, wenn sie die geforderte Menge an tokens erhalten kann und die Nachfolgerstelle die Tokens aufnehmen kann. Zur Ausführung werden alle aktiven Transitionen eine nach der anderen (Auswahl zufällig ¯\\_(ツ)_/¯ lol) iterativ aktiviert. Eine Folge von Schaltungen ist eine **Schaltfolge**.

Die Bedeutung eines Tokens hängt von der Stelle ab, an der es plaziert ist. Der globale Zustand des Netzes, also die Position aller Tokens, ist eine **Markierung**. Eine **tote Markierung** ist der Endzustands eines Netzes, bei dem keine Schaltungen mehr stattfinden können. Eine Markierung gilt als **erreichbar**, wenn es eine Schaltfolge gibt, die das Netz in diesen Zustand überführt. Die Menge aller erreichbaren Markierungen ist die **Erreichbarkeitsmenge**.


# Analyse von Systemen
Simulation eines Petrinetzes:
* Kann zeigen, dass bestimmte Situationen auftreten können
* Kann *nicht* zeigen, dass bestimmte Situationen *nicht* auftreten
* Ist ein Ausschnitt aus Menge aller möglichen Verhalten

**Verifikation** ist der Beweis von Eigenschaften. **Statische Eigenschaften** betreffen die Netztopologie, **dynamische Eigenschaften** sind abhängig von der Erreichbarkeitsmenge (zB Deadlocks). Zwei wichtige Klassen von Eigenschaften sind **Sicherheit** (ein unerwünschter Zustand tritt nicht ein) und **Lebendigkeit** (ein erwünschter Zustand kann wiederholt auftreten).

Eine Transition ist:
* **Aktivierbar** wenn sie in mindestens einer erreichbaren Markierung aktiviert
* **Lebendig** wenn sie in allen erreichbaren Markierungen *aktivierbar* ist
* **Tot** wenn sie in keiner erreichbaren Markierung aktiviert

Eine *Markierung* ist **tot**, wenn alle Transitionen tot sind (keine Transition ist aktivierbar, *alternative Definition zu oben*). *Es wird impliziert dass dies ein **Deadlock** ist.*
