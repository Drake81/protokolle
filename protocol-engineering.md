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

* **Einteilung in mehrere Schritte**
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

* **"Was"-Spezifikation**
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

* **"Wie"-Spezifikation**
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

# Beschreibunsmethoden und Beschreibungstechniken

Dienen der Beschreibung des **Protokollablaufs**

## Beschreibungsmethoden vs. Beschreibungstechniken

* **Beschreibungsmethoden**
    * Methoden für die Beschreibung
    * Grundlage für die Modelle der Beschreibunstechniken
    * Bsp:
        * endliche Zustandsautomaten
        * Petri Netze
    * **KEINE vollständige Beschreibung**

* **Beschreibungstechniken**
    * Spezifikationssprachen für eine *formale* Beschreibung
    * Bsp:
        * SDL
        * Lotos
    * Nutz eine formale Semantik
    * **WEITGEHEND volständige Beschreibung**


## Beschreibungsmethoden

* **Arten:**
    * Konstruktive Methoden
    * Deskriptive Methoden

### Konstruktive Methoden

* Beschreibt Protokoll durch *abstraktes* Modell
* Interpretation durch semantisches Modell
* Quasi-Implementierung
* Bsp:
    * endliche Zustansautomaten

* **Vorteile**
    * direkte Unterstützung von:
        * Entwurf
        * Implementierung
    * Ausführliche Spezifikation
        * *Rapid Prototyping*

* **Nachteile**
    * keine Darstellung von Eigenschaften

### Deskriptive Methoden

* beschreiben Eigenschaften eines Protokolls
* Unterlegen keine spezielle Interpretationsvorschrift
* Beschriebene Eigenschaften:
    * **Lebendigkeitseigenschaften**
    * **Sicherheitseigenschaften**
* Bsp: 
    * Temporale Logiken


* **Vorteile**
    * direkte Formulierung gewünschter Eigenschaften
    * verifizierbar

* **Nachteile**
    * i. Allg. nicht entscheidbar, ob die Spezifikation das erlaubte Verhalten vollständig beschreibt
    * kein Prototyping
    * keine direkte Ableitung von Implementierungen

### Klassifikation der Beschreibungsmethoden


                | Spezifikationsmethoden                                                            |
----------------|-----------------------------------------------------------|-----------------------|
Klassifikation  |               konstruktiv                                     |  deskriptiv       |
                | zustandsorientiert     |       transitionsorientiert          |                   |
                |                        | prozessorientiert | ablauforientiert |                   |
----------------|------------------------|-------------------|------------------|-------------------|
Methoden        |  endl. Zustandsautomat | Prozessalgebren   | Zeitablauf-Dia.  | Temporale Logiken |
                |  Petri-Netze           | Petri-Netze       | Petri-Netze      |                   |
----------------|------------------------|-------------------|------------------|-------------------|
FDTs            |  SDL                   | SDL               | MSC              | cTLA              |
                |                        | Lotos             |                  |                   |

* **Beschreibungsmethoden sind:**
    * Endliche Zustandsautomaten
    * Erweiterte endliche Zustandsautomaten
    * Petri-Netze
    * Algebraische Prozesskalküle
    * Temporale Logiken
    * Hybride Methoden

### Endliche Zustandsautomaten




## Beschreibungstechniken


# Entwicklung

# Entwurf

# Validation

# Verfikation

# Implementierung

# Test

# Implementierung am Beispiel FSM

