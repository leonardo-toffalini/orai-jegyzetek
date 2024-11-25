---
title: 11. Tartomány fa, Útkeresés
date: 2024-11-25
---
### Tartomany fa (Range tree)
<https://www.cs.umd.edu/class/fall2020/cmsc420-0201/Lects/lect17-range-tree.pdf>
<https://www.geeksforgeeks.org/exploring-range-trees/>
A tartomany fa egy $x$ koordinata szerinti kulso tarolasu kiegyensulyozott binaris kereso fa. 
Minden csucson van egy $u$  utjelzo ami eliranyitja a pontokat ugy, hogy balra vannak azok amiknel $x \leq u$ es jobbra azok amiknel $x > u$. Az adatok a levelekben vannak tarolva.

A tartomany fa minden $v$ csucsahoz hozzarendelunk egy halmazt: $\text{ASSOC}(v) := \{ i \mid x_{i} \text{ egy } v \text{ alatti levelben van} \}$

*Megj.:* Ha $l$ level $x$ cimkevel, akkor $\text{ASSOC}(l) = \{ i \mid x_{i} = x \}$.
$\text{ASSOC}(v)$ tarolasa $L(v)$ tombben ugy, hogy az $y$ koordinata szerint novekszik.

Hogyan epitjuk fel a tartomany fat es hogyan tudunk lekerdezni belole?

#### Lekerdezes tartomany faban
Mely pontok esnek az $[x_{b}, x_{j}, y_{a}, y_{f}]$ tengely iranyu teglalapba?

Valaszolo algoritmus:
1. $x_{b}$ es $x_{j}$ keresese
![[Drawing 2024-11-25 12.27.19.excalidraw]]
2. $F =$ fontos csucsok halmaza, $\lvert F \rvert \leq 2 \log n$
*All.:* Valasz $\subseteq \cup_{f\in F} \text{ASSOC}(f)$
*All.:* $\cup_{f\in F} \text{ASSOC}(f)$ -nak minden olyan $i$ eleme valasz, amire $y_{a} \leq y_{i} \leq y_{f}$

3. Minden $f \in F$ -re van az $L(f)$ tombbun, amely $y$-szerint van rendezve, tehat az elso harmada a tombbnek olyan elemekbol all ahol $y_{j} < y_{a}$, a masodik harmada olyanokbol all ahol $y_{a} < y_{j} < y_{f}$ es vegul az utolso harmado olyan elemekbol all ahol $y_{f} < y_{j}$.
A tomb ezen szep strukturaja miatt felezo keresessel meg tudjuk talalni $y_{a}$-t. Miutan megtalaltuk $y_{a}$-t, addig megyunk $L(f)$-ben jobbra amig meg nem haladjuk $y_{f}$-et.

Mivel egy csucsban legfeljebb $\log n + k_{f} + 1$ lepest vegzunk es $\lvert F \rvert \leq 2 \log n$ ezert az osszlepeszam $O(\log ^{2}n + k)$.

*Altalanositas:* Ha $d$ dimenzioban szeretnenk megoldani a feladatot $d = 2$ helyett, akkor meg tudjuk oldani $O(\log ^{d}n + k)$ idoben.

Az otlet az, hogy a $d$ dimenzios esetet tudjuk redukalni egy $d-1$ dimenzios esetre ugy, hogy ahol taroljuk a pontokat ott egy tomb helyett egy $d-1$ dimenzios feladatot oldunk meg.

 *Allitas:* Ha a dimenzio $d \geq 2$ akkor letezik $O(\log ^{d-1}n + k)$ ideju algoritmus. Tehat $\mathbb{R}^{2}$-ben $O(\log n + k)$.


#### Tartomany fa felepitese
*All.:* Fel lehet epiteni egy tartomany fat $O(n\log n)$ idoben, $O(n\log n)$ tarat hasznalva.

Konnyen lathato, hogy ennyi minimum kell, mert az osszes $n$ pont mindegyiket $\log n$-szer taroljuk.

Legyen $AX_{r}$ az osszes pont indexenek tombje $x$ szerint rendezve.
Legyen $AY_{r}$ az osszes pont indexenek tombje $y$ szerint rendezve.

Amikor egy csucsnal vagyunk es kette kell osztani az itt levo csucsokat akkor meg tudom oldani $O(\lvert \text{ASSOC}(v) \rvert)$ lepesben. Mert az $AX_{v}$ es az $AY_{v}$ tombok rendezve vannak mar es konstans idoben el tudom donteni egy pontrol az $AX_{v}$ tombben, hogy balra vagy jobbra megy es eleg csak sorban tovvabbadnunk az $AX_{r}$ es az $AY_{r}$ tomboket, mert mar eleve rendezve vannak.

#### Kaszkadolas (Cascading)
<https://en.wikipedia.org/wiki/Fractional_cascading>
Legyen $v$ egy csucs a tartomany faban, aminek ket  gyereke $a$ es $b$.
Definialjuk a kovetkezo tomboket: $AY(V)$, $HY_{va}$, $HY_{vb}$ 

TODO


### Utkereses terkepen
Adott $G$ iranyitott graf es $s, t \in V$ ket csucs kozott keressuk a legrovidebb utat es a hosszat: $d(s,t)$

#### Ketiranyu Dijkstra
*"Parhuzamosan"*, inditunk $G$-ben $s$-bol egy Dijkstra algoritmust es inditunk $G$ forditottban $t$-bol egy Dijkstra algoritmust.

Terminologia: Egy $v$ csucsot atvizsgaltnak nevezunk, ha $v \in S$ es $vw$ eleken mar voltunk. Egy $v$ csucs elert ha mar bekerult a $P$-be, tehat van mar egy kulcsa ami felso becslese az $s \to v$ ut hosszanak.

Naivan azt gondolnank, hogy ha van olyan $v$ csucs ami az $s$-bol inditott es a $t$-bol inditott Dijkstraban is mar atvizsgalt akkor keszen vagyunk, de ez igy nem igaz, mert peladul ha van egy olyan ut ami keves nagy elekbol all egy olyan ut ami sok kicsi elbol all. A sok kicsi elbol allo ut osszesen rovidebb mint a masik akkor elobb fogjuk megtalalni a nagy elekbol allo utat, de ez nem az optimalis.

Ha peladul a $w$ csucsot atvizsgaljuk a masodik keresesben, es $w$ egy latott csucs az elsoben $K(w)$ cimkevel, akkor kiszamitjuk $K(w) + d(w, t)$ erteket. Ezeknek a minimuma legyen $\text{MIN}$. (ezt a $\text{MIN}$ erteket mindig firrsitjuk)

Ha letezik olyan $u$ csucs, aki mindketto kereseseben atvizsgalt akkor a $\text{MIN}$ lesz a helyes valasz.

*Biz.:* todo


#### A* algoritmusok
Azt mondom hogy $h(v)$ also becsles $d(v,t)$-re, ha 
- $h(v) \geq 0$
- $h(t) = 0$
- $h(v) \leq d(v,t) \quad \forall v$
- $\forall uv$-re $h(u) \leq c(uv) + h(v)$

Tipikusan ez a $h$ fuggveny a legvonalbeli tavolsag egy utkeresesi problemaban.

Az A* algoritmus csak a kovetkezo sorban ter el a kanonikus Dijkstra algoritmustol:
```
u := argmin(K(v) + h(v))
```

*Megj.:* Ha $h \equiv 0$ akkor visszakapjuk az eredeti Dijkstra algoritmust.

 
