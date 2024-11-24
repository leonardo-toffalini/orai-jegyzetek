### 1. 
Verify that the in-degree function of a directed graph is submodular.

**Megoldás:**
Emlék: Egy $f: 2^{S} \to \mathbb{R}$ halmazfüggvegy szubmoduláris akkor és csak akkor, ha minden $X, Y \subseteq S$-re igaz a következő:
$$
f(X) + f(Y) \geq F(X \cap Y) + f(X \cup Y)
$$

Vegyünk két általános helyzetű csúcshalmazt.
![[in-degree-function-submodular]]
Első eset: Az egyik halmazba megy a komplementerből.
Ekkor $f(X)$ egyel nő és $f(X \cup Y)$ is egyel nő mert $X$-nek egyel több a befoka. Tehát a két oldal ugyanannyival nő.

Második eset: A metszetbe megy a komplementerből.
Ekkor $f(X)$ és $f(Y)$ is nő egyel és $f(X \cap Y)$ is meg $f(X \cup Y)$ is nő egyel. Tehát a két oldal ugyanannyival nő.

Harmadik eset: A metszetbe megy az egyik halmazból.
Ekkor $f(X)$ és $f(Y)$ is nő egyel és $f(X \cap Y)$ is nő egyel. Tehát a baloldal egyel több lett, mint a jobb.

Negyedik eset: A szimmetrikus differenciából a szimmetrikus differenciába megy.
Ekkor $f(Y)$ nőtt egyel, a jobboldala az egyenletnek nem nő. Tehát a baloldal egyel több lett, mint a jobb.

Ötödik eset: Az egyik halmazba megy a metszetből.
Ekkor egyik érték sem változik.

Az összes esetben a baloldal legalább annyival nőtt mint a jobboldal egy új irányított él bevételéval, tehát ha élenként felépítjük a gráfunkat, ez a tulajdonság marad minden halmazra.
Megjegyzés: Csak azokat az éleket tárgyaltunk, amelyeknek a vége az egyik halmazba megy, mivel ha nem az egyik halmaz felé vannak irányítva akkor nem változtatják egyik oldal értékét sem.


### 2.
Prove the following statements.
a) The non-negative linear combination of submodular functions is submodular.
b) The reflection of a submodular function is submodular.
c) The restriction of a submodular function is submodular.
d) The contraction of a submodular function is submodular.

**Megoldás:**
a) Be kell látni, hogy $f_{1}, \dots, f_{k}$ szubmodulárisak és $\lambda_{j} \geq 0, \quad j = 1, \dots, k$, ekkor $\sum_{j=1}^{k}\lambda_{j}f_{j}$ is szubmoduláris.
Elég belátni $j = 2$-re, mert nagyobb $j$-re indukcióval be tudjuk látni.
$f_{1}, f_{2}$ szubmodulárisak $\lambda_{1}, \lambda_{2} \geq 0$, ekkor $\lambda_{1}f_{1} + \lambda_{2}f_{2}$ szubmoduláris?
$$
(\lambda_{1}f_{1} + \lambda_{2}f_{2})(X) + (\lambda_{1}f_{1} + \lambda_{2}f_{2})(Y) \stackrel{?}{\geq} (\lambda_{1}f_{1} + \lambda_{2}f_{2})(X \cap Y) + (\lambda_{1}f_{1} + \lambda_{2}f_{2})(X \cup Y)
$$
Mivel $f_{1}$ és $f_{2}$ is szubmoduláris ezért tudjuk, hogy $\lambda_{1}f_{1}$ és $\lambda_{1}f_{2}$ is szubmodulárisak, mert a definiáló egyenlet mindkét oldalát megszorozzuk $\lambda_{1}$ vagy $\lambda_{2}$-vel. Tehát a fentit kibontva:
$$
\lambda_{1}f_{1}(X) + \lambda_{2}f_{2}(X) + \lambda_{1}f_{1}(Y) + \lambda_{2}f_{2}(Y) \stackrel{?}{\geq} \lambda_{1}f_{1}(X \cap Y) + \lambda_{2}f_{2}(X \cap Y) + \lambda_{1}f_{1}(X \cup Y) + \lambda_{2}f_{2}(X \cup Y)
$$
$$
\bigg(\lambda_{1}f_{1}(X) + \lambda_{1}f_{1}(Y)\bigg) + \bigg(\lambda_{2}f_{2}(X) + \lambda_{2}f_{2}(Y)\bigg) \stackrel{?}{\geq} \bigg(\lambda_{1}f_{1}(X \cap Y) + \lambda_{1}f_{1}(X \cup Y)\bigg) + \bigg(\lambda_{2}f_{2}(X \cap Y) + \lambda_{2}f_{2}(X \cup Y)\bigg)
$$
Itt már látszik, hogy elegendő az egyenkénti szubmodularitás $\lambda_{1}f_{1}$ és $\lambda_{2}f_{2}$-re.

b) Be kell látni, hogy tetszőleges $X, Y \subseteq S$-re:
$$
g(X) + g(Y) \geq g(X \cap Y) + g(X \cup Y)
$$
$$
f(S \setminus X) + f(S \setminus Y) \geq f(S \setminus (X \cap Y)) + f(S \setminus (X \cup Y))
$$
Ez eléggé olvashatatlan, tehát vezessük be a következőket:
$$
\overline X = S \setminus X, \quad \overline Y = S \setminus Y
$$
De Morgan azonosságból tudjuk, hogy
$$
\overline{X \cap Y} = \overline X \cup \overline Y, \quad \overline{X \cup Y} = \overline X \cap \overline Y
$$
ezért valóban
$$
f(\overline X) + f(\overline Y) \geq f(\overline X \cap \overline Y) + f(\overline X \cup \overline Y)
$$
Mivel $f$ szubmoduláris és a következő helyettesítésekkel visszakapjuk a szubmodularitást leíró egyenlőtlenséget, ezért $g$ is szubmoduláris.

c) Be kell látni, hogy tetszőleges $X, Z \subseteq S$-re:
$$
g(X) + g(Z) \geq g(X \cap Z) + g(X \cup Z)
$$
$$
f(X \cap Y) + f(Z \cap Y) \geq f((X \cap Z)\cap Y) + g((X \cup Z)\cap Y)
$$
Tudjuk a következőket:
$$
(X \cap Y) \cap (Z \cap Y) = (X \cap Z) \cap Y, \quad (X \cap Y) \cup (Z \cap Y) = (X \cup Z)\cap Y
$$
Új jelölésekkel: $X' = X \cap Y, \; Z' = Z \cap Y$.
$$
f(X') + f(Z') \geq f(X' \cap Z') + f(X' \cup Z')
$$
Ezért valóban igaz, hogy $g$ szubmoduláris, mivel $f$ feltétel szerint szubmoduláris.

d) Be kell látni, hogy tetszőleges $Y, Z \subseteq S$-re:
$$
g(Y) + g(Z) \geq g(Y \cap Z) + g(Y \cup Z)
$$
$$
(f(X \cup Y) - f(X)) + (f(X \cup Z) - f(X)) \geq (f(X \cup (Y \cap Z)) - f(X)) + (f(X \cup (Y \cup Z)) - f(X))
$$
$$
\iff f(X \cup Y) + f(X \cup Z) \geq f(X \cup (Y \cap Z)) + f(X \cup (Y \cup Z))
$$
Tudjuk, hogy
$$
X \cup (Y \cap Z) = (X \cup Y) \cap (X \cup Z), \quad X \cup (Y \cup Z) = (X \cup Y) \cup (X \cup Z)
$$
ezért a fenti ekvivalens a következővel:
$$
f(X \cup Y) + f(X \cup Z) \geq f((X \cup Y) \cap (X \cup Z)) + f((X \cup Y) \cup (X \cup Z))
$$
Ha bevezetjük a következő változókat: $X \cup Y := A, \; X \cup Z := B$
$$
f(A) + f(B) \geq f(A \cap B) + f(A \cup B)
$$
Ami már igaz, mert tudjuk a feltétel szerint, hogy $f$ szubmoduláris, tehát ez az állítás igaz tetszőleges $A, B \subseteq S$ halmazokra.

### 3.
Provide examples showing that the maximum/minimum of two submodular functions are not necessarily submodular.

**Megoldás:**
Legyen $V = \{  a, b \}$ és legyen ezen a halmazon értelmezett két szubmoduláris függvény $g$ és $h$.
$$
g(\emptyset) := 0, \quad g(\{ a \}) := 0, \quad g(\{ b \}) := 100, \quad g(\{ a, b \}) := 1
$$
$$
h(\emptyset) := 0, \quad h(\{ a \}) := 100, \quad h(\{ b \}) := 0, \quad h(\{ a,b \}) := 1
$$
Legyen $f = \min\{ g,h \}$. Ekkor
$$
f(\emptyset) = \min\{ 0, 0 \} = 0, \quad f(\{ a \}) = \min \{ 0, 100 \} = 0, \quad f(\{ b \}) = \min \{ 100, 0 \} = 0, \quad f(\{ a, b \}) = \min\{ 1, 1 \} = 1
$$
Látszik, hogy $X=\{ a \}, \; Y = \{ b \}$ választással $f(X) + f(Y) = 0 + 0 \not{\geq}\; 0 + 1 = f(X \cap Y) + f(X \cup Y)$. Tehát $f$ nem szubmoduláris.


Legyen $V = \{  a, b \}$ és legyen ezen a halmazon értelmezett két szubmoduláris függvény $g$ és $h$.
$$
g(\emptyset) := 18, \quad g(\{ a \}) := 9, \quad g(\{ b \}) := 10, \quad g(\{ a,b \}) = 0
$$
$$
h(\emptyset) := 0, \quad h(\{ a \}) := 10, \quad h(\{ b \}) := 9, \quad h(\{ a, b \}) := 18
$$
Legyen $f = \max \{ g, h \}$. Ekkor
$$
f(\emptyset) = 18, \quad f(\{ a \}) = 10, \quad f(\{ b \}) = 10, \quad f(\{ a, b \}) = 18
$$
Látszik, hogy $X = \{ a \}, Y = \{ b \}$ választással $f(X) + f(Y) = 10 + 10 = 20 \not{\geq} \; 36 = 18 + 18 = f(X \cap Y) + f(X \cup Y)$. Tehát $f$ nem szubmoduláris.


### 4.
Give a $2$-approximation for the Max Cut problem in undirected graphs, where the goal is to find a set $X$ with maximum degree.

**Megoldás:** 
 Induljunk ki eg ytetszőleges $C \subseteq E$ élhalmazból. Egy általános lépésben mohón vegyünk hozzá egy csúcsot $C$-hez vagy hagyjunk el egyet $C$-ből úgy, hogy a vágás mérete nőjön. Ha már nem tudunk így csúcsot hozzávenni vagy elhagyni $C$-ből, akkor áljon le az algoritmus és térjünk vissza a jelenlegi $C$ halmazzal.
 Ez az algoritmus $2$-közelítő, mivel $\forall v \in V$-re legalább $\frac{\operatorname d(v)}{2}$ él része $C$-nek, különben ha $v$-nek kevesebb mint $\frac{\operatorname d(v)}{2}$ éle lenne $C$ része, akkor az algoritmus belevenné $v$-t $C$-be, mert növelné a vágás méretét.

 
related: [[DL-CO]]