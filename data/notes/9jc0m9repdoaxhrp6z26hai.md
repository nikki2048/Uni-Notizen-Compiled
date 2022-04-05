
## Positionsbestimmung
Informatik = Wissenschaft von der **algorithmischen** Problemlösung.
- Gegeben: Problem(klasse)
- Gesucht: (automatisierbare) Lösung aus elementaren Schritten

### Informationsverarbeitung
Repräsentation/Organisation von Daten:
- Datenstrukturen

(Schrittweise) Modifikation von Daten:
- Algorithmen

*Software = Datenstrukturen + Algorithmen*

## Algorithmen
```text
Definition: Schrittweise Modifikation von Daten zur Lösung eines Problems
```

### Eigenschaften (Donald Knuth)
- Determinismus
- Input (# $\geq$ 0)
- Output (# $\geq$ 1)
- Terminierung

### Analyse von Algorithmen
- Partielle Korrektheit
- Totale Korrektheit
- Komplexität (Speicherplatz, Rechenzeit)
- Robustheit (bei inkorrekten Eingaben)

- **Komplexität**
  - Effizienz (Praxistauglichkeit)
  - Worst / Best / Average case
  - Wie viel länger dauert die Berechnung, wenn der Input verdoppelt wird?
  - Gibt es einen besseren Algorithmus? (Problem-Reduktion)
- **Effizienz**
  - Problem $\rightarrow$ Ressourcen
  - Ressourcen $\rightarrow$ Problem
  - Ressourcen-Typen:
    - Rechenzeit
    - Speicherplatz
    - Energieverbrauch

### Top-Down Software-Entwurf
- Spezifiziere Eingabe / Ausgabe
- Problemlösung
  - Beziehungen, Referenzen, Daten
    - Datenstrukturen
  - Wesentliche Verarbeitungsschritte
    - Module, Prozeduren, Algorithmen
- Analyse
  - Korrektheit, Aufwand / Komplexität
- Implementieren / Testen / Dokumentieren

### Software-Entwicklung
- Datenstrukturen
  - Statische Beziehungen
  - (explizite) funktionale Zusammenhänge
- Algorithmen
  - Dynamische Prozesse
  - (implizite) funktionale Zusammenhänge

# Übersicht
- Datenstrukturen
  - Konzepte
  - Standard-Typen
- Algorithmen
  - Entwurf und Analyse
  - Standard-Verfahren

## Datenstrukturen
- Abstrakte Datentypen
- Konkrete Datentypen

| Lineare Strukturen | Hierarchische Strukturen | Graph-Strukturen |
| ------------------ | ------------------------ | -----------------|
| Arrays <br> Listen <br> Stacks (Keller) <br> Queues (Warteschlangen) | Bäume (Binär, Balanciert, B-, ...) <br> Prioritätswarteschlangen <br> ... | Gerichtet / Ungerichtet <br> Planare Graphen <br> ... |

## Algorithmen
- Abstrakt
  - Allgemeine Entwurfsparadigmen
  - Komplexitätsanalyse
- Konkret
  - Sortieren
  - Suchen
  - Optimieren

| | **Linear** | **Hierarchisch** | **Graphen** |
|-|------------|--------------|---------|
| **Sortieren** | Einfache Verfahren | Höhere Verfahren | Topologisches Sortieren |
| **Suchen** | Hashing k-Selection | Suchbäume | Traversen |
| **Optimieren** | Greedy | Dyn. Programming, Divide & Conquer | Spannbäume, kürzeste Pfade Min-Cut |