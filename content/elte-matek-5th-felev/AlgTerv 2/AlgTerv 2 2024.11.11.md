---
title: 9. Párhuzamos algoritmusok
date: 2024-11-11
---

### Parhuzamos algoritmusok
NC (Nick Class): Olyan algortimusok vannak ebben az oszalyban, amelyek $n^{c_{1}}$ preoceszorral $O((\log n)^{c_{2}})$ idoben futnak.

Tegyuk fel, hogy van egy NC algoritmusunk es ez az algoritmus az $i$-edik lepesben megszamoljuk, hogy hany proceszor dolgozik: $w_{i}$
Legyen $W := \sum_{1}^{t}w_{i}$ ahol $t$ a lepesek szama. Ezt a $W$ valtozot az osszmunkanak hivjuk.
Tehat ha $1$ proceszorunk lenne, akkor $W$ lepest kene tennie ahoz hogy szimulalja a parhuzamos algoritmust.

*Tetel (Brent 1):* Ha letezik olyan algoritmus, amely $t$ lepesben $W$ osszmunkaval szamol, akkor $\forall p \in \mathbb{N}$-re van egy olyan algoritmusunk, amely $p$ proceszorral szamol es $\frac{W}{p} + t$ lepest tesz.
*biz.:* vegyuk az $i$-edik lepest, $p$ proceszor $\left\lceil  \frac{w_{i}}{p}  \right\rceil$ lepesben
Igy osszesen ennyi lepesre lesz szuksegunk:
$$
\sum_{i}^{t} \left\lceil  \frac{w_{i}}{p}  \right\rceil \leq \sum \frac{w_{i}}{p} + t
$$

Azt mondjuk, hogy egy feladat jol parhuzamosithato, ha ez teljesul.

### Bit-muveletek parhuzamos algoritmusokkal
$a, b < 2^{n}$
*All.:* $n$ proceszorral $O(\log n)$ lepesben ki lehet szamolni $a + b$ erteket.
*biz.:*
felfele:
a $j$-edik lepesben a $p_{i}$ proceszor akkor fog dolgozni, ha $2^{j}|i$ 
$p_{i}$ felelos az $\mathbf{i} i+1., \dots, i + 2^{j} - 1.$ szamjegyekert.
eredmeny:
- $0$: biztosan nem megy balra
- $1$: biztosan megy balra
- $*$: megy balra, ha jon jobbrol

Ekkor minden proceszor $O(1)$ idoben megcsinalja ezt

lefele:
Amikor jovunk lefele, akkor a $p_{16}$ tudja mar a helyes eredmenyt es mostmar csa ka a $8$ -al oszthatok dolgoznak, akkor a $p_{24}$ tudta mar hogy a tole kezdve $8$-nak mi az eredmenye, tegyuk fel hogy ez $*$ volt...

*Szorzas:* A szorzas gyakorlatilag annak felel meg, hogy $n$ darab $2n$ bites szamot osszeadunk.
Tegyuk fel, hogy va $2n^{2}$ proceszorunk
Az elozo modszerrel maris megy az egesz $O(\log ^{2}n)$ idoben

Az a celunk, hogy $O(\log n)$ futasideju parhuzamos algoritmust kapjunk.
*Elso megoldas:* **3-2 osszeadas**
$d + e = a + b + c$
Ezt meg lehet oldani $O(1)$ idoben $n$ proceszorral.
A $p_{i}$ proceszor azt csinalja, hogy $a_{i} + b_{i} + c_{i} = 2e_{i} + d_{1}$

Ezzel az eljarassal $3$ szam osszeget tudom redukalni $2$ szam osszegere.
Mivel jo sok proceszorunk van ezert tudjuk ezt a $3-2$ redukciot csinalni az osszes tagra az osszegben parhuzamosan.
Igy $n$ szam osszeget egy lepesben tudjuk $\frac{2}{3}n$ szam osszegere redukalni.
Addig redukalunk ameddig csak tudunk es igy a vegso futasi ido a kovetkezo lesz: $O\left( \log_{\frac{3}{2}} n + \log n \right) = O(\log n)$

*Masodik megoldas:* negativ szamjegyek
A kovetkezo alakra atalakitok egy szamot:
$$
x = \sum b_{i}4^{i}
$$
ahol $-3 \leq b_{i} \leq 3$

Egy binaris szamot ebbe az alakba atvaltani konstans ido, mert csak minden bit part nezzuk.
A visszavaltast nem neztuk meg oran de meg lehet oldani $O(\log n)$ lepesben $n$ proceszorral.

Azt allitom, hogy ilyen alakban ket szamot mar ossze lehet adni $O(1)$ idoben.

A $p_{i}$ proceszor osszeadja az $x_{i}$ es $y_{i}$ szamjegyeket es igy kapunk egy $-6$ es $6$ kozotti szamot.
TODO


*input:* formula a kovetkezo alakban:
$$
f(x_{1}, \dots, x_{n}) = (((((x_{1} + x_{3}) \cdot x_{6}) - (x_{3} \cdot 5)) \dots) \dots)
$$

*Def.:* Algebrai fa. Absztrakt szintaxis faja az algebrai kifejezesnek.
*Def.:* Ennek a fanak a merete a nemlevel csucsoknak a szama, azaz a muveleti jelek szama. jel.: $\lvert F \rvert$

*input:* algebrai fa
*cel:* masik fa, ami ugyanazt szamolja es a melysege $\leq 3 \log \lvert F \rvert + 1$

*Tetel (Brent 2):* Letezik ilyen fa.
*biz.:* 
1.) Tegyuk fol hogy van egy $F$ fank, vegyuk annak egy $z$ csucsat es leszarmazottait. 
$z$: facsucs, illetve egy uj valtozo
$z$-nek a leszarmazottait kidobjuk es igy kapunk egy $F'$ fat es $z$ helyebe az uj $z$ valtozot irjuk.
Eszrevetel:
$$f'(x_{1}, \dots, x_{n}, z) = f_{1}(x_{1}, \dots, x_{n})\cdot z + f_{0}(x_{1}, \dots, x_{n})$$
$F'|_{z=0} \to f_{0}$
$F'|_{z=1} \to f_{1} + f_{0}$

2.)
*All.:* Minden faban letezik olyan $z$ csucs melyre:
$F_{1}^{z} \leq \frac{\lvert F \rvert}{2}$
$F_{2}^{z} \leq \frac{\lvert F \rvert}{2}$
$F_{1}^{z} + F_{2}^{z} + 1 \geq \frac{\lvert F \rvert}{2}$

3.) Indukcioval:
Ha $\lvert F \rvert = 1 \to$ OK
todo


Legyen $A, B \in \mathbb{R}^{n \times n}$ 
Az APL nyelvnen:
$AB = A+ \circ * B = \sum_{k=1}^{n}a_{i,k} \cdot b_{k,j}$
$A^{n}$ $O(\log n)$ szorzas $\to$ $O(\log ^{2}n)$

$AB := A \lor \circ \land \to A^{n}$
$A:$ A $G$  $n$ csucsu grap szomszedasgi matrixa, foatloban $1$-esek.
*All.:* $A^{l}(i, j) = 1$, ha letezik $\leq l$ elu $i \to j$ ut

$AB := AL \circ + B$ ahol $L$ egy elbaszott $L$ betu mert valamiert nagyon kell APL nyelvben irni.

$$
A(i, j) := \begin{cases}
c(i, j) & \text{ha } ij \text{ nem el} \\
+\infty & \text{ha } ij\text{ nem el, de } i\neq j \\
0 & \text{kulonben}
\end{cases}
$$

*All.:* $A^{l}(i, j)$ legrovidebb $\leq l$ elu $i \to j$ seta




