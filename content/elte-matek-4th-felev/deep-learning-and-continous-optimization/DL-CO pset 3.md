### 1.
Let $G = (V ,E)$ be an undirected graph and $s, t \in V$. Consider the following problem:
$$
\begin{array}[cc]
a\min & \sum_{uv \in E} \lvert x_{u} - x_{v} \rvert  \\
\text{s.t. } & x_{s} - x_{t} = 1
\end{array}
$$
This is not a linear program in this form. Rewrite it as a linear program. (1pt)

**Megoldás**:
Legyen $\alpha = (\alpha_{1}, \alpha_{2}, \dots, \alpha_{\lvert E \rvert})$, ahol minden élhez tartozik egy $\alpha_{i}$.
Legyen az LP feladat feltétele, hogy minden $e_{i} = (uv) \in E$ -re $x_{u} - x_{v} \leq \alpha_{i}$ és $x_{v} - x_{u} \leq \alpha_{i}$.

Ez azt jelenti, hogy $\lvert x_{u} - x_{v} \rvert \geq \alpha_{i}$.
A fenti $2 \lvert E \rvert$ darab deltétel mellé még tartsuk meg a $x_{s} - x_{t} = 1$ feltételt és legyen a célfüggvényünk $\min \sum_{i = 1}^{\lvert E \rvert} \alpha_{i}$.

$$
\begin{array}[cc]
a\min & \sum_{i = 1} ^{\lvert E \rvert } \alpha_{i} \\
\text{s.t. } & x_{s} - x_{t} = 1 \\
\text{s.t. } & e_{i} = (uv) \text{-re } \alpha_{i} \geq x_{u} - x_{v} \\
\text{s.t. } & e_{i} = (uv) \text{-re } \alpha_{i} \geq x_{v} - x_{u}
\end{array}
$$


### 2.
Let us consider the following functions:
$$
f_{1}(w_{1}, w_{2}) = \frac{1}{2}w_{1}^{2} + \frac{7}{2}w_{2}^{2}
$$
$$
f_{2}(w_{1}, w_{2}) = 100(w_{2} - w_{1}^{2})^{2} + (1-w_{1})^{2}
$$
a) Calculate the gradients of the functions (2pts)
b) Are these function convex? (2pts)
c) Determine the global minimum of the functions. (2pts)
d) Choose a starting point $w = (w_{1}, w_{2})$ within distance $5$ from an optimal solution, and perform one step of the Gradient descent algorithm. (2pts)

**Megoldás**:
a) 
$$
\nabla f_{1}(w_{1}, w_{2}) = \nabla\left(\frac{1}{2}w_{1}^{2} + \frac{7}{2}w_{2}^{2}\right) = \begin{bmatrix}
w_{1} \\
7w_{2}
\end{bmatrix}
$$
$$
\nabla f_{2}(w_{1}, w_{2}) = \nabla\left(100(w_{2} - w_{1}^{2})^{2} + (1-w_{1})^{2}\right) = \begin{bmatrix}
400w_{1}^{3} - 400w_{1}w_{2} + 2w_{1} - 2 \\
-200w_{1}^{2} + 200w_{2} 
\end{bmatrix}
$$

b)
Elég belátni, hogy a Hesse mátrixok pozitív definitek minden $w_{1}, w_{2}$-re.
$$
\nabla ^{2}f_{1}(w_{1}, w_{2}) = \begin{bmatrix}
1 & 0 \\
0 & 7
\end{bmatrix}
$$
$$
\nabla ^{2}f_{2}(w_{1},w_{2}) = \begin{bmatrix}
1200w_{1}^{2} -400w_{2} + 2 & -400w_{1} \\
-400w_{1} & 200
\end{bmatrix}
$$
Az elsőre látszik, hogy pozitív definit, mert nem függ $w_{1}$ és $w_{2}$-től és egy diagonális mátrix, melynek a főátlójában csupa pozitív elem van.
A második nem pozitív definit, mert:
$$
\begin{bmatrix}
x_{1} & x_{2}
\end{bmatrix} \cdot
\begin{bmatrix}
1200w_{1}^{2} -400w_{2} + 2 & -400w_{1} \\
-400w_{1} & 200
\end{bmatrix}
\cdot \begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix}
=
\begin{bmatrix}
x_{1} & x_{2}
\end{bmatrix} \cdot
\begin{bmatrix}
1200w_{1}^{2}x_{1} - 400w_{2}x_{1} + 2x_{1} -400w_{1}x_{2} \\
-400w_{1}x_{1} + 200x_{2}
\end{bmatrix}
$$
$$
=
(1200w_{1}^{2}x_{1}^{2} - 400w_{2}x_{1}^{2} + 2x_{1}^{2} -400w_{1}x_{1}x_{2}) + (-400w_{1}x_{1}x_{2} + 200x_{2}^{2}) = 1200w_{1}^{2}x_{1}^{2} - 400w_{2}x_{1}^{2} + 2x_{1}^{2} - 800w_{1}x_{1}x_{2} + 200x_{2}^{2}
$$
$x_{1} = 1, \quad x_{2} = 0, \quad w_{1} = 0, \quad w_{2} = 1$ választással a fenti $x^{T} \cdot \nabla ^{2}f_{2}(w_{1},w_{2}) \cdot x = 0 -400 \cdot 1 \cdot 1 + 2 \cdot 1 - 0 + 0 = -400 + 2 = -398 < 0$. Mivel nem pozitív (semi) definit a Hesse mátrixa $f_{2}$-nek ezért nem konvex.

c)
Az első függvényről most láttuk be, hogy konvex tehát ott van globális minimuma, ahol a gradiense $0$. Ez meg csak a $(0,0)$ helyen valósul meg.

A Rosenbrock függvényről látszik, hogy nem negatív mert két négyzetes tag összege szerepel, melyek egyenként nem negatívak. Tehát jó minimum hely lenne, ahol a függvény felveszi a $0$-t. Ránézésre, pont ilyen hely a $(w_{1}, w_{2}) = (1, 1)$.
Formálisabban meg kell oldanunk a következő egyenletrendszert:
$$
\begin{bmatrix}
400w_{1}^{3} - 400w_{1}w_{2} + 2w_{1} - 2 \\
-200w_{1}^{2} + 200w_{2} 
\end{bmatrix} = \begin{bmatrix}
0 \\
0
\end{bmatrix}
$$
és megnézni melyik megoldás ad legkisebb értéket.
Látható, hogy az $(1, 1)$ megoldása a fentinek. Továbbá, nem vehet fel ennél kisebb értéket $f_{2}$.

d)
Legyen a kezdőpont $w_{t_{0}} = (1, 1)$. Legyen továbbá $\eta = 1$.
$$
w_{t_{1}} = w_{t_{0}} - \eta \nabla f_{1}(w_{t_{0}})
$$
$$
w_{t_{1}} = (1, 1) - \eta (1, 7) = (1, 1) - (1, 7) = (0, -6)
$$

Legyen $f_{2}$ esetben a kezdőpont $w_{t_{0}} = (0, 0)$. És megint legyen $\eta = 1$.
$$
w_{t_{1}} = w_{t_{0}} - \eta \nabla f_{2}(w_{t_{0}})
$$
$$
w_{t_{1}} = (0, 0) - \eta(-2, 0) = (0, 0) - (-2, 0) = (2, 0)
$$

### 3.
Given a convex, differentiable function $F: K \to \mathbb{R}$ over a convex subset $K$ of $\mathbb{R}^{n}$, the Bergman divergence of $x, y \in K$ is defines as follows:
$$
D_{F}(x,y) = F(x) - F(y) - \langle \nabla F(y), x-y \rangle
$$
Prove that $D_{F}(x,y) \geq 0$. (1pt)

**Megoldás**:
Az elsőrendű konvexitás kritérium szerint. Differenciálható $f:\mathbb{R}^{n} \to \mathbb{R}$ függvénynek egy konvex $K$ halmazon a következő igaz:
$$
f(y) \geqslant f(x)+\langle\nabla f(x), y-x\rangle
$$
Ezt rendezve egy oldalra kapjuk a következőt:
$$
f(y) - f(x) -\langle\nabla f(x), y-x\rangle \geq 0
$$
Ezzel megkaptuk a belátandó állítást, mivel a baloldalon pont a Bergman divergencia szerepel.



related: [[DL-CO]]