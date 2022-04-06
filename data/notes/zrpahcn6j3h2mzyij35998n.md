## Strukturen und Verknüpfungen
**Definition:** Eine *Verknüpfung* auf einer Menge *M* ist eine Abbildung
$$\begin{equation}
    M \times M \rightarrow M
\end{equation}$$
Eine *algebraische Struktur* ist eine Menge mit ein oder mehreren Verknüpfungen.

**Beispiele:**
- \- : $\mathbb{Z} \times \mathbb{Z} \rightarrow \mathbb{Z}, (x,y) \mapsto x - y$ istt eine Verknüpfung auf $\mathbb{Z}$.
- $\land$ ist eine Verknüpfung auf $B = \{0,1\}$ (wenn wir 0 und 1 als Wahrheitswerte definieren, und $\land$ durch die zugehörige Wahrheitstafel definiert ist).
- $7 \mathbb{Z} = \{7a \mid a \in \mathbb{Z}\} = \{\ldots, -14, -7, 0, 7, 14, \ldots\}$

**Schreibweise:**
Es seien $M$ eine Menge, $\bullet$ eine Verknüpfung auf $M, m \in M$, und $A,B \subseteq M$.
- $m \bullet A := \{m \bullet a \mid a \in A\} \subseteq M$
- $A \bullet m := \{a \bullet m \mid a \in A\} \subseteq M$
- $A \bullet B := \{a \bullet b \mid a \in A, b \in B\} \subseteq M$

## Monoide
**Definition:** Es sei $M$ eine Menge mitt einer Verknüpfung:
$$\begin{equation}
    \bullet : M \times M \rightarrow M, (x,y) \mapsto x \bullet y
\end{equation}$$
Wir nennen $(M, \bullet)$ ein *Monoid*, wenn folgende Axiome gelten:
1. $(x \bullet y) \bullet z = x \bullet (y \bullet z)$ für alle $x,y,z \in M$
2. Es existiert ein $e in M$ mit $e \bullet x = x = x \bullet e$ für alle $x \in M$ <br>
Das Monoid heißt *abelsch* oder *kommutativ*, wenn zusätzlich gilt:
3. $x \bullet y = y \bullet x$ für alle $x,y \in G$.

Man nennt 1. das Assoziativgesetz und 3. das Kommutativgesetz.

**Bemerkung:** Das Element $e$ in 2. ist eindeutig und wird das *neutrale Element* von $M$ genannt. 

**Beispiele:**
Es sei $A$ eine beliebige Menge, $B := \{0,1\}$.
- $(\mathbb{N}, +)$ ist kein Monoid, da 2. nicht gilt. 
- $(\mathbb{Z}, -)$ ist kein Monoid, da 1. nicht gilt.
- $(\mathbb{N}_0, +)$ ist ein abelsches Monoid mit neutralem Element 0.
- $(\mathbb{R}, \cdot)$ ist ein abelsches Monoid mit neutralem Element 1.
- $(B, \land)$ ist ein abelsches Monoid mit neutralem Element 1.

## Inverse und Einheiten
**Definition:** Es seien $(M, \bullet)$ ein Monoid mit neutralem Element $e$ und $a \in M$.
- Gibt es $b \in M$ mit $a \bullet b = e$, so heißt $a$ *rechtsinvertierbar* und $b$ *rechtsinvers* zu $a$ bzw. $b$ ein *Rechtsinverses* von $a$.
- Gibt es $b \in M$ mit $b \bullet a = e$, so heißt $a$ *linksinvertierbar* und $b$ *linksinvers* zu $a$ bzw. $b$ ein *Linksinverses* von $a$.
- Ist $a$ sowohl links- als auch rechtsinvertierbar, so heißt $a$ eine *Einheit*. 
- Gibt es $b \in M$ mit $b \bullet a = e = a \bullet b$, so heißt $a$ *invertierbar* und $b$ *invers* zu $a$ bzw. $b$ ein *Inverses* von $a$.

## Gruppen
**Definition:** Ein Monoid $(G, \bullet)$, in dem alle Elemente invertierbar sind, heißt *Gruppe*. D.h. in einer Gruppe gilt:

(M3) Für alle $x \in G$ existiert $x' \in G$ mit $x \bullet x' = e = x' \bullet x$

*M3 = Monoide 3. Axiom*

**Beispiele:**
- $(\mathbb{Z}, +)$ istt eine abelsche Gruppe.
- $(\mathbb{N}_0, +)$ ist keine Gruppe, da (M3) nicht gilt. 
- $(\mathbb{R}, \cdot)$ ist keine Gruppe, da (M3) nicht gilt.
- $(\mathbb{R} \backslash \{0\}, \cdot)$ und $(R_{>0}, \cdot)$ sind abelsche Gruppen. 

## Untergruppen 