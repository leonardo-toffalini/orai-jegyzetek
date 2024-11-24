date: 2024.02.27

#### ***Def***.: Legyen $D \subset H$ tetszoleges reszhalmaz. $D^{\perp} := \{ x \in H : x \perp D \}$ .

#### ***Áll***.: $D^{\perp}$ mindig zart alter.
***Biz***.: Ha $x, y \in D^{\perp}$, $\alpha, \beta \in \mathbb{R}$, akkor $(\alpha x + \beta y, d) = \alpha(x,d) + \beta(y,d) = \alpha 0 + \beta 0 = 0$.
Legyen $(x_{n}) \subset D^{\perp}, x_{n}\to x \in H$, megmutatjuk, hogy $x \in D^{\perp}$.
Ehhez kell, hogy $d \in D$ eseten $(x,d) = 0$.
Tudjuk, hogy $(x_{n}, d) = 0 \; \forall n$, $x_{n}\to x \xRightarrow{\text{sk. sz. folyt.}} (x_{n}, d) \to (x,d)$.

***Megj***.: $D \cap D^{\perp} = \{ 0 \}$ vagy $\emptyset$.

### ***Tétel*** (Riesz-féle ortogonális felbontásról):
1. Legyen $M \subset H$, $M \neq \emptyset$ zart alter. Ekkor $\forall x \in H$ esetn $\exists ! y \in M$ es $z \in M^{\perp}$: $x = y + z$
Jel.: $H = M \oplus M^{\perp}$ 
2. Legyen $M \subset H$, $M \neq \emptyset$ valodi zart alter. Ekkor $\exists x \in H \setminus M: \; \operatorname{dist}(x, M) = \| x \| = 1$

***Biz***.:
1. A fenti tetel masodik pontja miatt tudjuk, hogy tetszoleges $x \in H$-ra:
$$
\exists P_{M}x \in M, \; x-P_{M}x \perp M
$$
Legyen $y := P_{M}x \in M$, $z := x - P_{M}x \in M^{\perp}$.
Ezzel a jelolessel $x = y + z$
Meg kerdeses az egyertelmuseg.
$$
x = y + z \stackrel{?}{=} y' + z'
$$
$$
\implies y -y' = z' - z, \quad y-y' \in M, \quad z'-z \in M^{\perp}
$$
$$
\implies y-y' = 0 = z'-z
$$
Tehat az eloallitas egyertelmu!

2. Legyen $z \in H \setminus M$ tetszoleges vektor. Ekkor $$
x := \frac{z - P_{m}z}{\| z- P_{M} z \| }, \quad \operatorname{dist}(x, M) = \frac{\| z - P_{M}z \| }{\| z - P_{M}z \| } = 1
$$


### Normatl/Banach-terek revisited

#### **Def***.: Legyen $(X, \| \cdot \|_{1})$, $(X, \| \cdot \|_{2})$ normalt terek. Azt mondjuk, hogy $\| \cdot \|_{1}$ es $\| \cdot \|_{2}$ *ekvivalensek*, ha $\exists c_{1}, c_{2} > 0: \; c_{1} \| x \|_{1} \leq \| x \|_{2} \leq c_{2} \| x \|_{1}, \quad \forall x \in X$.

pl.: $(\mathbb{R}^{d}, \| \cdot \|_{p})$, $1 \leq p \leq \infty$ mind ekvivalens normak.
Eleg: $\| \cdot \|_{p} \sim \| \cdot \|_{\infty}$, mivel ez ekvivalencia relacio, tehat tranzitiv is.

#### **All***.: Ha $\| \cdot \|_{1} \sim \| \cdot \|_{2}$, $X$-en, akkor $(X, \| \cdot \|_{1})$ Banach-ter $\iff$ $(X, \| \cdot \|_{2})$ Banach-ter.
***Biz***.: Az ekvivalencia feltetel miatt $\| \cdot \|_{1}$ - Cauchy-sorozatok megegyeznek a $\| \cdot \|_{2}$ - Cauchy-sorozatokkal, es ugyanigy a konvergens sorozatok is.


### Ortonormalt sorozatok

#### **Def***.: Egy $(e_{k}) \subset H$ *ortonormalt* sorozat, ha $e_{j} \perp e_{k}, \; j \neq k$ es $\| e_{j} \| = 1, \; \forall j$.

peldak:
1. $\ell^{2} = \left\{  (x_{n}) \subset \mathbb{R} : \sum_{n=1}^{\infty}\lvert x_{n} \rvert^{2} < \infty  \right\}$ $((x_{n}), (y_{n})) = \sum_{n=1}^{\infty}x_{n}y_{n}$
$$
e_{k} = (0, 0, \dots, 0, 1, 0, \dots) \in \ell^{2}
$$
A $k$-adik elem egyes.

2. $\left(C[a,b], \int _{a}^{b} fg\right), \quad \| f \|^{2} = \int _{a}^{b}\lvert f \rvert^{2}$  Euklideszi-ter, de nem Hilbert-ter.
Ennek a teljesse tetele: $L^{2}(a, b), \quad f, g \in L^{2}(a,b): \; (f, g) = \int _{a}^{b}fg$
Megjegyzes: $C[a, b] \subset L^{2}(a,b)$

### Trigonometrikus rendszerek
$L^{2}(0,2\pi) := \left\{  f:[0,2\pi] \to \mathbb{R} : \int _{0}^{2\pi}\lvert f \rvert^{2} \, dx < \infty  \right\}$
a) $L^{2}(0, 2\pi)$ (tetszoleges $2\pi$ hosszu intervallumon is mukodik).
$$
e_{0} = \frac{1}{\sqrt{ 2\pi }}, \; e_{2k -1} = \frac{1}{\sqrt{ \pi }} \sin (kt), \; e_{2k} = \frac{1}{\sqrt{ \pi }} \cos (kt), \quad k = 1, 2, \dots
$$

b) $L^{2}(0, \pi)$ (tetszoleges $\pi$ hosszu intervallumon mukodik).
$$
e_{k} = \sqrt{ \frac{2}{\pi} } \sin(kt), \quad k = 1, 2, \dots
$$

c) $L^{2}(0, \pi)$
$$
e_{0} = \frac{1}{\sqrt{ \pi }}, \; e_{k} = \sqrt{ \frac{2}{\pi} } \cos(kt), \quad k = 1, 2, \dots
$$

### **All***.: A fenti peldak ortonormalt sorozatok
***Biz***.:
1. Mindegyikre trivi.
2. 
a) $L^{2}(0, 2\pi)$
$$
\| e_{0} \| ^{2} = \int _{0}^{2\pi} \frac{1}{2\pi} \, dx  = 1
$$
$$
\| e_{2k-1} \| ^{2} = \frac{1}{\pi} \int _{0}^{2\pi} \sin ^{2}(kt) \, dt = \frac{1}{2\pi} \int _{0}^{2\pi}(1 - \cos(2kt)) \, dt = 1 - \frac{1}{4k\pi}\left[ \sin(2kt) \right] _{0}^{2\pi} = 1
$$
$$
(e_{0}, e_{2k-1}) = \frac{1}{\sqrt{ 2\pi }} \int _{0}^{2\pi}\sin(kt) \, dt = 0 = (e_{0}, e_{2k}) 
$$
$$
(e_{2k-1}, e_{2j}) = \frac{1}{\pi} \int _{0}^{2\pi} \sin(kt) \cdot \cos(jt) \, dt = \frac{1}{2\pi} \int _{0}^{2\pi} \sin((k+j)t) + \sin((k-j)t) \, dt = 0 + 0 = 0
$$
$$
(e_{2k-1}, e_{2j-1}) = \frac{1}{\pi} \int _{0}^{2\pi} \sin(kt) \cdot \sin(jt) \, dt = \frac{1}{2\pi} \int _{0}^{2\pi} \cos((k-j)t) - \cos((k+j)t) \, dt = 0 - 0 = 0
$$
$$
(e_{2k},e_{2j}) = \text{HF}
$$

b) $L^{2}(0, \pi)$
$$
e_{k} = \sqrt{ \frac{2}{\pi} } \sin(kt), \quad k = 1, 2, \dots
$$
$$
\| e_{k} \| ^{2} = 1 \quad \text{HF}
$$
$$
(e_{k}, e_{j}) = \frac{2}{\pi} \int _{0}^{\pi} \sin(kt) \cdot \sin(jt) \, dt = \frac{1}{\pi} \int _{0}^{\pi} \cos((k-j)t) - \cos((k+j)t) \, dt  = \frac{1}{\pi} \left[ \frac{\sin((k-j)t)}{k-j} - \frac{\sin((k+j)t)}{k+j} \right]_{0}^{\pi} = 0
$$

c) Ugyanigy HF

#### **All***.: Legyenek $(e_{k})$ ortonormalt sorozat $H$-ban.
1. Legyen $M := \operatorname{span} \langle e_{1}, e_{2}, \dots, e_{n} \rangle$. Legyen $x \in H$ tetszoleges. Ekkor
$$
P_{M}x = \sum_{j = 1}^{n}(x,e_{j}) \cdot e_{j}
$$
2. *Bessel-egyenloseg*: $\forall x \in H, \; \forall n \in \mathbb{N}$
$$
\left\lvert \left\lvert  x - \sum_{j=1}^{n}(x, e_{j}) \cdot e_{j}  \right\rvert \right\rvert ^{2} = \| x \| ^{2} - \sum_{j=1}^{n}\lvert (x, e_{j}) \rvert ^{2}
$$
3. *Bessel-egyenlotlenseg*: $\forall x \in H$ eseten
$$
\sum_{j=1}^{n}\lvert (x, e_{j}) \rvert ^{2} \leq \| x \| ^{2}
$$
$$
(x, e_{j}) \text{ neve: } j\text{-edik Fourier egyutthato}
$$
$$
\implies \sum_{j=1}^{n} \lvert (x, e_{j}) \rvert ^{2} \text{ konverges}
$$
4. Legyen $(c_{j}) \subset \mathbb{R}$. Ekkor
$$
\sum c_{j} \cdot e_{j} \text{ konvergens } H \text{-ban} \iff \sum_{j=1}^{\infty} \lvert c_{j} \rvert ^{2} < \infty \iff (c_{j}) \in \ell^{2}
$$
#### **Lemma***: Ha $x_{1}, x_{2}, \dots, x_{n} \in H$ vektorok paronkent ortogonalisak, akkor
$$
\| x_{1} + x_{2} + \dots + x_{n} \| ^{2} = \| x_{1} \| ^{2} + \dots + \| x_{n} \| ^{2}
$$
***Biz***.:
$$
\| x_{1} + x_{2} + \dots + x_{n} \| ^{2} = \sum_{j = 1} ^{n} \sum_{k = 1}^{n}(x_{j}, x_{k}) = \| x_{1} \| ^{2} + \dots + \| x_{n} \| ^{2}
$$

***Allitas bizonyitasa***:
1. 
$$
\sum_{j = 1}^{n}(x, e_{j}) \cdot e_{j} \in M
$$
Kell, hogy $x- \sum_{j=1}^{n}(x, e_{j}) \cdot e_{j} \perp M$

Skalaris szorzat linearitasa miatt eleg, hogy $\forall k = 1, 2, \dots, n: \; x- \sum_{j=1}^{n}(x, e_{j}) \cdot e_{j} \perp e_{k}$
$$
\left(x- \sum_{j=1}^{n}(x, e_{j}) \cdot e_{j} , e_{k} \right) = (x, e_{k}) - \sum_{j=1}^{n}(x, e_{j})(e_{j}, e_{k}) = (x, e_{k}) - (x, e_{k})(e_{k}, e_{k}) = 0
$$

2. Legyen $x \in H$ tetszoleges.
$$
\| x \| ^{2} = \left\lvert \left\lvert  x - \sum_{j = 1}^{n}(x, e_{j}) \cdot e_{j} + \sum_{j = 1}^{n}(x, e_{j}) \cdot e_{j}  \right\rvert \right\rvert 
$$
Mivel $\sum_{j = 1}^{n}(x, e_{j}) \cdot e_{j} \in M$ es $x - \sum_{j = 1}^{n}(x, e_{j}) \cdot e_{j} \perp M$ ezert a fenti tovabb egyenlo
$$
= \left\lvert \left\lvert  x - \sum_{j = 1}^{n}(x, e_{j}) \cdot e_{j}   \right\rvert \right\rvert ^{2} + \left\lvert \left\lvert  \sum_{j = 1}^{n}(x, e_{j}) \cdot e_{j}   \right\rvert \right\rvert ^{2} = \left\lvert \left\lvert  x - \sum_{j = 1}^{n}(x, e_{j}) \cdot e_{j}   \right\rvert \right\rvert ^{2} + \sum_{j=1}^{n}\lvert (x, e_{j}) \rvert ^{2}
$$

3. Kovetkezik 2.-bol
$$
\forall n : \; \sum_{j=1}^{n}\lvert (x, e_{j}) \rvert ^{2} \leq \| x \| ^{2} \implies \sum_{j=1}^{\infty}\lvert (x, e_{j}) \rvert ^{2} \leq \| x \| ^{2}
$$

4. 
$$
\left( \sum_{j = 1} ^{n} c_{j} \cdot e_{j} \right)_{n \in \mathbb{N}} \subset H \text{ konvergens } \iff \text{ Cauchy-sorozat}
$$
$$
\iff \left\lvert \left\lvert  \sum_{j = m + 1}^{n}c_{j} \cdot e_{j}  \right\rvert \right\rvert ^{2} = \sum_{j = m+1}^{n}\lvert c_{j} \rvert ^{2} < \varepsilon, \quad n, m \geq N \iff \sum_{j = 1}^{\infty} \lvert c_{j} \rvert ^{2} < \infty
$$

### **Tetel***: Legyen $(e_{k}) \subset H$ ortonormalt. Ekkor ekvivalensek a kovetkezok:
i) Fourier-sor eloallitas teljesul, vagyis $\forall x \in H$
$$
x = \sum_{j=1}^{\infty}(x, e_{j}) \cdot e_{j}
$$
ii) *Parseval-egyenloseg*: $\forall x \in H$ eseten
$$
\| x \| ^{2} = \sum_{j = 1}^{\infty} \lvert (x, e_{j}) \rvert ^{2}
$$

iii) Ha $y \perp e_{j} \quad \forall j = 1, 2, \dots$, akkor $y = 0$.

***Biz***.:
i) $\implies$ ii)
$$
x = \sum_{j=1}^{\infty}(x, e_{j}) \cdot e_{j} \iff \left\lvert \left\lvert  x - \sum_{j=1}^{n}(x, e_{j}) \cdot e_{j}  \right\rvert \right\rvert ^{2} \to 0, \quad n \to \infty
$$
$$
\left\lvert \left\lvert  x - \sum_{j=1}^{n}(x, e_{j}) \cdot e_{j}  \right\rvert \right\rvert ^{2} \text{ Bessel egyenloseg miatt } = \| x \| ^{2} - \sum_{j = 1}^{n} \lvert (x, e_{j}) \rvert ^{2} 
$$
Tehat a fenti
$$
\iff \| x \| ^{2} - \sum_{j = 1}^{n} \lvert (x, e_{j}) \rvert ^{2}  \to 0, \quad n \to \infty
$$

i) $\implies$ iii)
Legyen $y = \sum_{j=1}^{\infty}(y, e_{j}) \cdot e_{j}$ de mivel feltetel miatt $(y, e_{j}) = 0, \; \forall j$ ezert $y = 0$

iii) $\implies$ i)
Legyen $x \in H$ tetszoleges. Kell, hogy $x = \sum_{j = 1}^{\infty} (x, e_{j}) \cdot e_{j}$.
Tudjuk
$$
\left( x - \sum_{j = 1}^{\infty} (x, e_{j}) \cdot e_{j}, \; e_{k} \right) = (x, e_{k}) - \sum_{j=1}^{\infty} (x,e_{j}) \cdot (e_{j}, e_{k}) = (x, e_{k}) - (x, e_{k}) = 0 \quad \forall k = 1, 2, \dots
$$
iii) $\implies$ $x - \sum_{j = 1}^{\infty} (x, e_{j}) \cdot e_{j} = 0$


#### **Def**.:
$(e_{k}) \subset H$ ortonormalt sorozat *teljes ortonormalt sorozat (TONS)* vagy **ortonormalt bazis (ONB)**, ha a fenti tetel harom allitasa kozul az egyik teljesul.



related: [[TovFejAnal]]