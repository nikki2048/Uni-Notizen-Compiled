

## Abstrakte Datentypen
Abstrakte Datentypen spezifizieren *Form und Funktionalität* der zu verarbeitenden Daten.

Beispiel (Addition zweier Zeiten):
- Datenobjekte, Datenfelder
  - Zeit: `hh:mm:ss`
- Funktionen:
  - Add: `Zeit` $\times$ `Zeit` $\rightarrow$ `Zeit`
- Axiome:
  - `Add` $([h_1, m_1, s_1], [h_2, m_2, s_2]) =$ <br>
  $[(h_1 + h_2 + (m_1 + m_2 + (s_1 + s_2) / 60) / 60) \: \% \: 24$, <br> $(m_1 + m_2 + (s_1 + s_2) / 60) \: \% \: 60$, <br> $(s_1+s_2)) \: \% \: 60]$

### Datentypen
- Aufzählungstypen (bool, enum)
  - 0-Dimensional
  - Endlicher Wertebereich (vollständige Spezifikation durch Tabellen möglich)
  - [[Beispiel | 2-semester.dsal.datenstrukturen.beispiele#aufzählungstypen-bool]]
- Skalare Typen (char, int, float, ...)
  - 1-Dimensional
  - [[Beispiel | 2-semester.dsal.datenstrukturen.beispiele#skalare-typen-integer]]
- Zusammengesetzte Typen (struct, class)
  - n-Dimensional
  - Endliche / Feste zusammengesetzte Typen
    - k-dim. Vektoren (Tupel)
    - Addressen-Eintrag
- Lineare Strukturen (list, queue, stack)
  - [1:1] Beziehung
  - [[Beispiel | 2-semester.dsal.datenstrukturen.beispiele#lineare-strukturen]]
- Bäume
  - [1:n] Beziehung
  - [[Beispiel | 2-semester.dsal.datenstrukturen.beispiele#baumstrukturen]]
- Graphen - n-m Strukturen
  - [n:m] Beziehung
  - Beliebige *topologische* Struktur
  - Nachbarschafsbeziehungen zwischen Knoten
  - Wichtige Spezialfälle:
    - Planare Graphen
    - Gerichtete Graphen
    - Zyklenfreie Graphen

### Warum abstrakt?
- Keine Festlegung, wie die jeweiligen Funktionen *implementiert* werden ("Transparenz")
- Axiome beschreiben *statische* Beziehungen ("$=$" vs. "$:=$")

## Lineare Strukturen
- Sequenz $\{x_1,\ldots,x_n\}$ von beliebigen Datenobjekten $x_i$
- Typische Operationen (Beispiele)
  - Füge $y$ am Anfang / am Ende / hinter $x_i$ ein
  - Ersetze $x_i$ durch $y$
  - Entferne $x_i$

### Listen
- $L = \{x_1, \ldots, x_n\}$
- Zugriff auf beliebige Elemente $x_i$
  - Per Index (random access)
    - Get(i)
  - Per Marker (sequential access)
    - GetFirst()
    - GetNext()
    - GetPrevious()

Random access:
- Typischerweise implementierung durch Arrays L[]
- Get(i) = L[i]
- Nachteile:
  - Elemente löschen erzeugt Lücken oder alle Elemente mit höherem Index müssen verschoben werden (garbage collection)
  - Statische Obergrenze für Listenlänge

Sequential Access:
- Implementierung durch Pointer oder Container
- Marker zeigt auf aktuelle Position
- Nachteil: Elementzugriff erfordert lineare Suche
  - kann meistens durch "for each" vermieden werden
- Vorteil: Beliebiges Erweitern und Löschen

Spezifikation:
- Wertebereich: $L = \{\} \cup W \cup W^2 \cup W^3 \cup \ldots$
- Create: $\:\:\:\:\:\:\:\:\:\:\:\:\: \rightarrow L$
- Get: $L \:\:\:\:\:\:\:\:\:\:\:\:\:\: \rightarrow W$
- Next: $L \:\:\:\:\:\:\:\:\:\:\:\: \rightarrow L$
- Insert: $W \times L \rightarrow L$
- Delete: $L \:\:\:\:\:\:\:\:\: \rightarrow L$
- Reset: $L \:\:\:\:\:\:\:\:\:\:\: \rightarrow L$
- Empty: $L \:\:\:\:\:\:\:\:\:\: \rightarrow Bool$
- IsLast: $L \:\:\:\:\:\:\:\:\:\:\: \rightarrow Bool$

<u>Achtung:</u> der Marker beschreibt einen *Zustand*, was sich mit *funktionalen* Axiomen schlecht formulieren lässt.

<u>Standard-Trick:</u> Führe ein zusätzliches Prädikat _Insert*_ ein, das aber keine eigene Listen-Funkttion darstellt:

```text
Insert(x,Insert(y,Insert(z,Create())))
    = {X,y,z}

Insert*(x,Insert(y,Insert(z,Create())))
    = {x,Y,z}

Insert*(x,Insert*(y,Insert(z,Create())))
    = {x,y,Z}
```