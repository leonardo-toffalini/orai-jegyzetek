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
Szamozzuk meg a csucsokat es legye $E_{1}$ az elore elek halmaza es $E_{2}$ a vissza elek halmaza. Nyilvan egyik sem tartalmaz kort mert mindketto topologikusan van rendezve. Mivel $E_{1} \cup E_{2} = E$ ezert
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
$O(n \cdot E)$


#### FPTAS a hatizsak feladatra
1. Felteheto, hogy $\forall i: w_{i} \leq W$
2. Legyen $E = \sum e_{i}$ es legyen $M \in \mathbb{R}$
3. Definialjuk a kovetkezo ertekeket:
$$
e'_{i} = \left\lfloor  \frac{e_{i}}{M}  \right\rfloor 
$$
4. Megoldjuk DP-vel a kovektezo hatizsak feladatot feladatot $(w_{i},\; e'_{i},\; W)$ 
Ezzel kapunk egy $\text{OPT}'$ es $I'$ megoldast.
5. A mi megoldasunk $I'$, $\text{MO}$ ertek ahol
$$
\text{MO} = \sum_{i \in I'}e_{i}
$$
Azaz a vesszos feladat altal kapott targy halmaznak az eredeti osszerteke.
Belathato, hogy
$$
\text{MO} = \sum_{i \in I'}e_{i} \geq M \cdot \sum_{i \in I'} e'_{i} \geq M \cdot \sum_{i \in I} e'_{i} \geq \sum_{i \in I} (e_{i} - M) \geq \text{OPT} - n \cdot M
$$
*Cel:*
$$\text{MO} \geq (1 - \varepsilon) \text{OPT}$$
Ha $nM \leq \varepsilon \cdot \text{OPT}$ akkor ez teljesul.

*All.:* 
$$\text{OPT} \geq \max e_{i} \geq \frac{E}{n}$$
Ebbol kovetkezik, hogy valasszuk $M$-et a kovetkezo keppen:
$$
M = \frac{\varepsilon \cdot E}{n^{2}}
$$

Igy a DP feladat lepesszama 
$$O(n \cdot E') = O\left( n \cdot \frac{E}{M} \right) = O\left( \frac{n^{3}}{\varepsilon} \right)$$









