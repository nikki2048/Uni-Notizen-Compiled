
## Überblick

- Warteschlange mit Vordrängeln
- Einfügen am Ende der Schlange 
- Jedes Element hat eine Priorität
- Deq() liefert immer das Element mit der *höchsten* Priorität


### Spezifikationen

- Elemente: $X \in W' = W \times R$
- Wertebereich: $L = \{\} \cup W' \cup W'^2 \cup W'^3 \cup \ldots$
- Create: $\rightarrow L$
- Enq: $W' \times L \rightarrow L$
- **Enqq** $W' \times L \rightarrow L$
- Deq: $L \rightarrow L$   
- Get: $L \rightarrow W'$
- Empty: $L \rightarrow Bool$



### Heap-Bedingungen

**<u>Idee:</u>**

 Front und back Pointer/Counter nutzen 
- Binäre Bäume: Schneller Elementzugriff
- Array- Implementierung vollständiger Bäume kombiniert die beiden Vorteile.


- Neue Sortier-Vorschirft der Knoten im Baum: 
- Für alle Knoten $T = Node(L,X,R$ muss gelten: 
    
    
    > max_prio(L) $\leq$ prio[X] <br>
     max_prio(R) $\leq$ prio[X]

- Wurzelknoten: Element mit der maximalen Priorität
- Sortierung der Elemente nur entlamg der Pfade im Binärbaum

### Effiziente Implementierung

<u>Arrayimplementierung:</u>

- Front Pointer bei front = 1 fest
- Element mit max. Priorität in S[1]
- Back-Pointer variable 
- Einfügen in S[back]

> Priorisierte Binärbaumbeziehungen: <br>
$(i) S[i] \rightarrow S[2*i], S[2*i+1]$ <br>
mit <br>
$(ii) prio(S[i]) \geq max(prio(S[2i]), prio(S[2i+1])$

![Array-Implemetierung](/assets/images/Prioritaetsschlangen.png){width: 100%, max-width: 645px}
    
#### Einfügen in eine Prioritätschlangen
- Falls die obige Bedingung nicht erfüllt ist wird das Element soweit nach vorne getauscht bis es an der richtigen Position ist

>  $Index$ (des aktuellen Knotens)$/2$ um auf den Elternknoten zu gelangen

#### Löschen aus einer Prioritätschlange

- Vorderstes Element wird gelöscht
- Letztes Element wird nach vorne kopiert
- Von Vorne nach Hinten vertauschen damit obige Bedingung wieder erfüllt ist

> $2^{Index}$ bzw. $2^{Index+1} -1$ des aktuellen Elementes, um auf die Kindknoten zu gelangen


