Toffalini Leonardo 2023.09.20.
#### 1.15 Bizonyítsuk be, hogy minden politóp zárt.
(politóp: véges sok pont konvex burka)

Egyel erősebb állítást fogunk belátni, be fogjuk látni hogy minden politóp *kompakt*.

Elég találni egy kompakt halmazt és egy folytonos függvényt, ami a kompakt halmazból egy politópot képez, mivel tudjuk, hogy kompakt halmaz folytonos képe is kompakt.

Legyen $H$ a véges sok pontot tartalmazó halmaz, ekkor jelölje $conv(H)$ a politópot.
$$conv(H) = \Big\{\sum_{i=1}^{n}{\alpha_{i} x_{i}} : \forall i: \alpha _{i} \ge 1, \sum_{i=1}^{n}{\alpha _{i} = 1}\Big\}$$ 
Legyen $S = \Big\{\alpha \in \mathbb{R}^n : \forall i: \alpha _{i} \ge 1, \sum_{i=1}^{n}{\alpha _{i} = 1}\Big\}$.

$$S = \Big\{\alpha \in \mathbb{R}^n : \forall i: \alpha _{i} \ge 1\} \cup \{\alpha \in \mathbb{R}^n : \sum_{i=1}^{n}{\alpha _{i} = 1}\Big\}$$

Látható, hogy $S$ két kompakt halmaz metszete, tehát maga $S$ is kompakt.
Most találnunk kell egy $g: S \rightarrow \mathbb{R}^{n}$  függvényt ami folytonos és képe a politóp.
$$g(\alpha) = \sum_{i=1}^{n}\alpha_{i}x_{i}$$
Ez a függvény folytonos és az $S$ halmazt képzi a $conv(H)$ halmazba.

Ezzel beláttuk az állítást, mivel találtunk egy folytonos függvényt ami egy kompakt halmazt képez a politópba, tehát a politóp is kompakt.
<div style="page-break-after: always;"></div>


#### 1.12 Lássuk be a következőt
Adott az $Ax \le b, x \ge 0$ egyenlőtlenség rendszer egy $x_0$ megoldása. Bizonyítsuk be, hogy ha az $x_0$ vektor nem nulla (azaz pozitív) komponenseihez tartozó $A$-beli oszlopok összefüggenek, akkor olyan megoldás is van, melynek kevesebb a nem nulla komponense.

$A = [a_1, \ldots, a_k], x_0 = [x_1, \ldots, x_k]^T$
Ezekre tudjuk, hogy $Ax_0 \le b$ .
Legyen: $A' = \left[\frac{a_1}{\beta_1}, \ldots, \frac{a_k}{\beta_k}\right], x_0' = \left[\beta_1 x_1, \ldots, \beta_k x_k\right]$   úgy, hogy $\forall i: \beta_i x_i \ge 1$, ha $x_i \ne 0$.
Úgy módosítottuk, hogy megmaradjon $Ax_0$ értéke, mivel $Ax_0 = A'x_0'$.

$$Ax_0 = A'x_0' = \sum_{i=1}^{k}{x_i a_i} = \sum_{i\in I}{x_i a_i} \le b$$
$I = \left\{i \in \{1, \ldots, k\}: x_i \ne 0\right\} = \{i_1, \ldots, i_l\}$ 
Tudjuk, hogy $\{a_i : i \in I\}$ összefüggő, tehát $\exists \alpha_1, \ldots, \alpha_l \in \mathbb{R}$ úgy, hogy $\sum_{i \in I}{\alpha_i a_i} = 0$.
Ekkor rendezve $a_m$-re: $$a_m = \sum_{i \in I, i \ne m}{-\frac{\alpha_i}{\alpha_m}a_i}$$
$$A'x_0' = \sum_{i \in I}{x_i a_i} = \sum_{i \in I, i \ne m}{x_i a_i} - \sum_{i \in I, i \ne m}{\frac{\alpha_i}{\alpha_m}a_i} x_m = \sum_{i \in I}{\left(x_i - x_m\frac{\alpha_i}{\alpha_m}\right)a_i} = Ay$$
Ahol $[y]_i := \left(x_i - x_m\frac{\alpha_i}{\alpha_m}\right)$, tehát $y_m = 0$. Ezért $y$-nak több nulla komponense van mint $x_0$-nak.

Már csak azt kell belátni, hogy $\forall i: y_i \ge 0$.
Válasszuk $m$-et úgy hogy $\alpha_m = max_{i \in I}{\alpha_i}$.
Mivel az elején átalakítottuk $x_0$ vektort $x_0'$ vektorrá úgy, hogy minden koordinátája legalább $1$, így valóban $\forall i: y_i \ge 0$.
