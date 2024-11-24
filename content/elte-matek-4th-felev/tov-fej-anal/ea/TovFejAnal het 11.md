date: 2024.05.07
#### Ismetles / bovites
$\mathcal{P}$ felgyuru: $\emptyset \in \mathcal{P}$, $\cap$-zart, $A, B \in \mathcal{P} \implies A \setminus B = C_{1} \cup ^{*} \dots \cup ^{*} C_{n} \in \mathcal{P}$ (ahol $C_{i} \in \mathcal{P}$)

$\mu : \mathcal{P} \to \overline{\mathbb{R}}_{+}$ $\mu \geq 0$ $\mu(\emptyset) = 0$ es $\sigma$-additiv ($\cup ^{*} A_{n} \in \mathcal{P} \implies \mu(\cup ^{*}A_{n}) = \sum \mu(A_{n})$)

$\mathcal{R}$ gyuru: $\emptyset \in \mathcal{R}$, $\setminus$-zart, $\cup ^{*}$-zart $\implies$ $\mathcal{R}$ $\cap$-zart es $\cup$-zart

#### All
$\mu : \mathcal{P} \to \overline{\mathbb{R}}$ mertek egyertelmuen kiterjesztheto a $\mathcal{P}$ altal generalt gyurure. ($\mathcal{P}$ felgyuru)

$\mathcal{M}$ $\sigma$-gyuru: $\emptyset \in \mathcal{M}$, $\setminus$-zart, $A_{n} \in \mathcal{M}$ $\forall n$, diszjunktak, akkor $\cup ^{*}A_{n} \in \mathcal{M}$

$X$ ($\neq \emptyset$) alaphalmaz, $\mathcal{P} \subset 2^{X}$
Legyen $\mu: \mathcal{P} \to \mathbb{R}$ veges mertek valamilyen $\mathcal{P}$ felgyurun. Ekkor definialhatjuk a kovetkezot
$$
\varphi = \sum_{k=1}^{n}c_{k} \cdot \chi_{p_{k}}, \quad p_{k} \in \mathcal{P}, \quad k = 1, .., n
$$
lepcsos fuggveny.

Ennek az integralja a kovetkezo:
$$
\int \varphi \, d\mu = \sum_{k=1}^{n}c_{k} \cdot \mu(p_{k}) \in \mathbb{R}
$$
#### Def
Egy $f : X \to \mathbb{R}$ merheto, ha $\exists (\varphi_{n})$ lepcsos fuggveny sorozat ugy, hogy $\varphi_{n} \to f$ $\mu$-m.m.

Volt: $\mu$ veges mertekbol kiindulva bevezettuk az integralhato fuggvenyek vektorteret. Ezek fuggvenyek halmazat neveztuk $C_{2}$-nek.
Ezeknek a fuggvenyeknek veges az integralja, azaz $f\in C_{2}$ eseten $\int f \, d\mu < \infty$


#### Def
1. $f \geq 0$ merheto fuggveny, ami nem integralhato, akkor $\int  f \, d\mu := +\infty$ 
2. $f_{+} := \max \{ f, 0 \}$, $f_{-} := -\min \{ f, 0 \}$ (figyelem, igy $f_{+} \geq 0$ es $f_{-} \geq 0$) es ezek a fuggvenyek merhetoek.
Ha $f_{+}$ es $f_{-}$ kozul valamelyik integralhato, akkor definialhato az $f$-nek az integralja a kovetkezo modon:
$$
\int f \, d\mu = \int f_{+} \, d\mu - \int f_{-} \, d\mu  \in \overline{\mathbb{R}}
$$
#### All
1. Legyen $f$ merheto fuggveny es $\exists \int f \, d\mu$, es tegyuk fel, hogy $f = g$ m.m. Ekkor $\exists \int g \, d\mu$ es
$$
\int f \, d\mu = \int g \, d\mu
$$
2. Legyen $f$ es $g$ merheto fuggvenyek es mindkettonek letezik integralja. Tovabba $f \leq g$ m.m. Ekkor
$$
\int f \, d\mu \leq \int g \, d\mu 
$$
3. Legyen $f$ merheto fuggveny es tegyuk fel, hogy letezik az integralja es legyen $c \in \mathbb{R}$ tetszoleges valos szam. Ekkor $c \cdot f$-nek is letezik integralja es
$$
\int c \cdot f \, d\mu = c \cdot \int f \, d\mu  
$$
Konvencio szerint ebben a temakorben $0 \cdot (+\infty) := 0$

4. Legyen $f$ es $g$ merheto fuggvenyek es mindkettonek letezik az integralja. Tegyuk fel, hogy $\int f \, d\mu$ es $\int g \, d\mu$ nem ellentetes elojelu vegtelenek. Ekkor (!) letezik az osszeguk integralja es ez a kovetkezo:
$$
\int (f + g) \, d\mu = \int f \, d\mu + \int g \, d\mu  
$$
5. Beppo-Levi tetel altalanositasa: Legyen $f_{n} \geq 0$ m.m. es merheto es tegyuk fel, hogy $f_{n} \nearrow f$ m.m. Ebbol kovetkezik, hogy $f$ is merheto es a hatarertek integralja letezik es merheto es a kovetkezokeppen nez ki:
$$
\int f_{n} \, d\mu \to \int f \, d\mu 
$$

6. Legyen $(g_{n})$ merheto fuggvenyek sorozata, $g_{n} \geq 0$ m.m. Ekkor $\sum g_{n}$ is merheto (ez volt altalaban), letezik az integralja es teljesul az, hogy
$$
\sum \int g_{n} \, d\mu = \int \sum g_{n} \, d\mu  
$$
#### All
Egy $f$ fuggveny pontosan akkor merheto, ha $\forall 0 < c < \infty$ valos szam eseten a kovetkezo, ugynevezett *nívóhalmazok* merhetok.
$$
\{ f < c \} = \{ x \in X : f(x) < c \} = f^{-1}((-\infty, c))
$$
$$
\{ f > c \} = \{ x \in X : f(x) > c \}
$$
$$
\{ f \leq c \} = \{ x \in X : f(x) \leq c \}
$$
$$
\{ f \geq c \} = \{ x \in X : f(x) \geq c \}
$$

#### Def
Az $A \subset X$ halmazra azt mondjuk, hogy merheto, ha $\chi_{A}$ merheto fuggveny.

#### All
Ha $A$ egy merheto halmaz, akkor
$$
\mu(A) := \int \chi_{A} \, d\mu  \in [0, +\infty]
$$
#### All
Az ily modon definialt merheto halmazok egy $\mathcal{M}$ $\sigma$-gyurut alkotnak. Erre a kiterjesztett merteket is $\mu$-vel jeloljuk.
Tovabba, a kiterjesztett halmazfuggveny is mertek az $\mathcal{M}$-en, tovabba, $\sigma$-veges es teljes.

Ha a fenti konstrukciot a $\mu: \mathcal{P} \to \mathbb{R}$, $\mathcal{P} := \{ I \subset \mathbb{R}: I \text{ korlatos intervallum} \}$ es egy ilyen $I$ merteke a kovetkezo $\mu(I) := \lvert I \rvert$. Ha ebbol kiindulva vegezzuk, akkor a kepzett $\mathcal{M}$ $\sigma$-gyuru a Lebesgue-merheto halmazok $\sigma$-gyuruje, az erre kiterjesztett mertek a Lebesgue-mertek ($\lambda$).

Volt allitas a mertek tulajdonsagaira:
a) monotonitas
b) $\sigma$-szubadditivitas
c) folytonossag $A_{n} \subset A_{n+1}$ $A_{n} \in \mathcal{P}, \; \cup A_{n} \in \mathcal{P} \implies \mu(A_{n}) \to \mu(\cup A_{k})$
d) folytonossag $A_{n+1} \subset A_{n}$ $\cap A_{n} \in \mathcal{P}, \; \mu(A_{1}) < \infty \implies \mu(A_{n}) \to \mu(\cup A_{k})$

pelda:
d)-ben fontos a $\mu(A_{1}) < \infty$ feltetel
Legyen
$$
A_{n} := [n, +\infty) \quad \forall n \in \mathbb{N}
$$
$$
\mu(A_{n}) = \infty \quad \forall n \in \mathbb{N}
$$
$$
\bigcap_{n = 1}^{\infty} = \emptyset
$$
es $\mu(A_{n}) = +\infty \not \to 0 = \mu(\emptyset)$

## Integralhato fuggvenyek terei
Legyen $(X, \mathcal{M}, \mu)$ egy olyan mertekter, ahol $\mathcal{M}$ $\sigma$-gyuru es $\mu : \mathcal{M} \to \overline{\mathbb{R}}$
Legyen $f : X \to \overline{\mathbb{R}}$ merheto fuggveny
$$
\| f \| _{p} = \left( \int _{X}\lvert f \rvert^{p}  \, d\mu  \right)^{1/p} \in [0, +\infty] \quad 1 \leq p < \infty
$$
spec. eset $p = \infty$
$$
\| f \| _{\infty} := \inf \{ M : \lvert f \rvert \leq M \; \text{m.m.} \} \in [0, +\infty]
$$
belathato, hogy $\| f \|_{\infty} = \lim_{ p \to \infty } \| f \|_{p}$

#### Def
$$
L^{p}(X, \mathcal{M}, \mu) = L^{p} := \{ f : f \; \text{merheto},\; \| f \|_{p} < \infty \}
$$
$$
 = \{ f : \lvert f \rvert ^{p} \; \text{integralhato} \} \quad 1 \leq p < \infty
$$
spec eset $p = \infty$
$$
= \{ f : f \; \text{merheto, m.m. korlatos} \}
$$
#### All
Legyen $p$ es $q$ konjugalt kitevok, $1 \leq p, q \leq \infty$ es $\frac{1}{p} + \frac{1}{q} = 1$ Ekkor
1. **Holder-egyenlotlenseg**
Legyen $f \in L^{p}, g \in L^{q}$ Ekkor $f \cdot g \in L^{1}$ es
$$
\| f \cdot g \|_{1} \leq \| f \| _{p} \cdot \| g \| _{q}
$$
2. **Minkowski-egyenlotlenseg**
Legyen $f, g \in L^{p}$ Ekkor
$$
\| f + g \| _{p} \leq \lvert\lvert f \rvert\rvert_{p}  + \lvert\lvert g \rvert\rvert_{p} 
$$
*Kovetkezmeny:* $L^{p}$ vektorter, sot, normalt ter ezzel a fuggvennyel ellatva. Azaz $(L^{p}, \lvert\lvert \cdot \rvert\rvert_{p})$ normalt ter.

*Biz.:*
Eloszor belatjuk, hogy $L^{p}$ vektorter
Legyen $c \in \mathbb{R}$ es $f \in L^{p}$ tetszoleges, ekkor megmutatjuk, hogy $c \cdot f \in L^{p}$ es, hogy $\| c \cdot f \|_{p} = \lvert c \rvert \cdot \lvert\lvert f \rvert\rvert_{p}$

$$
\| c \cdot f \|_{p}  = \left( \int \lvert c \cdot f \rvert ^{p}  \, d\mu  \right)^{1/p} = \left( \int \lvert c \rvert ^{p} \cdot \lvert f \rvert ^{p} \, d\mu  \right)^{1/p} = \left(\lvert c \rvert ^{p} \int \lvert f \rvert ^{p} \, d\mu  \right)^{1/p} = \lvert c \rvert \cdot \left( \int \lvert f \rvert ^{p} \, d\mu  \right)^{1/p} = \lvert c \rvert \cdot \| f \|_{p} 
$$
Legyen $f, g \in L^{p}$. Ekkor a Minkowski-egyenlotlenseg miatt $f + g \in L^{p}$ es $\| f + g \|_{p} \leq \| f \|_{p} + \| g \|_{p}$

$$
\| f \|_{p}  = 0 \xRightarrow{?} f = 0 \; \text{m.m.}
$$
$$
1 \leq p < \infty \quad \| f \|_{p}  0 \iff \int \lvert f \rvert ^{p} \, d\mu  = 0 \xRightarrow{\text{Beppo-Levi kovetkezmeny}} f^{p} = 0 \; \text{m.m.} \implies f = 0 \; \text{m.m.}
$$
$$
p = \infty \quad \| f \|_{\infty}  = 0 \iff \inf \{  M : \lvert f \rvert  \leq M \; \text{m.m.} \} = 0
$$
A fenti meggondolando! Azt kene ebbol kovetkeztetni, hogy $f = 0$ m.m.

#### Tetel
$L^{p}$ Banach-ter minden $1 \leq p \leq \infty$ eseten.
$L^{2}$ Hilbert-ter.

*Biz.:* (hianyos, oran nem lattuk be teljesen)
*Riesz-Fischer tetel:* Legyen $(f_{n})$ a $\mu$ mertek szerint integralhato fuggvenyek, vagyis $(f_{n}) \subset L^{1}$. Tegyuk fel, hogy $\int \lvert f_{n} - f_{m} \rvert \, d\mu \to 0$, ha $n, m \to \infty$ ($\iff (f_{n})$ $L^{1}$-ben Cauchy-sorozat)
Ekkor $\exists f \in L^{1}$ ugy, hogy $\int \lvert f_{n} - f \rvert \, d\mu \to 0$ ha $n \to \infty$ ($\iff f_{n} \to f$ $L^{1}$-ben)

*Megjegyzes:* A fenti Riesz-Fischer tetelnek az az altalanosizasa is igaz, hogy ha $\lvert f_{n} - f_{m} \rvert$ helyett $\lvert f_{n} - f_{m} \rvert ^{p}$-it irunk mindenhol.

Nyilvan igaz, hogy ha $\| f_{n} - f \|_{p} \to 0 \iff \| f_{n} - f \|_{p}^{p} \to 0 \iff \int \lvert f_{n} -f \rvert^{p} \, d\mu \to 0$

#### *Riesz-lemma*
(ezen mulik a Riesz-Fischer tetel bizonyitasa)
Legyen $(f_{n}) \subset L^{1}$ sorozat es tegyuk fel, hogy $\int \lvert f_{n} - f_{m} \rvert \, d\mu \to 0$ $n,m \to \infty$
Ekkor $\exists (f_{n_{k}})$ reszsorozat, melyre:
1. $\exists g \in L^{1}$ melyre $\lvert f_{n_{k}} \rvert \leq g \quad \forall k$
2. $\exists f \in L^{1}$ melyre $f_{n_{k}} \to f$ m..m. (ha $k \to \infty$)

*Biz.:*
Legyen $\varepsilon = \frac{1}{2^{k}}$ ahol $k \in \mathbb{N}$. A feltetel miatt $\exists (n_{k}) \subset \mathbb{N}$ ugy, hogy
$$
\int \lvert f_{n} - f_{n_{k}} \rvert  \, d\mu < \frac{1}{2^{k}} , \quad n \geq n_{k}, \quad k \in \mathbb{N}
$$
definialjuk a kovetkezo fuggvenyt:
$$
\lvert f_{n_{1}} \rvert + \sum_{k=1}^{\infty} \lvert f_{n_{k+1}} - f_{n_{k}} \rvert
$$
$$
f_{n_{1}} + \sum_{k=1}^{\infty} (f_{n_{k+1}} - f_{n_{k}})
$$
$$
\int \lvert f_{n_{1}} \rvert \, d\mu + \sum_{k=1}^{\infty} \int \lvert f_{n_{k+1}} - f_{n_{k}} \rvert  \, d\mu < \sum_{k=1}^{\infty} \frac{1}{2^{k}} < \infty
$$

Beppo-Levi kovetkezmenye szerint $\exists g \in L^{1}$ amire
$$
g = \lvert f_{n_{1}} \rvert + \sum_{k=1}^{\infty}\lvert f_{n_{k+1}} - f_{n_{k}} \rvert \geq 0
$$
$$
g \geq \lvert f_{n_{1}} \rvert  + \sum_{k=1}^{K} \lvert f_{n_{k+1}} - f_{n_{k}} \rvert  \geq \lvert f_{n_{1}} \rvert + \sum_{k=1}^{K}(\lvert f_{n_{k+1}} \rvert - \lvert f_{n_{k}} \rvert  ) = \lvert f_{n_{K}} \rvert 
$$
$\forall K \in \mathbb{N}$
Igy belattuk az elso reszet az allitasnak

Masreszt, $\exists f \in L^{1}$ amire $f = f_{n_{1}} + \sum_{k=1}^{\infty} (f_{n_{k+1}} - f_{n_{k}})$ a Beppo-Levi kovetkezmenye szerint

$$
S_{K} = f_{n_{1}} + \sum_{k=1}^{K}(f_{n_{k+1}} - f_{n_{k}}) = f_{n_{K}} \to f \; \text{ m.m.}, \quad K \to \infty
$$
related: [[TovFejAnal]]