# Einführung

Ziel: Ingenieurmäßige Entwicklung von Kommunikationssoftware

* **Unterscheidung zur norm. Softwareentwicklung durch:**
    * systematische Entwurfsmethodik nicht ausgeprägt
    * mehrere Spezifikationsebenen
    * Komplexität der Protokolle
    * Nebenläufigkeit, Nichtdeterminismen
    * hohe Zuverlässigkeitsanforderungen
    * Einfluss der Standardisierung
    * mehrfache Implementierung der Protokolle

* ** Einteilung in mehrere Schritte**
    * Anforderungsanlyse
        * Anforderungsspezifiaktion
    * Dienst u. Protokollentwurf
        * Dienst u. Protokollspezifikation
    * Protokollverfikation
        * verfizierte Spezifikation
    * Leistungsvorhersage
        * optimierter Entwurf
    * Implementierung
        * Kode
    * Test
        * getestete Kommunikationsoftware
    * Installation/Integration

* **Interne Ereignisse**
    * Innerhalb des Protokolles oder Dienstes auftretende Ereignisse die von außen nicht sichbar sind.
    * z.b. Fehler wie: Verbindungsabbruch (entspricht einer spontanen Transition in einem Zustansautomaten)

* **Nichtdeterminismus** tritt auf bei
    * Nebenläufig
    * interne Ereignisse
    * wenn keine Aussage über Reihenfolge der Ereignisse
    * bei Verhaltensalternativen nach Ereigniss
    * ermöglicht:
        * Vereinfachte Darstellung
        * Höhere Flexibilität

** Auflösung von Nichtdeterminismen erst in der Implementierung**

## Dienstspezifikation

"Was"-Spezifikation

* Was soll für ein Dienst erbracht werden
* Häufigvernachlässigt
* Schnittstelle von außen betrachtet

Die Dienstspezifikation beschreibt die Eigenschaften des bereit-
gestellten Dienstes und die Art und Weise seiner Nutzung.

* **Interessiert:**
    * Dienstnutzer
    * Verifizierer
    * Test-Ingenieur

* **Techniken der Dienstbeschreibung**
    * textuell
    * Zeitablaufdiagramme
    * Zustandsdiagramme
    * Parameter-Tabellen

* **Elemente der Dienstspezifikation**
    * Auflistung von (Teil-) Diensten und Dienstprimitiven
    * Abhängigkeiten zwischen Dienstprimitiven
    * lokales / globales Verhalten
    * interne Ereignisse
    * Nichtdeterminismen
    * Parameter und Abhängigkeiten zwischen ihnen

**SAP - Service Access Point (Dienstzugangspunkt)**

* **lokales Verhalten**
    * beschreibt zulässige Interaktionen an einem Dienstzugangspunkt

* **globales Verhalten**
    * beschreibt Verhalten zwischen verschiedenen SAPs

## Protokollspezifikation

"Wie"-Spezifikation

* Wie soll der Dienst erbracht werden
* Interne Umsetzung des Dienstes
* "Wie"-Spezifikation ist nötig, weil Protokolle *mehrfach* implementiert werden *müssen*
    * verschiedene Betriebssysteme
    * unterschiedliche Ablaufumgebungen

Die Protokollspezifikation beschreibt die Art und Weise, wie die
Instanzen in einem Protokoll miteinander kommunizieren, um den
spezifizierten Dienst zu erbingen.

* **Elemente der Prorokollspezifikation**
    * Datenformatbeschreibung
        * i.d.R. mit ASN.1
    * Ablaufbeschreibungen
        * verhaltensorientiert
            * Zustandsautomaten
        * ablauforientiert
            * Zeitablaufdiagramme
            * MSC
    * Nichtdeterminismen
    * interne Ereignisse
    * lokale Aktionen

# Beschreibungstechniken

# Entwicklung

# Entwurf

# Validation

# Verfikation

# Implementierung

# Test

# Implementierung am Beispiel FSM

