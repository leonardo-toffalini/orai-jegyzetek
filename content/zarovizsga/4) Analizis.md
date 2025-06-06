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
- $\sin$
- $\cos$
- $\tan$

#### Inverz trigonometrikus fuggvenyek
- $\sin ^{-1}$
- $\cos ^{-1}$
- $\tan ^{-1}$

#### Hiperbolikus fuggvenyek
- $\sinh$
- $\cosh$
- $\tanh$

#### Inverz hiperbolikus fuggvenyek
- $\sinh ^{-1}$
- $\cosh ^{-1}$
- $\tanh ^{-1}$

### Differencialhatosag
### Fuggvenyvizsgalat
### Tobbvaltozos differencialhatosag
### Szelsoertek
### Komplex differencialhatosag

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

## c) Vegtelen sorok
### Szamsorozatok es sorok
### Fuggvenysorozatok es sorok
### Hatvanysor
### Taylor sor
### Komplex fuggvenyek es hatvanysorok
### Komplex exponencialis fuggveny
### Fourier sorok
 