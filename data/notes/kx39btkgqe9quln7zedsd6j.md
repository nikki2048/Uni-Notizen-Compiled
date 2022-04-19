
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
