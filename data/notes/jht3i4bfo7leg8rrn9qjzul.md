

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

**Satz**

Jede Liste hat die Form

Insert*($x_1,$ $\ldots$ Insert*($x_i$,Insert($x_i+1$, Insert($x_n$, Create()))))

<u> Beweis durch vollständige Induktion </u>
 - Induktionsanfang: Create()
 - Induktionsschritt: insert(), insert*()

--- 
Modifikation am Listenanfang für Einfüge und Löschungsoperationen: 

- **Anchor:** 
  - Erstes Element enthält keine Daten
  - Platzhalter für Einfüge-/Löschoperationen

### Doppelt verkettete Listen

- Flexibler Zugriff (upstream/ downstream)
  - Next(), Prev()

- Marker zeigt auf aktuelle Element
  - Delete-Operationen beziehen sich auf das aktuelle Element und nicht wie bisher auf das folgende Element
  - Insert-Operationen fügen ein Element *nach* dem aktuellen Element ein

- Spezialfälle an Listenenden
  - **Anchor** am Listenanfang 
  - **Sentinel** am Listenende 

## Warteschlangen 

- Einfügen nur am Ende
- Auslesen / Entfernen nur am Anfang
- "First in, first out" (FIFO-Prinzip)

Spezifikationen: 

- Wertebereich: $L = /{/} \cup W \cup W^2 \cup W^3 \ldots$
- Create: $\rightarrow L$
- Enq: $W \times L \rightarrow L$
- Deg: $L \rightarrow L$
- Get : $L \rightarrow W$
- Empty: $L \rightarrow Bool$

**Satz**

Jede Warteschlange hat die Form: 

Enq($x_n,$ Enq($x_{n-1}$,$\ldots$ Enq($x_1$, Create())))

<u> Beweis durch vollständige Induktion </u>

- Induktionsanfang: Create()
- Induktionsschritt: Jede andere Operation (Enq, Deq) erhält diese Form

**Pointer-Implementierung**:

- Interner Pointer entfällt
- Front und Back Pointer: 
  - Front Pointer: Anchor
  - Back Pointer: Sentinel

**Array-Implementierung:** 
- Da nur am Anfang eingefügt und am Ende ist keine *garbage collection* notwendig
- Maximale Länge wird als bekannt vorrausgesetzt

## Stack 
- Liste mit eingeschränkten Funktionalitäten 
- Einfügen nur am Anfang
- Auslesen / Entfernen nur am Anfang
- "Last in, first out"  (LIFO)

Spezifikationen: 
- Wertebereich: $L = /{ \cup W \cup W^2 \cup W^3 \cup/}$
- Create: $\rightarrow L $
- Push: $W \times L \rightarrow L$
- Pop: $L \rightarrow L$
- Top: $L \rightarrow W$
- Empty: $L \rightarrow Bool$


*Satz*
Jeder Stack hat die Form: 


Push($x_1$, Push($x_2$, $\ldots$ Push($x_n$, Create())))

<u> Beweis durch vollstädnige Induktion </u>
- Induktionsanfang: Create()
- Induktionsschritt: Jede andere Operation erhält diese Form

**Array-Implemetierung:**
- Da nur am Anfang eingefügt und gelöscht wird, ist keine garbage collection notwendig 
- Maximale Größe wird als bekannt vorausgesetzt

<u>Merke</u>
- rekursive Algorithmen lassen sich in der Regel mit einer Stack-Datenstruktur auch iterativ formulieren. 
- Das LIFO-Prinzip entspricht der Abarbeitungsreihenfolge der geschachtelten Prozeduren (was zuletzt aufgerufen wird, wird als erstes bearbeitet)
