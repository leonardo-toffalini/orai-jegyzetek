### 1.
Legyen adott egy $n \times n$ pixelből álló fekete-fehér kép. Szeretnénk a képen a bal felső saroktól a jobb alsó sarokig egy jobbra-lefele haladó határvonalat húzni úgy, hogy a vonaltól jobbra-felfele eső fekete, valamint a vonaltól balra-lefele eső fehér pixelek számának az összege a lehető legkisebb legyen. Oldjuk meg ezt a feladatot $O(n^{2})$ időben.

**Megoldás:**
Tároljuk egy $A$ mátrixban a részmegoldásokat, azaz $A[i, j]$ legyen az $i \times j$ pexeles képeknek a megoldása.
(Az $n\times n$ pixeles képet a következőképp teároljuk: legyen *image* egy $n \times n$-es mátrix, melynek ott van $1$-es értéke, ahol a képnek fekete pixele, és legyen *image_flip* egy $n \times n$-es mátrix, aminek ott van $1$-es értéke, ahol a képnek fehér pixele. Mindenhol máshol $0$ van mindkét mátrixban.)

Az algoritmus induljon el az $A$ mátrix bal-felső sarkából és egy általános $A[i, j]$ elemre hasonlítsa össze annak az értékét ha felülről jön a határvonal vagy ha balról jön a határvonal. Tehát $A[i-1, j]$ és $A[i, j-1]$ értékét kell valahogyan összehasonlítani.
Ekkor legyen 
$$
A[i, j] := \min \left\{  A[i-1, j] + \operatorname{sum}\{ i\text{-edik sorban } j\text{-től balra lévő fehér cellák} \}, A[i, j-1] + \operatorname{sum}\{ j\text{-edik oszlopban } i\text{-től felfele lévő fekete cellák} \}  \right\}
$$
A szóban leírt summákat úgy tudjuk megvalósítani, hogy a képet egyesekkel és nullásokkal tároljuk, ahol $1$ jelöli a feketét és $0$ a fehér cellát. Ekkor az $i$-edik sorban $j$-től balra lévő fehér cellák száma:
$$
\sum_{k=1}^{j} \lvert A[i, k] -1 \rvert 
$$
mivel $\lvert A[i, k] -1 \rvert = 1 \impliedby A[i,k] = 0$  és $\lvert A[i, k] - 1 \rvert = 0 \impliedby A[i, k] = 1$.
A $j$-edik oszlopban $i$-től felfelé lévő fekete cellák száma:
$$
\sum_{k=1}^{i} A[k, j]
$$
Az algoritmus futásának végén $A[n, n]$ tartalmazza az értékét az optimális határvonalnak, ha magát a határvonalat szeretnénk megadni, akkor minden cellában egy szám kettest fenntartunk, melynek az első eleme a határvonal értékét jelöli, a második eleme a hozzá tartozó határvonalnak őt megelőző elemét.

```python
import numpy as np

def sol(image: np.ndarray) -> int:
	for i in range(n):
		for j in range(n):
			A[i][j] = min(A[i-1][j] + np.sum(np.abs(image[i][:j]) - 1), A[i][j-1] + sum(image[:i][j-1]))
	return A[-1][-1]
```

### 2.
Van egy $n$ érték bankónk, amit szeretnénk felváltani. A postán, ahol váltani szeretnénk, kifogyhatatlan mennyiségben vannak $e_{1}, e_{2}, \dots, e_{m}$ értékű pénzérmék. Adj $O(nm)$ idejű algoritmust, amely eldönti, hogy hányféleképpen tudják felváltani a bankónkat, ha a pénzérmék sorrendje nem számít! Például $n=5$ és $1, 2, 3$ lehetséges pénzérmék esetén $5$-féle váltás van: $\{  1, 1, 1, 1, 1 \}, \{ 1, 1, 1, 2 \}, \{ 1, 1, 3 \}, \{ 1, 2, 2, \}, \{ 2, 3 \}$.

**Megoldás:**
Tartsunk fenn egy $A[0:n]$ tömböt, ahol $A[j]$ azt jelöli, hogy $j$ értékű bankót hányféleképpen lehet felváltani.
A megoldást dinamikus programozással adjuk. Az $A$ tömbnek a nulladik elemét inicializáljuk $1$-re, mert $0$ értékű bankót egy féleképpen tudunk felbontani.
Menjünk végig a pénzérméken $i$ iterátorral és minden pénzérmére menjünk végig $A$ tömbön $j$ iterátorral. Ha $e_{i} \leq j$, akkor tudunk úgy váltani, hogy egy $e_{i}$ pénzérmét hozzáveszünk a $(j-e_{i})$ értékű bankó váltásához. Tehát $j$ értékű bankót már $A[j-e_{i}]$ féle képpen is tudjuk váltani.

A következő egy rövid python program, hogy érthetőbb legyen az algoritmus.

```python
def exchange(n, coins):
	A = [0] * (n + 1)                   # inicializalunk egy (n+1) hosszu csupa nulla tombot
	A[0] = 1                            # a nulladik elem inicializalva 1-re
	for i in range(len(coins)):
		for j in range(n+1):
			if coins[i] <= j:
				A[j] += A[j - coins[i]] # lenyeges lepes
	return A[-1]                        # utolso elemet visszaadjuk
```


related: [[AlgTerv 1]]