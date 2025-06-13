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
*All.:* $(\mathbb{C}, +, \cdot)$ egy test
*biz.:* $(\mathbb{C}, +)$ Abel csoport

### Polinomok gyokeinek szama test folott
polinom: $a_{n} x^{n} + \dots + a_{1}x + a_{0}$
$\geq n + 1$ egyertelmuen meghataroz egy $n$-ed foku polinomot

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
*Def.:* Azt mondjuk, hogy az $R$ gyuruben ervenyes a szamelmelet alaptetele, ha mKR minden nem nulla es nem egyseg eleme sorrendtol es asszocialtsagtol eltekintve egyertelmuen folirhato $R$ irreducibilis elemeinek szorzatakent.

### Euklideszi algo
```python
def gcd(a, b):
  if b == 0:
    return a
  return gcd(b, a % b)
```

### Irreducibilitas
*Def.:* Legyen $R$ szokasos gyuru. A $p \in R$ elemet irreducibilisnek nevezzuk, ha nem nulla, nem egyseg, es $p$-nek nincs nemtrivialis felbontasa.

### Primszamok
### Kongruenciak es csoportelmeleti vonatkozasaik
### Matrixcsoportok
### Permutaciocsoportok
### Elemrend
### Faktorcsoport
### Algebrais es transzcendens szamok
### Minimalpolinom

