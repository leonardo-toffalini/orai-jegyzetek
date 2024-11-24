## Normálegyenlet

Az $Ax = b$ egyenlet $\| \cdot \|_2$ szerinti legjobb megoldása, azaz a $b$ vektor vetülete $\operatorname{ran}(A)$-ra. Ekkor az $Ax - b$ hibavektor merőleges az $A$ képterére, azaz $A^*$ magjában van, tehát
$$
A^*(Ax -b) = 0.
$$

### 1. Feladat

Legyen
$$
A = \begin{bmatrix}
    1 & 0 \\
    0 & 1 \\
    0 & 0
    \end{bmatrix}.
$$

a) Mi $A$ képtere?
$$
\operatorname{ran}(A) = \langle (1, 0, 0), (0, 1, 0) \rangle = \left\{ \begin{bmatrix}
a \\
b \\
0
\end{bmatrix} : a,b \in \mathbb{R} \right\}
$$
$$
\implies \operatorname{ran}(A)^{\perp} = \left \{ \begin{bmatrix}
0 \\
0 \\
c
\end{bmatrix} : c \in \mathbb{R} \right\}
$$

b) Mi $A^*$ magja?
$$
A^{*} = \begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0
\end{bmatrix}
$$
$$
\operatorname{Ker}(A^{*}) = \left \{ \begin{bmatrix}
0 \\
0 \\
c
\end{bmatrix} : c \in \mathbb{R} \right\}
$$
$$
\implies \operatorname{ran}(A)^{\perp} = \operatorname{Ker}(A^{*})
$$


c) Mi az $A x = [1, 1, 1]^T$ 2-es norma szerinti legjobb megoldása, geometrialiag?
$$
\hat{x} = \begin{bmatrix}
1 \\
1 \\
0
\end{bmatrix}
$$

d) Írjuk fel a normálegyenletet és oldjuk is meg.
$$
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0
\end{bmatrix} \cdot
\begin{bmatrix}
1 & 0 \\
0 & 1  \\
0 & 0
\end{bmatrix} x = 
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0
\end{bmatrix} \cdot
\begin{bmatrix}
1  \\
1 \\
1
\end{bmatrix}
$$
$$
\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix} x
=
\begin{bmatrix}
1 \\
1
\end{bmatrix} \implies x = \begin{bmatrix}
1 \\
1
\end{bmatrix}
$$

## Iteratív megoldók

**Tétel (Banach-fixpont)**: Ha $X$ teljes metrikus tér, $f: X \to X$ kontrakció, akkor $f$-nek pontosan egy fixpontja van, továbbá tetszőleges $x_0$  esetén az $x_{n+1} = f(x_n)$ képlettel definiált sorozat tart ehhez a fixponthoz.

**Következmény:** Ha $f: V \to V$ kontrakció egy adott normában, azaz Lipschitz-folytonos és a megfelelő $0 \leq L < 1$ konstans mellett minden $x,y \in V$ pontra $\|f(x) - f(y)\| \leq L \| x - y\|$ teljesül, akkor $f$-nek van fixpontja és tetszőleges kezdőpontból indulva, az $f$ ismételt alkalmazásával tartani tudunk ehhez.

**Példa:**
$f(x) = \frac12 x$ esetén $f(0) = 0$, és $x_n = 2^{-n} x_0$ nullához tart.

**Példa:** Ha $f(x) = Ax + b$ alakú, azaz affin függvény, akkor adódik, hogy
$$ \| f(x) - f(y) \| \leq \| A \| \|x - y\|, $$

tehát amennyiben $A$ operátornormája kisebb mint egy, akkor $f$ kontrakció. Végesdimenzióban $A$ egy mátrix, $b$ egy oszlopvektor, $\|A\|$ az $A$ indukált mátrixnormája.

**Következmény:** Egy affin függvény iterálásával kapott sorozat végesdimenzióban konvergens lesz ha van olyan norma, ami által indukált operátornormája a függvényben szereplő mátrixnak kisebb, mint $1$.

**Tétel:** $$\rho(A) = \inf\{\| A\| : \| \cdot \| \text{ indukált mátrixnorma}\}$$

**Következmény:** Ha $\rho(A) < 1$, akkor a megfelelő affin függvény iterálásával kapott sorozat konvergens, hiszen van olyan indukált mátrixnorma, amivel $\rho(A) \leq \|A\| < \rho(A) + \epsilon < 1$.

**Ötlet:** Ha az $Ax = b$ egyenletet szeretnénk megoldani, akkor készítsünk olyan $f$ kontrakciót, amelynek $x^*$ fixpontjára $Ax^* = b$.

### Hogyan készíthetünk ilyen fixpont-iterációt I.

Legegyszerűbb megközelités (egyszerű- vagy **Richardson-iteráció**)
$$
\begin{align}
Ax &= b\\
0 &= b - Ax \\
x &= x - Ax + b \\
\\
f(x) &= (I-A)x +b
\end{align}
$$

Egy gond ezzel, hogy sokszor az $I-A$ mátrix spektrálsugara még nem elég kicsi. Ezen segithetünk egy $\omega$ paraméter bevezetésével:
$$
\begin{align}
Ax &= b\\
0 &= \omega(b - Ax) \\
x &= x - \omega Ax + \omega b \\
\\
f_{\omega}(x) &= (I-\omega A)x +\omega b
\end{align}
$$

Itt $\rho(I-\omega A) < 1$ pontosan akkor teljesül, ha az $A$ mátrix $\lambda$ sajátértékeire $| 1 - \omega \lambda | < 1$. A konvergencia akkor a leggyorsabb, ha ez a spektrálsugár minél kisebb. Például ha az $A$ mátrix szimmetrikus és pozitiv definit akkor az optimális választás $\omega$-ra: 

$$\omega_{\text{opt}} = \frac{2}{\lambda_{\min} + \lambda_{\max}}.$$

### 2. Feladat

Miért ez az $\omega_{\text{opt}}$?
$I - \omega A$ sajatertekei: $1-\omega \lambda$.
Azert ez az opt, mert lasd P1 feladat.

### Hogyan készíthetünk ilyen fixpont-iterációt II.

A fenti átalakitás általánosítása, ha $A=M-N$ felbontással élünk, majd ezzel számolunk.
$$
\begin{align}
Ax &= b\\
(M-N)x &= b\\
Mx &= Nx + b\\
x &= M^{-1}N x + M^{-1} b\\
\\
f(x) &= M^{-1}N x + M^{-1} b
\end{align}
$$

Itt tehát az iterációs mátrix $B=M^{-1}N$ és ennek a spektrálsugarát már hatékonyabban tudjuk befolyásolni az $M, N$ alkalmas megválasztásával.

#### Nevezetes módszerek

Legyen $A = L+ D+ U$ egy felbontása az $A$ mátrixnak rendre szigorú alsóháromszög, diagonális, és szigorú felsőháromszög mátrixokra. 

 * **Jacobi** iteráció: $M = D$
 * Relaxált Jacobi (**JOR**): $M = \frac1\omega D$
 * **Gauss-Seidel** iteráció: $M = D + L$
 * Relaxált Gauss-Seidel (**SOR**): $M = \frac1\omega D + L$

**Tétel:** Ha $A$ szigorúan diagonálisan domináns (SZDD), akkor a Jacobi és a Gauss-Seidel iteráció konvergens.

**Definíció:** Egy négyzetes mátrixot M-mátrixnak nevezünk, ha főátlóján kívül nempozitív elemei vannak, és van olyan elemenként pozitív vektor, melynek a mátrix általi képe szintén elemenként pozitív.

**Tétel:** Ha $A$ M-mátrix, akkor konvergens a JOR és az SOR $0 < \omega < 1$ esetén.


**Tétel:** Ha $A$ szimmetrikus és pozitív definit (SZPD), akkor konvergens az SOR iteráció $0 < \omega < 2$ esetén.

### 3. Feladat

Legyen $A$ SZDD. A Gersgorin-tétel segítségével mutasssuk meg, hogy $\rho(D^{-1}(D - A)) < 1$, azaz a Jacobi-iteráció konvergál.
Gersgorin-tetel szerint minden sajatertek a $0$-koruli korokben vannak, melyeknke sugarai $\frac{\sum_{j=1}^{n}a_{ij}}{a_{ii}}$, es ez $<1$ mert feltetel szerint SZDD. Tehat a spektral sugar $<1$.

### 4. Feladat
Tekintsük az
$$
\left[\matrix{2 & -1 \cr -1 & 2}\right] x= \left[ \matrix{1 \cr 3} \right]
$$
egyenletet.

a) Melyik módszereket használhatjuk ennek iteratív megoldására?
Mindent lehet, mert SZPD, SZDD, M-matrix

b) Írjuk fel a JOR iterációhoz tartozó iterációs mátrixot. Hogy alakul ennek spektrálsugara az $\omega$ függvényeként? Milyen $\omega$ választással lesz a leggyorsabb a konvergencia?

## Gradiens-alapú módszerek

Bizonyos esetekben egy lineáris algebrai egyenletrendszer megoldása előáll mint egy megfelelő függvény minimumhelye.

### 5. Feladat

Legyen $\phi: V \mapsto \mathbb{R}$ definíciója 
$$\phi_{A,b}(x) = x^T A x - b^Tx.$$

Mutassuk meg az alábbiakat.

a) 
$$
\phi'_{A,b}(x) = \nabla \phi_{A,b} (x) =  x^T(A + A^T) - b^T
$$

b)

$$
\phi_{A,b}''(x) = A + A^T
$$

c)
$$
\phi_{A,b} (x) = x^T \frac{(A + A^T)}{2} x - b^Tx,
$$
azaz feltehetjük, hogy $A$ szimmetrikus.

d)

Ha $A$ szimmetrikus és sajátérték-felbontása $A=Q\Lambda Q^T$, akkor
$$
\phi_{A,b}(x) = \phi_{\Lambda, Q^T b}(Q^Tx).
$$

### P1. Feladat
Írjunk programot, amely egy $A$ SZPD mátrix esetén egy ábrán ábrázolja az $I-\omega A$ mátrix sajátértékeinek abszolútértékét az $\omega$ függvényeként. Bemeneti paraméterek lehetnek a mátrix sajátértékei.
```python
import numpy as np
import matplotlib.pyplot as plt

def plot_eigens(eigens: np.ndarray):
	omegas = np.arange(0, 2.5, 0.01)
	for eigen in eigens:
		vals = np.abs(1 - eigen * omegas)
		plt.plot(omegas, vals)
	plt.show()
```

### P2. Feladat
Írjunk általános függvényt a fenti, $A = M-N$ felbontással adódó iterációkhoz, majd ezzel implementáljuk a tanult iterációkat.

Alkalmazzunk is ezek közül egy olyat, amit értelmes az
$$
\left[\matrix{2 & -1 \cr -1 & 2}\right] x= \left[ \matrix{1 \cr 3} \right]
$$
egyenlet megoldására. Addig iteráljunk, míg két szomszédos iterált $\| \cdot \|_2$ szerinti távolsága $10^{-4}$ alá nem csökken.

```python
import numpy as np

```


related: [[NumMod 1]]