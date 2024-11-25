### 1.
Legyen $H=\ell_{\mathbb{K}}^2, \quad e_n:=(\stackrel{n-1}{\overbrace{0, \ldots, 0}}, 1,0 \ldots)$ (vagyis minden rögzített $n$-re $e_n$ az a sorozat, amelyre $e_n(n)=1$, és $e_n(k)=0$, ha $k \neq n$.)
(a) Mutassuk meg, hogy $\left(e_n\right)_{n \in \mathbb{N}}$ teljes ortonormált rendszer $\ell_{\mathbb{K}}^2$-ban!
(b) Legyen $x$ az a $\mathbb{K}$-ban haladó sorozat, amelyre $n \in \mathbb{N}$ esetén $x_n:=\frac{1}{n}$. Igazoljuk, hogy $x \in \ell_{\mathbb{K}}^2$, és írjuk fel $x$-nek az $\left(e_n\right)_{n \in \mathbb{N}}$ rendszer szerinti Fourier sorát!

**Megoldas:**
a) Ortogonalis, mert 
$$
\forall k \neq n: \quad (e_{n}, e_{k}) = \sum_{j=1}^{\infty}e_{n}(j)e_{k}(j) = \sum_{j=1}^{\infty}0 = 0
$$
Normalt, mert
$$
\forall n : \quad (e_{n},e_{n}) = \sum_{j = 1}^{\infty}e_{n}(j) = 1
$$
Teljes, mert
$$
\forall x \in \ell ^{2}_{\mathbb K} : \quad (x, e_{n}) = 0, \quad \forall n \implies x \equiv 0
$$
Ez igaz, mert ha minden $n$-re a skalar szorzat $0$-akkor minden $n$-re az $x$ $n$-edik eleme $0$, tehat o maga csak a csupa $0$ lehet.

b) $x \in \ell ^{2}_{\mathbb K}$, mert
$$
\sum_{j=1}^{\infty} \lvert x_{j} \rvert ^{2} = \sum_{j=1}^{\infty} \left\lvert  \frac{1}{j}  \right\rvert ^{2} = \sum_{j=1}^{\infty} \frac{1}{j^{2}} = \frac{\pi ^{2}}{6} < \infty
$$
Fourier-sorfejtese:
$$
x = \sum_{j = 1}^{\infty} (x, e_{j})e_{j} = \sum_{j=1}^{\infty} \left( \sum_{k=1}^{\infty} x(k) \cdot e_{j}(k) \right) \cdot e_{j} = \sum_{j=1}^{\infty} \left( \sum_{k=1}^{\infty} \frac{1}{k} \cdot e_{j}(k) \right)e_{j}
$$
$$
= \sum_{j=1}^{\infty} \frac{1}{j}e_{j} = \left(  \frac{1}{1}, \frac{1}{2}, \frac{1}{3}, \dots  \right)
$$


### 2.
Legyen $I=[a, b], H=L^2(I), K$ a konstansfüggvények $1$-dimenziós altere.
(a) Adjuk meg egy $f \in L^2(I)$ vetületét $K$-ra!
(b) Határozzuk meg a $K^{\perp}$ alteret!
(c) Igazoljuk, hogy $K$ zárt altér!
(d) Igazoljuk, hogy minden $f \in L^2(I)$ függvényhez létezik egyetlen olyan $u \in L^2(I)$, hogy $\int_a^b u=0$ és $f-u$ konstans függvény.

**Megoldas:**
a) ONB-t keresunk $K$-ban
Legyen $B := \{\text{konstans } 1 \text{ fuggveny}\}$
$$
\lvert\lvert 1_{K} \rvert\rvert = \sqrt{ \int _{I}1 \, dx  } = \sqrt{ b- a }
$$
ONB $K$-ban: $\frac{1}{\sqrt{ b-a }}$
$$
f_{K} = \left( f, \frac{1_{K}}{\sqrt{ b-a }} \right) \cdot \frac{1_{K}}{\sqrt{ b-a }} = \frac{1}{b-a} \int _{I}f(x) \, dx \cdot 1
$$

b) $K^{\perp} := \{  g \in H : g \perp c \quad \forall c \in K \}$
$$
= \left\{  f \in L^{2}(I): \int _{I}f \cdot c = 0, \; \forall c \in K   \right\}
$$
$$
= \left\{  f \in L^{2}(I) : c \cdot \int _{I}f, \; \forall c \in K   \right\}
$$
$$
= \left\{  f \in L^{2}(I) : \int _{I}f   \right\}
$$

c) $K$ zárt altér
$$
\forall c_{1}, c_{2} \in K, \; \forall k \in \mathbb{R}: \quad kc_{1} + c_{2} \in \mathbb{R}
$$
$$
\implies \text{alter}
$$
$$
\operatorname{dim} K < \infty \implies \text{zart}
$$
d) Minden $f \in L^2(I)$ függvényhez létezik egyetlen olyan $u \in L^2(I)$, hogy $\int_a^b u=0$ és $f-u$ konstans függvény.
Riesz fele ortogonalitas tetel:
$$
(H, (\cdot,\; \cdot)) \text{ Hilbert-ter } H_{1} \text{ zart altere } H\text{-nak}
$$
$$
\implies H = H_{1} \oplus H_{1}^{\perp}
$$
A c) feladatresz miatt tudjuk, hogy alkalmazhato a tetel, mert $H = L^{2}(I)$ Hilbert-ter, $H_{1} = K$.
$$
\forall f \in L^{2}(I) : \exists! u \in K^{\perp}, \; c\in K : f = u + c
$$
$$
\implies f - u = c \in K
$$



### 3.
Legyen $\Omega=B(0,1) \subset \mathbb{R}^2$ az egységkörlap, és $\alpha>0$ rögzített szám. Az $f(x)=\frac{1}{|x|^\alpha}$ függvény mely $p$ esetén lesz $L^p(\Omega)$-beli?

**Megoldas:**
Kerdes:
Mely $p$-re lesz a kovetkezo integral veges?
$$
\left(\int _{\Omega}\left\lvert  \frac{1}{\lvert x \rvert ^{\alpha}}  \right\rvert ^{p} \, dx\right)^{1/p}
$$
$$
\begin{align}
\left(\int _{\Omega}\left\lvert  \frac{1}{\lvert x \rvert ^{\alpha}}  \right\rvert ^{p} \, dx\right)^{1/p} & = \left( \int _{\Omega} \frac{1}{\lvert x \rvert ^{\alpha \cdot p}} \, dx  \right)^{1/p} \\
\left( \int _{0}^{2\pi} \int _{0}^{1} \frac{1}{\lvert r \rvert } \cdot r \, dr  \, d\vartheta  \right) & =
\end{align}
$$


related: [[TovFejAnal]]