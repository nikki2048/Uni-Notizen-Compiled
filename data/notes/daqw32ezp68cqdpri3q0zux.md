
## Überblick

- Darstellung allgemeiner Beziehungen zwischen Objekten/ Elementen **[n:m]**
    -   Objekte = Knoten
    - **V = $\{v_1, \ldots v_n\}$**
    - Beziehungen = Kanten: 
    - **E = $\{(a_1,b_1), \ldots (a_m.b_m)\}$**
    - Kanten können **gerichtet**(Vorgänger/Nachfolger) oder **ungerichtet**(Nachbarschaft) sein.

## Begriffsdefinitionen

### Zusammenhängend:

#### stark:
- für jede Paar $v_i, v_j$ von Knoten existiert ein Pfad von Kanten von $v_i$ nach $v_j$ und von $v_j$ nach $v_i$.

#### schwach:
- für jede Paar $v_i, v_j$ von Knoten existiert ein Pfad von Kanten von $v_i$ nach $v_j$ und von $v_j$ nach $v_i$, **wenn man alle <u> gerichteten </u> Kanten durch <u> ungerichtete </u> Kanten ersetzt**

### Vollständig
- Zwischen je zwei Knoten existiert eine Kante
> $m = n \times (n-1)/2$

### Isomorph
- Graphen ($V_1,E_1$) und ($V_2,E_2$) durch Permutationen der Knoten(indizes) ineinander überführbar
- <u>Notwenige Kriterien: $n_1 = n_2, m_1 = m_2 </u> Anzahl der Knoten mit Grad k

### Planare Graphen
- Einbettung in die Ebene
- Zerlegung der Ebene in disjunkte Zellen
- Kompatibilitätsbedingungen zwischen Kanten


## Repräsentationen

### Adjazenzmatrix

- Knoten: $V = \{v_1, v_n\}$
- $A \in Bool^{n \times n}$
- $a_{ij} = 1$ falls (i,j) $\in$ E, $a_{ij} = 0 sonst$

- j-te Spalte: alle Vorgänger von $v_j$
- i-te Zeile: alle Nachfolger von $v_i$
- A symmetrisch für <u>ungerichtete</u> Graphen

#### Erreichbarkeit 
- A pro Schritt
- $A^k$ nach k Schritten
- i-te Zeile von $A^k$: alle Knoten die man vom i-ten Knoten aus in <u>genau</u> k Schritten erreicht
- i-te Zeile von $(A+I)^k$: alle Knoten die man vom i-ten Knoten aus in <u>höchstens</u> k Schritten erreicht.

> $(A+I)^k = \sum\limits_{i = 0}^{k}\binom{k}{i}A^i$

### Adjazenzlisten
- Bei komplexen Graphen bestehen oft nur lokale Knotenbeziehungen
- Die meisten Einträge der Adjazenzmatrix sind 0 
- Speichere nur die existierenden Kanten

- Für <u>gerichtete</u> Graphen werden Vorgänge- und Nachfolger-Listen verwaltet
- Speicherverbrauch
    - A-Matrix: $n^2$ bit
    - A-Listen: $n \times k \times \log n$

### Kantenstrukturen

- Kanten verbinden Knoten
- Kanten verweisen auf benachbarte Kanten (Umlaufsinn)
- Garantiert die Planarität


