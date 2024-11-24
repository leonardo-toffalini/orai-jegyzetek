date: 2024.02.20

pelda normara:
3. $(C[0, 1]), \| \cdot \|_{1}$, $f \in C[0, 1], \| f \|_{1} = \int _{0}^{1}\lvert f \rvert \,$.
Tulajdonsagok kozul a 2. es a 3. trivi
Kell 1. tulajdonsag:
$$
\int _{0}^{1}\lvert f \rvert  \, = 0 \xRightarrow[]{?}  f \equiv 0
$$
Mivel $f$ folytonos ezert ha egy $a \in [0, 1]$ es $f(a) \neq 0$ volna akkor $\exists B_{\delta}$ ugy hogy $f \rvert_{B_{\delta}} \neq 0 \implies \int _{0}^{1}\lvert f \rvert \, \neq 0$

***Megj***.: A normalt ternek a normaja altal indukalt metrika eltolas invarians, vagyis igaz, hogy $\rho_{\| \cdot \|} (x+z, y+z) = \rho_{\| \cdot \|}(x,y)$ $\forall x, y, z \in X$.

*Feladat*: Mutassunk olyan metrikat $\mathbb{R}$-en, mely nem eltolas invarians, tehat nem normanak az indukalt metrikaja.

### Banach-ter

***Def***.: Azt mondjuk, hogy $(X, \| \cdot \|)$ normalt ter egy *Banach-ter*, ha $X$ teljes metrikus ter a norma altal indukalt metrikaval, ($\rho_{\| \cdot \|}(x,y) := \| x - y \|$)-al.
Vagyis az $(x_{n}) \subset X$-ra: $\| x_{n}-x \| \to 0, \iff \exists N \in \mathbb{N}: \forall n,m > N \text{ melyre } \| x_{n} - x_{m} \| \to 0$.

peldak:
1. $(C[0, 1], \| \cdot \|)$ Banach-ter
Bizonyitas volt elozo felevben. Itt $f_{n}$ tart $f$-hez a normaban, ha egyenletesen tart hozza.

2. $(\mathbb{R}^{d}, \| \cdot \|_{p})$ Banach-ter $\forall d, p \geq 0$
*Biz*.: $(x^{n}) \subset \mathbb{R}^{d}$ Cauchy-sorozat $\| \cdot \|_{p}$ szerint $\iff$ $\forall 1 \leq i \leq d$ es $(x_{i}^{d})\subset \mathbb{R}$ Cauchy-sorozat $\lvert \cdot \rvert$ szerint.
$\implies (x_{i}^{n})\subset \mathbb{R}$ konvergens, $\exists x_{i}\in \mathbb{R}$ $x_{i}^{n}\to x$, $n\to \infty$
$\implies$ $x := (x_{1}, \dots, x_{n})$, $x^{n}\to x$ $(\mathbb{R}^{d}, \| \cdot \|_{p})$-ben

3. $(C[0, 1]), \| \cdot \|_{1}$, $f \in C[0, 1], \| f \|_{1} = \int _{0}^{1}\lvert f \rvert \,$ *NEM* Banach-ter!
*Biz*.: Ellenpelda:
![[nem banach ter pelda]]

Azt latjuk be hogy ha $f_{n}\to f$, akkor $f\rvert_{\left[ 0, \frac{1}{2} \right]} \equiv 0$, $f \rvert_{\left[ \frac{1}{2}, 1 \right]} \equiv 1$ ellentmondas, mert ekkor $f \not\in C[0, 1]$.
$$
\int _{0}^{1/2}\lvert f \rvert  \, = \int _{0}^{1/2}\lvert f-f_{n} \rvert  \, \leq \int _{0}^{1}\lvert f-f_{n} \rvert  \, = \| f-f_{n} \| \to 0
$$
$$
\implies \int _{0}^{1/2}\lvert f \rvert  \, = 0 \implies f \equiv 0 \left[ 0, \frac{1}{2} \right] \text{-en}
$$

$$
\int _{\frac{1}{2} + \frac{1}{n}} ^{1} \, \lvert f-1 \rvert   = \int _{\frac{1}{2} + \frac{1}{n}} ^{ 1} \lvert f - f_{n} \rvert  \, \leq \int _{0}^{1}\lvert f - f_{n} \rvert  \, \to 0
$$
$$
\implies \int  _{\frac{1}{2} + \frac{1}{n}} ^{ 1} \lvert  f-1 \rvert  \,\to 0, n \to \infty \implies \int _{\frac{1}{2}}^{1} \lvert f-1 \rvert  \, = 0
$$

### Skalaris szorzas

***Def***.: $(\cdot, \cdot) : X \times X \to \mathbb{R}$  *skalaris szorzas* ($X$ valos vektorter), ha kovetkezok teljesulnek:
1. $(x, x) = 0 \iff x = 0_{X}$
2. $(x,x) \geq 0$ $\forall x \in X$
3. $(x, y) = (y, x) \forall x,y \in X$ (szimmetria)
4. $(\alpha x + \beta y, z) = \alpha(x, z) + \beta(y, z)$ (bilinearitas)
(Pozitív szemidefinit, szimmetrikus bilinearis forma, valos vektorteren)

*peldak*:
1. $\mathbb{R}^{d}$-n $(x,y) := \sum_{i=1}^{d}x_{i}\cdot y_{i}$, $x, y \in \mathbb{R}^{d}$
2. $C[0, 1]$ $(f, g) := \int _{0}^{1}f\cdot g \,$
3. $\ell^{2} := \left\{  (x_{n}) \subset \mathbb{R} : \sum_{n = 1}^{\infty}\lvert x_{n} \rvert^{2} < \infty \right\}$ $(x, y) := \sum_{n=1}^{\infty}x_{n}y_{n}$ 

*Biz*.:
1. $\ell^{2}$ vektorter, $\lambda \in \mathbb{R}, (x_{n}) \in \ell^{2} \implies (\lambda \cdot x_{n}) \in \ell^{2}$
$$
(x_{n}), (y_{n}) \in \ell^{2} \quad \sum_{n = 1} ^{\infty} \lvert x_{n} + y_{n} \rvert ^{2} \leq 2\sum_{n=1}^{\infty} \lvert x_{n} \rvert ^{2} + 2 \sum_{n=1}^{\infty} \lvert y_{n} \rvert ^{2} < \infty \text{ (szamtani, mertani kozep)}
$$

$\sum x_{n}\cdot y_{n} \in R$:
$$
\sum_{n=1}^{\infty} \lvert x_{n}y_{n} \rvert \leq \frac{1}{2} \sum_{n=1}^{\infty} \lvert x_{n} \rvert ^{2} + \frac{1}{2} \sum_{n=1}^{\infty}\lvert y_{n} \rvert ^{2} < \infty
$$

$\implies$ skalaris szorzas tulajdonsagai teljesulnek!! :)



***Def***.: Legyen $(\cdot, \cdot) : X \times X \to \mathbb{R}$  skalaris szorzas, ekkor: $\| x \| := (x, x)^{1/2}$ definicioval $(X, \| \cdot \|)$ normalt ter.

***Biz***.:
1. $\| x \| = 0 \iff x = 0$
2. $\| \lambda x \| = \lvert \lambda \rvert \cdot \| x \|$ 
$\| \lambda x \| = (\lambda x, \lambda x)^{1/2} = (\lambda ^{2}(x, x))^{1/2} = \lvert \lambda \rvert (x, x)^{1/2} = \lvert \lambda \rvert \cdot \| x \|$

3. Kicsit kesobb belatjuk egy tetel kapcsan a haromszog egyenlotlenseget is.


***All***.: Legyen $(X, (\cdot, \cdot))$ egy skalaris szorzassal ellatot ter, ekkor
1. Teljesul a Cauchy-Schwartz-Bunyakovszkij egyenlotlenseg, azaz:
$$
\lvert (x,y) \rvert \leq \| x \| \cdot \| y \| 
$$
2. Paralelogramma azonossag
$$
\| x + y \|  ^{2} + \| x-y \| ^{2} = 2 \cdot \| x \| ^{2} + 2 \cdot \| y \|  ^{2}
$$
3. Skalaris szorzas folytonos , azaz
$$
x_{n} \to x, y_{n} \to y \implies (x_{n}, y_{n}) \to (x,y)
$$
***Biz***.:
2. HF kiszamolni, csak definicioba be kell helyettesiteni.
1. 
	1. tfh $\| y \| = 1$,
$$
0 \leq \| x - (x,y) \cdot y \| ^{2} = (x-(x,y)y, x-(x,y)y)= (x,x) - (x,y)(y,x) - (x,y)(x,y) + (x,y)^{2} \cdot (y,y)
$$
$$
= \| x \| ^{2} - (x,y)^{2} \implies (x,y)^{2} \leq \| x \| ^{2}\implies \lvert (x,y) \rvert \leq \| x \| \cdot 1
$$
	2.  ha $\| y \| \neq 1$ csak skalazzuk jol es keszen vagyunk
$y = t\cdot y'$ $\| y' \| = 1$
$$
\lvert (x, t \cdot y') \rvert  = \lvert t(x, y') \rvert = \lvert t \rvert \cdot \lvert (x, y') \rvert \leq \lvert t \rvert \cdot \| x \| \cdot \| y' \| = \| x \| \cdot \| ty' \|  = \| x \| \cdot \| y \| 
$$

3. haromszog egyenlotlenseg
$$
\| x + y \| ^{2} = (x+y, x+y) = (x,x) + (y,y) + 2(x,y) = \| x \| ^{2} + \| y \| ^{2} + 2(x,y) \buildrel \text{Cauchy Schwartz} \over \leq \| x \| ^{2} + \| y \| ^{2} + 2 \| x \| \cdot \| y \| = (\| x \|  + \| y \| ) ^{2}
$$
$$
\implies \| x + y \| \leq \| x \| + \| y \| 
$$
4. Folytonossag
$$
\lvert (x_{n}, y_{n}) - (x,y) \rvert = \lvert (x_{n} - x, y_{n}-y) + (x_{n}-x, y) + (x, y_{n}-y) \rvert
$$
$$
\buildrel \text{Cauchy Schwartz} \over \leq \| x_{n}-x \| \cdot \| y_{n}-y \|  + \| x_{n} - x \| \cdot \| y \| + \| x \| \cdot \| y_{n}-y \|  \to 0 \text{ mert minden tag tart } 0 \text{-hoz}
$$


### Hilbert-ter

***Def***.:  Ha $(X, (\cdot, \cdot))$ Banach-ter a skalaris szorzat altal indukalt normara nezve, akkor $X$ *Hilbert-ter*.
Tehat, ha $\| x \| := (x, x)^{1/2}$, tovabba $\rho_{\| \cdot \| }(x,y) := \| y-x \|$ metrikaval a $(X, \rho_{\| \cdot \|})$ metrikus ter teljes.

Azt mondjuk, hogy $(X, (\cdot, \cdot))$ Hilbert-ter, ha a skalaris szorzat altal indukalt norma altal indukalt metrikaval $X$ teljes metrikus ter.

*peldak*:
1. $(\mathbb{R}^{d}, (\cdot,\cdot))$, $(x,y) = \sum x_{i}\cdot y_{i}$ $\implies \| x \| = (\sum \lvert x_{i} \rvert^{2})^{1/2} = \| x \|_{2}$ Hilbert-ter

2. $(\ell^{2}, (\cdot,\cdot))$ Hilbert-ter

*Biz*.: Lasd jegyzet...

3. $\left( C[0, 1], \int _{0}^{1}fg \, \right)$ *NEM* Hilbert-ter!
$$
\| f \|_{2} := \left( \int _{0}^{1}\lvert f \rvert ^{2} \,  \right)^{1/2}
$$
Ellenpelda, ugyanaz mint $C[0,1]$-ben volt $\| \cdot \|_{1}$-al.


### Ortogonalitas

***Def***.: $x, y \in H$, $A, B \subset H$.
1. $x \perp y$, ha $(x, y) = 0$
2. $x \perp A$, ha $\forall y \in A$-ra $(x,y) = 0$
3. $A \perp B$, ha $\forall x \in A$ es $\forall y \in B$ -re $(x,y) = 0$


***Tetel*** (Meroleges vetitesrol).:
1. Legyen $K \subset H$ nem ures konvex, zart halmaz, legyen $x \in H$.
Ekkor $\exists! y \in K$ ugy hogy $\| x- y \| \to \min$, vagyis ha $\operatorname{dist}(x, K) := \inf \{ \| x- z \| : z \in K \} = \| x-y \|$
*Jel*.: $y:= P_{K}x$, $P_{K} : H \to K$ Lipschitz tulajdonsagu $L\leq 1$-el.
(Azaz konvex zárt halmaztól vett távolság felvétetik.)

2. Legyen $K \subset H$ nemures, zart *alter*, $x \in H$, ekkor a fenti tulajdonsagu $y$ az az egyetlen vektor $K$-ban, amire $x- y \perp K$.
Ilyenkor $P_{K}:H\to K$ linearis lekepezessel $y = P_{K}x$. Tovabba $P_{K}$ legfeljebb $1$ normaju.
(Azaz merőleges vetítés zárt altérre,)

***Biz***.:
1. Legyen $d:=\operatorname{dist}(x, K)$. definicio szerint $\exists(y_{n}) \subset K : \| x-y_{n} \| \to d$
Mutassuk meg, hogy $(y_{n})$ Cauchy sorozat
$$
\| y_{n} - y_{m} \| ^{2} = \| y_{n} -x + x - y_{m} \| ^{2} = 2\cdot \| y_{n} - x \| ^{2} + 2 \cdot \| x-y_{m} \| ^{2} - \| y_{n} - x - (x-y_{m}) \| ^{2}
$$
$$
= \dots + \dots - 4 \cdot \left\lvert \left\lvert  \frac{y_{n}+ y_{m}}{2} - x  \right\rvert \right\rvert ^{2} \leq 2 \cdot \| y_{n} - x \|  ^{ 2} + 2 \cdot \| x-y_{m} \| ^{2} - 4 \cdot d^{2} \to 2d^{2} + 2d^{2} - 4d^{2} = 0
$$

Mivel $H$ Hilbert-ter $\implies$ $\exists y =: \lim y_{n} \in K$  es $K$ zartsaga mitatt. Tovabba, $\| x-y_{n} \| \to \| x-y \| = d$.

2. Legyen $K$ zart alter, $x \in H$, $y$ a fenti vektor.
Legyen $z \in K$ tetszoleges. Ekkor kell: $(x-y, z) = 0$.
$$
0 \leq \| x-(y+z) \| ^{2} \text{ mivel } (y + z) \in K \text{ ezert } = \| x -y  \| ^{2} + \| z \| ^{2} - 2(x-y, z) \geq \| x-y \| ^{2}
$$
$$
\implies \| z \| ^{2} - 2(x-y, z)  \geq 0
$$
$$
\implies 2(x-y,z) \leq \| z \| ^{2}
$$
alkalmazzuk ezt $-z \in K$-ra:
$$
-2(x-y,z) \leq \| z \| ^{2}
$$
$$
\implies 2\lvert (x-y, z) \rvert \leq \| z \| ^{2}
$$
Mivel $t\cdot z \in K$, $t \geq 0$
$$
\implies 2t \lvert (x-y, z) \rvert  \leq t ^{2} \cdot \| z \| ^{2} \to 0, \text{ ha } t \to 0
$$
$$
\implies (x-y, z) = 0
$$
3. Ha $x-y \perp K$ akkor $\| x-y \| = \min \{ \| x-z \| : z \in K \}$.
Legyen $z \in K$ tetszoleges. Ekkor
$$
\| x-z \| ^{2} = \| x - y + y -z \| ^{2} = \| x - y \| ^{2} + \| y-z \| ^{2} + 2 (x-y,y-z)
$$
Mivel $y-z \in K$ es $x-y \perp K$ ezert $(x-y, y-z) = 0$
Tehat
$$
\| x-z \| ^{2} \geq \| x-y \| ^{2}
$$


related: [[TovFejAnal]]