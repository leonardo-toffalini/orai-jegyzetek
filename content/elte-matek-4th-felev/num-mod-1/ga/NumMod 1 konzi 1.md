ZH menete:
- kezdes: 12:15 - 
- gepes resz: 14:00 - 

kb zh feladatok:
1:
- 16. feladat ("norma-e a kovetkezo kifejezes")
- "matrix kondicioszam szamolasa"
2:
- "valamilyen (LU/LL^T/LDU ) felbontas kezzel"
3:
- $\rho(Q)$ kiszamitasa es ezzel valo manipulacio
- pl Relaxalt Jabobi adott matrixra (pl 4. feladat)
4:
- Adott egyenlet gyokeinek keresese visszavezetve fixpont iteraciora
- 6. feladat
5:
- 6. feladat

### Kondicioszam
norma $\to$ indukalt norma
$$
\lvert\lvert A \rvert\rvert_{2}  := \sqrt{ \lambda_{\max}(A^{*}A) } = \sqrt{ \rho(A^{*}A) }
$$
ha $A^{*} = A$ es $A > 0$ (SZPD), akkor $\lvert\lvert A \rvert\rvert_{2} = \max \lambda_{i}$

### Direkt megoldok
$\exists! A = LU$ felbontas, es $A = LDU$ felbontas
Ha $LU = A = A^{T} = (LU)^{T} = U^{T}L^{T}$ tehat ha $A$ szimmetrikus, akkor $LL^{T}$ felbontast kapunk.
Ugyanigy van $LDL^{T}$ felbontas.

### Iterativ megoldok
$Ax = b \implies Ax - b = 0$  $\implies x + (Ax - b) = x$ ekkor eleg fixpontot keresni $f(x) = x + (Ax -b)$ fuggvenyre $f(x^{*}) = x^{*}$.

**Banach-fixpont tétel*** $f: X \to X$ teljes metrikus teren ertelmezett kontrakcio, tehat
$$
\lvert\lvert f(x) - f(y) \rvert\rvert  \leq L \cdot \lvert\lvert x - y \rvert\rvert  \quad L \in [0, 1)
$$
Ennek létezik fixpontja és lehet komponalassal konvergalni oda.

*Richardson*: $f(x) = x - \omega (Ax - b)$
*Jacobi*:
$A = ( L + D + U)$  
$0 = Ax - b$
$0 = ( L + D + U)x - b$
$Dx = -(L + U) x + b$
$x = -D^{-1}(L + U)x + D^{-1}b$
*Gauss-Seidel* hasonlo...

$f(x) = Q + r$ (affin)
$\rho(Q) < 1$
$\rho(A) \leq \lvert\lvert A \rvert\rvert$, ahol $\lvert\lvert \cdot \rvert\rvert$ tetszoleges indukalt norma.
> "Tehat rho egy infimuma minden indukalt normanak"

Roviditesek:
- SZPD
- SZDD
- M-matrix

Gersgorin tetel: "Vesszuk a a komplex sikon a korlapokat akkor ezek uniojan belul vannak a sajatertekek."

Gradiens ereszkedes
$x \leftarrow x - \omega (Ax - b)$
$\phi(x) := \frac{x^{T}Ax}{2} - b^{T}x$     $\phi$ konvex $\iff$ $A \geq 0$
$\phi'(x) = Ax - b$

$\phi$ minimalizaljuk $\iff$ $\phi'$ gyokeinek megkeresese

$x_{n + 1} = x_{n} - (\nabla\phi)(x_{n})$
$m(h, h) \leq (A'(u)h, h) \leq M(h, h)$
$0 < m \leq M$





related: [[NumMod 1]]