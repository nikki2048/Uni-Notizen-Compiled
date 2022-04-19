

//TODO: Ordentliche Gliederung

**Sprache:** Menge aller Wörter, die einen Automaten zum Endzustand bringen



**Alphabet:** Buchstaben, Symbole (Σ), Σ* Menge aller Wörter über Alphabet

**Wort:** Endliche Folge von Zeichen, Ɛ: leeres Wort

**Lauf:** Auswertung eines Wortes auf einem Automaten

 

| Wichtige Symbole| Beschreibung |
| ----------- | ----------- |
| $\sum$* | Menge aller Wörter eines Alphabets |
| $\epsilon$ | leeres Wort |

---

**DFA's Formal**: 5-Tupel (Q, Σ, δ, q0, F)


1. $Q$: Menge aller Zustände 
2. $\sum$:  Eingabealphabet 
3. $\varsigma$: Q x Σ -> Q (Transitionsfunktion)
4. $q_0 \in Q$:  Anfangszustand 
5.  $F$:  Menge aller Endzustände 

---
**Wichtig:**

* leere Sprache $\emptyset$ hat **kein** Inhalt
* Sprache $\{\varepsilon\}$ hat **ein** Element (das leere Wort) als Inhalt
---