# Einführung

Ziel: Ingenieurmäßige Entwicklung von Kommunikationssoftware

* **Unterscheidung zur norm. Softwareentwicklung durch:**
    * systematische Entwurfsmethodik (nicht ausgeprägt)
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

**Auflösung von Nichtdeterminismen erst in der Implementierung**

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

* beschreiben *Eigenschaften* eines Protokolls
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

Anmerkung: **FDT -> Field Device Tool**

**konstruktiv und zustandorientiert**

* Methoden:
    * endl. Zustandsautomaten
    * Petri-Netze
* FDTs:
    * SDL 

**konstruktiv und transitorientiert und prozessorientiert**

* Methoden:
    * Prozessalgebren
    * Petri-Netze
* FDTs:
    * SDL
    * Lotos

**konstruktiv und transitorientiert und ablauforientiert**

* Methoden:
    * Zeitablaufdiagramme
    * Petri-Netze
* FDTs:
    * MSC

**deskriptiv**

* Methoden:
    * Temporale Logiken
* FDTs:
    * cTLA             

* **Beschreibungsmethoden sind:**
    * Endliche Zustandsautomaten
    * Erweiterte endliche Zustandsautomaten
    * Petri-Netze
    * Algebraische Prozesskalküle
    * Temporale Logiken
    * Hybride Methoden

### Endliche Zustandsautomaten

* Quintupel aus: (S,I,O,T,s0)
    * S - Zustände
    * I - Eingaben
    * O - Ausgaben
    * T - Zustandsüberführungsfunktion
    * s0 - Init-Zustand
* Transition t ist Zustandsübergang
* Wenn t != I, dann *spotane Transition*

* **Vorteile**
    * natürliche Beschreibung
    * einfache Darstellung
    * gut nutzbar für Implementierung

* **Nachteile**
    * Kommunikationsablauf kann nicht dargestellt werden
    * viele Zustände -> sehr groß und unübersichtlich

### Erweiterte endliche Zustansautomaten

* Tupel aus: (S,C,I,O,T,s0,c0)
    * S - Zustände
    * C - Kontexte
    * I - Eingaben
    * O - Ausgaben
    * T - Zustandsüberführungsfunktion
    * s0 - Init-Zustand
    * c0 - Init-Kontext
* Transition t ist Zustandsübergang
* Wenn t != I, dann *spotane Transition*
* Kontext entspricht *wertbelegung der Variablen*

* **Vorteile**
    * natürliche Beschreibung
    * einfache Erstellung und Darstellung
    * weniger komplex als endl. Zustandsautomat
    * gut nutzbar für Implementierung

* **Nachteile**
    * Kommunikationsablauf kann nicht dargestellt werden
    * viele Zustände -> sehr groß und unübersichtlich
    * weniger geeigent für Dienstspezifikationen
    * Testfälle nicht direkt ableitbar

**Beliebteste Beschreibunsmethode für Protokolle**

### Petri-Netze

**Netz**

* Tripel N=(P,T,F)
    * P - Plätze (Zustände,Bedingungen)
    * T - Transition (Ereignisse, Übergänge)
    * F - Flussrelation (Kanten zwischen den Plätzen/Zuständen)

**Petri-Netz**

* Quintupel N=(P,T,F,V,m0)
    * (P,T,F) - ein Netz
    * V - positive ganze Zahl die einer Kante zugeordnet ist
        * V - Kantenvielfalt (V=1 für gewöhnliche Netzte)
    * m0 - Anfangsmarkierung von P

* **Vorteile**
    * abstrakte Modellierung des Kontrollflusses
        * Unterstützung der Verifikation
    * Darstellung paralleler Abläufe
    * Nachvollziehen von Abläufen durch Verfolgen des Markenflusses
        * Prototyping

* **Nachteile**
    * sehr abstrakte Darstellung
        * Problem: Fehlerlokalisierung
    * sehr komplex bei vielen Zuständen
    * keine oder aufwendige Darstellung wichtiger Protokollelemente
        * Aufbau PDUs, Reihenfolgeüberwachung u. a.

**Petri-Netze werden für die Protokollbeschreibung in der Praxis**

* **Nutzung von Petri-Netzen**
    * Leistungsanlyse
    * Verfikation

### Prozessalgebren

* **Prozessalgebren**
    * modellieren das Verhalten von Systemen durch Menge wechselwirkender Prozesse
    * nur das äußere Verhalten der Prozesse wird betrachtet.
    * Verallgemeinerung der klassischen Automatentheorie
    * Beschreibung der Systeme über die Kooperation kleinerer Komponenten, die **Prozesse**.

* **Grundelemente**
    * Aktion
    * Kompositionsoperatoren

* **Aktion**
    * ist: atomare, synchrone Interaktion mit einem *anderen* Prozess
    * werden durch *Label* repräsentiert

* **Label**
    * Ports über die interagiert wird
    * Keine Unterscheidung zwischen Ein-/Ausgabeereignissen

* **Vorteile**
    * exakte und vollständige Beschreibung
    * Unterstützung der formalen Verifikation
    * Unterstützung Testfallableitung

* **Nachteile**
    * sehr abstrakte Darstellung
    * große Distanz zur Implementierung
        * mehr Freiheitsgrade für Implementierung
    * hoher Grad an Formalität
        * Probleme in der Nutzerakzeptanz

**Sehr begrenzte Nutzung für praktische Protokollentwicklung**

### Temporale Logiken

Temporale Logiken sind Erweiterungen der Aussagenlogik und der Prädikatenlogik durch Operatoren, die die Formulierung von Aussagen mit Bezug auf die Zeit gestatten.

* nicht die absolute Zeit interessiert, sondern die zeitliche Folge, in der sich die Dinge ereignen
* beschreiben Eigenschaften, die das Protokoll erfüllen soll
* Einhaltung der Eigenschaften im Protokollentwurf wird durch temporallogisches Schließen oder Model Checking überprüft

**Wichtigste deskriptive Beschreibungsmethode für Kommunikationsprotokolle !!!**

* **Unterscheidung der Eigenschaften**
    * Sicherheitseigenschaften
        * safety properties
    * Lebendigkeitseigenschaften
        * liveness properties

* **Sicherheitseigenschaften**
    * Bestimmt unerwünschte Ereignisse werden *nicht* eintreten
        * Beispiel: Keine Dateneinheit geht verloren
    * Erfüllt wenn nichts passiert  

* **Lebendigkeitseigenschaften**
    * sicherstellen, dass Ereignisse auch wirklich eintreten
    * beschreiben was passieren *muss*
        * Beispiel: Nach Verbindungsaufbau wird Datentransfer-Phase erreicht und die Daten übertragen

* **Arten temporaler Logiken**
    * *Lineare temporale Logiken*
        * modellieren Verhalten in lineare Folge von Zuständen
        * nur zeitliches Verhalten
        * Erlaubt Aussagen zu Gegenwart und Zukunft
        * Nutzung: *Software Verfikation*
    * *Verzweigende temporale Logiken*
        * alternatives Verhalten in einem Zustand möglich
        * Verschiedene zeitliche Abläufe
        * Zustandsbaum
        * Nutzung: *Hardware Verfikation*

* **Vorteile**
    * explizite Spezifikation der zu erfüllenden Eigenschaften
    * Allgemeingültigkeit kann formal bewiesen werden
        * Inkonsistenzen können aufgedeckt werden

* **Nachteile**
    * Übergang zur Implementierung kompliziert
        * fehlende Werkzeugunterstützung
    * hoher Einarbeitungsaufwand
        * Vorkenntnisse erforderlich

**Für praktischen Protokollspezifikationen kaum genutzt !!!**

### Zusammenfassung

* **FSM** reine FSM werden nur begrenzt genutzt
* **EFSM** Populärste Beschreibungsmethode für Protokolle
* **Petri-Netze** werden in der Praxis kaum genutzt 
* **Prozessalgebren** sehr begrenzte Nutzung
* **Temporale Logiken** werden in der Praxis kaum genutzt
    * Anwendung in Kombination mit anderen Methoden
    * (Model Checking)

## Beschreibungstechniken


# Entwicklung

# Entwurf

# Validation

# Verfikation

# Implementierung

# Test

# Implementierung am Beispiel FSM

