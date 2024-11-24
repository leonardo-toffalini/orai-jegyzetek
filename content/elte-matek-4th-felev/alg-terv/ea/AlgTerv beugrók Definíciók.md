# Definíciók
### 1.
*Definiálja a bináris kupacot!*

***Def.:*** A bináris kupac egy szép bináris fa, melynek csúcsaiban 1-1 rekord van egy kitüntetett *KULCS* mezővel. Jelölje $K(v_{i})$ a $v_{i}$ csúcsban lévő rekord kulcsát.
Továbbá, teljesül a *kupacrendezetttség*: minden gyökértől különböző $v_{i}$ csúcsra igaz, hogy $K(szülő(v_{i})) \leq K(v_{i})$
Azaz, minden gyökértől különböző csúcsra igaz, hogy a szülőjében tárolt rekordnak a kulcsa klegfeljebb akkora, mint a csúcsban tárolt rekord kulcsa.

### 2.
*Definiálja a szomszédsági mátrixot és az éllístás tárolást!*

A $G=(V,E)$ gráf (ahol $V = \{ 1, 2, \dots, n \}$, amit továbbiakban végig felteszünk), szomszédsági mátrixa a következő $n \times n$ -es mátrix:
$$
A(i, j) = \begin{cases}
1 & \text{ha } ij \in E \\
0 & \text{ha } ij \not \in E
\end{cases}
$$
Ugyanennek a gráfnak az éllistás megadása a következő:
A gráf minden csúcsához egy láncolt lista tartozik, a listafejeket egy tömbben tároljuk. Az $i \in V$ csúcs listájában tároljuk az $i$-ből kimenő éleket (az adat részben a végpont), és ha az éleken súly (vagy költség vagy hossz) is adot, akkor azt is (ekkor az adatrész 2 mezőből áll). Irányítatlan gráfnál minden élet mindkét végpontjánál tárolunk.


### 3.
*Definiálja, hogy egy irányított gráf élsúlyozása konzervatív!*

***Def.:*** Egy $G = (V,E)$ irányítatlan gráf egy $c: E \to \mathbb{R}$ súlyozását konzervatívnak nevezzük, ha $G$ minden körének összsúlya nemnegatív.

### 4.
*Definiálja a rendezési feladatot és a stabil rendezést!*

***Def.:*** Rendezési feladat:
	Input: $a_{1}, a_{2}, \dots, a_{n} \in U$ ahol $U$ egy tetszőleges rendezett univerzum.
	Output: az indexek egy $i_{1}, i_{2}, \dots, i_{n}$ permutációja, amelyre igaz, hogy $a_{i_{1}} \leq a_{i_{2}} \leq \dots \leq a_{i_{n}}$.

Egy rendezés stabil, ha az egyforma értékű elemek közül a később érkezett kerül későbbre.
pl.:
	Input: $a_{1} = 16, \; a_{2} = 9, \; a_{3} = 4,\; a_{4} = 9$
	Output: $3, \; 2, \; 4, \; 1$
	Magyarázat: $a_{3} \leq a_{2} \leq a_{4} \leq a_{1}$ és mivel $a_{2} = a_{4}$ és mivel $a_{2}$ előbb volt az inputban, mint $a_{4}$ ezért ebben a sorrendben lesznek az outputban is.

### 5.
*Definiálja a bináris keresőfát!*

***Def.:*** Adott egy $U$ rendezett univerzum. Egy $S \subseteq U$ halmazt szótárnak nevezünk. A bináris keresőfa egy olyan bináris fa, amelynek csúcsaiban rekordok vannak, amelyek kulcsa a szótár egy eleme (minden $v$ csúcsra $K(v) \in S$ jelöli a $v$ csúcsban tárolt rekord kulcsát).
Továbbá, teljesül a keresőfatulajdonság: az összes $v$ csúcsra, a $v$ bal gyerekének minden $u$ leszármazottjára igaz, hogy $K(u) < K(v)$ és a $v$ jobb gyerekének minden $w$ leszármazottjára igaz, hogy $K(w) > K(v)$.

### 6.
*Definiálja az AVL-fákat!*

***Def.:*** Egy bináris keresőfa AVL-fa, ha minden $v$ csúcsra igaz, hogy
$$
\lvert m(bal(v)) - m(jobb(v)) \rvert \leq 1
$$
ahol $m(w)$ a $w$ csúcs magassága, azaz a belőle lefele vezető leghosszabb út hossza, és $m(\operatorname{nil}) := -1$

### 7.
*Definiálja a blokkoló élet és a stabil párosítást!*

***Def.:*** Egy $fl \in E$ él blokkoló $M$ párosításra nézve, ha
a) $fl \not \in M$ és
b) $f$ és $l$ kölcsönösen jobban szeretik egymást, mint az $M$-beli párjukat

Egy $M$ párosítás stabil, ha nem létezik $M$-re nézve blokkoló él.

### 8.
*Definiálja, hogy hash függvények egy halmaza mikor univerzális!*

***Def.:*** Hash függvények egy $\mathcal{H}$ halmaza univerzális, ha $\forall K_{1} \neq K_{2} \in U$-ra és $h \in \mathcal{H}$-ra $\mathbb{P}(h(K_{1}) = h(K_{2})) = \frac{1}{M}$.
Ahol $\mathcal{H} = \{ h: U \to [0, \; M-1] \}$ hash függvények halmaza, amik $M$ értéket vesznek fel.

### 9.
*Írja le egy nyelv eldönthetőségének definícióját!*

***Def.:*** Egy $T$ Turing-gép eldönit az $\mathcal L$ nyelvet, ha minden inputra leáll véges sok lépésben és egy $x$ inputra pontosan akkor áll meg ELF(ogad) állapotban, ha $x \in \mathcal L$.
Egy nyelv algoritmikusan eldönthető, ha van olyan Turing-gép, ami őt eldönti.

### 10.
*Írja le a DTIME oszályok és a P oszály definícióját!*

***Def.:*** Nyelvosztály: $\operatorname{DTIME}(t(n)) = \{  \mathcal L \text{ nyelv } \mid \exists \mathcal L \text{-et eldöntő } T \text{ Turing-gép, amelyre } time_{T}(n) \leq t(n) \; \forall n \}$
Azaz minden $x$ inputra legfeljebb $t(\lvert x \rvert)$ lépést tesz.
$$
P = \bigcup_{c = 1}^{\infty}\operatorname{DTIME}(n^{c})
$$

### 11.
*Írja le az NP oszály definícióját!*

***Def.:*** NP osztály: egy $\mathcal L$ nyelv az NP oszályban van, ha minden $x \in \mathcal L$-ra létezik egy $y$ polinom hosszú és polinomiális időben ellenőrozhető bizonyíték. Azaz pontosabban, ha $\mathcal L$-hez létezik polinomiális lépésszámú $E$ ellenőrző Turing-gép és $c$ konstans, hogy:
	Ha $x \in \mathcal L$, akkor $\exists y$, hogy $\lvert y \rvert \leq \lvert x \rvert^{c}$ és $E$ az $(x, y)$ párt ELF(ogadja).
	Ha $x \not \in \mathcal L$, akkor $\forall y$-ra $E$ az $(x, y)$ párt ELUT(asítja).

### 12.
*Írja le az NP-teljesség definícióját és adjon 4 pédát NP-teljes problémára!*

***Def.:*** Az $\mathcal L$ nyelvet NP-teljesnek hívjuk, ha $\mathcal L \in \operatorname{NP}$, és ha $\mathcal L \in \operatorname {P}$ igaz lenne, akkor minden $\mathcal L' \in \operatorname{NP}$ nyelvre $\mathcal L' \in \operatorname{P}$ következne.

például:
1. Hamilton kör
2. 3-SAT és csak simán SAT
3. nonogram játék
4. Leghosszabb út
5. $k$-nál hosszabb út
6. hátizsák feladat


related: [[AlgTerv 1]]