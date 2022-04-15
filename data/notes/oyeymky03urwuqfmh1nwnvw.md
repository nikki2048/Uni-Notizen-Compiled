
## Deterministische Endliche Automate

---

**Sprache:** Menge aller Wörter, die einen Automaten zum Endzustand bringen
* *erkannte Sprache:* $L(A) := \{w \in \sum^* |$ A akzeptiert $w\}$

* Sprache L DFA-erkennbar: es gibt ein A mit L = L(A)

**Operationen auf Sprachen:**

Durchschnitt: $K \cap L$ <br>
Vereinigung: $K \cup L$ <br>
Differenz: $K \backslash L$ <br>

Komplement in $\sum^*$: <br>
$\bar L := \sum^* \backslash L$

Verkettung: $K,L \subseteq \sum^*$: <br>
$KL := \{uv | u \in K, v \in L\} \subseteq \sum^*$

**Potenzen:**
* $L^n$ für $n \in \mathbb{N}$
* $L^0 := \{\epsilon\}$
* $L^{n+1} := L^nL$

**Iteration (Kleene-Stern):**

* $L^* = \bigcup\limits_{n \in \mathbb{N}} L_n$
* $\{\epsilon\} \in L^0 \subseteq L^n$ 

---

**Alphabet:** Buchstaben, Symbole (Σ), Σ* Menge aller Wörter über Alphabet

**Wort:** Endliche Folge von Zeichen, Ɛ: leeres Wort

1. Präfix: Anfangsstück des Wortes v = uw
2. Infix: Mittelstück des Wortes v = wuw'
3. Suffix: Endstück des Wortes v = wu


**Lauf:** Auswertung eines Wortes auf einem Automaten <br>
* Folge von ($r_0,a_1,r_1,a_2,\ldots r_{n-1},r_n,a_n$) <br> auf Wort $w =(a_1,a_2, \ldots, a_n)$
* für jedes $w \in \sum^*$ gibt es **einen** lauf

*akzeptierender Lauf* : $r_n \in F$ (Menge der Endzustände)


 

Wichtige Symbole
 
 1. $\sum$* : Menge aller Wörter eines Alphabets 
 2. $\epsilon$ : leeres Wort 
 3. $|w|$: Länge des Wortes
 4. $|w|_a$ Häufigkeit des Buchstabens in einem Wort

---

**DFA's Formal**: 5-Tupel (Q, Σ, δ, q0, F)


1. Q: Menge aller Zustände 
2. Σ:  Eingabealphabet 
3. δ: Q x Σ -> Q (Transitionsfunktion)
4. q0 ∈ Q:  Anfangszustand 
5.  F:  Menge aller Endzustände 

---
**Wichtig:**

* leere Sprache ∅ hat **kein** Inhalt
* Sprache {Ɛ} hat **ein** Element (das leere Wort) als Inhalt
---









