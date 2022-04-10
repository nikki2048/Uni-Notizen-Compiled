
Abstrakte Datentypen spezifizieren *Form und Funktionalität* der zu verarbeitenden Daten.

Beispiel (Addition zweier Zeiten):
- Datenobjekte, Datenfelder
  - Zeit: `hh:mm:ss`
- Funktionen:
  - Add: `Zeit` $\times$ `Zeit` $\rightarrow$ `Zeit`
- Axiome:
  - `Add` $([h_1, m_1, s_1], [h_2, m_2, s_2]) =$ <br>
  $[(h_1 + h_2 + (m_1 + m_2 + (s_1 + s_2) / 60) / 60) \: \% \: 24$, <br> $(m_1 + m_2 + (s_1 + s_2) / 60) \: \% \: 60$, <br> $(s_1+s_2)) \: \% \: 60]$

## Datentypen
- Aufzählungstypen (bool, enum)
  - 0-Dimensional
  - Endlicher Wertebereich (vollständige Spezifikation durch Tabellen möglich)
  - [[Beispiel | 2-semester.dsal.kapitel-1.datenstrukturen.abstrakte-datentypen.beispiele#aufzählungstypen-bool]]
- Skalare Typen (char, int, float, ...)
  - 1-Dimensional
  - [[Beispiel | 2-semester.dsal.kapitel-1.datenstrukturen.abstrakte-datentypen.beispiele#skalare-typen-integer]]
- Zusammengesetzte Typen (struct, class)
  - n-Dimensional
  - Endliche / Feste zusammengesetzte Typen
    - k-dim. Vektoren (Tupel)
    - Addressen-Eintrag
- Lineare Strukturen (list, queue, stack)
  - [1:1] Beziehung
  - [[Beispiel | 2-semester.dsal.kapitel-1.datenstrukturen.abstrakte-datentypen.beispiele#lineare-strukturen]]
- Bäume
  - [1:n] Beziehung
  - [[Beispiel | 2-semester.dsal.kapitel-1.datenstrukturen.abstrakte-datentypen.beispiele#baumstrukturen]]
- Graphen - n-m Strukturen
  - [n:m] Beziehung
  - Beliebige *topologische* Struktur
  - Nachbarschafsbeziehungen zwischen Knoten
  - Wichtige Spezialfälle:
    - Planare Graphen
    - Gerichtete Graphen
    - Zyklenfreie Graphen

## Warum abstrakt?
- Keine Festlegung, wie die jeweiligen Funktionen *implementiert* werden ("Transparenz")
- Axiome beschreiben *statische* Beziehungen ("$=$" vs. "$:=$")