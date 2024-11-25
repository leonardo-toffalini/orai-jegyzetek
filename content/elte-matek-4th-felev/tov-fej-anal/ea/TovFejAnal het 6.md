date: 2024.03.19

máj. 26. ea megtartva
ápr. 2. tavaszi szünet miatt elmarad
ápr. 9. 1. ZH időpontja
ápr. 16. ea magtartva

*Megjegyzes*: Ha $Y$ Banach-ter, akkor $\mathcal{L}(X, Y)$ szinten Banach-ter.
peldaul, ha $X = Y$ es $X$ banach ter, akkor $\mathcal{L}(X) = \mathcal{L}(X, X)$ is Banach-ter.

Specialis eset: $Y = \mathbb{R}$ (vagy $\mathbb{C}$), ilyenkor $\mathcal{L}(X, \mathbb{R}) = X'$  $X$ dualis tere. Ez mindig Banach ter, $X$-tol fuggetlenul, az elozo megjegyzes szerint.
Elnevezes: $\varphi \in X'$-ket folytonos linearis funkcionaloknak nevezzuk.

Ha $\varphi \in X'$ ekkor a kovetkezokeppen tudjuk definialni $\varphi$ normajat: $\| \varphi \| = \min \{ M : \lvert \varphi(x) \rvert \leq M \cdot \| x \| \}$.

Legyen $H$ Hilbert-ter (Banach- ter a skalaris szorzat altal indukalt normara nezve)
$x \in H$ ekkor $\| x \|^{2} = (x, x)$

(Riesz-Frechet tetelnek bizonyitasanak a folytatasa, az elozo eloadas jegyzeteben szerepel)

*Megjegyzes:* Szokas Riesz-reprezentacios tetelnek is nevezni a Riesz-Fréchet tetelt. Ez alapjan szokas azonositani $H$-t $H'$-vel, tehat $H \equiv H'$ es meg is tudjuk mondani melyeik izometrikus izomorfia viszi az egyiket a masikba.

***Q.:*** (Altalanos) Banach-terekben mik lesznek a dualis ter elemei, azaz mik $X'$ elemei?
*Emlek*: Rang-tetel (dimenzio formula): $A:X \to Y$ linearis lekepezes, tovabba $\operatorname{dim}X, \operatorname{dim} Y < \infty$, ekkor $\operatorname{dim} \operatorname{Ker}A + \operatorname{dim} \operatorname{Im}A = \operatorname{dim}X$.

Legyen $X$ (vegtelen dimenzios) vektorter, $\varphi: X \to \mathbb{R}$ linearis $\varphi \not\equiv 0$.
$\operatorname{Ker} \varphi \subset X$ $1$-kodimenzios alter

### ***Def***.:
Legyen $X$ (vegtelen dimenzios) vektorter, azt mondjuk, hogy $M \subset X$ alter $1$-kodimenzios alter vagy hipersik, ha tetszoleges $A \setminus M$ es $\operatorname{lin}\langle M, a \rangle = X$.

### ***All***.: 
Legyen $X$ vektorter. Ekkor az $X$-beli hipersikok megfelelnek a $\varphi : X \to \mathbb{R}$ lekepezesek magtereinek.

***Biz***.: 1.) Ha $\varphi : X \to \mathbb{R}$ linearis, akkor $\operatorname{Ker} \varphi \subset X$  linearis.
Legyen $a \in X \setminus \operatorname{Ker} \varphi$, legyen $x \in X$ tetszoleges.
$$
\varphi\left(x - \frac{\varphi(x)}{\varphi(a)} \cdot a\right) \in \langle a \rangle = \varphi(x) - \frac{\varphi(x)}{\varphi(a)} \cdot \varphi(a) = 0
$$
$$
\implies x - \frac{\varphi(x)}{\varphi(a)} \cdot a \in \operatorname{Ker} \varphi
$$
2.) Van egy hipersikunk, hogyan definialunk egy olyan linearis lekepezest melynek pont ez a magja.
Legyen $M \subset X$ hipersik, legyen $a \in X \setminus M$ tetszoleges
Tudjuk: $\langle M, a \rangle = X \implies$ tetszolehes $x \in X$ eloall mint $X = m + t\cdot a, \quad m \in M, t \in \mathbb{R}$.
$$
\varphi(x) := t, \quad \text{ ha } x = m + t \cdot a, \quad \text{ ahol } m \in M, t \in \mathbb{R}
$$
ez linearis, mert $y = m' + t' \cdot a$
$$
\varphi(x + y) = t + t' = \varphi(x) + \varphi(y)
$$
masreszt a magja pont az $M$, mert
$$
\varphi(x) = 0 \iff t = 0 \quad \text{ tehat } x = m \in M
$$

### ***All***.:
$X$ normalt ter, akkor $X' = \mathcal{L}(X, \mathbb{R})$ elemei megfelelnek a zart hipersikoknak.

***Biz***.: $\varphi \in X'$ $\operatorname{Ker}\varphi \subset X$ zart alter. Nem biz.

Pelda olyan $X$ Banach-terre, aminek pontosan le tudjuk irni a dualis teret, azaz $X'$-t.
$$
X := \ell^{p} := \left\{  (x_{n}) \subset \mathbb{R} : \sum_{n=1}^{\infty} \lvert x_{n} \rvert ^{p} < \infty \right\}, \quad 1 \leq p < \infty
$$
$$
\ell^{\infty} := \{ (x_{n}) \subset \mathbb{R}: \sup_{n \in \mathbb{N}} \lvert x_{n} \rvert < \infty \}
$$

$$
x \in \ell^{p}: \quad \| x \| _{p} = \left( \sum_{n=1}^{\infty}\lvert x_{n} \rvert ^{p} \right)^{1/p}, \quad 1 \leq p < \infty
$$
$$
x \in \ell^{\infty}: \quad \| x \| _{\infty} = \sup_{n \in \mathbb{N}} \lvert x_{n} \rvert 
$$

### ***Tetel*** (Holder altalanositas):
Legyen $p$ es $q$ konjugalt kitevok, azaz $\frac{1}{p} + \frac{1}{q} = 1$, $1 \leq p, q, \leq \infty$
1.) Ha $x \in \ell^{p}, \; y \in \ell ^{q}$, akkor $x \cdot y = (x_{n} \cdot y_{n})_{n \in \mathbb{N}} \in \ell^{1}$, es $\| x \cdot y \|_{1} = \sum_{n=1}^{\infty} \lvert x_{n} \cdot y_{n} \rvert \leq \| x \|_{p} \cdot \| y \|_{q}$

### ***Tetel*** (Minnkowski altalanositas):
$x, z \in \ell^{p} \implies x + z \in \ell ^{p}, \quad \| x + z \|_{p} \leq \| x \|_{p} + \| z \|_{p}$

### ***Tetel***:
$\ell^{p}$ Banach ter, $1 \leq p < \infty$

### ***Tetel***:
$(\ell ^{p})'$ izometrikusan izomorf $\ell ^{q}$-val, $1 \leq p < \infty$

***Biz***. (egy resze):
Legeyn $y = (y_{n})_{n \in \mathbb{N}} \in \ell ^{q}$. $\varphi_{y} \in (\ell ^{p})'$ legyen olyan, hogy
$$
\varphi_{y}(x) := \sum_{n=1}^{\infty} x_{n} \cdot y_{n}, \quad x = (x_{n})_{n \in \mathbb{N}} \in \ell ^{p}
$$
Belatjuk, hogy $\varphi_{y} \in (\ell ^{p})'$ es hogy $\| \varphi_{y} \| \leq \| y \|_{q}$
- $\varphi_{y}: \ell ^{p} \to \mathbb{R}$ linearis: $\varphi _y (x + z) = \varphi_{y}(x) + \varphi_{y}(z)$
$$
\sum_{n = 1}^{\infty} (x_{n} + z_{n}) \cdot y_{n} = \sum_{n=1}^{\infty}x_{n} \cdot y_{n} + \sum_{n=1}^{\infty} z_{n} \cdot y_{n}
$$
$$
\varphi _{y}(c \cdot x) = c \cdot \varphi_{y}(x)
$$
- $\varphi_{y} \in (\ell ^{p})'$ : A Holder egyenloseg miatt
$$
\lvert \varphi_{y}(x) \rvert  = \left\lvert  \sum_{n=1}^{\infty}x_{n} \cdot y_{n}  \right\rvert \leq \sum_{n=1}^{\infty} \lvert x_{n} \cdot y_{n} \rvert  \leq \| x \| _{p} \cdot \| y \| _{q}
$$
$$
\implies \varphi_{y} \in \mathcal{L}(\ell ^{p}), \quad \| \varphi_{y} \|  \leq \| y \|  _{q}
$$

*Megjegyzes:* Fontos specialis eset amikor $p = 2$. Ekkor $(\ell ^{p})' \equiv \ell ^{p}$, mert ez Hilbert ter is egyben.

*Megjegyzes:* Ha a $H$ Hilbert-terben van ONB, jeloljuk $(e_{n})$-el, akkor $\forall x \in H: \quad x = \sum (x, e_{n}) \cdot e_{n}$
Perseval egyenloseg igaz, tehat $\| x \|^{2} = \sum \lvert (x, e_{n})^{2} \rvert < \infty$
Tehat $x_{n} := (x, e_{n}), \quad n\in\mathbb{N} \quad (x_{n}) \in \ell ^{2}$.
Tehat minden Hilbert ter amiben letezik ONB azonosithato $\ell ^{2}$-vel, ezeket szokas szeparabilis Hilbert tereknek hivni.

### Operator spektruma
1.) $X, Y$ vektorterek, $A: X \to Y$ linearis lekepezes, legyen $b \in Y$.
Tekinsuk $Ax = b$ (1) egyenletet
- Adott $b \in Y$ eseten (1)-nek van megoldasa, ha $b \in \operatorname{Im}A$ 
- $\forall b \in Y$ eseten (1)-nek van megoldasa $\iff \operatorname{Im}A = Y$, tehat $A$ szurjektiv
- A megoldas egyertelmu, ha $A$ injektiv, tehat $\operatorname{Ker} A = 0$ 

### ***All***.:
(1)-nek $\forall b \in Y$ eseten egyertelmu megoldasa van $\iff A$ bijektiv, azaz $\exists A^{-1}$

2.) $X, Y$ normalt terek. Felteheto a kerdes, hogy mikor fugg a megoldas folytonosan a jobboldaltol, azaz $b$-tol? Tehat mikor igaz az, hogy $A^{-1}$ (is) folytonos?

3.) $X = Y$ $\mathbb{K}$ feletti normalt terek. Tekintsuk a kovetkezo egyenletet
$$
(A - \lambda \cdot I) \cdot x = b
$$
### ***Def.:***
Legyen $X$ normalt ter, legyen $A \in \mathcal{L}(X)$. Azt mondjuk, hogy a $\lambda \in \mathbb K$ az $A$ operator *regularis erteke*, ha $A - \lambda \cdot I$ bijektiv es $(A - \lambda \cdot I)^{-1} \in \mathcal{L}(X)$.

Jeloles: $\rho(A) := \{ \lambda \in \mathbb K : \lambda \text{ regularis erteke } A \text{-nak} \}$ (rezolvens halmaz)
$\sigma(A) := \mathbb{C} \setminus \rho(A)$ az $A$ operator spektruma, azaz a rezolvens halmaz komplementere.

Mikor igaz, hogy $\lambda \in \sigma(A)$?
3 eset:
a) $A - \lambda \cdot I$ nem szurjektiv
b) $A - \lambda \cdot I$ nem injektiv
c) $A - \lambda \cdot I$ bijektiv, de $(A - \lambda \cdot I)^{-1}$ nem folytonos

*Megjegyzes:* Ha $\operatorname{dim}X< \infty$, akkor a dimenzio tetelbol kovetkezik, hogy a) $\iff$ b)
$$
\operatorname{dim} \operatorname{Ker} A + \operatorname{dim} \operatorname{Im} A = \operatorname{dim} X
$$
tehat pontosan akkor injektiv ha szurjektiv
Masreszt a c) nem fordulhat elo, mert veges dimenzioban minden linearis operator folytonos is egyben.

*Megjegyzes:* (Banach-fele homeomorfizmus tetelbol kovetkezik) Ha $X$ Banach ter, akkor ha az $B \in \mathcal{L}(X)$ bijektiv, akkor az inverze szuksegkeppen folytonos, tehat $B^{-1}\in\mathcal{L}(X)$.

### ***Def.:***
Ha $\lambda \in \sigma(A)$ olyan, hogy $A - \lambda \cdot I$ nem injektiv, akkor $\lambda$ sajaterteke $A$-nak, jelolesben $\lambda \in \sigma_{p}(A)$ ("pontspektrum").

$A - \lambda \cdot I$ nem injektiv $\iff \exists x \neq 0: \quad (A - \lambda \cdot I)x = 0 \iff Ax = \lambda \cdot x$. Ekkor $x$ neve "sajatvektor".

*Megjegyzes:* Ha $\operatorname{dim} X < \infty$, akkor $\sigma(A) = \sigma_{p}(A)$.

Pelda vegtelen dimenzios esetre amikor egy pont spektrumpont de nem sajatertek:
Legyen $X = \ell ^{2}$ legyen ezen ertelmezve a jobb eltolas $J(x_{1}, x_{2}, \dots) = (0, x_{1}, x_{2}, \dots) \in \ell ^{2}$
$J$ nem szurjektiv $\implies 0 \in \sigma(J)$ masreszt $0$ nem lehet sajaterteke, mert csak a $0$-t viszi onmagaba.



related: [[TovFejAnal]]