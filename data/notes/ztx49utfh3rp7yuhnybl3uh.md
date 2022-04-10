
## Aufzählungstypen (Bool)
0-Dimensional

- Wertebereich: $\{true, false\}$
- $\neg : bool \times bool \rightarrow bool$
- $\land : bool \times bool \rightarrow bool$
- $\lor : bool \times bool \rightarrow bool$

$\neg \: true = false, \neg \: false = true$

| $\land$ | True | False |
| ------- | ---- | ----- |
| **True**    | True | False |
| **False**   | False| False |
<br>

| $\land$ | True | False |
| ------- | ---- | ----- |
| **True**    | True | True  |
| **False**   | True| False  |

## Skalare Typen (Integer)
1-Dimensional

- Wertebereich: $\mathbb{Z} = \mathbb{N}_{+} \cup \{0\} \cup -\mathbb{N}_{+}$
- $+ : \mathbb{Z} \times \mathbb{Z} \rightarrow \mathbb{Z}$
- $- : \mathbb{Z} \times \mathbb{Z} \rightarrow \mathbb{Z}$
- $- : \mathbb{Z} \rightarrow \mathbb{Z}$
- $\times : \mathbb{Z} \times \mathbb{Z} \rightarrow \mathbb{Z}$
- $\div : \mathbb{Z} \times \mathbb{Z} \rightarrow \mathbb{Z}$

Axiome:
- $+(0,b) = b$
- $+(a+1,b) = +(a,b)+1 \:\:\:\:$     (count down to 0)
- $+(a-1,b) = +(a,b)-1 \:\:\:\:$     (count up to 0)
<br><br>
- $-(b,b) = 0$
- $-(a+1,b) = -(a,b)+1$
- $-(a-1,b) = -(a,b)-1$
<br><br>
- $-(b) = -(0,b)$
<br><br>
- $\times(0,b) = 0$
- $\times(a+1,b) = +(\times(a,b),b)$
- $\times(a-1,b) = -(\times(a,b),b)$
<br><br>
- $\div(a,0) = \text{ERR}$
- $\div(a,b) = 0$ if $|a| < |b|$
- $\div(a+b,b) = \div(a,b)+1$
- $\div(a-b,b) = \div(a,b)-1$

## Lineare Strukturen
- Beliebige Sequenz von Basisobjekten (skalare / zusammengesetzte Typen) mit variabler Länge
  - Arrays
  - Listen (einfch / doppelt verkettet)
  - Queue (FIFO)
  - Stack (LIFO)
- Unterscheiden sich im Wesentlichen in der Zugriffsfunktionalität

### Beispiel (Sequenz):
- Wertebereich: $W = \{\} \cup N \cup N^2 \cup N^3 \cup \ldots$
  - $\neq 2^N$
- Create: $\:\:\:\:\:\:\:\:\:\:\:\:\:\:\:\:\:\: \rightarrow W$
- Append: $N \times W \rightarrow W$
- Remove: $N \times W \rightarrow W$

Axiome:
- Create() = $\{\}$
- Append($X,\{y_1, \ldots, y_n\}$) = $\{y_1,\ldots,y_n,X\}$
  - Append(z,Append(y,Append(x,Create()))) = $\{x,y,z\}$
- Remove(x,Create()) = Create()
- Remove(x,Append(x,z)) = z
- Remove(x,Append(y,z)) = Append(y,Remove(x,z)) *if x $\neq$ y*

## Baumstrukturen
- Hierarchische Strukturen
- Mutter / Kind-Beziehung [1:n]
- Keine Zyklen
- Eindeuttige Vorfahren

Axiome:
- Insert(x,Create()) = Node(Create(),x,Create())
- Insert(x,Node(left,x,right)) = Node(left,x,right)
- Insert(x,Node(left,y,right)) = <br>
    if x < y: Node(Insert(x,left), y, right) <br>
    if x > y: Node(left,y,Insert(x,right))
