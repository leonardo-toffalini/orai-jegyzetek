### 1. Feladat

Adjuk meg kézzel kiszámítva az $$A =  \left[\matrix{ 
2 & -1 & 3\cr
4 & 2 & 1 \cr
-6 & -1 & 2
}\right]$$

mátrix $LU$ felbontását, miután ellenőriztük, hogy létezik.

***Sol***.:
$$
\Delta_{1} = 2 \neq 0
$$
$$
\Delta_{2} = \det \begin{bmatrix}
2 & -1 \\
4 & 2
\end{bmatrix}
= 2 \cdot 2 + 4 \cdot 1 = 8 \neq 0
$$
$$
\Delta_{3} = \det
\begin{bmatrix}
2 & -1 & 3 \\
4 & 2 & 1 \\
-6 & -1 & 2
\end{bmatrix} = 48 \neq 0
$$
Tehat letezik LU-felbontas, most szamitsuk is ki!

$$
A = \begin{bmatrix}
2 & -1 & 3 \\
4 & 2 & 1 \\
-6 & -1 & 2
\end{bmatrix} = 
\begin{bmatrix}
l_{11} & 0 & 0 \\
l_{21} & l_{22} & 0 \\
l_{31} & l_{32} & l_{33}
\end{bmatrix}
\cdot
\begin{bmatrix}
1 & u_{12} & u_{13} \\
0 & 1 & u_{23} \\
0 & 0 & 1
\end{bmatrix} = L \cdot U
$$
$$
\implies L = 
\begin{bmatrix}
2 & 0 & 0 \\
4 & 4 & 0 \\
-6 & -4 & 6
\end{bmatrix}
, \quad
U =
\begin{bmatrix}
1 & -\frac{1}{2} & \frac{3}{2} \\
0 & 1 & -\frac{5}{4} \\
0 & 0 & 1
\end{bmatrix}
$$


### 2. Feladat
Igazoljuk a felsőháromszög-mátrixok alábbi tulajdonságait! (alsóháromszögmátrixokra analóg)

1. Két felsőháromszög-mátrix szorzata szintén felsőháromszög-mátrix.
Csoportot alkotnak es ez volt lin alg oran.
2. Determinánsa a főátlóbeli elemek szorzata.
Ez az egyetlen permutacio amiben nincsen $0$ elem.
3. Sajátértékei éppen a főátlóban lévő elemei a megfelelő multiplicitással.
Karakterisztikus polinomja: $\mathcal{P}_{A} = \det (xI - A)$ mely szinten felso/also haromszog matrix, tehat a determinansa $= \mathrm{Tr}A = \Pi_{i = 1}^{n} (x - a_{ii})$, es mivel a sajatertekek pontosan a karakterisztikus polinom gyokei, ezert a sajatertekek $a_{ii}$ elemek.
4. Egy felsőháromszög-mátrix inverze szintén felsőháromszög-mátrix.
Csoportot alkotnak es ez volt lin alg oran.

### 3. Feladat

Előadáson láttuk, hogy az $LU$ felbontásban az $U$ mátrix főátlóbeli elemei 1-esek voltak, míg az $L$ mátrix főátlóbeli elemei (általában) nem. Egy $A$ mátrix $LU$ felbontásának segítségével mutassuk meg, hogy létezik egy másik $\tilde LDU$ felbontás, ahol $\tilde L,U$ főátlóbeli elemei 1-esek, $D$ pedig diagonális. 

***Sol***.:
Legyen $\tilde{L}D = L$
$$
D = \begin{bmatrix}
d_{11} & 0 & \dots & 0 \\
0 & d_{22} & \dots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & d_{nn}
\end{bmatrix}
$$
Tovabba jelolje $\tilde{l}_{j}$ az $\tilde{L}$ $j$-edik sorat es $l_{j}$ az $L$ $j$-edik sorat. Ekkor legyen $\tilde{l}_{j} \cdot d_{jj} = l_{j}$, es $d_{jj} = l_{jj}$, ezekkel az ertekekkel $\tilde{L}$-nek mar valoban csupa $1$-es lesz a foatlojaban.

### 4. Feladat
Adjuk meg az 1. feladatbeli mátrix $LDU$ felbontását.

***Sol***.:
$$
\implies L = 
\begin{bmatrix}
2 & 0 & 0 \\
4 & 4 & 0 \\
-6 & -4 & 6
\end{bmatrix}
, \quad
U =
\begin{bmatrix}
1 & -\frac{1}{2} & \frac{3}{2} \\
0 & 1 & -\frac{5}{3} \\
0 & 0 & 1
\end{bmatrix}
$$
$$
\implies \tilde{L} = 
\begin{bmatrix}
1 & 0 & 0 \\
2 & 1 & 0 \\
-3 & -1 & 1
\end{bmatrix}
, \quad
D = 
\begin{bmatrix}
2 & 0 & 0 \\
0 & 4 & 0 \\
0 & 0 & 6
\end{bmatrix}
$$

### 5. Feladat

Tegyük fel, hogy $A$ egy szimmetrikus pozitív definit mátrix. Hogyan tudjuk meghatározni a Cholesky-felbontását az $LDU$ felbontás segítségével, mi az összefüggés a kettő között?

### 6. Feladat
 
 Legyen   $$A=\left[\matrix{2 & -1 & 0\cr
                          -1 & 2 & -1\cr 
                          0 & -1 & 2}\right]$$

Ellenőrizzük, hogy az $A$ mátrixnak lesz Cholesky-felbontása, majd adjuk is meg!

***Sol***.:
Tudjuk, hogy $A \in \mathbb{R}^{n \times n}$ akkor es csak akkor pozitiv definit, ha minden bal felso aldeterminansa $> 0$.
Ellenorizzuk ezt le!

$$
\Delta_{1} = 2 > 0
$$
$$
\Delta_{2} = \det
\begin{bmatrix}
2 & -1  \\
-1 & 2
\end{bmatrix}
= 4 + 1 = 5 > 0
$$
$$
\Delta_{3} = \det A = 4 > 0
$$
Nem csak pozitív definit de szimmetrikus is, tehat teljesul a Cholesky-felbontas osszes kriteriuma.

### 7.* Feladat
(Összefüggés $L$ és $A$ gyöke közt a Cholesky-felbontásban)

Vezessük be egy négyzetes mátrix poláris felbontásának fogalmát. $B$ négyzetes mátrix felírható $B=UP$ (vagy $B=PU$) alakban, ahol $P=(B^*B)^{1/2}$. A mátrix gyöke értelmezhető, ugyanis $B^*B$ szimmetrikus pozitív szemidefinit mátrix, így a sajátérték felbontásban felírható $(B^*B)^{1/2}=VD^{1/2}V^*$ egy $V$ ortogonális mátrix mellett. A kapott $U=BP^{-1}$ (vagy $U=P^{-1}B$) mátrix unitér  (mutassuk meg). Ezt a felbontás hívjuk a $B$ mátrix poláris felbontásának.

Mutassuk meg, hogy egy $A$ szimmetrikus pozitív definit mátrix esetén a Cholesky-felbontásból származó $L$ mátrixra, ha $L=UP$ az $L$ mátrix poláris felbontása, teljesül hogy 

$$LU^{-1}=\sqrt{A}.$$

### 8. Feladat

Írjunk programot, amely egy adott négyzetes mátrixra kiszámolja a sarokdeterminánsait!

```python
import numpy as np

def compute_left_upper_determinants(A):
	n = A.shape[0]
	deltas = []
	for i in range(n):
		determinant = np.linalg.det(A[0:i, 0:i])
		deltas.append(determinant)
	return deltas
```


 ### 9. Feladat
 
 Írjunk programot, amely eldönti, hogy a mátrix szigorúan diagonálisan domináns-e vagy sem!

```python
import numpy as np

def sol_9(A):
	n = A.shape[0]
	for i in range(n):
		if 2*A[i, i] <= np.sum(np.abs(A[i, :], axis = 1):
			return False
	return True
```


### 10. Feladat

Írjunk programot, mely kiszámítja az alábbi egyenletrendszer megoldását a Cramer-szabály, illetve a Gauss-módszer segítségével! 

$$\left[\matrix{
8 & -6 & -7 & 5 \cr
2 & -1 & -2 & 1 \cr
6 & 1 & -9 & 2 \cr
-2 & -5 & 4 & 0 \cr
}\right]
\cdot
\left[ \matrix{
x_1 \cr x_2 \cr x_3 \cr x_4}\right] = \left[ \matrix{
-28 \cr -7 \cr-23 \cr 8}\right]
$$
```python
import numpy as np


def cramers_rule(A, b):
	n = A.shape[0]
	x = []
	det = np.linalg.det(A)
	for i in range(n):
		Ai = A.copy()
		Ai[:, i] = b
		xi = np.linalg.det(Ai) / det
		x.append(xi)
	return x


def gauss_elim(A, b):
	n = A.shape[0]
	
```


related: [[NumMod 1]]