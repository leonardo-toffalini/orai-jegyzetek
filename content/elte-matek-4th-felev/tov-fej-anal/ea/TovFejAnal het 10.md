date: 2024.04.30

Riesz-Fischer tetel ekvivalens a kovetkezovel: $(C_{2}, \; \| \cdot \|_{1})$ Banach-ter
Erre a terre bevezetjuk a kovetkezo jelolest: $L^{1}$-ter
Megjegyzes: Ebben a terben egy elem az egy ekvivalencia osztalyt jelent, ahol a majdnem mindenutt egyenlo fuggvenyek ekvivalensek, azaz $f \sim g \iff f = g$ m.m.


Eddig volt: Lebesgue-integralelmelet.

$\varphi$ lepcsos fv
$$
\varphi(x) = \sum_{k=1}^{n} c_{k} \cdot \chi_{I_{k}}
$$
$I_{k}$ intervallum $\forall k$
$$
\int \varphi \, dx = \sum_{k=1}^{n}c_{k} \cdot \lvert I_{k} \rvert 
$$
(Itt mar szerepel a Lebesgue mertek, mivel egy intervallum Lebesgue merteke az pont a hossza)

# Mertekek, mertekszerinti integral (altalanosan)
Legyen $X \neq \emptyset$ alaphalmaz.

#### Def.:
Legyen $\mathcal{P} \subset 2^{X} = \{ A : A \subset X \}$. Ekkor $\mathcal P$ felgyuru, ha:
1. $\emptyset \in \mathcal{P}$
2. $A, B \in \mathcal{P} \implies A \cap B \in \mathcal{P}$
3. Ha $A, B \in \mathcal{P}$, akkor $\exists C_{1}, C_{2}, \dots, C_{n} \in \mathcal{P}$ paronkent diszjunkat, akkor
$$
A \setminus B = C_{1} \cup ^{*} \dots \cup ^{*} C_{n}
$$
*pelda:*
$\mathcal{P} \subset 2^{\mathbb{R}}$, $\mathcal{P} = \{ I \subset \mathbb{R}: I \;\text{ intervallum} \}$
*Biz.:*
1. $(a, a) = \emptyset \in \mathcal{P}$
2. 
	- $A \cap B = \emptyset$ az 1. pont miatt ekkor $A \cap B \in \mathcal{P}$
	- $A \subset B \implies A \cap B = A \in \mathcal{P}$
	- $A$ es $B$ altalanos helyzetu, ekkor a mettszetuk is egy intervallum, ezert $\in \mathcal{P}$

3. 
	- $A \cap B = \emptyset$ ekkor $A \setminus B = A in \mathcal{P}$
	- $A \subset B \implies A \setminus B \in \mathcal{P}$
	- $A$ es $B$ altalanos helyzetu intervallumok, ekkor az $A \setminus B$ ket diszjunkt intervallum unioja, azaz $A \setminus B = C_{1} \cup ^{*} C_{2}$

*pelda:*
$\mathcal{P} = \{ I \subset \mathbb{R}: I \; \text{ korlatos intervallum} \}$

*Megjegyzes:* A masodik felgyuru axiomabol kovetkezik teljes indukcioval, hogy ha $A_{1}, A_{2}, \dots, A_{n} \in \mathcal{P} \implies A_{1} \cap A_{2} \cap \dots \cap A_{n} \in \mathcal{P}$

#### Def.:
Legyen $\mathcal{P}$ egy $X$-beli felgyuru. Egy $\mu: \mathcal{P} \to \overline{\mathbb{R}}$ mertek, ha
1. $\mu \geq 0$
2. $\mu(\emptyset) = 0$
3. $\sigma$-additivitas:
Ha $A_{1}, A_{2}, \dots \in \mathcal{P}$, paronkent diszjunktak es ez a megszamlalhato sok halmaz diszjunkt unioja is $\bigcup_{k=1}^{\infty}A_{k} \in \mathcal{P}$, akkor $\mu\left( \bigcup_{k=1}^{\infty}A_{k} \right) = \sum_{k=1}^{\infty}\mu(A_{k})$.

A $(X, \mathcal{P}, \mu)$ harmast mertekternek nevezzuk.

*pelda:*
1. $\mathcal{P} = \{ I \subset \mathbb{R}: I \; \text{ intervallum} \}$ es $\mu: \mathcal{P} \to \overline{\mathbb{R}}$  ahol $\mu(I) = \lvert I \rvert$
2. $\mathcal{P} = \{ I \subset \mathbb{R}: I \; \text{ korlatos intervallum} \}$ es $\mu : \mathcal{P} \to \overline{\mathbb{R}}$ ahol $\mu(I) = \lvert I \rvert$
3. $\mathcal{P} = 2^{A}$ ahol $A \neq 0$ tetszoleges halmaz $\mu : \mathcal{P} \to \overline{\mathbb{R}}$ ahol $B \subset A$ $\mu(B) = B$ elemszama

#### Def.:
Egy $\mathcal{R} \subset 2^{X}$  gyuru, ha
1. $\emptyset \in \mathcal{R}$
2. $A, B \in \mathcal{R} \implies A \setminus B \in \mathcal{R}$
3. $A, B \in \mathcal{R}$ diszjunktak, akkor $A \cup ^{*} B \in \mathcal{R}$

*Megjegyzes:*
1. $A, B \in \mathcal{R}$ tetszoleges $\implies A \cup B \in \mathcal{R}$ (teljes indukcioval ekkor barhany halmazra is igaz ez az allitas)
*Biz.:* $A \cup B = (A \setminus B) \cup ^{*}B$ es keszen is vagyunk csak az axiomakat kell alkalmaznunk.

2. $A, B \in \mathcal{R} \implies A \cap B \in \mathcal{R}$  (teljes indukcioval kovetkezik, hogy veges mettszetre is zart)
*Biz.:* Legyen $A, B \in \mathcal{R}$ ekkor $A \cap B = (A \cup B) \setminus ((A \setminus B) \cup (B \setminus A))$ es itt minden tag eleme $\mathcal{R}$-nek, es keszen is vagyunk

3. Minden gyuru felgyuru is.

*pelda:*
$\mathcal{R} = \{ B \subset A: \lvert B \rvert < \infty \}$

#### Def.:
Legyen $\mathcal{P}$ egy felgyuru. Azt mondjuk, hogy $\mathcal{R}$ a $\mathcal{P}$ altal generalt gyuru, ha $\mathcal{R}$ a $\mathcal{P}$-t tartalmazo legszukebb gyuru.

#### All.:
Legyen $\mathcal{P}$ tetszoleges felgyuru. Ekkor a $\mathcal{P}$ altal generalt gyuru a kovetkezo:
$$
\mathcal{R} = \{ P_{1} \cup ^{*} P_{2} \cup ^{*} \dots \cup ^{*} P_{n} : P_{i} \in \mathcal{P} \quad \forall i, \quad n \in \mathbb{N} \}
$$

*Biz.:* $\emptyset$

#### Tetel
Minden $\mu : \mathcal{P} \to \overline{\mathbb{R}}$ mertek *egyertelmuen* kiterjesztheto a $\mathcal{P}$ altal generalt $\mathcal{R}$ gyurure.

*Biz.:* $P_{1} \cup ^{*} P_{2} \cup ^{*} \dots \cup ^{*} P_{n} \in \mathcal{R}$ eseten legyen
$$
\mu(P_{1} \cup ^{*} P_{2} \cup ^{*} \dots \cup ^{*} P_{n}) := \mu(P_{1}) + \mu(P_{2}) + \dots + \mu(P_{n})
$$
A tovabbi resze a bizonyitasnak technikas es nem latjuk be az oran.

#### All.:
Legyen $\mu : \mathcal{P} \to \overline{\mathbb{R}}$ felgyurun ertelmezett mertek. Ekkor 
1. $\mu$ monoton, azaz ha $A, B \in \mathcal{P}$ olyan halmazok, hogy $A \subset B$ akkor $\mu(A) \leq \mu(B)$
2. $\mu$ az $\sigma$-subadditiv, azaz, ha $A \in \mathcal{P}$ es $A_{1}, A_{2}, \dots \in \mathcal{P}$ ahol $\bigcup_{k=1}^{\infty}A_{k} \in \mathcal{P}$ akkor $\mu(A) \leq \sum_{k=1}^{\infty}\mu(A_{k})$
3. $\mu$ folytonos, azaz, ha $A_{n} \subset A_{n+1} \quad \forall n \in \mathbb{N}$ es $A_{k} \in \mathcal{P} \quad \forall k \in \mathbb{N}$ es $\bigcup A_{n} \in \mathcal{P}$ akkor $\mu(A_{n}) \to \mu\left( \bigcup A_{n} \right)$
4. $\mu$ folytonos, azaz, ha $A_{n+1} \subset A_{n}$ es $A_{k} \in \mathcal{P}$ es $\cap A_{n} \in \mathcal{P}$ es $\mu(A_{1}) < \infty$ akkor $\mu(A_{n}) \to \mu(\cap A_{n})$

#### Def.:
Egy $\mu : \mathcal{P} \to \overline{\mathbb{R}}$ mertek veges, ha $\mu(P) < \infty$ $\forall P \in \mathcal{P}$

A tovabbiakban csak veges mertekekrol lesz szo, tehat $\mu$ veges merteket jelol innentol kezdve.

#### Def.:
Egy $A \subset X$ halmaz $\mu$-nullahalmaz, ha $\forall \varepsilon > 0$ $\exists(P_{n}) \subset \mathcal{P}$ ugy, hogy
$$
A \subset \bigcup_{n=1}^{\infty}P_{n} \quad \text{es} \quad \sum_{n=1}^{\infty}\mu(P_{n}) < \varepsilon
$$

#### Def.:
Egy $T(x)$ tulajdonsag $\mu$-majdnem mindenutt ($\mu$-m.m.) igaz, ha $\{ x \in X : \neg T(x) \}$ $\mu$-nullahalmaz.

*pelda:*
Ha $f, g : X \to \mathbb{R}$ akkor $f = g$ $\mu$-m.m. ha $\{ x \in X : f(x) \neq g(x) \}$ $\mu$-nullahalmaz.

#### All.:
1. $\emptyset$ $\mu$-nullahalmaz.
2. Ha $A \subset X$  $\mu$-nullahalmaz, $B \subset A$, akkor $B$ is $\mu$-nullahalmaz.
3. Megszamlalhatoan sok $\mu$-nullahalmaz unioja is $\mu$-nullahalmaz.
3. $P \in \mathcal{P}$ $\mu$-nullahalmaz $\iff$ $\mu(P) = 0$

*Biz.:* Gyakorlaton.

#### Def.:
$\varphi$ lepcsos fv $X$-en, ha $\varphi = \sum_{k=1}^{n}c_{k} \cdot \chi_{P_{k}}$ ahol $P_{k} \in \mathcal{P}$ $k= 1 , \dots, n$

Egy $\varphi$ lepcsos fv $\mu$ *veges* mertek szerinti integralja a kovetkezo:
$$
\int \varphi \, d\mu := \sum_{k=1}^{n}c_{k} \cdot \mu(P_{k})
$$
Innentol kezdve eljatszhato az osszes lepes amit eljatszottunk a $\mu(A) = \lvert A \rvert$ mertekre.

Tehat bevezetheto egy "ugyanolyan" integralelmelet, mint amit elozoleg bezettunk es minden ugyanugy igaz lesz. Azaz igaz a Beppo-Levi, Lebesgue dominalt konvergencia es a Riesz-Fischer tetel is igaz lesz.

Bevezetjuk az integralhato fuggvenyek vektorteret $C_{2}$-t. Azaz $C_{2} := \{ f : f \; \text{ integralhato } \; \mu \; \text{-szerint} \}$

*Megjegyzes:*
A Lebesgue-integral eseten a kiindulasi felgyuru es veges mertek a kovetkezo: $\mathcal{P} = \{  I \subset \mathbb{R}: I \; \text{ korlatos intervallum} \}$ es $\mu : \mathcal{P} \to \overline{\mathbb{R}}$ a kovetkezokeppen definialt $\mu(I) = \lvert I \rvert$

### Merheto fuggvenyek es halmazok
Tovabbra is $\mu$ egy veges mertek valamilyen $\mathcal{P}$ felgyurun ertelmezve.

#### Def.:
Egy $f : X \to \overline{\mathbb{R}}$ fuggveny merheto, ha $\exists (\varphi_{n})$ lepcsos fuggveny sorozat, hogy $\varphi_{n} \to f$ m.m.

#### All.:
1. Ha $f$ integralhato fuggveny, akkor $f$ merheto is.
2. Ha $f$ es $g$ veges erteku merheto fv-ek, akkor $\lvert f \rvert$, $c \cdot f$, $f + g$, $f \cdot g$, $\max\{ f, g \}$, $\min \{  f, g \}$ is merheto.
3. Ha $f$ merheto es $f \neq 0$ m.m., akkor $\frac{1}{f}$ is merheto.
4. Ha $f_{n}$ merheto fv-ek es $f_{n} \to f$ m.m., akkor $f$ is merheto.

*Biz.:*
1. Ha $f$ integralhato, akkor $f = f_{1} - f_{2}$ ahol $f_{1}, f_{2} \in C_{1}$ es ekkor $\exists (\varphi_{n}), (\psi_{n})$ lepcsos fv-ekbol allo sorozat, hogy $\varphi_{n} \nearrow f_{1}, \psi \nearrow 2$ m.m. Ekkor $\varphi_{n} - \psi_{n}$ is lepcsos fv es ekkor $\varphi_{n} - \psi_{n} \to f$ m.m. Tehat $f$ is merheto definiciobol.
A tobbit nem bizonyitjuk.

#### Def.:
Legyen $f : X \to \overline{\mathbb{R}}$ merheto fv. Ekkor $f$-nek letezik az integralja $\mu$ szerint, ha a kovetkezok valamelyik teljesul:
1. $f$ integralhato, akkor $\int f \, d\mu$ a felepitesbol
2. Ha $f \geq 0$ m.m. es $f$ nem integralhato, akkor $\int f \, d\mu := +\infty$ 
3. $f = f_{1} - f_{2}$ ahol $f_{1} = \max\{ f, 0 \}$ es $f_{2} = - \min\{ f, 0 \}$ ekkor $f_{1}$ es $f_{2}$ is merheto es $f_{1}, f_{2} \geq 0$. Tegyuk fel, hogy valamelyik integralhato. Ekkor legyen
$$
\int f \, d\mu = \int f_{1} \, d\mu - \int f_{2} \, d\mu 
$$
(ez lehet veges vagy $\pm \infty$ is)

*Megjegyzes:* Ha a fenti harom eset egyike sem teljesul, akkor azt mondjuk, hogy az $f$ *merheto* fv-nek nem letezik integralja.

#### Def.:
Azt mondjuk, hogy egy $A \subset X$ halmaz $\mu$-merheto, ha $\chi_{A}$ karakterisztikus fuggvenye merheto. Ekkor $\mu(A) := \int \chi_{A} \, d\mu \in [0, +\infty]$ (mivel $\chi_{A} \geq 0$ tehat 1.-es vagy 2.-es eset teljesul az elozo definicioban)

#### Def.:
Egy $\mathcal{M} \subset 2^{X}$ $\sigma$-gyuru, ha
1. $\emptyset \in \mathcal{M}$
2. $A, B \in \mathcal{M} \implies A \setminus B \in \mathcal{M}$
3. $A_{1}, A_{2}, \dots \in \mathcal{M}$ paronkent diszjunktak, akkor $\bigcup ^{*} A_{n} \in \mathcal{M}$

*Megjegyzes:* Minden $\sigma$-gyuru gyuru is.

#### All.:
A fenti definialt merheto halmazok rendszere $\sigma$-gyurut alkot es az eredeti felgyurun ertelmezett mertek kiterjesztese $\mathcal{M}$-re is mertek.

#### Def.:
A Lebesgue mertek a Lebesgue-merheto halmazok $\sigma$-gyurujen ertelmezett kiterjesztett mertek, ahol az eredeti mertek $\mu : \mathcal{P} \to \mathbb{R}$ ahol $\mathcal{P} = \{ I \subset \mathbb{R} : I \; \text{ korlatos intervallum} \}$ es $\mu(I) = \lvert I \rvert$ 

*Megjegyzes:* Letezik nem Lebesgue-merheto halmaz, de ez csak a kivalasztasi axioma segitsegevel igazolhato.

#### Def.:
Egy $\mu$ merteket teljesnek nevezunk, ha minden olyan $A$ merheto halmaz eseten amelyre a $\mu(A) = 0$, $A$ minden reszhalmaza is merheto.
Azaz nullmerteku halmazok reszhalmazai is merhetoek.

#### Def.:
Egy $\mu$ merteket $\sigma$ vegesnek nevezunk, ha minden $P \in \mathcal{P}$ eseten $\exists (A_{n})$ merheto halmazokbol allo sorozat, amelyekenk a merteke veges, azaz $\mu(A_{k}) < \infty \quad \forall k$ es $P \subset \bigcup A_{n}$

#### All.:
A fenti elmeletben kapott $\mu : \mathcal{M} \to \overline{\mathbb{R}}$  mertek az $\sigma$ veges es teljes.

*Kovetkezmeny:* A Lebesgue-mertek is $\sigma$ veges es teljes.

related: [[TovFejAnal]]