#tétel-biz 

***Tétel***:
1. $\forall z, w \in \mathbb{C}: e^{z+w} = e^{z}e^{w}$
2. $\forall z \in \mathbb{C}: e^{z}\ne 0$ és $e^{-z} = \frac{1}{e^{z}}$
3. $\forall z \in \mathbb{C}: e^{z + 2\pi i} = e^{z}$ és $e^{z} = 1 \iff z = 2k\pi i, k \in \mathbb{Z}$
4. $e^{z}:\mathbb{C} \to \mathbb{C}$ szürjektív.

***Biz***.:
1. $e^{z} = \sum_{j=0}^{\infty}{\frac{z^{j}}{j!}}$ és $e^{w} = \sum_{j=0}^{\infty}{\frac{w^{j}}{j!}}$ abszolút konvergensek.
$$
e^{z}e^{w} \text{ Cauchy szorzata: } \sum_{n = 0}^{\infty}{\sum_{j = 0}^{n}{\frac{z^{j}}{j!} \cdot \frac{w^{n-j}}{(n-j)!}}} = \sum_{n=0}^{\infty}{\frac{1}{n!}\sum_{j=0}^{n}{{n \choose j} z^{j}w^{n-j}}} = \sum_{n=0}^{\infty}{\frac{(z+w)^{n}}{n!}} = e^{z + w}
$$
2. $1 = e^{0} = e^{z- z} = e^{z}\cdot e^{-z} \implies 1 = e^{z}\cdot e^{-z} \implies \frac{1}{e^{z}} = e^{-z}$
3. $e^{z + 2\pi i} = e^{z}\cdot \left( e^{k\pi i} \right) = e^{z} \left( \cos(2\pi) + i \sin(2\pi) \right) = e^{z} \left( 1 + i \cdot 0 \right) = e ^{z}$
$1 = e^{z} = e^{x + iy} = e^{x} \left( \cos(y) + i\sin(y) \right) \implies e^{x}\cos(y) = 1, e^{x}\sin(y) = 0$
$e^{x}\cos(y) = 1 \implies x = 0, y = 2k\pi$
$e^{x}\sin(y) = 0 \implies x = 0, y = n\pi$
$\implies z = 0 + 2k\pi i = 2k\pi i$

4. $e^{z} = e^{x + iy} = e^{x}\left( \cos(y) + i\sin(y) \right) = w$
$\lvert w \rvert = e^{x}$
$arg(w) = y$
![[exp(z) szürjektív]]
$\implies e^{x + iy}\Big|_{y=y_{0}}$ szürjektív $\implies e^{x+iy}$ szürjektív, mert $y_0$ tetszőlegesen választható.