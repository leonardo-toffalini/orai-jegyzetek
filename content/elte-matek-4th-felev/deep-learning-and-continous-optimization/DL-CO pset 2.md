### First order condition
Let $f$ be a differentiable function $f: \mathbb{R}^n \rightarrow \mathbb{R}$ over a convex set $K$. Then $f$ is convex if and only if for all $x, y \in K$
$$
f(y) \geqslant f(x)+\langle\nabla f(x), y-x\rangle .
$$


### 1.) Verify the following statements. (5pts)
(a) $e^{a x}$ is convex on $\mathbb{R}$ for any $a \in \mathbb{R}$.
Az elsőrendű kritérium szerint  $e^{ax}$ akkor és csak akkor konvex, ha $e^{ay} \geq e^{ax} + \langle (e^{ax})', y-x \rangle$
$$
e^{ay} \geq e^{ax} + (y-x)ae^{ax}
$$
$$
e^{ay} \geq e^{ax}(1 + a(y-x))
$$
$$
\frac{e^{ay}}{e^{ax}} \geq 1 + a(y-x)
$$
$$
e^{a(y-x)} \geq 1 + a(y-x)
$$
Ami már egy ismert állítás $z = a(y-x)$-el $e^{z} \geq 1 + z$.
(b) $x^a$ is convex on $\mathbb{R}_{>0}$ when $a \geqslant 1$ or $a \leqslant 0$, otherwise it is concave.
A másodrendű kritérium szerint $x^{a}$ konvex akkor és csak akkor, ha $\nabla ^{2}x^{a} \succeq 0$ minden $x \in \operatorname{dom}x^{a}$ -ra.
$$
\nabla ^{2}x^{a} \succeq 0 \iff (x^{a})'' \geq 0
$$
$$
(x^{a})'' = (ax^{a-1})' = a(a-1)x^{a-2}
$$
A fenti pontosan akkor nemnegatív, ha $a \geq 1$ vagy $a \leq 0$ és pontosan akkor nem pozitív, ha $a \in [0, 1]$.

(c) $\log x$ is concave on $\mathbb{R}_{>0}$.
Tudjuk, hogy $\log x$ akkor konkáv, ha $-\log x$ konvex.
A másodrendű kritérium szerint $-\log x$ akkor és csak akkor konvex, ha $(-\log x)'' \geq 0$
$$
(-\log x)'' = \left( -\frac{1}{x} \right)' = \frac{1}{x^{2}} \geq 0, \quad \forall x \geq 0
$$

(d) $x \log x$ is convex on $\mathbb{R}_{>0}$.
A másodrendű kritérium szerint $x\log x$ konvex akkor és csak akkor, ha $(x\log x)'' \geq 0, \quad \forall x \in \mathbb{R}^{+}$.
$$
(x\log x)'' = \left( \log x + x \frac{1}{x} \right)' = (\log x + 1)' = \frac{1}{x} \geq 0, \quad \forall x \in \mathbb{R}^{+}
$$

(e) $\max \left\{x_1, \ldots, x_n\right\}$ is convex on $\mathbb{R}^n$.
Mivel $(\mathbb{R}^{n}, \lvert\lvert \cdot \rvert\rvert_{\max})$ normált tér, ahol $\lvert\lvert x \rvert\rvert_{\max} := \max \{ x_{1}, \dots, x_{n} \}$, ezért
$$
\lvert\lvert \lambda x + (1 - \lambda)y \rvert\rvert_{\max} \leq \lvert\lvert \lambda x \rvert\rvert_{\max} + \lvert\lvert (1 - \lambda)y \rvert\rvert_{\max} = \lvert \lambda \rvert \cdot \lvert\lvert x \rvert\rvert_{\max} + \lvert 1 - \lambda \rvert \cdot \lvert\lvert y \rvert\rvert_{\max}
$$
Továbbá, mivel $\lambda \in [0, 1]$, ezért $\lvert \lambda \rvert = \lambda$ és $\lvert 1 - \lambda \rvert = 1- \lambda$.
Tehát a fenti két széléből kapjuk a következőt:
$$
\lvert\lvert \lambda x + (1-\lambda)y \rvert\rvert _{\max} \leq \lambda \cdot \lvert\lvert x \rvert\rvert _{\max} + (1 - \lambda) \cdot \lvert\lvert y \rvert\rvert _{\max}
$$
Jelölje $f(x) := \max \{ x_{1}, \dots, x_{n} \} = \lvert\lvert x \rvert\rvert_{\max}$, ekkor pont a konvex függvény definícióját kapjuk, azaz $f(\lambda x + (1 - \lambda)y) \leq \lambda f(x) + (1 - \lambda) f(y)$.

### 2.) Consider the optimization problem
$$
\begin{array}{cc}
\min & x^2+2 x+1 \\
\text { s.t. } & (x+2)(x-4) \leqslant 0
\end{array}
$$
with variable $x \in \mathbb{R}$.
(a) Give the feasible set, the optimal value, and the optimal solution. (1pt)
Ahhoz, hogy a feltétel teljesüljön kell, hogy pontosan az egyik tényező legyen negatív vagy $0$. Tehát $x \in [-2, 4]$.
Ekkor a feladat ekvivalens azzal, hogy egy függvénynek keressük a minimum helyét egy zárt intervallumon, amit úgy tudunk megtalálni, hogy megkeressük hol $0$ a deriváltja a függvénynek és megvizsgáljuk az intervallum széleit.
$$
0 = (x^{2} + 2x + 1)' = 2x + 2 \implies x = -1
$$
Tehát a vizsgálandó helyek: $-2, -1, 4$
$$
f(-2) = 1, \quad f(-1) = 0, \quad f(4) = 25
$$
Tehát az optimum hely $x = -1$ és optimum érték $f(-1) = 0$.

(b) Plot the objective $x^2+2 x+1$ versus $x$. On the same plot, show the feasible set, optimal point and value, and plot the Lagrangian $L(x, \lambda)$ versus $x$ for a few positive values of $\lambda$. Derive and sketch the Lagrange dual function $g$. (2pts)
$$
L(x, \lambda) = x^{2} + 2x + 1 + \lambda (x + 2) (x-4)
$$
$$
g(\lambda) = \inf_{x} L(x, \lambda) = \inf_{x} \{ x^{2} + 2x + 1 + \lambda (x + 2) (x-4) \}
$$

(c) State the dual problem, and verify that it is a concave maximization problem. Find the dual optimal value and dual optimal solution $\lambda^*$. (2pts)
$$
\begin{array}{cc}
\max & \inf_{x} \{ x^{2} + 2x + 1 + \lambda (x + 2) (x-4) \} \\
s.t. & \lambda \geq 0
\end{array}
$$

A célfüggvény a következőképpen írható fel:
$$
\inf_{x} \{ (1 + \lambda)x^{2} + (2 - 2\lambda)x -7 \}
$$
Itt az $\inf$ -et lecserélhetjük $\min$ -re és tudjuk, hogy ott van minimum helye egy függvénynek ahol a deriváltja $0$.
$$
((1 + \lambda)x^{2} + (2 - 2\lambda)x -7)' = 0
$$
$$
\begin{array}{cc}
2(1 + \lambda)x + 2 - 2\lambda = 0 \\
\implies x = \frac{\lambda - 1}{\lambda + 1}
\end{array}
$$
$$
\implies g(\lambda) = \left(\frac{\lambda - 1}{\lambda + 1}\right)^{2} + 2 \frac{\lambda - 1}{\lambda + 1} + 1 + \lambda\left(\frac{\lambda - 1}{\lambda + 1} + 2\right) \left(\frac{\lambda - 1}{\lambda + 1} -4\right)
$$
Erről be kell még látni hogy konkáv, tehát $g(\lambda)'' \leq 0$.


Az optimum hely $\lambda = 0$ és az optimum érték $\inf_{x} \{ x^{2} + 2x + 1 \} = 0$.


related: [[DL-CO]]