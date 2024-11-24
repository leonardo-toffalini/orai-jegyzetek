2.
Q: Legyen $A \in \mathbb{R}^{m\times n}, b \in \mathbb{R}^{m}$, és $c_{1}, \dots, c_{k} \in \mathbb{R}^{n}$. Fogalmazzuk meg a következő feladatot LP feladatként: $Ax = b, x \geq 0$, $\min f(x)$, ahol $f(x) := \max \{  c_{1}x, \dots, c_{k}x \}$.

Legyen
$$
Q = \begin{bmatrix}
A \\
-A \\
-I_{n} \\
I_{n}
\end{bmatrix},
\hat{x} = x,
\hat{b} = \begin{bmatrix}
b \\
-b \\
\underline{0} \\
\underline{\alpha}
\end{bmatrix}
$$
Ahol $\underline{0} = [0, \dots, 0]^T$, $\underline{\alpha} = [\alpha, \dots, \alpha]$, $\underline{0}, \underline{\alpha} \in \mathbb{R}^{n}$.

3.
Q: Vezessük vissza a következő egyenlőtlenség rendszereket egymásra (abban az értelemben, hogy ha az egyiket meg tudjuk oldani, akkor az összeset meg tudjuk):
$$
Ax = b,
x \geq 0
$$
$$
Bx \leq b, x \geq 0
$$
$$
Qy \leq b
$$
$$
Px_{0} = b_{0}, Qx \leq b_{1}
$$


A felsorolt négy különböző feladat ekvivalenciáját úgy fogjuk bemutatni, hogy visszavezetjük mindegyiket a $Qx \leq b$ alakra.

a) Az $Ax = b, x \geq 0$ alakot úgy tudjuk visszavezetni $Qx \leq b$ alakra, ha
$$Q = \begin{bmatrix}
A \\
-A \\
-I_{n}
\end{bmatrix},
\hat{x} = x,
\hat{b} = \begin{bmatrix}
b \\
-b \\
0
\end{bmatrix}$$
$Q, \hat{x}, \hat{b}$-vel írjuk fel a $Q\hat{x}\leq \hat{b}$ feladatot.

b) A $Bx \leq b, x \geq 0$ feladatot úgy tudjuk visszavezetni a $Qx \leq b$ alakra, ha
$$
Q = \begin{bmatrix}
B \\
-I_{n}
\end{bmatrix},
\hat{x} = x,
\hat{b} = \begin{bmatrix}
b \\
0
\end{bmatrix}
$$
$Q, \hat{x}, \hat{b}$-vel írjuk fel a $Q\hat{x} \leq \hat{b}$ feladatot.

c) A $Px_{0} = b_{0}, Qx \leq b_{1}$ feladatot úgy tudjuk $Qx \leq b$ alakban felírni, ha
$$
\hat{Q} = \begin{bmatrix}
P && 0\\
-P && 0\\
0 && Q
\end{bmatrix},
\hat{x} = \begin{bmatrix}
x_{0} \\
x
\end{bmatrix},
\hat{b} = \begin{bmatrix}
b_{0} \\
-b_{0} \\
b_{1}
\end{bmatrix}
$$
$\hat{Q}, \hat{x}, \hat{b}$-vel írjuk fel a $\hat{Q}\hat{x} \leq \hat{b}$ feladatot.

4.
Q: Igaz, hogy egy $K \subset \mathbb{R}^{n}$ halmaz konvex akkor és csak akkor, ha $\forall x, y \in K$-re $\frac{x+y}{2} \in K$?


Nem. Ellenpélda:

Legyen $H_{1} := \{ 0, 1 \}$, továbbá legyen $H_{2} := \left\{  0, \frac{1}{2}, 1  \right\}$. Tehát legyen $H_{n}$ a $H_{n-1}$ halmaz pontjainak páronkénti felezőpontjai.
Ekkor látható, hogy $H_{\infty} := \lim_{ n \to \infty }H_{n}$ halmaz minden két $x, y \in H_{\infty}$ pontjára igaz, hogy $\frac{x+y}{2} \in H_{\infty}$ , de például $x = 0, y = 1$ pontokra $0 \cdot x + \frac{1}{3} \cdot y \not\in H_{\infty}$, tehát $H_{\infty}$ nem konvex.


related: [[DL-CO]]