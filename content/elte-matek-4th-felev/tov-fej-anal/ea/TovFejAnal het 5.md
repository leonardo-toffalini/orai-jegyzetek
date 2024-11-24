date: 2024.03.12


### Folytonos linearis lekepezesek

$X, Y$ vektorterek, $A: X \to Y$ lekepezes linearis, ha 
1.) $A(x + y) = A(x) + A(y)$, $\forall x, y \in X$
2.) $A(\lambda \cdot x) = \lambda A(x)$, $\forall x \in X$

jel.: $A(x) = Ax$

Legyen most $(X, \| \cdot \|_{X})$ es $(Y, \| \cdot \|_{Y})$ normalt terek

### ***Def***.:
Az $A: X \to Y$ *folytonos linearis lekepezes*, ha linearis es folytonos a normak altal indukalt metrikakra nezve.

### ***Def***.:
Legyen $A: X \to Y$ linearis lekepezes. Azt mondjuk, hogy $A$ *korlatos linearis lekepezes*, ha $\exists M \geq 0$ konstans, hogy $\| Ax \|_{Y} \leq M \cdot \| x \|_{X}$ $\forall x \in X$.

### ***All***.:
Legyen $A: X\to Y$ normalt terek kozotti linearis lekepezes. Ekkor ekvivalensek:
(i) $A$ folytonos
(ii) $A$ folytonos $0_{X}$-ban
(iii) $A$ korlatos linearis lekepezes

***Biz***.:
(i) $\implies$ (ii) trivialis
(ii) $\implies$ (iii)
Legyen $\varepsilon = 1$. Ekkor a $0_{X}$ beli folytonossag definicioja szerint $\exists \delta > 0$ szam, hogy $\forall x \in X$ $\| x - 0 \|_{X} = \| x \|_{X} \leq \delta$ eseten $\| Ax \|_{Y} \leq 1$.
Legyen $x \in X$ tetszolekes. Ekkor $\left\|  \frac{\delta x}{\| x \|}  \right\| = \delta$ . Ezert $\| A\left( \delta \cdot \frac{x}{\| x \|} \right)  \|_{Y} \leq 1$, $\forall x \in X$.
Tehat 
$$
\left \|  \frac{\delta}{\| x \|_{X}} \cdot Ax  \right \|_{Y} = \frac{\delta}{\| x \|_{X}} \| Ax \|_{Y} \leq 1
$$
$$
\implies \| Ax \| _{Y} \leq \frac{1}{\delta} \| x \| _{X}
$$
Tehat $M := \frac{1}{\delta}$ valaszthato.

(iii) $\implies$ (i)
Tegyuk fel hogy $\| Ax \|_{Y} \leq M \cdot \| x \|_{X}$ $\forall x \in X$. Ekkor, ha $x, y \in X$ tetszoleges vektorok, akkor
$$
\| A(x - y) \| _{Y} = \| Ax - Ay \| _{Y} \leq M \cdot \| x - y \| _{X}
$$
Tehat $A$ Lipschitz folytonos, amibol kovetkezik, hogy folytonos.

*Megj*.: Ha $A:X \to Y$ folytonos linearis lekepezes, akkor Lipschitz-tulajdonsagu is.

*Jeloles*: Az $X$ es $Y$ normalt terek kozti folytonos (vagy korlatos) linearis lekepezesek teret $\mathcal L(X, Y)$-al jeloljuk. $\mathcal{L}(X) = \mathcal{L}(X, X)$.

### Def/Tetel
Legyen $A \in \mathcal{L}(X, Y)$. Ekkor az $M$ korlatozo konstansok kozul letezik legkisebb, amit $\| A \|$-val jelolunk.
Tehat $\| Ax \|_{Y} \leq \| A \| \cdot \| x \|_{X}$, $\forall x \in X$.

***Biz***.:
Legyen $M \geq 0$ olyan, hogy $\| Ax \|_{Y} \leq M \cdot \| x \|_{X}$
$$
\left\{  \frac{\| Ax \| _{Y}}{\| x \| _{X}} : x \in X \setminus \{ 0_{X} \}  \right\}
$$
ez a halmaz felulrol korlatos $\mathbb{R}$-ben
$$
\implies \exists \sup \left\{  \frac{\| Ax \| _{Y}}{\| x \| _{X}} : x \in X \setminus \{ 0_{X} \}  \right\}
$$
tovabba
$$
\| A \| :=  \sup \left\{  \frac{\| Ax \| _{Y}}{\| x \| _{X}} : x \in X \setminus \{ 0_{X} \}  \right\} \leq M \quad \text{ megengedett } M \text{-ekre}
$$
Masreszt $\| A \|$ definicioja miatt $\| Ax \|_{Y} \leq \| A \| \cdot \| x \|_{X}$. Ezzel belattuk a definiciot.

Atirva:
$$
\sup \left\{  \frac{\| Ax \| _{Y}}{\| x \| _{X}} : x \in X \setminus \{ 0_{X} \}  \right\} = \sup \left\{  \left \|  A\left(  \frac{1}{\| x \| _{X}} \cdot x \right)  \right \|_{Y} : x \in X \setminus \{ 0_{X} \}   \right\}
$$
$$
= \sup \{  \| Ax \| _{Y} : \| x \| _{X} = 1  \} = \| A \| 
$$

### ***All***.:
$\mathcal{L}(X, Y)$ vektorter normalt ter a fenti operator normaval.

***Biz***.:
1.) $\| A \| \geq 0$ igaz
2.) $\| A \| = 0 \iff A \equiv 0$
$\impliedby$ irany trivialis
$\implies$ $\sup \{ \| Ax \| : \| x \| = 1 \} = 0 \implies \| Ax \| = 0 \; \forall x \in X, \| x \| = 1$
	$\implies$ $\| Ax \| = 0 \; \forall x \in X : \left \|  \frac{x}{\| x \|_{X}}  \right \| = 1$
3.) $\| \lambda \cdot A \| \stackrel{\text{def}}{=} \sup \{ \| (\lambda \cdot A)x \|_{Y} : \| x \|_{X} = 1 \}$ 
$= \sup \{ \lvert \lambda \rvert \cdot \| Ax \|_{Y} : \| x \|_{X} = 1 \}$
$= \lvert \lambda \rvert \cdot \sup \{ \| Ax \|_{Y} : \| x \|_{X} = 1 \} = \lambda \cdot \| A \|$

4.)
$$
\begin{align}
\| (A + B)x \| _{Y} = \| Ax + Bx \|_{Y} & \leq \| Ax \| _{Y} + \| Bx \| _{Y} \\
& \stackrel{\text{def}}{\leq} \| A \|  \cdot \| x \| _{X} + \| B \| \cdot \| x \| _{X} \\
& = (\| A \| + \| B \| ) \cdot \| x \| _{X}
\end{align}
$$
$$
\implies \| A + B \|  \leq \| A \|  + \| B \| 
$$

*Megj*.: $\mathcal{L}(X)$ algebra a kompoziciora, mint szorzasra nezve, es $1$-elemes: $1 = \operatorname{Id}_{X}$.

### ***All***.:
$A \in \mathcal{L}(Y, Z), \; B \in \mathcal{L}(X, Y)$. Ekkor $A \cdot B \in \mathcal{L}(X, Z)$  es $\| A \cdot B \| \leq \| A \| \cdot \|  B \|$.
***Biz***.:
$A \cdot B = A \circ B$  folytonos - volt / mindjart lesz
$(A \cdot B)(x + y) = A(Bx + By) = ABx + ABy$
$(A\cdot B) (\lambda \cdot x) = A(\lambda \cdot Bx) = \lambda \cdot A(Bx) = \lambda ABx$

$$
\| (A \cdot B) x \|_{Z} = \| A(Bx) \|_{Z} \leq \| A \| \cdot \| Bx \| _{Y} \leq \| A \|  \cdot \|  B \| \cdot \| x \| _{X}
$$
$$
\implies \| A \cdot B \|  \leq \| A \|  \cdot \| B \| 
$$


### ***Def***.:
Azt mondjuk, hogy az $X$ es $Y$ normalt terek *izometrikusan izomorfak*, ha $\exists J : X \to Y$ linearis bijekcio, amelyre $\| Jx \|_{Y} = \| x \|_{X} \; \forall x \in X$.

*Megj*.: Ilyenkor $\| J \| = 1$.

### ***Def***.:
Egy $A:X \to \mathbb{R}$   linearis lekepezest szokas *linearis funkcionalnak* nevezni.
Masreszt, ha $A:X \to \mathbb{R}$ folytonos linearis lekepezes, akkor szokas *folytonos linearis funkcionalnak* nevezni.

*Jel*.: $\mathcal{L}(X, \mathbb{R}) = X'$  az $X$ normalt ter *dualis tere*, $\varphi \in X'$.

*peldak*:
1.) $X = C[0, 1]$, $\|  \cdot \|_{\max}$
$\varphi(f) := \int _{0}^{1}f \in \mathbb{R}$

All.: $\varphi \in \mathcal{L}(X, \mathbb{R}) = X'$
Biz.:
1.) $\varphi$ linearis: $\varphi(f+g) = \int _{0}^{1}f + g = \int _{0}^{1}f + \int _{0}^{1}g = \varphi(f) + \varphi(g)$, tovabba $\varphi(\lambda \cdot f) = \lambda \cdot \varphi(f)$
2.) $\varphi$ folytonos $\iff$ korlatos
$\lvert \varphi(f) \rvert = \left\lvert  \int _{0}^{1}f \right\rvert \leq \int _{0}^{1}\lvert f \rvert \leq 1 \cdot \max \limits_{[0,1]} \lvert f \rvert = 1 \cdot \| f \|_{\max}$

2.) $X = \mathbb{R}^{d}, \; \| \cdot \|_{1}$
$\varphi \in X' = \mathcal{L}(\mathbb{R}^{d}, \mathbb{R})$
$$
\varphi(x) = \varphi\left( \sum_{j = 1}^{d}x_{j} \cdot e_{j} \right) = \sum_{j=1}^{d}x_{j}\varphi(e_{j}) = (x, a_{\varphi})
$$
ahol $a_{\varphi} = (\varphi(e_{1}), \dots, \varphi(e_{d}))$

### ***All***.:
Legyen $X$ veges dimenzios normalt ter, $Y$ tetszoleges normalt ter. Ekkor minden $A :X \to Y$  linearis lekepezes folytonos / korlatos is.

***Biz***.: $X \cong \mathbb{R}^{d}$ , $\mathbb{R}^{d}$-n barmely ket norma ekvivalens legyen $\| x \|_{1} = \lvert x_{1} \rvert + \dots + \lvert x_{d} \rvert$
Legyen $A : (\mathbb{R}^{d}, \| \cdot \|_{1}) \to (Y, \| \cdot \|_{Y})$ linearis lekepezes.
Belatjuk, hogy $A$ korlatos. Legyen $\{ e_{1}, \dots, e_{d} \} \subset \mathbb{R}^{d}$ bazis rogzitve.
$x \in \mathbb{R}^{d}$ tetszoleges, $M := \max \{ \| Ae_{1} \|, \dots, \| Ae_{d} \| \}$.
$$
\| Ax \|_{Y} \stackrel{\text{(lin.)}}{=} \left \|  \sum_{j = 1}^{d} x_{j} \cdot Ae_{j}  \right \|_{Y} \stackrel{(\Delta\neq)}{\leq} \sum_{j=1}^{d}\| x_{j} \cdot Ae_{j} \|_{Y}  = \sum_{j=1}^{d} \lvert x_{j} \rvert  \cdot \| Ae_{j} \| _{Y} \leq M \cdot \sum_{j=1}^{d}\lvert x_{j} \rvert  = M \cdot \| x \| _{1}
$$
Tehat $A$ korlatos, amibol kovetkezik, hogy folytonos.

### ***All***.:
Legyen $H$ Hilbert-ter, legyen $y \in H$ rogzitett vektor.
$$
\varphi_{y}(x) := (x, y), \quad  x \in H
$$
allitas: $\varphi_{y} \in H' = \mathcal{L}(H, \mathbb{R})$, masreszt $\| \varphi_{y} \| \leq \| y \|_{H}$

***Biz***.:
1.) $\varphi_{y}$ linearis, mert
$$
\begin{align}
\varphi_{y}(\lambda_{1}x_{1} + \lambda_{2}x_{2}) &\stackrel{\text{def}}{=} (\lambda_{1}x_{1} + \lambda_{2}x_{2}, y) \\
& = \lambda (x_{1}, y) + \lambda_{2}(x_{2}, y) \\
& = \lambda_{1} \varphi(x_{1}) + \lambda_{2}\varphi(x_{2})
\end{align}
$$
2.) $\varphi_{y}$ korlatos $\implies$ folytonos
$$
\lvert \varphi_{y}(x) \rvert  = \lvert (x, y) \rvert \stackrel{\text{Cauchy Schwartz}}{\leq} \| x \|_{H} \cdot \| y \| _{H}
$$
$\implies \| \varphi_{y} \| \leq \| y \|_{H}$

### Tetel (Riesz-Fréchet)
Legyen $J:H \to H'$, $Jy := \varphi_{y} \in H'$. Ekkor $J$ izometrikus izomorfia a $H$ es a $H'$ kozott, vagyis $J$ linearis bijekcio es $\| Jy \|_{H'} = \| \varphi_{y} \|_{H'} = \| y \|_{H}$.

***Biz***.:
1.) $J$ linearitasa
$$
J(y_{1} + y_{2}) \stackrel{?}{=} \varphi_{y_{1}} + \varphi_{y_{2}} \in H'
$$
Kell, hogy
$$
\begin{align}
J(y_{1} + y_{2})(x) & = \varphi_{y_{1} + y_{2}}(x) \stackrel{?}{=} \varphi_{y_{1}}(x) + \varphi_{y_{2}}(x) \\
& = (x, y_{1} + y_{2}) = (x, y_{1}) + (x, y_{2})
\end{align}
$$
ugyanigy
$$
J(\lambda y) = \varphi_{\lambda y} = \lambda J(y) = \lambda \varphi_{y}
$$

2.) $J y \in H'$ ez volt, $\| Jy \| = \| \varphi_{y} \| \leq \| y \|_{H}$.
$$
\lvert (Jy)(y) \rvert = \lvert \varphi_{y}(y) \rvert = \lvert (y, y) \rvert \stackrel{def}{=} \| y \|_{H} \cdot \|  y \| _{H}
$$
$$
\implies \| \varphi_{y} \|  = \| y \| _{H}
$$

3.)
Kell meg, hogy bijekcio!

i) $J$ injektiv, mivel $J$ linearis ezert eleg belatni, hogy $Jy \equiv 0_{H'} \implies y = 0_{H}$, vagyis $\operatorname{Ker}(J) = 0_{H}$.
$Jy \equiv 0 \iff \varphi_{y}(x) = 0 \quad \forall x \in H \implies \varphi_{y}(y) = 0 \iff (y, y) = 0 \implies y = 0$ 

ii) $J$ szurjektiv a $H'$-re, vagyis tetszoleges $\varphi \in H'$ folytonos linearis funkcional eloall mint $\varphi_{y}$ valamely $y \in H$ eseten.
Legyen $\varphi \in H'$  tetszoleges, megmutatjuk, hogy $\exists y \in H$ ugy, hogy $\varphi(x) = \varphi_{y}(x) \quad \forall x \in H$ vagyis $\varphi(x) = (x, y) \quad \forall x \in H$.
Tekintsuk a $\operatorname{Ker} \varphi := \{ x \in H : \varphi(x) = 0 \}$ alteret, raadasul $\operatorname{Ker} \varphi$ zart alter, ugyanis, ha $(x_{n}) \subset \operatorname{Ker} \varphi, \; x_{n} \to x \in H$, akkor $\varphi(x_{n}) \to \varphi(x) = 0$ ($\varphi$ folytonos) $\implies x \in \operatorname{Ker}\varphi$.

Riesz tetel az ortogonalis felbontasrol masodik esete azt mondja, hogy
1.)
$$
\operatorname{Ker} \varphi = H \implies \varphi \equiv 0 \implies \varphi = \varphi_{0} \quad y = 0 \text{ jó}
$$
2.)
$$
\operatorname{Ker} \varphi \subset H \text{ valodi zart alter} \implies \exists e \in H \setminus \operatorname{Ker} \varphi : \| e \|  = 1, \quad e \perp \operatorname{Ker} \varphi
$$
Legyen
$$
y := \varphi(e) \cdot e
$$
Ez pont jo, vagyis $\varphi(x) = (x, \varphi(e) \cdot e) \quad \forall x \in H$.

$$
\varphi(x) = (x, \varphi(e) \cdot e) \iff \varphi(x) - (x, \varphi(e) \cdot e) = 0 
$$
$$
\iff \varphi(x) \cdot (e, e) - (x, \varphi(e) \cdot e) = 0
$$
$$
\iff (\varphi(x)\cdot e, e) - (\varphi(e) \cdot x, e) = 0
$$
$$
\iff (\varphi(x) \cdot e - \varphi(e) \cdot x, e) = 0
$$

All.: $\varphi(x)\cdot e - \varphi(e) \cdot x \in \operatorname{Ker}\varphi$ es ekkor keszen is vagyunk, mivel $e \perp \operatorname{Ker} \varphi$.
Biz.: $\varphi(\varphi(x) \cdot e - \varphi(e) \cdot x) \stackrel{lin}{=} \varphi(x) \cdot \varphi(e) - \varphi(e) \cdot \varphi(x) = 0$







related: [[TovFejAnal]]