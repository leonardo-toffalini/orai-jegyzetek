### Lienaris egyenletrendszerek
*Tetel:* Egy $Ax = 0$ homogen egyenletrendszer megoldas-halmaza eloall $\{ yB : y \in \mathbb{R}^{2} \}$ alakban.
*Tetel:* Ha $Ax = b$ egyenletrendszernek $x_{0}$ egy megoldasa, akkor a megoldashalmaz eloall $\{ yB + x_{0} : y \in \mathbb{R}^{n} \}$ alakban.

*Tetel:* (Fredholm alternativa tetel) Az $Ax = b$ rendszernek akkor es csak akkor van megoldasa, ha nem letezik olyan $y$, amelyre $yA = 0$ es $yb \neq 0$.
*Megj.:* A Gauss eliminacio vegen vagy egy redukalt lepcsos alakot kapunk vagy van tilos sor.

### Linearis egyenlotlensegrendszerek tulajdonsagai
A tovabbiakban a 
$$
Ax \leq b
$$
rendszert vizsgaljuk. Felmeul a kerdes, hogy van-e megoldasa ennek a rendszernek, erre a Farkas lemma ad valaszt. Felmerul a kerdes hogy milyen alaku a megoldashazlma, erre a politederek adnak valaszt. Hogyan lehet megadni a rendzsernek megoldashalmazat parameteresen, erre valaszt ad majd az hogy minden korlatos polieder politop es forditva.

### Kupok
*Def.:* (kup) A $C$ nemures halmaz kup ha $\alpha \cdot x \in C$ minden $\alpha \in \mathbb{R}^{+}$ es $x \in C$-re.
*Def.:* (konvex kup) A $C$ kup konvex ha $x + y \in C$ minden $x, y \in C$-re.
*Def.:* (generalt kup) A $C$ nemures halmaz generalt kup ha letezik $a_{1}, \dots, a_{n} \in \mathbb{R}^{m}$ vektor melyre $C = \left\{  \sum \lambda_{i}a_{i} : \lambda_{i} \geq 0  \right\}$.
Tehat $n$ vektor nemnegativ linearis kombinacioinak halmaza egy generalt kup.
*Megj.:* Elkepzelhetjuk az $A \in \mathbb{R}^{m \times n}$ matrixot ahol $A$ oszlopai $a_{i}$ vektorok. Ekkor a kovetkezokeppen is tudjuk definialni $C$-t:
$$
C = \{ Ax : x \geq 0 \}.
$$

*Def.:* (metszet kup) A $C$ nemures halmaz metszet kup, ha letezik $b_{1}, \dots, b_{m} \in \mathbb{R}^{n}$ melyre $C = \{ x: b_{1}x \leq 0, \dots, b_{m}x \leq 0 \}$.
*Megj.:* Elkepzelhetjuk a $B \in \mathbb{R}^{m \times n}$ matrixot ahol $B$ sorai a $b_{i}$ vektorok. Ekkor a kovetkezokeppen is tudjuk definialni $C$-t:
$$
C = \{ x: Bx \leq 0 \}.
$$
*Def.:* Egy $q \neq 0$ vektor eseten a $\{ \lambda q : \lambda \in \mathbb{R}^{+} \}$ halmazt iranynek nevezunk.
*Def.:* Egy felegyenesen egy irany eltoltjat ertjuk.
*Def.:* Egy kup polarisan azon vektorok halmazat ertjuk, melyeknek a skalaris szorzata minden kupbeli elemmel nem pozitiv, tehat
$$
K^{*} = \{ x : x \cdot z \leq 0 \quad \forall z \in K \}.
$$

### Politopok
*Def.:* Veges sok pont konvex burka politop.

### Poliederek
*Def.:* Veges sok felter metszete polieder. $R = \{ x : Qx \leq b \}$, ahol $Q \in \mathbb{R}^{m \times n}$ es $b \in \mathbb{R}^{m}$. Tehat egy linearis egyenlotlensegrendszer megoldashalmaza.
*Def.:* Azt mondjuk, hogy a $q$ vektor mozgasvektora a $z \in R$ polieder elemenek, ha letezik $\lambda > 0$ melyre $z + \lambda q \in R$ es $z - \lambda q \in R$.
*Def.:* Azt mondjuk, hogy a $z \in R$ a polieder relativ belso pontja ha van mozgasvektora, es azt mondjuk, hogy extrem pont ha nincs.
*Def.:* Ha minden vektor mozgasvektora $z \in R$-nek, akkor belso pont.
*Megj.:* A kulonbseg a relativ belso pont es a belso pont kozott az hogy a relativ belso pont lehet egy egyenesen vagy egy sikon, mig a belso pont korul van egy kicsi sugaru gomb mely a poliederben van.
*Def.:* Egy $R \subseteq \mathbb{R}^{n}$ nemures polieder $F$ oldala $R$-nek egy
$$
F = \{ x \in R : cd = \delta \}
$$
alaku nemures reszhalmaza, ahol $\delta = \max \{ cd : x \in R \}$ valamely $cx$ linearis celfuggvenyre, melyre a maximum letezik.
*Def.:* Egy polieder valodi oldalan olyan oldalt ertunk, mely nem az egesz polieder.
*Def.:* Egy polieder csucsan egy egyelemu oldalt ertunk.

### Bazismegoldasok, eros bazismegoldasok
*Def.:* Az $R = \{ x: Qx \leq b \}$ polieder egy $z$ elemere nezve a $Q$ matrix egy sorat $z$-aktivnak hivjuk, ha $z$ egyenloseggel teljesul. A $z$-re nezve aktiv sorok reszmatrixat a $Q$ $z$-aktiv reszmatrixanak nevezzuk es $Q_{z}^{=}$-fel jeloljuk
*Def.:* A $z \in R$ elem szintjen a $\sigma(z) = r(Q) - r(Q_{z}^{=})$ szamot ertjuk.
*Def.:* A $Qx \leq b$ rendszer $z$ megoldasat bazismegoldasnak nevezzuk, ha a $z$-aktiv $Q_{z}^{=}$ reszmatrix rangja $r(Q)$, mas szoval ha $\sigma(z) = 0$.
*Def.:* Ha egy bazis megoldas ezen felul olyan, hogy a $z$ nem nulla komponenseinek megfelelo $Q$ oszlopai linearisan fuggetlenek, akkor eros bazis megoldasnak hivjuk.
*Megj.:* Ha $Q$ teljes rangu, tehat oszlopai linearisan fuggetlenek, akkor minden bazis megoldas eros bazis megoldas.

*Tetel:*
1. Minden megoldhato linearis egyenlotlenseg rendszernek letezik bazis megoldasa, nevezetesen barmely minimalis szintu $z$ megoldas bazis megoldas.
2. Letezik eros bazis megoldas is, nevezetesen egy maximalisan sok $0$ komponenst tartalmazo $z$ bazis megoldas eros.

*Tetel:* A $Qx \leq b$ egyenlotlenseg rendszer egy $z$ megoldasa akkor es csak akkor eros bazis megoldas, ha letezik $Q$-nak egy olyan $r(Q)$ sorbol es $r(Q)$ oszlopbol allo nem szingularis $Q'$ reszmatrixa, amelyre $z$ a $Q'x' = b'$ egyertelmu $x'$ megoldasabol allo elo $0$ komponensek kiterjesztesevel.
*Kov.:* Legfeljebb veges sok eros bazis megoldas van.

### Alkalmazasai
???

### Linearis optimalizalas
*Tetel:* (Iranymenti korlatossag tetele)
*Tetel:* Ha egy egyenlotlenseg rendszer megoldhato akkor van eros bazis megoldasa.
*Def.:* Linearis programozasi feladat
$$
\begin{aligned}
\text{s.t.} \quad Ax \leq b \\
\quad \max cx \\
\end{aligned}
$$
Tehat keresunk egy olyan $x$-et amelyre teljesul egy egyenlotlenseg rendszer es maximalizalja a $c \cdot x$ celfuggvenyt.
*Megj.:* Meglepoen sok dolog irhato fel ebben az egyszeru alakban.

### Felbontasi tetelek
*Tetel:* Egy politop es egy generalt kup osszege polieder. Specialisan, minden politop korlatos polieder es minden generalt kup eloall metszetkupkent.
*Tetel:* Minden metszetkup eloall generalt kupkent.
*Tetel:* Minden nemures polieder eloall mint egy politop es egy generalt kup osszege. Specialisan, minden korlatos polieder politop.
*Megj.:*
- polieder = politop + generalt kup
- metszet kup = generalt kup
- politop = korlatos polieder

### Dualitas
*Tetel:* (Gyenge dualitas)
$$
\max \{ cx : Qx \leq b \} \leq \min \{ yb : yQ = c, \; y \geq 0 \}.
$$
*Biz.:*
$$
yb - cx = yb - yQx = y(b - Qx) \geq 0
$$
mert $y \geq 0$ es $Qx \leq b \implies b - Qx \geq 0$. Tehat $yb - cx \geq 0 \implies yb \geq cx$.

*Tetel:* (Eros dualitas) Ha $\exists x : Qx \le b$ es $\exists y: yQ = c, \; y \geq 0$, azaz a primal es dual feladat is megoldhato, akkor
$$
\max cx = \min yb.
$$

### Farkas-lemma
*Tetel:* $\exists x : Ax \leq b \iff \not \exists y : yA = 0, \quad yb < 0, \quad y \geq 0$.
*Tetel:* Az $\{ Ax = b : x \geq 0 \}$ rendszernek pontosan akkor van megoldasa, ha az $\{ yA \geq 0: yb < 0 \}$ rendszernek nincs.

### Szimplex modszer
Huh... Vizualok nelkul nehez leirni szoban, de

Ismetlesul: $x$ bazis megoldas $\iff$ letezik $B$ az $A$ oszlopainak reszhalmaza, melyre $B$ az oszlopter egy bazisa.

Celunk az, hogy talaljunk egy $x$ vektort melyre $Ax = b$ es $x \geq 0$. Feltesszuk hogy $A$ oszlopai fuggetlenek.
Mivel $x \geq 0$ ezert vannak azok az elemei melyek $0$-ak es azok melyek $>0$, tehat felirhatjuk a kovektezo alakban $x$-et:
$$
x = (0 \dots 0 \; z \; 0 \dots 0).
$$
Legyen $B$ azon reszmatrix mely tartalmazza azon oszlopokat melyre $x_{i} \neq 0$. Ekkor nyilvan $\exists ! z: Bz = b$.
A szimplex modszer ugy fog menni, hogy egy bazist iteralunk addig ameddig el nem jutunk egy megengedett megoldasig.

*Altalanos lepes:*
A $B$ bazist vizsgaljuk.
Megoldjuk a $B z = b$ egyenletet amibol magkapjuk a $z$ vektort.
Ha $z \geq 0$, akkor keszen vagyunk mert $x = (0 \dots 0 \; z \; 0 \dots 0) \geq 0$  es megoldasa $Ax = b$ rendszernek.
Ha $z \not{\geq} 0$, akkor letezik $z_{i}$ melyre $z_{i} < 0$.
Most jon a trukk: Vegyuk a $w = (0 \dots 0 \; 1 \; 0 \dots 0)$ vektort, ami akkora mint $B$ szelteben es pont ott van $1$-es ahol $z_{i} < 0$.
Ekkor oldjuk meg az $yB = w$ rendszert es megkapjuk az $y$ vektort.
Nezzuk meg hogy $yb$ mire jon ki:
$$
yb = y(Ax) = z_{i} < 0.
$$
Tehat azt kapjuk, hogy $yb < 0$. Innen megint kette agazunk.
Ha $yA \geq 0$, akkor $y$ a dualis feladat megoldasa, tehat a Farkas lemma miatt a primalnak nincs megoldasa.
Ha $yA \not{\geq} 0$, akkor letezik $j$ mire $ya_{j} < 0$, es ekkor csereljuk fel az $a_{i}$ es $a_{j}$ oszlopvektorokat es folytassuk ezzel az uj bazissal az iteracoit.

*Megj.:* (Bland szabaly) Tobb serto index esetben a minimalis indexet valasztjuk.
*Lemma:* A Bland szabaly mellett veges az algoritmus.

### Teljesen unimodularis (TU) matrixok
*Def.:* Azt mondjuk, hogy a $Q$ egeszerteku matrix teljesen unimodularis, ha minden aldeterminansa $0$, $-1$, vagy $+1$.
*Tetel:* Ha $Q$ TU matrix, akkor $(Q, I)$ is TU matrix, ahol $(A, B)$ azt jeloli hogy $A$ belle konkatenaljuk $B$-t.
*Tetel:* Ha $Q$ TU matrix, akkor $(Q, -Q)$ is TU matrix.

### TU matrixok alkalmazasai
*Tetel:* Tetszoleges $M$ TU matrixszal megadott egyenlotlenseg rendszer eseten, ha a $b$ jobboldali korlatozo vektor egesz ($Ax \leq b$), akkor minden eros bazis megoldas egesz
*Tetel:* Digraf incidencia matrixa TU matrix.
*Tetel:* Paros graf incidencia matrixa TU matrix.
