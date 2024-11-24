date: 2024.03.05

peldak ONB-re:
1.) $H = \ell^{2}$
$e^{1} = 1, 0, ,\dots), \quad e^{2} = (0, 1, 0, \dots), \quad e^{j} = (0, 0, \dots, 1_{j}, \dots)$
***Áll***.: Ez egy ONB $\ell^{2}$-ben
***Biz***.: Mert a fourier sor eloallitas teljesul
$x \in \ell^{2} : x = \sum_{j = 1}^{\infty}(x, e^{j})\cdot e^{j}$
$(x, e^{j}) = x_{j}$
Kell: $x = \sum_{j=1}^{\infty}x_{j}\cdot e^{j}$ 
Ehhez az kell, hogy $x = \lim_{ n \to \infty } \sum_{j=1}^{n}x_{j}\cdot e^{j} = \lim_{ n \to \infty } (x_{1}, x_{2}, x_{3}, \dots, x_{n}, 0, 0, \dots)$.
$\| x - (x_{1}, x_{2}, \dots, x_{n}, 0, 0, \dots) \|_{\ell^{2}} \to 0, \quad n \to \infty$
$\| 0, 0, 0, \dots, x_{n+1}, x_{n+2}, \dots \|_{\ell^{2}} = \sum_{j=n+1}^{\infty}\lvert x_{j} \rvert^{2} \to 0, \quad n\to \infty, \text{ mert } \sum_{j=1}^{\infty}\lvert x_{j} \rvert^{2} < \infty$

2.) $L^{2}(I)$-ben
$$
e_{0} = \frac{1}{\sqrt{ 2\pi }}, \; e_{2k -1} = \frac{1}{\sqrt{ \pi }} \sin (kt), \; e_{2k} = \frac{1}{\sqrt{ \pi }} \cos (kt), \quad k = 1, 2, \dots
$$
***All***.: Ez ONB minden $I$-re, melyre $\lvert I \rvert = 2\pi$
(nem bizonyitjuk, hogy ONB)

#### ***All***.: (Basel-problem)
$$
\sum_{k=1}^{\infty} \frac{1}{k^{2}} = \frac{\pi ^{2}}{6}
$$
***Biz***.:
Azt hasznaljuk, hogy a trigonometrikus rendszer ONB $L^{2}(-\pi, \pi)$-ben.
Legyen $f(t) = t \in C[-\pi, \pi] \subset L^{2}(-\pi, \pi)$.
Teljesul a Fourier-sor eloallitas, vagyis
$$
f(t) = \sum_{k=0}^{\infty} (f, e_{k}) \cdot e_{k}
$$
*Parseval-egyenloseg*:
$$
\| f \| ^{2}_{L^{2}} = \sum_{k = 0}^{\infty} \lvert (f, e_{k}) \rvert ^{2}
$$
$$
\| f \| ^{2}_{L^{2}(-\pi, \pi)} = \int _{-\pi}^{\pi}t \cdot t \, dt = \left[  \frac{t^{3}}{3}  \right]_{-\pi}^{\pi} = \frac{\pi ^{3}}{3} + \frac{\pi ^{3}}{3} = \frac{2\pi ^{3}}{3}
$$
$$
(f, e_{0}) = \int _{-\pi}^{\pi} \frac{1}{\sqrt{ 2\pi }}t \, dt = 0 \text{, mert paratlan fuggveny szimmetrikus tartomanyon.}
$$
$$
(f, e_{2k}) = \frac{1}{\sqrt{ \pi }} \int _{-\pi}^{\pi} (\cos kt) \cdot t \, dt = 0 \text{, mert paratlan fuggveny szimmetrikus tartomanyon.}
$$
$$
(f, e_{2k-1}) = \frac{1}{\sqrt{ \pi }} \int _{-\pi}^{\pi} t \cdot \sin kt \, dt = \frac{1}{\sqrt{ \pi }}\left( - \left[t \cdot \frac{\cos kt}{k}\right]_{-\pi}^{\pi} + \int _{-\pi}^{\pi} \frac{\cos kt}{k} \, dt  \right) = 
$$
$$
= \frac{1}{\sqrt{ \pi }}\left( -\left[ t \cdot \frac{\cos kt}{k} \right]_{-\pi}^{\pi} + 0 \right) = -\frac{1}{\sqrt{ \pi }}\left[ t \cdot \frac{\cos kt}{k} \right]_{-\pi}^{\pi} = 
$$
Ha $k$ paros:
$$
= -\frac{1}{\sqrt{ \pi }}\left( \frac{\pi}{k} + \frac{\pi}{k} \right) = -\frac{2\pi}{\sqrt{ \pi }k} = -\frac{2\sqrt{ \pi }}{k}
$$
Ha $k$ paratlan:
$$
= -\frac{1}{\sqrt{ \pi }}\left( -\frac{\pi}{k} - \frac{\pi}{k} \right) = \frac{2\sqrt{ \pi }}{k}
$$

Tehat a jobboldal a kovetkezo:
$$
\sum_{k = 1}^{\infty} \left(\frac{2\sqrt{ \pi }}{k}\right)^{2} = \pi \cdot 4 \sum_{k=1}^{\infty}\frac{1}{k^{2}}
$$

Baloldal:
$$
\frac{2\pi ^{3}}{3}
$$
bal = jobb:
$$
\implies \sum_{k=1}^{\infty} \frac{1}{k^{2}} = \frac{\pi ^{2}}{6}
$$

### Fontos kulombseg a veges dimenziohoz kepest
Legyen $(e_{n}) \subset H$ ONS.
$K := \{ e_{n} : n \in \mathbb{N} \}$ korlatos ($\| e_{n} \| = 1$) es zart (!)
$\| e_{n}-e_{m} \|^{2} = (e_{n} - e_{m}, e_{n} - e_{m}) = (e_{n}, e_{n}) + (e_{m}, e_{m}) -2(e_{n}, e_{m}) = 1 + 1 + 0 = 2$

$\implies$ $(e_{n})$-bol nem valaszthato ki Cauchy sorozat, tehat konvergens sem.

### Kompaktsag
***Def***.: Legyen $(X, \rho)$ egy metrikus ter. Azt modjuk, hogy $K \subset X$ *kompakt*, ha barmely $(x_{n}) \subset K$ sorozatnak van olyan $x_{n_{j}}$ reszsorozata, amely egy $x \in K$-hoz konvergal.

***Megj***.:  Ez a fogalom ekvivalens a korabbival (minden nyilt fedesbol kivalaszthato veges nyilt fedes).

***All***.: Ha $K \subset X$ kompakt, akkor korlatos es zart.
***Biz***.:
1.) zartsag:
Legyen $(x_{n}) \subset K$ konverges, tehat $x_{n} \to x \in X$
Kell $x \in K$
Mivel $K$ kompakt, ezert $\exists (x_{n_{j}}) : x_{n_{j}} \to a \in K$, $\implies a = x  \implies x \in K$.

2.) Korlatossag ($\iff \exists K \subset B(a, r), \quad a \in X, r >0$)
Indirekt, tegyuk fel, hogy $K$ *nem* korlatos. Legyen $x_{1} \in K$ tetszoleges.
Ekkor $\exists x_{2} \in K \setminus B(x_{1}, 1)$.

Tekintsuk $B(x_{1}, 1) \bigcup B(x_{2}, 1) \subset B(x_{1}, \rho(x_{1},x_{2}) + 1)$ korlatos halmazt.

Indirekt felteves szerint $\exists x_{3} \in K \setminus \left(B(x_{1}, 1) \bigcup B(x_{2},1)\right)$.

Induktivan definialunk egy $(x_{n}) \subset K$ sorozatot, ugy, hogy $x_{n} \not\in \bigcup_{j = 1}^{n-1} B(x_{j}, 1)$
Ekkor $\rho(x_{n}, x_{m}) \geq 1 \implies (x_{n})$  nem Cauchy-sorozat $\implies$ nem valaszthato ki konvergens reszsorozat. Ellentmondas!

***Megj***.: A fenti allitas megforditasa nem mindig igaz. (Veges dimenzioban igaz oda-vissza!)

***All***.: $(\mathbb{R}^{d}, \| \cdot \|_{p}), \quad 1 \leq p \leq \infty$ terben minden korlatos es zart halmaz kompakt. (Altalanosabban, veges dimenzios normalt terben is igaz.)

***Biz***.: $\mathbb{R}^{d}$-ben igaz a Bolzano-Weierstrass tetel, vagyis minden korlatos sorozatbol kivalaszthato konvergens reszsorozat. A zartsag miatt a hatarertek $\in K$.

#### ***Tetel*** (Hausdorff):
$(X, \rho_{X}), (Y, \rho_{Y})$ metrikus terek, $f: X \to Y$ folytonos, $K \subset X$ kompakt. Ekkor $f(K)$ is kompakt.

***Biz***.: Legyen $(y_{n}) \subset f(K)$. Ekkor $y_{n} = f(x_{n}), \quad n \in \mathbb{N}, x_{n} \in K$.
Tehat $(x_{n}) \subset K$ kompakt $\xRightarrow{def} \exists (x_{n_{j}})$ reszsorozat, $x_{n_{j}} \to x \in K$.
$f$ folytonos $\implies$ $f(x_{n_{j}}) = y_{n_{j}} \to f(x) \in f(K)$ 


#### ***Tetel*** (Weierstrass):
$(X, \rho)$ metrikus ter, $f:X \to \mathbb{R}$ folytonos, $K \subset X$ kompakt. Ekkor $f$-nek van minimuma es maximuma $K$-n.

***Biz***.: Hausdorff $\implies f(K) \subset \mathbb{R}$  kompakt $\implies f(K)$ korlatos es zart $\implies f(K)$ -nak van legkisebb es legnagyobb eleme.

#### Tetel (Heine):
$(X, \rho_{X}), (Y, \rho_{Y}), f: X \to Y$ folytonos, $K \subset X$ kompakt. Ekkor $f$ egyenletesen folytonos $K$-n.

***Biz***.: Indirekt tegyuk fel, hogy $f$ nem egyenletesen folytonos $K$-n. Ekkor
$$
\exists (x_{n}) \subset K, \quad \exists(y_{n}) \subset K, \quad \rho_{X}(x_{n}, y_{n}) \to 0
$$
es
$$
\rho_{Y}(f(x_{n}), f(y_{n})) \geq \varepsilon > 0 \quad \forall n
$$
K kompakt $\implies$ $\exists (x_{n_{j}})$ reszsorozat, $x_{n_{j}} \to x \in K$
$\rho_{X}(x_{n_{j}}, y_{n_{j}}) \to 0 \implies y_{n_{j}} \to x \in K$
$f$ folytonos $K$-n $\implies$ $f(x_{n_{j}}) \to f(x)$ es $f(y_{n_{j}}) \to f(x)$ ellentmondas, mert $\rho_{Y}(f(x), f(x)) = 0$.




related: [[TovFejAnal]]