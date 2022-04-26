

## Überblick
**Hierarchische Datenstruktur:**
- Zusammenfassung von Gruppen
- Eindeutige Schachtelung [1:n]

**Typische Anwendungen:**
- Such / Entscheidungsprobleme
- Strukturierte Aufzählung
- Komplexitätsreduktion


### Definition
- Menge von **Knoten** $V = \{ v_1, \ldots, v_2 \}$, wobei $v_i \in W$ beliebiger Datentyp.
- Menge von **Kanten** $E = \{(a_1,b_1), \ldots ,(a_m,b_m) \}$, wobei $a_i,b_i \in W$, beliebiger Datentyp
- Falls $(a,b) \in E$, dann ist:
  - $v_a$ Vorgänger von $v_b$
  - $v_b$ Nachfolger von $v_a$
<br><br>

- Eine Folge von Kanten $(i_1,i_2),(i_2,i_3), \ldots , (i_{k1}, i_k)$ heißt **Pfad** von $v_{i1}$ nach $v_{ik}$
- Für $i_1 = i_k$ ist dieser Pfad ein **Zyklus**
- Ein Baum $B = (V,E)$ besteht aus einer Menge von Knoten $V$ und einer Menge von Kanten $E$, so dass gilt:
  - Es gibt keine Zyklen
  - Jeder normale Knoten hat genau einen Vorgänger
  - Es existiert genau ein Wurzelknoten, der keinen Vorgänger hat
<br><br>

- Der eine Knoten ohne Vorgänger heißt **Wurzelknoten**
- Knoten ohne Nachfolger heißen **Blätter**
- Knoten mit Nachfolgern heißen **innere Knoten**
<br><br>

- Die **Tiefe** eines Knotens ist gleich der Länge des zugehörigen Pfades von der Wurzel
- Die **Höhe** eines Baumes ist gleich der Tiefe des tiefsten Knotens
- Der **Grad** eines Knotens ist die Anzahl seiner Nachfolger


### Abgeleitete Eigenschaften
- Für jeden Knoten existert ein eindeutiger Pfad, der ihn mit dem Wurzelknoten verbindet. 
- Jeder Knoten ist Wurzelknoten eines zugehörigen **Sub-Baumes**

### Balancierter Baum
- Seien $w_1, \ldots w_k$ die Nachfolger des Knotens v, dann gilt für alle $w_i$: <br>
>height(subtree($w_i$)) $\leq$ height(subtree(v))-1
- Gilt außerdem <br> 
>height(subtree($w_i$)) $\geq$ height(subtree(v))-2

dann heißt der Baum **balanciert**

### Vollständiger Baum
- Gilt für alle Knoten v mit Nachfolgern $w_1, \ldots w_k$ eines Baumes: <br>
> height(subtree($w_i$)) = height(subtree(v))-1

so heißt er **vollständig**.


## Datentyp: Binärbaum

- Knotentyp: beliebig
- Create  : $\rightarrow$ Tree
- Node : Tree $\times$ Val $\times$ Tree $\rightarrow$ Tree
- Left : Tree $\rightarrow$ Tree
- Right: Tree $\rightarrow$ Tree
- Value: Tree $\rightarrow$ Val
- Empty: Tree $\rightarrow$ Bool

## Implementierungsmöglichkeiten

### Pointer

#### Einfach:
- Implementieren mit Value, Left und Right Referenzen

#### Doppelt:
- Implementieren mit Value, Left und Right Referenzen **+ Parent Referenzen**


### Array-Implementierung
- Vollständige Bäume
- N(k) = Anzahl der Knoten der Tiefe k
- N(k) = $2^k$
- Speichere die Knoten der Tiefe k in den Array-Einträgen $A[2^k \ldots 2^{k+1}-1]$
>Jeder Knoten A[i] hat Nachfolger A[2i] A[2i+1]


## Arithmetische Terme

- Term = Variable  oder Summe von Produkten
- Produkt = Multiplikation von Termen

## Traversierung
> vor den Argumenten $\rightarrow$ **Präfix** <br>
  zwischen den Argumenten $\rightarrow$ **Infix** <br>
  nach den Argumenten $\rightarrow$ **Postfix**


### Traversierungsstrategien

#### Depth - First (Tiefensuche): 


#### Breadth-First:
- Zähle die Knoten nach ihrer Tiefe sortiert auf, d.h. alle Knoten mit Tiefe **k** vor dem ersten Knoten mit Tiefe **k+1**
- Finde den kürzesten Pfad

## Suchbäume 
- Bäume ermöglichen wesentlich schnelleren Zugriff auf Elemente als bei linearen Strukturen
- Die Tiefe+1 eines Knoten beschreibt die Anzahl der Zugriffe, um ihn zu finden. 

### Suchen/Einfügen in Suchbäumen: 
- Sortierung in Baum: 
> max(Left(T)) $\leq$ Value(T) $<$ min(Right(T))

### Löschen
<u> **Fallunterscheidung** </u>: 
- <u>Blatt-Knoten </u>
  - direktes Löschen

- <u> nur ein Nachfolger </u>
  - Teilbaum an die Stelle des gelöschten Knotens anfügen

- <u> zwei Nachfolger </u>
  - min(Rechten Teilbaum)
  - max(Linken Teilbaum)
- an die Stelle des Knotens kopieren und dieses Löschen

## Anzahl der Knoten
- **Minimale** Anzahl von Knoten in einem Binärbaum der Höhe
- **$h: N_{min}(h) = h+1$**
- **Maximale** Anzahl: **$N_{max}(h) = 2^{h+1}-1$**

## Höhe eines Baumes

- Für n Knoten ist die **maximale** Höhe des Binärbaumes: 
- **$H_{max}(n) = n-1$**
- Die **minimale** Höhe: **$H_{min}(n) = \lceil \log_2(n+1) \rceil -1$**

## Balancierter Baum - Höhe/Knotenanzahl

- Minimale Anzahl von Knoten:
- **$N_{bal,min}(h) \geq \sqrt{2^h}$**

- Maximale Höhe für n Knoten:
- **$H_{bal,max}(n) \leq \lceil \log(n)/\log(\sqrt{2}) \rceil$**



## k-dimensionale Suchbäume
- Verwende $2^k$-näre Bäume
  - Quadtree ($R^2$)
  - Octree ($R^3$)

- kD-Bäume (k-dimensionale Binärbäume)

### Quadtree

- Aufspaltung einer Fläche in mehrere Kästchen

![Quadtree-Aufspaltung](/assets/images/Quadtree.png){width: 60%, max-width: 645px}

## kD-Bäume
- Datentyp: Binärbaum
- Jeder Knoten enthält einen k-dim. Wert
- Sortierung für Knoten **T** der Tiefe **h**:
> $max_h$(Left(T)) $\leq$ $Value_h(T)$  < $min_h(Right(T))$
- Aufteilung in x und y Werte

![kd-Baum](/assets/images/kD-Baum.png){width: 60%, max-width: 645px}
