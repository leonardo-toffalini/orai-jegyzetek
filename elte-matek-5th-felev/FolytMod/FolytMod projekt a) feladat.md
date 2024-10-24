*a) Számítsuk ki a (4) Lorenz-modell egyensúlyi helyzeteit, valamint azok stabilitását a következő paraméterek értékei mellett. (Szükség lehet a harmadfokú egyenlet Cardano-féle megoldóképletére.)*

#### EH-k kiszamolasa

$$
\alpha=10, \quad \beta=28, \quad \gamma=8 / 3
$$

Megoldando egyenletrendszer:
$$
\begin{cases}
x' = \alpha y - \alpha x = 0 \\
y' = x(\beta - z) - y = 0 \\
z' = xy - \gamma z = 0
\end{cases}
$$

$$
\begin{cases}
y - x = 0 \\
x(\beta - z) - y = 0 \\
xy - \gamma z = 0
\end{cases}
$$
Az elso egyenletbol kovetkezik, hogy $x = y$

Adjuk ossze az elso es a masodik egyenletet:
$$
\begin{cases}
x(\beta - z) - y + y - x = 0 \\
xy - \gamma z = 0
\end{cases}
$$

$$
\begin{cases}
x(\beta - z) - x = 0 \\
xy - \gamma z = 0
\end{cases}
$$

$$
\begin{cases}
x(\beta - 1 - z) = 0 \\
xy - \gamma z = 0
\end{cases}
$$

Az elso egyenletbol kovetkezik, hogy $z = \beta - 1$

Eddig ott tartunk, hogy $x = y$ es $z = \beta - 1$. Ezeket irjuk be az utolso egyenletbe:
$$
\begin{align}
x(x) - \gamma(\beta - 1) &= 0 \\
x^{2} - \gamma(\beta - 1) &= 0
\end{align}
$$
$$
\implies x_{0, 1} = \pm \sqrt{ \gamma(\beta - 1) }
$$

Tehat megkaptuk azt, hogy ha $\beta > 1$ akkor a kovetkezo harom egyensulyi helyzet letezik:
$$
\begin{align}
P_{1} &= \left(0, 0, 0\right) \\
P_{2} &= \left(\sqrt{ \gamma(\beta - 1) },\; \sqrt{ \gamma(\beta - 1) },\; \beta - 1\right) \\
P_{3} &= \left(-\sqrt{ \gamma(\beta - 1) },\; -\sqrt{ \gamma(\beta - 1) },\; \beta - 1\right)
\end{align}
$$

Ha $\beta < 1$ akkor csak egy egyensulyi helyzet van: $(0, 0, 0)$


#### EH-k stabilitasa
Legyen $(\bar{x}, \bar{y}, \bar{z})$ egy egyensulyi helyzet. Ekkor a differencial egyenlet linearizaltjat 

Az eredeti Lorenz modell egyenlete:
$$
\begin{cases}
x' = \alpha y - \alpha x \\
y' = x(\beta - z) - y \\
z' = xy - \gamma z
\end{cases}
$$

$$
f(x, y, z) = \begin{bmatrix}
\alpha y - \alpha x \\
x(\beta - z) - y \\
xy - \gamma z
\end{bmatrix}
$$

Ki kell szamolnunk $f$ Jacobi matrixat, azaz $f'$-et:
$$
f'(x, y, z) = \begin{bmatrix}
-\alpha & \alpha & 0 \\
\beta - z & -1 & -x \\
y & x & -\gamma
\end{bmatrix}
$$

Legyenek $(x_{i}, y_{i}, z_{i})$ az egyensulyi helyzetek.
Ki kell szamolnunk $f'(x_{i}, y_{i}, z_{i})$ sajatertekeit

$$
\det(f'(x, y, z) - \lambda I) = \det \left(
\begin{bmatrix}
-\alpha - \lambda & \alpha & 0 \\
\beta - z & -1 - \lambda & -x \\
y & x & -\gamma - \lambda
\end{bmatrix}
\right)
$$
Az utolso oszlop szerint felbontva a kovetkezot kapjuk
$$
\det(\dots) = -(\gamma + \lambda)(-\alpha \beta + \alpha \lambda + \alpha z + \alpha + \lambda ^{2} + \lambda) + x(-\alpha x - \alpha y - \lambda x)
$$

Ha $(x, y, z) = (0, 0, 0)$ akkor a masodik tag $0$ es tudjuk, hogy az elso tagnak gyoke $-\gamma$
Tehat a kovetkezo masodfoku egyenletet kell meg megoldanunk:
$$
\begin{align}
-\alpha \beta + \alpha \lambda + \alpha + \lambda ^{2} + \lambda &= 0 \\
\lambda ^{2} + (1 + \alpha)\lambda + \alpha(1 - \beta) &= 0
\end{align}
$$
A sajatertekek a kovektezok:
$$
\lambda_{1, 2} = \frac{-(1 + \alpha) \pm \sqrt{ (1 + \alpha)^{2} - 4 \alpha(1 - \beta) }}{2}
$$
$$
\lambda_{3} = -\gamma
$$

Lathatoan $\lambda_{1} > 0$ igy $P_{1} = (0, 0, 0)$ egy instabil egyensulyi helyzet.

Mostmar csak a maradek ketto e.h.-t kell vizsgalnunk, de szerencsere ugyanazt az egyenletet kell megoldani mindkettohoz:
$$
\begin{align}
\mu ^{3} + (1 + \alpha + \gamma) \mu ^{2} + (\alpha + \beta)\gamma \mu + 2\alpha \gamma(1 - \beta) &= 0
\end{align}
$$

Mostmar nem tudunk ranezesre mondani egy gyokot igy tenyleg meg kell oldanunk egy harmadfoku egyenletet... :(

Legyen
$$
p = \frac{3(\alpha + \beta)\gamma - (2\alpha \gamma(1 - \beta))^{2}}{3}
$$
$$
q = \frac{2(1 + \alpha + \gamma)^{3} - 9(1 + \alpha + \gamma)(\alpha + \beta)\gamma + 27 \cdot 2\alpha \gamma(1 - \beta)}{27}
$$

Ezekkel az uj valtozokkal a kovetkezo ekvivalens az elozo harmadfoku egyenlettel:
$$
\xi ^{3} + p\xi + q = 0
$$

Erre tudjuk alkalmazni a Cardano formulat:
$$
\xi = \sqrt[3]{ \frac{q}{2} + \sqrt{ \frac{q^{2}}{4} + \frac{p^{3}}{27} } } + \sqrt[3]{ \frac{q}{2} - \sqrt{ \frac{q^{2}}{4} + \frac{p^{3}}{27} } }
$$

Ha 
$$
\beta < \frac{\alpha(\alpha + \gamma + 3)}{\alpha - \gamma - 1}
$$
akkor mindharom megoldas negativ es igy $P_{2}$ es $P_{3}$ stabil egyensulyi helyzetek.

Ha
$$
\beta > \frac{\alpha(\alpha + \gamma + 3)}{\alpha - \gamma - 1}
$$
akkor mar $P_{2}$ es $P_{3}$ instabil egyensuly helyzetek.



