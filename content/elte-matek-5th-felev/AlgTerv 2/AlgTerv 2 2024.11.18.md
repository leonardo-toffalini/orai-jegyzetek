---
title: 10. Geometriai algoritmusok
date: 2024-11-18
---

*input:* pontok a sikon, azaz $p_{1}, \dots, p_{n} \in \mathbb{R}^{2}$ ahol $p_{i} = (x_{i}, y_{i})$

### I. Konvex burok
Feltesszuk, hogy $x_{1} < x_{2} < \dots < x_{n}$

algo:
```
FOR k = 1..n
	conv(p_1, ..., p_k)
```

`F = [1, 5, 11, ..., k]`
`A = [1, 3, 7, ..., k]`

$k$-ra mar megcsinaltuk es most akarjuk $k+1$ -re
Azt az $F(j)$ pontot keresem amire az $F(j-1) - F(j)$ egyenes a $p_{k+1}$ pont felett megy es az $F(j) - F(j+1)$ egyenes a $p_{k+1}$ egyenes alatt megy

Ha egy adott $j$-t megtippelunk akkor azt konstans idoben le tudjuk tesztelni.

Ha megtalaltuk azt a $j$-t amire a fenti teljesul, akkor az F tobb $j+1$ hosszu lesz es a vegere $j+1$-et kell irni

A meglepo, hogy ha felezo keresessel szeretnenk megtalalni a $j$-t akkor csak $n\log n$ futasideju algoritmust fogunk kapni de mi $n$ idore torekszunk.
Ezt el tudjuk erni ha a vegerol egyesevel visszafele keresunk!

```
FOR f = k..1 (-1)
	IF j az ugropont:
		break

f := j+1
F(f) := k+1
```
ugyanezt $A$-val

Ezzel az eljarassal minden pontot csak egyszer nezzuk meg.


### II. Legkozelebbi pontpar tavolsaga
*feladat:* $\delta = d(p_{i}, p_{j})$ ahol $i \neq j$ es $\delta \leq d(p_{k}, p_{l}) \quad \forall k \neq l$

Divide and conquer algoritmus lesz
Divide:
	Kiszamoljuk az $x$ koordinatak mediansat: $x^{m}$
	 $P_{B}$ (particio-bal) azon pontok amelyeknek az $x$ koordinataja kisebb mint $x^{m}$
	$P_{J}$ (particio-jobb) azon pontok amelyeknek az $x$ koordinataja nagyobb mint $x^{m}$

Rekurzios resz:
	Rekurzivan megoldjuk a feladatot $P_{B}$-re, ami visszaadja, hogy a legkozelebbi pontpar tavolsaga $\delta_{1}$
	Rekurzivan megoldjuk a feladatot $P_{J}$-re, ami visszaadja, hogy a legkozelebbi pontpar tavolsaga $\delta_{2}$
	Legyen a megoldas $\delta := \min(\delta_{1}, \delta_{2})$

Meg kell meg nezni azokat a pontparokat ahol az egyik pont $P_{B}$-ben van mig a masik pont $P_{J}$-ben.
Vegyuk eszre, hogy eleg csak azokat a pontparokat vizsgalni, ahol az egyik pont legfeljebb $\delta$ tavolsagra van az $x^{m}$ egyenestol es a masik pont is csak legfeljebb $\delta$ tavolsagra van az $x^{m}$ egyenestol.
Tehat csak az $x=x^{m}$ egyenes egy $\delta$ sugaru strip-jeben kell vizsaglnunk a pontparokat mar.

Uralkodj:
	$Q := \{ p_{i} \mid x^{m} - \delta < x < x^{m} + \delta \} = \{ q_{1}, q_{1}, \dots, q_{r} \}$
	$y$-szerint rendezzuk $Q$-t: $y(a_{1}) \leq y(a_{2}) \leq \dots$
	Leellenorizzuk minden $q_{i}$-ra, hogy a felette levo $q_{j}$-re van-e $\delta$-tol kozelebb levo
	Eszreveheto, hogy eleg csak a $q_{i}$ feletti $\delta$ magassagu strip-ben nezni, igy durva legfeljebb $8$ pontot kell ellenoriznunk (javithato ez a szam)

```
FOR i = 1..r
	FOR l = 1..7
		dist = d(q_i, q_{i+l})
		IF dist < delta THEN delta := dist
```

*Megjegyzesek:*
1. $\delta ^{2}$-et taroljuk igy nem kell folyton gyokot vonni a tavolsagok vizsgalasakor.
2. A minimalis tavolsagu pontpar megtalalasa is konnyu, csak fenntartunk ket indexet a ket pontra amik a legkozelebb vannak.
3. Az elejen megnezzuk, hogy vannak-e egybeeso pontok, ha igen akkor nem is csinalunk tobbet hanem visszaadjuk hogy $0$ a legkozelebbi pontok tavolsaga.
4. Ha $n \leq 3$ akkor konstans idoben megkeressuk a legkozelebbi pontpart (vagy azok tavolsagat)
5. Ha sok olyan pont van amelyeknek megegyezik az $x$ koordinataja, akkor baj lehet, mert nem feltetlenul felezi a $P_{B}$ es $P_{J}$ particiok a ponthalmazt.
	Ezert azt csinaljuk, hogy $P_{B}$-be azok a pontok mennek amiknek az $x$ koordinataja kisebb mint $x^{m}$ *es* ha $x=x^{m}$ akkor az $y$ koordinataja *pozitv*. Hasonlo modon $P_{J}$-be azok mennek amiknek az $x$ koordinataja nagyobb mint $x^{m}$ *es* ha $x = x^{m}$ akkor az $y$ koordinataja *negativ*
6. $d$ dimenzioban $O(n\log ^{d-1}n)$ lepesben megoldhato ugy, hogy a vegso $\delta$ sugaru strip-re ugy gondolunk mint egy $d-1$ dimenzios feladatra.

*Jel.:* $p_{i} <_{x} p_{j}$ ha $x_{i} \leq x_{j}$ es ha $x_{i} = x_{j}$ akkor $y_{i} < y_{j}$
vagyis $(x_{i}, y_{i}) <_{\text{lex}} (x_{j} y_{j})$

*Lepesszam:* $O(n\log ^{2}n)$
$$
T(n) \leq c \cdot n + 2T\left( \frac{n}{2} \right) + \stackrel{Q\text{ rendezese}}{\overbrace{n\log n}}
$$
$$
\implies T(n) \leq O(n\log ^{2}n)
$$

*Lepesszam javitasa:* Lehet $O(n\log n)$ lepesben is megcsinalni!
Az elejen rendezzuk a pontokat $x$-szerint es $y$-szerint is, es igy mar nem kell mindig $Q$-t rendezni.
Lesz egy $X = [\dots]$ es egy $Y = [\dots]$ tomb, ahol
$$
x_{X[i]} \leq x_{X[i+1]}
$$
$$
y_{Y[i]} \leq y_{Y[i+1]}
$$

Fontos lepes: Tudom a $Q$ tombot $O(n)$ idoben $x$- es $y$-szerint is rendezni.
Vegig megyek az $X$ tombon es mindegyik elemrol el tudom donteni $O(1)$ idoben hogy benne lesz-e $Q$-ban. $\implies XQ$: a $Q$ tomb $x$-szerint rendezve.
Vegig megyek az $Y$ tombon es mindegyik elemrol el tudom donteni $O(1)$ idoben hogy benne lesz-e $Q$-ban. $\implies YQ$: a $Q$ tomb $y$-szerint rendezve.


### III. Tengely iranyu teglalap feladat
#### a) eltarolni az inputot $O(n\log n)$ tarban es idoben
#### b) Felsorolni az osszes pontot, melyek benne vannak egy adott tengely iranyu teglalapban
tengely iranyu teglalap: $(x_{bal},\; x_{jobb},\; y_{also},\; y_{felso})$
valasz: $\{ i \mid x_{bal} \leq x_{i} \leq x_{jobb} \text{ es } y_{also} \leq y_{i} \leq y_{felso} \}$
legyen $k:= \lvert -| |- \rvert$ (a fenti halmaz merete)

*cel:* egy valasz ideje $O(\log n + k)$
*megoldas:* Tartomany fa
 
 A tartomany fa egy $x$ koordinata szerinti kulso tarolasu kiegyensulyozott binaris kereso fa
Minden csucson van egy $u$  utjelzo ami eliranyitja a pontokat ugy, hogy balra vannak azok amiknel $x \leq u$ es jobbra azok amiknel $x > u$. Az adatok a levelekben vannak tarolva.





