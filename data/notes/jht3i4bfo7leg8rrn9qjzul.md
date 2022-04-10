
- Sequenz $\{x_1,\ldots,x_n\}$ von beliebigen Datenobjekten $x_i$
- Typische Operationen (Beispiele)
  - Füge $y$ am Anfang / am Ende / hinter $x_i$ ein
  - Ersetze $x_i$ durch $y$
  - Entferne $x_i$

## Listen
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

