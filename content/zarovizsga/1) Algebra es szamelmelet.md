### Alapfogalmak
*Csoport*
$(A, \cdot)$ csoport ha a kovetkezok teljesulnek
- $\cdot$ asszociativ: $(a \cdot b) \cdot c = a \cdot (b \cdot c) \quad \forall a, b, c \in A$
- egysegelem: $\exists e$ ugy hogy $\forall a \in A$-ra $e \cdot a = a$
- inverz elem: $\forall a \in A$-ra $\exists b \in A$ ugy hogy $a \cdot b = e = b \cdot a$. Tovabba, minden $a$-ra $b$ egyertelmu: $b = a^{-1}$

*Abel csoport*
$(A, \cdot)$ Abel csoport ha csoport es $(\cdot)$ kommutativ.
$$
a \cdot b = b \cdot a \quad \forall a, b \in A
$$

*Gyuru*
$(R, +, \cdot)$ gyuru ha
- $(R, +)$ Abel csoport, tehat az osszeadas asszociativ egy kommutativ es letezik nullelem
- $(R, \cdot)$ felcsoport, tehat a szorzas asszociativ
- az osszeadas distributiv a szorzasra nezve
$$
(x + y)z = xz + yz \quad \text{es} \quad z(x + y) = zx + zy
$$


### Komplex szamok
$$
\mathbb{C} = \{ a + bi : a,b \in \mathbb{R} \}
$$
$$
(a + bi) + (c + di) = (a + c) + (b + d)i
$$
$$
(a + bi) \cdot (c + di) = (ac - bd) + (a d + bc)i
$$
*All.:*
$$
\frac{1}{z} = \frac{\bar{z}}{\lvert z \rvert ^{2}}.
$$
*Biz.:*
$$
\frac{1}{z} \cdot \frac{\bar{z}}{\lvert z \rvert ^{2}} = \frac{z \cdot \bar{z}}{\lvert z \rvert ^{2}} = \frac{\lvert z \rvert ^{2}}{\lvert z \rvert ^{2}} = 1.
$$

*All.:* $z = r(\cos \varphi + i \sin \varphi)$.
*All.:* 
$$
z \cdot w = rs( \cos(\varphi + \psi) + i \sin (\varphi + \psi)).
$$
*Megj.:* Komplex szamokkal nagyon szepen leirhatok a forgatasok a sikban. Nem kell szarozni matrixokkal.
*Megj.:* Trigonometrikus alakban pofon egyszeru komplex szammal osztani is.

*Def.:* A $z \in \mathbb{C}$ szam $n$-edik egyseggyok, ha $z^{n} = 1$.
*All.:*
$$
\varepsilon = \cos \frac{2\pi}{n} + i \sin \frac{2\pi}{n} \implies o(\varepsilon) = n.
$$
*Megj.:* Egyenlo tavolsagonkent felbontjuk az egysegkort.

*All.:* $(\mathbb{C}, +, \cdot)$ egy test

### Polinomok gyokeinek szama test folott
polinom: $a_{n} x^{n} + \dots + a_{1}x + a_{0}$
$\geq n + 1$ pont egyertelmuen meghataroz egy $n$-ed foku polinomot

*Tetel:* Ha $x_{0}$ gyoke $f(x) = a_{n} x^{n} + \dots + a_{1}x + a_{0}$ polinomnak, akkor ki lehet emelni belole, azaz
$$
f(x) = (x - x_{0})g(x),
$$
ahol $g(x)$ valami polinom.

*Tetel:* Ha $x_{1}, \dots, x_{k}$ $(k \leq n)$  gyokei $f(x)$ polinomnak, akkor egyszerre ki lehet emelni az osszeset, azaz
$$
f(x) = (x - x_{1}) \dots (x - x_{k}) g(x),
$$
ahol $g(x)$ valami polinom.

*Def.:* Azt mondjuk, hogy a $T$ test algebrailag zart, ha $T[x]$ minden nem konstans polinomjanak van $T$-ben gyoke.

*Tetel:* (Algebra alaptetele) A komplex szamok teste algebrailag zart.
*Megj.:* Az algebra alaptetele azt mondja hogy minden valos vagy komple egyutthatos polinomnak van komplex gyoke. Peldaul az $f(x) = x^{2} + 1$ polinomnak nincsen a valosak folott gyoke, de a komplexek folott az $i$ gyoke.
*Kov.:* Osszeteve az algebra alaptetelet es hogy ki lehet emelni a gyokoket arra a kovetkeztetesre jutunk, hogy minden $f \in \mathbb{C}[x]$ polinomnak annyi gyoke van mint amekkora a foka, mivel $f$-nek van gyoke, akkor kiemeljuk es marad egy $g \in \mathbb{C}[x]$ aminek szinten van gyoke, es igy tovabb.

### Szamelmelet alaptetele szamokra es polinokra
*Tetel:* Minden $1$-nel nagyobb termeszetes szam felbomlik egyertelmuen primszamok szorzatara, azaz $\forall 1 < n \in \mathbb{N}$-re
$$
n = \prod p_{i}^{\alpha_{i}}.
$$

*Def.:* A $f \in K[x], deg f \geq 1$ polinom reducibilis, ha $\exists g, h \in K[x]$ ugy hogy $f = gh$ es mindketto kisebb foku mint f.
*Def.:* Az $f$ irreducibilis ha nem reducibilis.

*Tetel:* A szamelmelet alaptetele test folotti egyvaltozos polinomok folott.
Legyen $f \in K[x]$ normalt polinom. Ekkor $\exists ! n$ es $\exists ! p_{1}, \dots, p_{n} \in K[x]$ normalt irreducibilis polinomok ugy, hogy $f = p_{1}, \dots, p_{n}$. (Az egyertelmuseg sorrendtol fuggetlenul ertendo.)

*Def.:* Legyen $R$ szokasos gyuru. A $p \in R$ elemet irreducibilisnek nevezzuk, ha nem nulla, nem egyseg, es $p$-nek nincs nem-trivialis felbontasa.
*Def.:* Azt mondjuk, hogy az $R$ gyuruben ervenyes a szamelmelet alaptetele, ha $R$ minden nem nulla es nem egyseg eleme sorrendtol es asszocialtsagtol eltekintve egyertelmuen folirhato $R$ irreducibilis elemeinek szorzatakent.
(Szokasos gyuru = kommutativ nullosztomentes egysegelemes gyuru)

### Euklideszi algoritmus
```python
def gcd(a, b):
  if b == 0:
    return a
  return gcd(b, a % b)
```

*Tetel:* (Bezout) Legyen $a, b \in \mathbb{N}$ es $d = \operatorname{gcd}(a, b)$. Ekkor letezik $\lambda, \mu \in \mathbb{Z}$ ugy, hogy $\lambda \cdot a + \mu \cdot b = d$.
A fenti allitasban szereplo egyutthatokat a gcd-vel egyutt is ki lehet szamolni a kiterjesztett euklideszi algoritmussal

### Irreducibilitas
*Def.:* Legyen $R$ szokasos gyuru. A $p \in R$ elemet irreducibilisnek nevezzuk, ha nem nulla, nem egyseg, es $p$-nek nincs nemtrivialis felbontasa.

### Primszamok
Kis fermat tetel

### Kongruenciak es csoportelmeleti vonatkozasaik
*Def.:* $a \equiv b \mod m$, ha $m \mid a - b$
*All.:* Ha $ax \equiv a y \mod m$ es $(a, m) = 1$, akkor $x \equiv y \mod m$.
*Tetel:* Az $ax \equiv b \mod m$ egyenletnek letezik megoldasa akkor es csak akkor ha $(a, m) \mid b$. Tovabba a megoldasok egy maradek osztalyt alkotnak modula $m / (a, m)$.
*Tetel:* (Kinai maradektetel) Ha $m_{1}, \dots, m_{k} \in \mathbb{Z}$ es paronkent relativ primek es $c_{1}, \dots, c_{k} \in \mathbb{Z}$, akkor az $x \equiv c_{i} \mod m_{i}$ szimultan kongruencia rendszer ekvivalens az $x \equiv c \mod \prod m_{i}$ kongruenciaval.
*Tetel:* (Euler–Fermat) Ha $(a, m) = 1$, akkor $a^{\varphi(m)} \equiv 1 \mod m$.
*Tetel:* (Kis Fermat) Ha $p$ prim es $a \in \mathbb{Z}$, akkor ha $p \not \mid a$ akkor $a^{p-1} \equiv 1 \mod p$ es $a^{p} \equiv a \mod p$.

*All.:* A $\mathbb{Z}_{m} = \{ 0, 1, \dots, m-1 \}$ halmaz Abel csoport az osszeadasra.
*All.:* $\mathbb{Z}_{m}$ kommutativ egysegelemes gyuru.
*All.:* $\mathbb{Z}_{m}$ test pontosan akkor, ha nullosztomentes, tehat pontosan akkor ha $m$ prim.
*Tetel:* (Wilson) $(p-1)! \equiv -1 \mod p$.

### Matrixcsoportok
*Def.:*
- $P \in \mathbb{R}^{2}$ pontot fixalo forgatosok csoportja $O(2)$
- Az origot fixalo forgatasok csoportja $SO(2)$

*Def.:* Legyen $T$ test es $n \geq 1$ egesz. Ekkor a $T$ folotti $n \times n$-es invertalhato matrixok csoportjat a szorzasra general linear group-nak, $GL(n, T)$-nek, nevezzuk. Azok a matrixok melyek determinansa $1$ reszcsoportot alkotnak $GL(n, T)$-ben, es special linear group-nak nevezzuk, es $SL(n, T)$-vel jeloljuk.

cheatsheet:
- invertalhato $n \times n$-es matrixok csoportja $GL(n, T)$
- determinans = 1 matrixok csoportja $SL(n, T)$
- $GL(n, \mathbb{R})$-beli ortogonalis matrixok csoportja $O(n)$
- ezen belul det = 1 reszcsoport $SO(n)$
- $GL(n, \mathbb{C})$-beli uniter matrixok csoportja $U(n)$
- ezen belul det = 1 reszcsoport $SU(n)$

### Permutaciocsoportok
*Def.:* Az $X$ veges halmazt onmagara kepezo bijekciokat az $X$ halmaz permutacioinak nevezzuk. Ha $\lvert  X \rvert = n$, akkor $S_{X}$ csoportot alkot a kompoziciora nezve. Ha $X = \{ 1, \dots, n \}$, akkor $S_{X}$ helyett $S_{n}$-et irunk.

inverzio, inverzio szam, paritas, elojel, ugyanannyi paros es paratlan permutacio,

transzpozicio, ciklus

*Tetel:* Veges halmaz minden permutacioja felirhato paronkent diszjunkt ciklusok szorzatakent.
*Tetel:*
$$
(x_{1} x_{2} x_{3} \dots x_{k}) = (x_{1} x_{2})(x_{2} x_{3}) (x_{3} x_{4}) \dots (x_{k-2} x_{k-1})(x_{k-1} x_{k}).
$$
*Tetel:* Ha $f$ permutacio felbonlik paratlon sok paros hosszu ciklusra, akkor $f$ paratlan, kulonben paros.

### Elemrend
*Def.:* Legyen $G$ csoport es $g \in G$. A $g$ elem rendje a $g$ kulonbozo hatvanyainak a szama, A $g$ elem rendjenek jele $o(g)$. Azt mondjuk, hogy a $k$ egesz szam jo kitevoje a $g$-nek, ha $g^{k} = 1$.
*Tetel:*
1. $g$ hatvanyai vagy paronkent kulonboznek es ekkor $o(g) = \infty$, vagy periodikusan ismetlodnek $o(g)$ periodusokban
2. a rend a legkisebb pozitiv jo kitevo veges rend eseten, tehat ha $o(g) < \infty$ akkor $g^{o(g)} = 1$ es ez a legkisebb
3. tetszoleges $k, l \in \mathbb{Z}$-re, ha $o(g) < \infty$ akkor
$$
g^{k} = g^{l} \iff o(g) \mid k - l, \quad \text{specialisan } \quad g^{k} = 1 \iff o(g) \mid k.
$$
- a hatvany rendjenek keplete:
$$
o(g^{k}) = \frac{o(g)}{(o(g), k)}.
$$

*Tetel:* Legyen $G$ csoport, es $g \in G$ es $o(g) = d < \infty$. Ekkor $g$ hatvanyainak rendje $d$-enk osztoja, es $g$-nek pontosan $\varphi(d)$ darab $d$ rendu hatvany van, ahol $\varphi$ az Euler fele tociens fuggveny.
*Megj.:* $\varphi(n)$ azt szamolja hogy hany $n$-nel kisebb egesz szam van mely relativ prim $n$-el.

### Faktorcsoport
*Def.:* Legyen $H \leq G$, ekkor $aH$-t baloldali mellekosztalynak es $Ha$-t jobboldali mellekosztalynak hivjuk.
*Def.:* Legyen $H \leq G$ reszcsoport, ekkor
$$
G / H = \{a H: a \in G\},
$$
faktorcsoport neven ismert.

*Megj.:* Tehat a faktorcsoport a baloldali mellekosztalyok csoportja.
*Peldaul:* Modulo $m$ osszeadas csoportja $\mathbb{Z}_{m}$.

### Algebrai es transzcendens szamok
*Def.:* Az $x \in \mathbb{R}$ szam algebrai, ha letezik $p \in \mathbb{Z}[x]$ ($p \neq 0$) polinom, melyre $p(x) = 0$.
*Def.:* Az $x \in \mathbb{R}$ szam transzcendens, ha nem algebrai.
*Tetel:* Az $e$ es $\pi$ tanszcendens szamok.
*Tetel:* Majdnem minden szam transzcendens, mivel megszamlalhatoan sok egesz egyutthatos polinom van, ezert megszamlalhatoan sok algebrai szam van.

### Minimalpolinom
*Def.:* Az $x \in \mathbb{R}$ szam minimalpolinomja a legkisebb foku polinom, melynek $x$ gyoke.
*Tetel:* Ha $f(x) = 0$, akkor $m \mid f$.
