## a) Differencialszamitas
### Egyvaltozos folytonossag
*Def.:* Legyen $f$ ertelmezve valamely $a$-t tartalmazo nyilt intervallumban. Az $f$ fuggveny folytonos az $a$ helyen, ha $\forall \varepsilon >0$-hoz letezik $\delta >0$, amelyre teljesul, hogy
$$
\lvert x - a \rvert < \delta \implies \lvert f(x) - f(a) \rvert < \varepsilon.
$$
*Def.:* Legyen $f$ ertelmezve egy $[a, b)$ intervallumon. Az $f$ fuggveny jobbrol folytonos az $a$ helyen, ha $\forall \varepsilon > 0$-hoz letezik $\delta > 0$ ugy, hogy
$$
0 \leq x - a < \delta \implies \lvert f(x) - f(a) \rvert < \varepsilon.
$$
*Def.:* Legyen $f$ ertelmezve egy $(c, a]$ intervallumon. Az $f$ fuggveny balrol folytonos az $a$ helyen, ha $\forall \varepsilon > 0$-hoz letezik $\delta > 0$ ugy, hogy
$$
0 \leq a - x < \delta \implies \lvert f(x) - f(a) \rvert < \varepsilon.
$$
*Def.:* Legyen $a < b$. Az $f$ fuggveny folytonos az $[a, b]$ intervallumon, ha minden $x \in (a, b)$ helyen folytonos, tovabba $a$-ban jobbrol, $b$-ben pedig balrol folytonos.

*Tetel:* Ha $f \in C[a, b]$, akkor $f$ korlatos $[a, b]$-ben.
*Tetel:* (Weierstrass) Korlatos zart intervallumon folytonos fuggvenynek mindig van a minimum es maximum helye.
*Tetel:* (Bolzano–Darboux) Ha $f \in C[a, b]$, akkor $f$ az $[a, b]$ intervallumon felvesz minden $f(a)$ es $f(b)$ kozotti erteket.

*Def.:* Az $f$ fuggveny egyenletesen folytonos az $I$ intervallumon, ha $\forall \varepsilon > 0$-hoz letezik univerzalis $\delta > 0$, amelyre barmely ket $x_{0}, x_{1} \in I$ pontra
$$
\lvert x_{1} - x_{0} \rvert  < \delta \implies \lvert f(x_{1}) - f(x_{0}) \rvert < \varepsilon .
$$
*Tetel:* Korlatos zart intervallumon folytonos fuggveny egyenletesen folytonos.
*Def.:* Az $f$ fuggveny Lipschitz az $A$ halmazon, ha van olyan $K \geq 0$ konstans, hogy
$$
\lvert f(x_{1}) - f(x_{0}) \rvert \leq K \cdot \lvert x_{1} - x_{0} \rvert 
$$
minden $x_{0}, x_{1} \in A$-ra.
*Tetel:* Ha $f$ Lipschitz az $A$ halmazon akkor $f$ egyenletesen folytonos $A$-n.
*Tetel:* Ha $f$ monoton az $I$ nyilt intervallumon, akkor $I$-ben legfeljebb megszamlalhatoan sok szakadasi helye van.

### Hatarertek
*Def.:* Legyen $f$ ertelmezve egy $a$-t tartalmazo nyilt intervallumban, kiveve esetleg $a$-t magat. Az $f$ fuggveny hatarerteke az $a$ helyen letezik es erteke $b$, ha $\forall \varepsilon > 0$-hoz letezik $\delta > 0$ ugy, hogy
$$
0 < \lvert x - a \rvert < \delta \implies \lvert f(x) - b \rvert  < \varepsilon.
$$
*Def.:* (Alternativ definicio) Legyen $f$ ertelmezve egy $a$-t tartalmazo nyilt intervallumon, kiveve esetleg $a$-t magat. Az $f$ fuggveny hatarerteke az $a$ helyen letezik es erteke $b$ ha az
$$
f^{*}(x) = \begin{cases}
f(x), & \text{ha } x \neq a \\
b, & \text{ha } x = a
\end{cases}
$$
fuggveny folytonos az $a$ helyen.

*Tetel:* Legyen $f$ ertelmezve egy $a$-t tartalmazo nyyilt intervallumon. Az $f$ fuggveny akkor es csak akkor folytonos $a$-ban, ha $\lim_{ x \to a } f(x)$ letezik, es erteke $f(a)$.
*Tetel:* Ha letezik az $f$ hatarerteke $a$-ban akkor az egyertelmu.

*Def.:* Legyen $f$ ertelmezve egy $(a, c)$ nyilt intervallumon. Az $f$ fuggveny jobb oldali hatarerteke letezik az $a$ helyen es az erteke $b$, ha $\forall \varepsilon > 0$-hoz letezik $\delta > 0$ ugy, hogy
$$
0 < x - a < \delta \implies \lvert f(x) - b \rvert < \varepsilon.
$$

*Tetel:*
$$
\lim_{ x \to a } f(x) = b \iff \lim_{ x \to a+0 } = \lim_{ x \to a-0 } = b
$$

*Def.:* Legyen $f$ ertelmezve egy $a$-t tartalmazo nyilt intervallumon, kiveve esetleg $a$-t magat. Az $f$ fuggveny hatarerteke az $a$ helyen $\infty$, ha $\forall P \in \mathbb{R}$-hez letezik $\delta > 0$ ugy, hogy
$$
0 < \lvert  x- a \rvert < \delta \implies f(x) > P.
$$
*Def.:* Legyen $f$ ertelmezve egy $(a, \infty)$ felegyenesen. Azt mondjuk, hogy az $f$ fuggveny hatarerteke $\infty$-ben $b$, ha $\forall \varepsilon > 0$-hoz letezik olyan $K \in \mathbb{R}$ , amelyre teljesul, hogy
$$
x > K \implies \lvert f(x) - b \rvert < \varepsilon.
$$
*Def.:* Legyen $f$ ertelmezve egy $(a, \infty)$ felegyenesen. Azt mondjuk, hogy az $f$ fuggveny hatarerteke $\infty$-ben $\infty$, ha minden $P$-hez letezik $K$ ugy, hogy
$$
x > K \implies f(x) > P.
$$

*Tetel:* (Atviteli elv) Legyen $f$ ertelmezve $\alpha$ egy $\dot{U}$ pontozott kornyezeten. Akkor es csak akkor teljesul $\lim_{ x \to \alpha } f(x) = \beta$, ha valahanyszor egy $(x_{n})$ sorozatra
$$
\{ x_{n} \} \subset \dot{U} \quad \text{es} \quad x_{n} \to \alpha,
$$
akkor $\lim_{ n \to \infty } f(x_{n}) = \beta$.

*Tetel:* Az $f$ fuggveny akkor es csak akkor folytonos az $a$ pontban, ha ertelmezve van $a$ egy kornyezeteben, es minden $x_{n} \to a$ sorozatra $f(x_{n}) \to f(a)$.

*Tetel:* Ha $\alpha$ egy pontozott kornyezeteben $f(x) \leq g(x) \leq h(x)$ es $\lim_{ x \to \alpha } f(x) = \lim_{ x \to \alpha }h(x) = \beta$ akkor $\lim_{ x \to \alpha }g(x) = \beta$.

*Tetel:* Legyen $\alpha$ jelentese egy $a$ szam, vagy $a - 0$ vagy $a+0$ vagy $\infty$ vagy $-\infty$. Ha $\lim_{ x \to \alpha }f(x) = b$ es $\lim_{ x \to \alpha }g(x) = c$ veges hatarertekek leteznek, akkor
1. $\lim_{ x \to \alpha }(f(x) + g(x))$ letezik es erteke $b + c$.
2. $\lim_{ x \to \alpha }(f(x) \cdot g(x))$ letezik es erteke $b \cdot c$.
3. $c \neq 0$ eseten $\lim_{ x \to \alpha }(f(x) / g(x))$ letezik es az erteke $b / c$.

### Elemi fuggvenyek
#### Polinom fuggvenyek
*Def.:* A $p : \mathbb{R} \to \mathbb{R}$ fuggvenyt polinomnak nevezzuk, ha
$$
p(x) = a_{n}x^{n} + \dots + a_{2}x^{2} + a_{1}x + a_{0},
$$
ahol $a_{i} \in \mathbb{R}$ es $a_{n} \neq 0$.

#### Racionalis fuggvenyek
*Def.:* Racionalis tortfuggvenynek nevezzuk a $p / q$ alaku fuggvenyeket, ahol $p$ es $q$ polinomok es $q$ nem azonosan nulla.

#### Exponencialis fuggvenyek
*Def.:* Tetszoleges $a > 0$-re az $x \mapsto a^{x}$ ($x \in \mathbb{R}$) fuggvenyt $a$ alapu exponencialis fuggvenynek nevezzuk.

#### Hatvany fuggvenyek
$$
x \mapsto x^{b}
$$

#### Logaritmus fuggvenyek
*Def.:* Az $a^{x}$ fuggvenynek $a > 0$ es $a \neq 1$ eseten letezik inverze, ezt hivjuk $a$ alapu logaritmus fuggvenynek es $\log_{a}x$-el jeloljuk. Nyilvan $\log_{a}x$ csak a pozitiv felegyenesen ertelmezett.

#### Trigonometrikus fuggvenyek
- $\sin : \mathbb{R} \to [-1, 1]$
- $\cos : \mathbb{R} \to [-1, 1]$
- $\tan : \mathbb{R} \to \mathbb{R}$

#### Inverz trigonometrikus fuggvenyek
- $\sin ^{-1} : [-1, 1] \to [0, \pi]$
- $\cos ^{-1} : [-1, 1] \to [-\pi / 2, \pi / 2]$
- $\tan ^{-1} : \mathbb{R} \to \mathbb{R}$

#### Hiperbolikus fuggvenyek
$$
\sinh := \frac{e^{x} - e^{-x}}{2}
$$
$$
\cosh := \frac{e^{x} + e^{-x}}{2}
$$
$$
\cosh ^{2}(x) - \sinh ^{2}(x) = 1
$$
Tehat a $(\cosh u, \sinh u)$ pont az $x^{2} - y^{2} = 1$ hiperbolara esik minden $u$-ra. Innen jon a hiperbolikus jelzo. Ahogyan a $(\cos u, \sin u)$ az $x^{2} + y^{2} = 1$ korre esik ugy ez egy hiperbolara.
$$
\tanh := \frac{\sinh}{\cosh}
$$

#### Inverz hiperbolikus fuggvenyek
- $\sinh ^{-1}$
- $\cosh ^{-1}$
- $\tanh ^{-1}$

### Differencialhatosag
*Def.:* Legyen $f$ ertelmezve az $a$ pont egy kornyezeteben. Azt mondjuk, hogy az $f$ fuggveny az $a$ pontban differencialhato, ha a
$$
\lim_{ x \to a } \frac{f(x) - f(a)}{x - a}
$$
veges hatarertek letezik. Tovabba, azt mondjuk, hogy a fenti hatarertek az $f$ derivaltja az $a$ pontban.

*Tetel:* Ha $f$ differenecialhato $a$-ban, akkor $f$ folytonos $a$-ban.
*Megj.:* Forditva nagyon nem igaz az allatis, peldaul lehet mutatni olyan fuggvenyt ami folytonos mindenhol de sehol sem differencialhato (Weierstrass fuggveny). Vagy egy meg egyszerubb pelda az $x \mapsto \lvert x \rvert$ ami folytonos $0$-ban de nem differencialhato ott.

*Def.:* Azt mondjuk hogy $f$ differencialhato $[a, b]$-n ha $\forall x \in (a, b)$-ben differencialhato es a hatarpontokban balrol illetve jobbrol differencialhato.
*Def.:* Az $f$ fuggveny derivaltjanak nevezzuk az $f'$ fuggvenyt amely ertelmezve van mindazon $x$ helyen ahol $f$ differencialhato es ott az erteke pont $f'(x)$.

### Fuggvenyvizsgalat
*Tetel:* Legyen $f$ folytonos $[a, b]$-ben es differencialhato $(a, b)$-n. Ekkor
1. $f$ akkor es csak akkor monoton novekedo $[a, b]$-ben, ha $f'(x) \geq 0$ minden $x \in (a, b)$-re.
2. $f$ akkor es csak akkor szigoruan monoton novekedo $[a, b]$-ben, ha $f'(x) \geq 0$ minden $x \in (a, b)$-re, es $[a, b]$-nek nincs olyan reszintervalluma, amelyen $f'$ azonosan nulla.
*Megj.:* Nyilvan a monotn csokkeno es szigoruan monoton csokkeno tulajdonsagra hasonlo allitas megfogalmazhato.
*Kovetkezmeny:* Ha van ket folytonose es differencialhato fuggvenyem $[a, b]$-ben es $f(a) = g(a)$ akkor eleg belatnom azt hogy $f'(x) \geq g'(x)$ minden  $x \in [a, b]$-re, ahhoz hogy belassam hogy $f(x) \geq g(x)$ minden $x \in [a, b]$-re.

*Tetel:* Legyen $f$ differencialhato az $a$ pont egy kornyezeteben.
1. Ha $f'(a) = 0$ es $f'$ lokalisan novekedo az $a$ helyen, akkor az $a$ pont az $f$-nek lokalis minimumhelye.
2. Ha $f'(a) = 0$ es $f'$ szigoruan lokalisan novekedo $a$-ban akkor az $a$ pont $f$-nek szigoru lokalis minimumhelye.
*Megj.:* Nyilvan itt is hasonlo allitasok megfogalmazodhatnak a lokalis es szigoruan lokalis maximumhely jellemzeserol.

*Tetel:* Legyen $f$ ketszer differencialhato $a$-ban. Ha $f'(a) = 0$ es $f''(a) > 0$, akkor $f$-nek $a$-ban szigoru lokalis minimuma van. Ha $f'(a) = 0$ es $f''(a) < 0$, akkor $f$-nek $a$-ban szigoru lokalis maximuma van.

*Tetel:* Legyen $f$ differencialhato az $I$ intervallumon.
1. Az $f$ fuggveny akkor es csak akkor konvex $I$-ben, ha $f'$ monoton novekedo $I$-ben.
2. Az $f$ fuggveny akkor es csak akkor szigoruan konvex $I$-ben, ha $f'$ szigoruan monoton novekedo $I$-ben.

*Tetel:* Legyen $f$ ketszer differencialhato $I$-ben. Az $f$ fuggveny akkor es csak akkor konvex $I$-ben, ha $f''(x) \geq 0$ minden $x \in I$-re.
*Def.:* Azt mondjuk, hogy az $a$ pont az $f$ fuggvenynek inflexios pontja, ha $f$ folytonos $a$-ban, $f$-nek letezik a derivaltja $a$-ban, es van olyan kicsi kornyezet melyre $f$ konvex $a$-tol balra es konkav $a$-tol jobbra, vagy forditva. Ergo $f$ konvexrol konkavra valt $a$-ban.
*Tetel:* Legyen $f$ haromszor differencialhato $a$-ban. Ha $f''(a) = 0$ es $f'''(a) \neq 0$ akkor $f$-nek inflexios pontja van $a$-ban.

*Teljes fuggvenyvizsgalat:*
1. hatarertekek meghatarozasa
2. azon intervallumok meghatarozasa, amelyeken $f$ monoton novo, illetve csokkeno
3. $f$ lokalis es abszolut szelsoertekhelyei es szelsoertekeinek meghatarozasa
4. azon pontok meghatarozasa, amelyeken $f$ folytonos, illetve differencialhato
5. azon intervallumon meghatarozasa, amelyeken $f$ konvex, illetve konkav
6. $f$ inflexios pontjainak meghatarozasa

### Tobbvaltozos differencialhatosag
*Def.:* Legyen $H \subset \mathbb{R}^{p}$ es $a \in \operatorname{int} H$. Azt mondjuk, hogy az $f: H \to \mathbb{R}^{q}$ fuggveny differencialhato az $a$ pontban, ha van olyan $A : \mathbb{R}^{p} \to \mathbb{R}^{q}$ linearis lekepezes, hogy
$$
f(x) = f(a) + A(x - a) + \varepsilon(x) \cdot \lvert x - a \rvert 
$$
minden $x \in H$-ra, ahol $\varepsilon(x) \to 0$ ha $x \to a$.

*Tetel:* Az $f: H \to \mathbb{R}^{q}$ fuggveny akkor es csak akkor differencialhato az $a$ pontban, ha $f$ mindegyik $f_{i}$ koordinatafuggvenye differencialhato $a$-ban. Ekkor az $A$ linearis lekepezes matrixaban az $i$-edik sor $j$-edik eleme egyenlo $D_{j}f_{j}(a)$ parcialisa derivalttal.

*Def.:* Az elozo tobbvaltozos differencialhatosag definicioban szereplo $A$ lekepezest az $f$ fuggveny $a$ pontbeli derivaltjanak nevezzuk es $f'(a)$-val jeloljuk. Az $f'(a)$ linearis lekepezes matrixat pedig $A_{ij} = D_{i}f_{j}$ adja es Jacobi-matrixnak hivjuk.

*Tetel:*
1. Ha az $f$ fugveny differencialhato az $a$ pontban, akkor $f$ folytonos $a$-ban, tovabba $f$ mindegyik koordinatafuggvenyenek mindegyik valtozo szerinti parcialis derivaltja letezik es veges az $a$ pontban.
2. Ha $f$ mindegyik koordinatafuggvenyenek mindegyik valtzo szerinti parcialis derivaltja letezik es veges az $a$ pont egy kornyezeteben es folytonos az $a$ pontban, akkor $f$ differencialhato az $a$ pontban.

### Szelsoertek
Ez mit jelent? Minek a szelso erteke?

### Komplex differencialhatosag
*Def.:* Legyen $f: \mathbb{C} \to \mathbb{C}$ komplex fuggveny ertelmezve a $z_{0} \in \mathbb{C}$ pont egy kornyezeteben. Azt mondjuk, hogy az $f$ fuggveny az $z_{0}$ pontban differencialhato, ha a
$$
\lim_{ z \to z_{0} } \frac{f(z) - f(z_{0})}{z - z_{0}}
$$
veges hatarertek letezik. Tovabba, azt mondjuk, hogy a fenti hatarertek az $f$ derivaltja az $z_{0}$ pontban.

*Tetel:* (Cauchy–Riemann) Adott $f(z) = u(x, y) + iv(x,y)$ komplex fuggveny, ahol $u$ es $v$ ketvaltozos valos erteku fuggvenyek es $z = x + iy$. Ekkor $f$ komplex differencialhato $z_{0} = x_{0} + iy_{0}$ pontban akkor es csak akkor ha $u(x, y)$ es $v(x, y)$ differencialhatok az $(x_{0}, y_{0})$ pontban es teljesitik a Cauchy–Riemann egyenleteket:
$$
\begin{aligned}
\frac{\partial u}{\partial x} &= \frac{\partial v}{\partial y} \\
\frac{\partial u}{\partial y} &= -\frac{\partial v}{\partial x} \\
\end{aligned}
$$
*Def.:* Azt mondjuk, hogy az $f$ komplex fuggveny holomorf az $U$ nyilt halmazon, ha $U$ minden pontjaban komplex differencialhato.
*Def.:* Azt mondjuk, hogy az $f$ komplex fuggveny analitikus a $z_{0}$ pontban, ha $z_{0}$ egy nyilt kornyezeteben $f$ felirhato egy konvergens fuggenysorozatkent:
$$
f(z) = \sum_{n=0}^{\infty} c_{n} (z - z_{0})^{n}.
$$
*Tetel:* Minden holomorf fuggveny analitikus es forditva.

## b) Integralszamitas
### Egyvaltozos primitiv fuggveny
### Riemann-integral
### Terulet es ivhossz
### Tobbszoros integral
### Vonalintegral
### Potencial
### Lebesgue-mertek
### L^p terek
### Normalt ter es Hilbert-ter
*Def.:* (Metrikus ter)
*Def.:* (Teljes metrikus ter) Olyan metrikus ter, melyben minden Cauchy-sorozat konvergens a ter metrikaja szerint.
*Def.:* (Normalt ter)
*Def.:* (Banach ter) Olyan normalt ter, melyben minden Cauchy-sorozat konvergens a ter normaja altal indukalt metrika szerint.
*Def.:* (Euklideszi ter)
*Def.:* (Hilbert ter) Olyan euklideszi ter, melyben minden Cauchy-sorozat konvergens a ter skalar szorzata altal indukalt norma altal indukalt metrika szerint.

## c) Vegtelen sorok
### Szamsorozatok es sorok
### Fuggvenysorozatok es sorok
### Hatvanysor
### Taylor sor
### Komplex fuggvenyek es hatvanysorok
### Komplex exponencialis fuggveny
### Fourier sorok
 