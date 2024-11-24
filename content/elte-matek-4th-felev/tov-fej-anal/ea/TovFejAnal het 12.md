date: 2024.05.14

#### \<emlek\>
$$
L^{p}(X, \mathcal{M}, \mu) = \{ f : f \; \text{ merheto es } \lvert f \rvert ^{p} \; \text{ integralhato, azaz veges az integralja} \}
$$
$1 \leq p < \infty$ es
$$
L^{\infty}(X, \mathcal{M}, \mu) = \{ f : f \; \text{ merheto} \exists M : \lvert  f \rvert \leq M \; \text{ m.m.} \}
$$ 

$(X, \mathcal{M}, \mu)$ mertektrer $X \neq \emptyset$ $\mathcal{M}$ a merheto halmazok $\sigma$ gyuruje es a $\mu$ a merheto halmazok $\sigma$ gyurujere kiterjesztett mertek
$$
\mu : \mathcal{M} \to \overline{R}_{+}
$$

Ha $f \in L^{p}$ akkor $\| f \|_{p} = \left( \int \lvert f \rvert^{p} \, d\mu \right)^{1/p}$ ha $1 \leq p < \infty$ es ha $p = \infty$ akkor $\| f \|_{\infty} = \inf \{ M : \lvert f \rvert \leq M \; \text{ m.m.} \} = \operatorname{esssup} \lvert f \rvert$

#### All
$1 \leq p, q < \infty$ konjugalt kitevok, ha $\frac{1}{p} + \frac{1}{q} = 1$ (definialjuk $\frac{1}{\infty} = 0$)
Ekkor teljesulnek a kovetkezok:
1. Holder egyenlotlenseg: $f \in L^{p}, g \in L^{q} \implies f \cdot g \in L^{1}$ es $\| f \cdot g \|_{1} \leq \| f \|_{p} \cdot \| g \|_{q}$

2. Minkowski egyenelotlenseg: $f, g \in L^{p}$  ekkor $\| f + g \|_{p} \leq \| f \|_{p} + \| g \|_{p}$ 

3. $L^{p}$ Banach-ter es $L^{2}$ Hilbert-ter

Lattuk: $\| f \|_{2} = \left( \int \lvert f \rvert^{2} \, d\mu \right)^{1/2}$ ez egy skalaris szorzatbol szarmazik, ahol $(f, g)_{L^{2}} = \int f \cdot g \, d\mu$

#### Def
$(X, \| \cdot \|)$ Banach-ter ekkor a kovetkezot dualis ternek hivjuk $X' = \mathcal{L}(X, \mathbb{R}) = \{ \varphi: X \to \mathbb{R} : \varphi \; \text{ folytonos es linearis} \}$. A dualis ter Banach-ter ha az eredeti is az.

Ha $\varphi \in X'$ akkor
$$
\| \varphi \|_{X'} = \min \{ M: \lvert \varphi(x) \rvert \leq M \cdot \| x \|_{X} \} = \sup \{ \lvert \varphi(x) \rvert : \| x \|_{X} = 1 \} = \sup \left\{  \frac{\lvert \varphi(x) \rvert }{\| x \|} : x \neq 0, x \in X  \right\}
$$
#### \</emlek\>

Najo oke de ezt miert ideztuk fel? A kerdes az lesz, hogy mi az $L^{p}$ terek dualis terei?


#### Def
Legyen $1 \leq p, q \leq \infty$ konjugalt kitevok, legyen $g \in L^{q}$ es $f \in L^{p}$ es $j : L^{q} \to (L^{p})'$ es $(jg)(f) = \int f \cdot g \, d\mu$

*Bizonyitas:*
$$
f \cdot g \in L^{1} \implies (jg)(f) \in \mathbb{R}
$$
kell meg: $jg$ linearis az $L^{p}$ teren, vagyis a
$$
(jg)(\lambda_{1}f_{1} + \lambda_{2}f_{2}) \stackrel{?}{=} \lambda_{1}(jg)(f_{1}) + \lambda_{2}(jg)(f_{2})
$$

$$
\int (\lambda_{1}f_{1} + \lambda_{2}f_{2})\cdot g \, d\mu \stackrel{?}{=} \lambda_{1} \cdot \int f_{1} \cdot g \, d\mu + \lambda_{2} \cdot \int f_{2} \cdot g \, d\mu   
$$
ez mar igaz, kesz.

kell meg: $jg$ folytonos az $L^{p}$-n
Legyen $f \in L^{p}, \| f \|_{p} \neq 0$ tetszoleges,
$$
\lvert (jg)(f) \rvert  \stackrel{\text{def}}{=} \left\lvert  \int f \cdot g \, d\mu   \right\rvert \stackrel{\text{Holder}}{\leq} \| g \| _{q} \cdot \| f \|_{p} = M \cdot \| f \|_{p} 
$$

Kesz.

*Megjegyzes:* A fentibol az is adodik, hogy
$$
\| jg \| _{(L^{p})'} \leq \| g \|_{q} 
$$

### Riesz tetel
A fenti $j: L^{q} \to (L^{p})'$ lekepezes egy izometrikus izomorfia, ha $1 < p < +\infty$ es $\frac{1}{p} + \frac{1}{q} = 1$ 

*Bizonyitas:* csak annyit latunk be, hogy $j$ egy izometria.
A kovetkezoket kell belatnunk
1. $j : L^{q} \to (L^{p})'$ linearis, vagyis $\forall \lambda_{1}, \lambda_{2} \in \mathbb{R}$ es $g_{1}, g_{2} \in L^{q}$ -ra
$$
j(\lambda_{1} \cdot g_{1} + \lambda_{2} \cdot g_{2}) = \lambda_{1} \cdot j(g_{1}) + \lambda_{2} \cdot j(g_{2})
$$
Mivel mindket oldalon $(L^{p})'$-beli elemek allnak, azaz linearis fuggvenyek.
Kell: $\forall f \in L^{p}$ es
$$j
(\lambda_{1}g_{1} + \lambda_{2}g_{2})(f) = \lambda_{1} (jg_{1})  + \lambda_{2} (jg_{2})
$$
$$
\int f(\lambda_{1}g_{1} + \lambda_{2}g_{2}) \, d\mu \stackrel{!}{=} \lambda_{1}\int fg_{1} \, d\mu + \lambda_{2}\int fg_{2} \, d\mu  
$$
ezzel belattuk, hogy $j$ linearis

2. $j : L^{q} \to (L^{p})'$ izometria, vagyis $\forall g \in L^{q}$ eseten
$$
\| jg \| _{(L^{p})'} = \| g \| _{q}
$$
mar az elobb belattuk, hogy a baloldal kisebb mint a jobboldal (megjegyzesben emlitettuk)

tehat mar csak azt kell belatnunk, hogy $\| jg \|_{(L^{p})'} \geq \| g \|_{q}$

Azt mutatjuk meg, hogy $\exists 0 \neq f \in L^{p} : \lvert (jg)(f) \rvert = \| g \|_{q} \cdot \| f \|_{p}$ (<- igeret)

Legyen $g \in L^{q}$ adott, ehhez kell nekunk legyartanunk egy $f \in L^{p}$-t
Legyen $f$ a kovetkezo (figyelem itt kihasznaljuk, hogy $1 < p < \infty \implies 1 < q < \infty$)
$$
f := \lvert g \rvert ^{q - 1} \cdot \operatorname{sgn}(g)
$$

*all.:* $f \in L^{p}$
*biz.:*
$$
\| f \| _{p}^{p} = \int \lvert f \rvert ^{p} \, d\mu = \int \lvert g \rvert ^{p(q-1)} \cdot 1 \, d\mu 
$$
hasznaljuk ki, hogy $\frac{1}{p} + \frac{1}{q} = 1 \implies pq = p + q$

$$
\implies \| f \| _{p}^{p} = \int \lvert g \rvert ^{q} \, d\mu = \| g \| _{q}^{q} = \| g \| _{q}^{p(q-1)} 
$$
$$
\implies \| f \| _{p} = \| q \| _{q}^{q-1} \in \mathbb{R}
$$
ezzel belattuk, hogy $L^{p}$-ben van

$$
\lvert (jg)(f) \rvert = \left\lvert  \int fg \, d\mu   \right\rvert   = \left\lvert  \int \lvert g \rvert ^{q-1} \cdot \operatorname{sgn}(g) \cdot g \, d\mu   \right\rvert = \left\lvert  \int \lvert g \rvert ^{q-1} \cdot \lvert g \rvert  \, d\mu   \right\rvert = \left\lvert   \int \lvert g \rvert ^{q} \, d\mu   \right\rvert  = \| g \| _{q}^{q} = \| g \| _{q}^{1} \cdot \| g \| _{q}^{q-1} = \| g \| _{q} \cdot \| f \| _{p}
$$
ezzel belattuk az igeretet

-- biz vege --

### Steinhaus-tetel
$j : L^{\infty} \to (L^{1})'$ izometrikus izomorfia

*Megjegyzes:* $j : L^{1} \to (L^{\infty})'$ nem szurjektiv

## Szorzatmertek szerinti integral es helyettesitess integral
#### Def
Ha $\mathcal{P}$ es $\mathcal{Q}$ az $X$ es $Y$ alaphalmazokon felgyuruk, akkor
$$
\mathcal{P} \times \mathcal{Q} = \{ A \times B : A \in \mathcal{P}, B \in \mathcal{Q} \}
$$
es itt $\mathcal{P} \times \mathcal{Q}$ egy $X \times Y$ -beli felgyuru.

*Biz.:*
1. $\emptyset \subset X \times Y$ es $\emptyset = \emptyset \times \emptyset \in P \times Q$
2. $A \times B, \; C \times D \in P \times Q \implies (A \times B) \cap (C \times D) = (A \cap C) \times (B \cap D) \in P \times Q$
3. $(A \times B) \setminus (C \times D)$ eloall veges diszjunkt $\cup$-kent $P \times Q$-bol ($\emptyset$ biz)

#### Def
Ha $\mu : \mathcal{P} \to \overline{\mathbb{R}}$ es $\nu: \mathcal{Q} \to \overline{\mathbb{R}}$ mertekek direkt szorzata:
$$
(\mu \times \nu)(A \times B) := \mu(A) \cdot \nu(B)
$$
konvencio: $\infty \cdot 0 = 0 \cdot \infty = 0$
ez a $\mathcal{P} \times \mathcal{Q}$-n mertek

*Biz.:*
1. $(\mu \times \nu)(\emptyset) = 0$
2. $(\mu \times \nu)(\cup(A_{n} \times B_{n})) = \sum\mu(A_{n})\nu(B_{n})$

***Kerdes:*** $f: X \times Y \to \mathbb{R}$
$$
\iint \limits_{X \times Y} f(x, y) \, d(\mu \times \nu) \stackrel{?}{=} \int _{Y}\left( \int _{X}f(x,y) \, d\mu(x)  \right) \, d\nu(y)  \stackrel{?}{=} \int _{X} \left( \int _{Y}f(x,y) \, d\nu(y)  \right) \, d\mu(x)
$$

### Fubini-tetel
Ha $f$ integralhato $\mu \times \nu$ mertek szerint, akkor a fentiben mindenhol fenn all az egyenloseg.

### Tonelli-tetel
Ha $f$-nek letezik integralja a $\mu \times \nu$ mertek szerint, akkor a fentiben mindenhol fenn all az egyenloseg.

#### Def
A $\nu : \mathcal{N} \to \overline{\mathbb{R}}$ ($\mathcal{N}$ $\sigma$-gyuru) elojeles mertek, ha
1. $\nu(\emptyset) = 0$
2. $\sigma$-additiv

#### Def
Legyen $\mu: \mathcal{N} \to \overline{\mathbb{R}}_{+}$ mertek, $\nu : \mathcal{N} \to \overline{\mathbb{R}}$ elojeles mertek. Ekkor azt mondjuk, hogy $\nu$ abszolut folytonos $\mu$-re nezve (jel. $\nu \ll \mu$), ha $\forall A \in \mathcal{N}, \mu(A) = 0$ eseten $\nu(A) = 0$

#### Def
Legyen $\mu: \mathcal{N} \to \overline{\mathbb{R}}_{+}$ mertek, $\nu : \mathcal{N} \to \overline{\mathbb{R}}$ elojeles mertek. Ekkor azt mondjuk, hogy $\nu$ merheto tartoju a $\mu$-re nezve, ha $\exists M \in \mathcal{N} : \mu(M) \geq  0$ amire $\nu(A) = 0$, ha $A \cap M = \emptyset$

Legyen $\mu: \mathcal{M} \to \overline{\mathbb{R}}$ olyan mertek, ami egy veges mertek kiterjesztese a merheto halmazok $\mathcal{M}$ $\sigma$-gyurujere. Legyen $f : X \to \overline{\mathbb{R}}$ merheto fuggveny az $A \in \mathcal{M}$ ekkor definialjuk a kovetkezot: (1)
$$
\nu_{f}(A) := \int _{A}f \, d\mu \stackrel{\text{def}}{=} \int f \cdot \chi_{A} \, d\mu  
$$
ha ez letezik.

#### All
Ha $f : X \to \overline{\mathbb{R}}$  merheto es letezik az integralja, akkor a fenti $\nu_{f}: \mathcal{M} \to \overline{\mathbb{R}}$ egy elojeles merteket definial.

*Biz.:*
1. 
$$
\nu_{f}(\emptyset) = \int f \cdot \chi_{\emptyset} \, d\mu = \int 0 \, d\mu = 0
$$

2. 
$$
\nu_{f}(\cup ^{*}A_{n}) = \int f \cdot \chi_{\cup ^{*}A_{n}} \, d\mu \stackrel{!}{=} \int f \cdot \sum \chi_{A_{n}} \, d\mu = \sum \int f \cdot \chi_{A_{n}} \, d\mu
$$
ha $f \geq 0$ m.m. akkor a fenti utolso egyenloseg igaz, ha nem igaz, hogy $f \geq 0$ m.m. akkor vegezzuk el egyesevel $f_{+}$-ra es $f_{-}$ ugyanezt a jatszmat

*Megjegyzes:* A fenti $\nu_{f}$ abszolut folytonos a $\mu$-re nezve: $\nu_{f} \ll \mu$
Ugyanis, ha $\mu(A) = 0$, akkor $\chi_{A} = 0$ $\mu$-m.m., tehat $f \cdot \chi_{A} = 0$ $\mu$-m.m. $\implies \nu_{f}(A) = \int f \cdot \chi_{A} \, d\mu = \int 0 \, d\mu = 0$ 

### Radon-Nikodým tetel
Legyen $X$ merheto $\mu$-re nezve ($\mathcal{M}$ $\sigma$-algebra)
Ekkor a fenti (1)-es formula kolcsonosen egyertelmu megfeleltetest ad a $\mu$-re nezve merheto tartoju es abszolut folytonos elojeles mertekek es az integrallal rendelkezo $f$ merheto fuggvenyek kozott.

*Jel.:* $f = \frac{d\nu}{d\mu}$ Radon-Nikodýn derivalt
$$
\nu_{f}(A) = \int _{A} \frac{d\nu}{d\mu} \, d\mu = \int _{A}d\nu = \nu(A) 
$$
Newton-Leibniz tetelre hasonlito valami bohockodas.

### Helyettesiteses integralas altalanositasa
Legyen $\nu \ll \mu$, $\nu$ tartoju $\mu$-re nezve (Radon-Nikodýn tetel feltetelei)
Ha $\exists \int g \, d\nu$ akkor $\exists \int g \cdot \frac{d\nu}{d\mu} \, d\mu$ es
$$
\int g \, d\nu = \int g \cdot \frac{d\nu}{d\mu} \, d\mu  
$$

Radon-Nikodýn tetelhez megjegyzes: A $\nu_{f}$ mertek $\iff$ $f \geq 0$
masreszt $\nu_{f}$ korlatos $\iff$ $f$ korlatos
related: [[TovFejAnal]]