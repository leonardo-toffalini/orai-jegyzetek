#MOC
1. ... [[anal3m beugro 9]] ...
2. feladat
**a)** Newton-Leibniz ([[Newton-Leibniz görbékre]])
***Tétel***: $F = \nabla f \implies \int \limits_{\gamma} F \, dx = f(\gamma(b)) - f(\gamma(a))$
***Biz***.:
$$
\int \limits_{\gamma} F \, dx  = \int _{a}^{b}F(\gamma(t))\gamma'(t) \, dt = \int _{\gamma (a)}^{\gamma(b)}F(\gamma) \, d\gamma = \left[ \nabla f(u) \right]_{\gamma(a)}^{\gamma(b)} = \nabla f(\gamma(b)) - \nabla f(\gamma(a))
$$

**b)** Luiville ([[Luiville tétel]])
***Tétel***:
$$
f \in \mathcal{O}(\mathbb{C}), \text{ korlátos} \implies f \equiv \text{ konstans}
$$

***Biz***.:
$$
\text{CIF deriváltra} \implies f'(z) = \frac{1}{2\pi i}\int \limits_{\lvert \xi - a \rvert = r} \frac{f(\xi)}{\left( \xi - z \right) ^{2}} \, d\xi \xRightarrow{\text{Triviális becslés}} \lvert f'(z) \rvert  \leq \frac{1}{2\pi i}\cdot \frac{M}{r^{2}} \cdot 2 \pi = \frac{M}{ri}
$$
Ha $\lvert f'(z) \rvert \leq \lim_{ r \to \infty } \frac{M}{ri} = 0 \implies f'(z) = 0 \implies f(z) \equiv \text{ konstans}$.

3. feladat
kettős integrál...
polár koordinátákkal könnyű

4. feladat
**b)** Komplex exponenciális függvény és tulajdonságai ([[Komplex exponenciális tulajdonságai]], [[Elemi komplex változós függvények]])

$$
z \in \mathbb{C}: \exp(z) = e^{z} := \sum_{j=0}^{\infty} \frac{z^{j}}{j!}
$$

***Tulajdonságai***:
1. $e^{z+w} = e^{z}e^{w}$
2. $\forall z \in \mathbb{C}: e^{z}\neq 0, e^{-z}=\frac{1}{e^{z}}$
3. $e^{z}=e^{z+2\pi i}, e^{z}=1 \iff z = 2k\pi i, k \in\mathbb{Z}$
4. $e^{z}$ szürjektív $\mathbb{C}\setminus \{ 0 \}$-n

***Biz***.:
1. biz
$$
e^{z}e^{w} = \left(\sum_{n = 0}^{\infty}{\frac{z^{n}}{N!}}\right) \cdot \left( \sum_{j = 0}^{\infty} {\frac{w^{j}}{j!}} \right) = \sum_{n=0}^{\infty}\sum_{j=0}^{n}{\frac{z^{n}\cdot w^{n-j}}{n!\cdot(n-j)!}}
$$
$$
= \sum_{n=0}^{\infty} \frac{1}{n!} \sum_{j=0}^{n} {n \choose j} z^{n}w^{n-j} = \sum_{n = 0}^{ \infty} \frac{1}{n!} \left( z + w \right) ^{n} = e^{z+w}
$$

2. biz
$$
1 = e^{0} = e^{z-z} = e^{z}e^{-z} \implies e^{z} \neq 0, e^{-z} \neq 0\implies e^{-z} = \frac{1}{e^{z}}
$$

3. biz
$$
e^{z + 2\pi i} = e^{z}e^{2\pi i} = e^{z}\left( \cos(2\pi) + i \sin(2\pi) \right) = e^{z}\left( 1 + 0 \right) = e^{z}
$$
$$
1 = e^{z} = e^{x + iy} = e^{x}e^{iy} = e^{x}\left( \cos(y) + i\sin(y) \right) \implies e^{x}\cos(y) = 1, e^{x}\sin(y) = 0
$$
$$
e^{x}\cos(y) = 1 \implies x = 0, y = 2k\pi
$$
$$
e^{x}\sin(y) = 0 \implies x = x = 0, y = n\pi
$$
$$
\implies x = 0, y = 2k\pi \implies z = 0 + 2k\pi i = 2k\pi i
$$

4. biz
$e^{z}= e^{x + iy} = e^{x}\left( \cos(y) + i \sin(y) \right) = w$
$\lvert w \rvert = e^{x}$
$arg(w) = y$
![[exp(z) szürjektív]]
Rögzített $y = y_{0}$-ra az ábrán ábrázolt félegyenes szürjektív.
Mivel tetszőlegesen lehet $y_{0}$-t választani, ezért szürektív egész $\mathbb{C}\setminus \{ 0 \}$-n.


**b)** I. típusú normáltartomány, Green tétel, Lemma normáltartományokra

***Def***.: I típusú normáltartomány:
$$
f, g \in C^{1}[a, b] \forall x \in (a, b): h(x) < g(x) \text{ és } h(a) \leq g(a), h(b) \leq g(b)
$$
$$
K := \{ \left( x, y \right) \in \mathbb{R}^{2}: x \in [a, b], h(x) \leq y \leq g(x) \}
$$

***Tétel***: $H \subset \mathbb{R}^{2} \text{ nyílt } \partial H = \gamma \text{ szakaszonként } C^{1} \text{ zárt Jordan-görbe}$
$H \cup \partial H = K \subset D \subset \mathbb{R}^{2}$ nyílt, $P , Q \in C^{1}(D)$.
Ekkor:
$$
\int \limits_{\gamma} P \, dx + Q \, dy = \iint \limits_{H} \partial_{x}Q - \partial_{y}P \, dxdy
$$

***Lemma***: Ha $K$ egy I. típusú normáltartomány, $K \subset D \subset \mathbb{R}^{2}$ nyílt.
$P \in C^{1}(D)$, $\vec{E}_{1} = (P, 0)$ vektormező.
Ekkor:
$$
\int \limits_{\partial K} \vec{E_{1}} = \int \limits_{\partial K} P \, dx = \iint \limits_{K} -\partial_{y}P \, dxdy 
$$

***Biz***. (Lemma):
Bal oldala a Lemmabeli egyenletnek:
![[Green lemma excali]]
$c_{1}: [a, b] \to \mathbb{R}^{2}, x \mapsto (x, h(x))$
$$
\int \limits_{c_{1}} \vec{E_{1}} = \int _{a}^{b}(\vec{E_{1}}(c_{1}(t))) \cdot c_{1}'(t)  \, dt = \int _{a}^{b} \left( P(c_{1}(t)), 0 \right) \cdot c_{1}'(t) \, dt = \int _{a}^{b} \left( P(x, h(x)), 0 \right) \cdot (1, h'(x)) \, dx =
$$
$$
 = \int _{a}^{b} P(x, h(x)) \, dx 
$$

$c_{3}^{-}:[a, b] \to \mathbb{R}^{2}, x\mapsto(x,g(x))$
$$
\int \limits_{c_{3}} \vec{E_{1}} = - \int \limits_{c_{3}^{-}} \vec{E_{1}} = -\int _{a}^{b} P(x, g(x)) \, dx 
$$
$c_{2}:[h(b), g(b)] \to \mathbb{R}^{2}, y \mapsto (b, y)$
$$
\int \limits_{c_{2}} \vec{E_{1}} = \int _{h(b)}^{g(b)} \left( P(b, y) \right) \cdot (0, 1) \, dy = \int _{h(b)}^{g(y)} 0 \, dy = 0 
$$
Hasonló módon $\int \limits_{c_{4}} \vec{E_{1}}  = 0$
$$
\implies \int \limits_{\partial H} \vec{E_{1}} = \int _{a}^{b}P(x, h(x)) \, dx - \int _{a}^{b}P(x,g(x)) \, dx
$$

jobboldala a Lemmabeli egyenletnek:
$$
-\iint \limits_{H} \partial_{y}P \, dxdy = - \int _{a}^{b}\int _{h(x)}^{g(x)}\partial_{y}P \, dy  \, dx \stackrel{\text{Newton Leibniz}}{=} -\int _{a}^{b} P(x, g(x)) - P(x, h(x) \, dx =
$$
$$
= \int _{a}^{b}P(x, h(x)) - P(x, g(x)) \, dx \implies \text{ baloldal } = \text{ jobboldal}
$$
