---
title: 6. Közelítő algoritmusok 2
date: 2024-10-14
---

*Megj.:* Lehet hogy egy altalanosan nehez feladatot kapunk, de ha valami spec esetet akarunk megoldani akkor lehet hogy meg lehet oldani polinomialis idoben.

# Kozelito megoldasok
A kovetkezok adottak:
- $x$ input $\mapsto X(x)$ megengedett megoldasok halmaza
- $f_{x} : X(x) \to \mathbb{R}$  kiertekelesi fuggveny

Feladat: keressunk $y \in X(x)$ megengedett megoldast, amire $f_{x}(y)$ minimalis.

*Def.:* Egy $A$ algoritmust $\alpha$-kozelitonek hivunk, ha $\forall x$ inputra, melyre $X(x) \neq \emptyset$, kiad egy $y \in X(x)$ -et, melyre $f_{x}(y) \leq \alpha \cdot \text{OPT}$.
Ahol $\text{OPT}$ azt a megoldast jeloli amire $f_{x}(y)$ minimalis.

*Megj.:* Ha maximumot keresunk akkor $f_{x}(y) \geq \frac{1}{\alpha} \cdot \text{OPT}$

Egyszeru peldak:
1. Adott $G$ iranyitott graf, keressunk $E' \subseteq E$ reszgrafot, ami aciklikus es $\lvert E' \rvert$ maximalis.
$2$-kozelites konnyen elerheto a kovetkezo modon:
Szamozzuk meg a csucsokat es legyen $E_{1}$ az elore elek halmaza es $E_{2}$ a vissza elek halmaza. Nyilvan egyik sem tartalmaz kort mert mindketto topologikusan van rendezve. Mivel $E_{1} \cup E_{2} = E$ ezert
$$
\max(\lvert E_{1} \rvert, \; \lvert E_{2} \rvert ) \geq \frac{\lvert E \rvert }{2}
$$

2. Adott $G$ iranyitatlan graf, keressuk $\tau(G)$-t legkisebb lefogo csucshalmaz
$2$-kozelito algoritmus:
Legyen $M$ egy nem bovitheto parositas. Ekkor 
$$
\lvert M \rvert  \leq \tau(G) \leq 2 \lvert M \rvert 
$$
Igy ez nyilvan egy $2$-kozelito algoritmus.

### Metrikus utazo ugynok
Input: $G$ graf, $c : E \to \mathbb{R}^{+}$

*Def.:* Egy tura egy olyan seta amely minden csucsot legalabb egyszer erint.

Feladat: Egy minimalis koltsegu *turat* talalni.

$2$-kozelito algoritmus a metrikus utazo ugynok feladatra:
1. Keressuk meg a $T$ minimalis koltsegu feszito fat
2. $T$-bol kepzunk egy $2 \cdot c(T)$   koltsegu turat ugy, hogy a $T$ feszito fat bejarjuk ugy. Ekkor minden elen pontosan ketszer fogunk atmenni.
Ekkor belathato a kovetkezo:
$$
c(T) \leq \text{OPT} \leq 2 \cdot c(T)
$$

*Def.:* Az $A$ algoritmus $\varepsilon$ relativ hibaval kozelit, ha $(1 + \varepsilon)$-kozelito
*Megj.:* max: $\frac{1}{1 + \varepsilon} \approx 1 - \varepsilon$

*Def.:* Polinomial Time Approximation Scheme (PTAS)
Minden $\varepsilon > 0$ -hoz adunk egy $A_{\varepsilon}$ polinomialis algoritmust, ami $\varepsilon$ relativ hibaval kozelit.

*Def.:* Fully PTAS (FPTAS)
Letezik $A$ algoritmus $\varepsilon$ relativ hibaval
$$
O\left( \text{poli}\left( \frac{1}{\varepsilon}, \; n \right) \right)
$$

*Def.:* Efficient PTAS (EPTAS)
Letezik $A$ algoritmus $\varepsilon$ relativ hibaval
$$
O\left( f\left( \frac{1}{\varepsilon} \right) \cdot n^{c} \right)
$$


### Hatizsak feladat (again)
#### Dinamikus Programozas algoritmus
Tudunk egy felso korlatot adni az optimum-ra: $E \geq \text{OPT}$.
Peldaul $E = \sum e_{i}$ de ennel tudnk jobbat is adni.

$\forall i$ $\forall e \leq E$ kiszamoljuk, hogy mi a legkisebb hatizsak, amibe ki tudunk vinni $e$ erteket az elso $i$ targy kozul.

```
T(0, 0) = 0
FOR j = 1 .. E:
	T(0, j) := W + 1  // ez jeloli, hogy nem tudunk kivinni

FOR i = 1 .. n:
	FOR j = 0 .. E:
		T(i, j) := T(i-1, j)
	FOR j = e_i .. E:
		IF T(i-1, j-e_i) + w_i < T(i, j) THEN
			T(i, j) := T(i-1, j-e_i) + w_i

FOR j = E .. 0 (-1):
	IF T(n, j) <= W THEN
		e := j
		j := 0

I := {}  // a kivitt targyak halmaza
FOR i = n .. 1 (-1):
	IF T(i, e) < T(i-1, e) THEN
		I := I U {i}
		e := e - e_i
```
$O(n \cdot E)$ de ez nem polinomialis, mert az input a targyak sulyai es ertekei amik szamjegyekkel vannak megadva. Tehat az input merete $O\left( \sum \log w_{i} + \sum \log e_{i} \right)$


#### Ibarra–Kim approximációs algoritmusa
Legyen adva $n$ darab tárgy pozitív egész $w_i$ súlyokkal és $e_i$ értékekkel, valamint egy $w$ súlykorlát, továbbá egy $\varepsilon>0$ pontossági korlát. Tegyük fel, hogy minden $i$-re $w_i \leq w$, hiszen a súlykorlátnál nehezebb tárgyakat úgysem vihetnénk magunkkal. Legyen

$$
\mathrm{OPT}=\max \left\{\sum_{i \in I} e_i \mid I \subseteq\{1,2, \ldots, n\} \quad \text { és } \quad \sum_{i \in I} w_i \leq w\right\}
$$

valamint legyen $I^*$ egy olyan részhalmaz, amire a maximum éppen eléretik.

Legyen most $M$ egy késöbb alkalmasan választandó szám, ezzel készítsük el a $w_i^{\prime}=w_i, e_i^{\prime}=\left\lfloor e_i / M\right\rfloor$ súlyokat és értékeket, erre a dinamikus programozási algoritmussal keressük meg a $w$ méretű hátizsákban elvihető legnagyobb értéket, legyen ez OPT'. Ezen optimum vétessen fel valamely $J$ részhalmazon, ezt egyébként a dinamikus programozási algoritmussal visszalépéssel (minden minimumszámításnál annak megjegyzésével, hogy a két tag közül melyik eredményezi a minimumot) ki lehet számítani.

Elöször is vegyuik észre, hogy

$$
\frac{e_i}{M}-1 \leq\left\lfloor\frac{e_i}{M}\right\rfloor \leq \frac{e_i}{M}
$$

valamint hogy $I^*$ optimális valsztása miatt

$$
\mathrm{OPT}^{\prime}=\sum_{i \in J}\left\lfloor\frac{e_i}{M}\right\rfloor \leq \frac{1}{M} \sum_{\mathrm{i} \in J} e_i \leq \frac{1}{M} \mathrm{OPT}
$$


Másfelol a $J$ optimális volta miatt

$$
\mathrm{OPT}^{\prime}=\sum_{i \in J} e_i^{\prime} \geq \sum_{i \in I^*} e_i^{\prime} \geq \sum_{i \in I^*} \frac{e_i}{M}-1 \geq \frac{1}{M} \sum_{i \in I^*} e_i-n=\frac{1}{M} \mathrm{OPT}-n .
$$


Ezek alapján tehát látjuk, hogy

$$
\mathrm{OPT}-n M \leq M \cdot \mathrm{OPT}^{\prime} \leq \mathrm{OPT}
$$

most még megmutatjuk, hogy $n M \leq \varepsilon$ OPT, ezzel azt fogjuk látni, hogy

$$
(1-\varepsilon) \mathrm{OPT} \leq M \cdot \mathrm{OPT}^{\prime} \leq \mathrm{OPT}
$$

azaz az algoritmusból adódó $M$. $OPT'$ a valódi optimumnak legfeljebb $\varepsilon$ hibájú becslése.

Megadjuk végül $M$ értékét. Legyen $E=\sum_{i=1}^n e_i$, ezzel legyen

$$
M=\frac{\varepsilon E}{n^2}
$$

ekkor

$$
n M=\varepsilon \frac{E}{n} \leq \varepsilon \max _{1 \leq i \leq n} e_i \leq \varepsilon \mathrm{OPT},
$$

hiszen az átlag nem nagyobb a maximumnál valamint bármelyik konkrét egyetlen tárgyat önmagában el tudjuk vinni.

Már csak az algoritmus lépésszáma van hátra, ez

$$
O\left(n \sum_{i=1}^n e_i^{\prime}\right) \leq O\left(n \sum_{i=1}^n \frac{e_i}{M}\right) \leq O\left(\frac{n E}{M}\right) \leq O\left(\frac{n^3}{\varepsilon}\right)
$$

ami valóban polinomiális approximációs algoritmust jelent.



