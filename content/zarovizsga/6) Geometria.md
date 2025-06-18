### Vektorok hasznalata: skalaris, vektorialis es vegyes szorzat
*Def.:* $u, v \in \mathbb{R}^{n}$ a ket vektor skalaris szorzatatan a kovetkezo szamot ertjuk:
$$
u \cdot v =  \sum_{i=1}^{n} u_{i} \cdot v_{i}.
$$
*Megj.:* A skalaris szorzas egy bilinerais szimmetrikus pozitiv szemidefinit fuggveny.
*Tetel:*
$$
u \cdot v = \lvert u \rvert \cdot \lvert v \rvert \cdot \cos \varphi.
$$
*Kov.:* $u \cdot b = 0 \iff u \perp v$.
*Kov.:* Adott $a \in \mathbb{R}^{n}$, minden $v \in \mathbb{R}^{n}$ vektor felbonthato $v = v_{p} + v_{m}$ komponensekre, ahol $v_{p}$ parhuzamos $a$-val es $v_{m}$ meroleges $a$-ra. Tovabba a kovetkezo kepletek adjak a komponenseket:
$$
v_{p} = \lambda a, \quad \text{ahol } \lambda = \frac{a \cdot v}{\lvert a \rvert ^{2}}.
$$

*Def.:* Adott ket $u, v \in \mathbb{R}^{3}$ vektornak a vektorialis szorzatan azt a vektort ertjuk, amit ugy kapunk, hogy a 
$$
\left| \begin{matrix}
i & j & k \\
u_{1} & u_{2} & u_{3} \\
v_{1} & v_{2} & v_{3} \\
\end{matrix} \right|
$$
determinanst az elso sora szerint fejtjuk ki. Jelolesben $u \times v$.
*Megj.:* A vektorialis szorzas egy bilinearis antiszimmetrikus  fuggveny.
*Tetel:*
$$
u \times v = 0 \iff u \parallel v.
$$
*Tetel:* (Computer graphics)
1. $a \times b$ meroleges az $a$ es $b$ altal veszitett sikra.
2. $\lvert a \times b \rvert = \lvert a \rvert \cdot \lvert b \rvert \cdot \sin \varphi$, tehat a vektorialis szorzat altal letrejott vektor hossza pont akkora mint az $a$ es $b$ altal feszitett parallelogramma terulete.
3. Az $a, b, a \times b$ vektorok ebben a sorrendben jobbrendszert alkotnak.

*Def.:* Az $i, j, k$ rendezett bazissal megegyezo iranyitasu vektorok jobbrendszert alkotnak. Jobbkez szabaly.
*Megj.:* A fenti tetel alapveto a szamitogepes grafikaban raszterizalasnal, amikor haromszogek felulet normaljat szamoljuk.

*Def.:* Az $a, b, c \in \mathbb{R}^{3}$ vektorok vegyes szorzatan a $(a, b, c) = (a \times b) \cdot c$ szamot ertjuk.
$$
(a, b, c) = \left| \begin{matrix}
a_{1} & a_{2} & a_{3} \\
b_{1} & b_{2} & b_{3} \\
c_{1} & c_{2} & c_{3} \\
\end{matrix} \right|
$$
*Megj.:* A vegyes szorzas linearis, es az elojele fugg a permutacio elojeletol, tehat $(a, b, c) = (-1)^{\pi} \pi(a, b, c)$.
*Tetel:* $(a, b, c) = 0 \iff a, b, c$ linearisan osszefuggnek.
*Tetel:* Az $a, b, c$ vektorok vegyes szorzata pont az altaluk feszitett paralellepipedon elojeles terfogata.

*Tetel:* (Kifejtesi tetel) ...
*Tetel:* (Jacobi azonossag) ...
*Tetel:* (Lagrange azonossag) ...

### Konvexitas alapfogalmai
*Def.:* Az $A \subseteq \mathbb{R}^{d}$ halmaz konvex, ha minden $a, b \in A$-ra $[a, b] \in A$.
*Tetel:* Konvex halmazok tetszoleges csaladjanak mettszete is konvex.
*Def.:* A $H \subseteq \mathbb{R}^{d}$ halmaz konvex burkan a legszukebb konvex halmazt ertjuk mely tartalmazza $H$-t.
*Tetel:* Minden $H \subseteq \mathbb{R}^{d}$ halmaznak egyertelmuen letezik a konvex burka.
*Def.:* Az $a_{1}, \dots, a_{n} \in \mathbb{R}^{d}$ pontok konvex konbinaciojan a
$$
\sum_{i=1}^{n} \alpha_{i} \cdot a_{i}
$$
szamot ertjuk, ahol $\alpha_{i} \in \mathbb{R}^{+}_{0}$ es $\sum \alpha_{i} = 1$.
*Tetel:* A $K \subseteq \mathbb{R}^{d}$ halmaz pontosan akkor konvex, ha tetszolegesen sok pontjanak minden konvex kombinacioja benne van $K$-ban.
*Tetel:* Tetszoleges $H \subseteq \mathbb{R}^{d}$ halmaz konvex burka eloall, mint a halmaz opntjainak osszes konvex kombinaciojanak halmaza.
*Tetel:* (Radon lemma) Tetszoleges $d+2$ darab pont $\mathbb{R}^{d}$-ben felbonthato ket halmaz diszjunkt uniojara ugy hogy a ket halmaz konvex kombinaciojanak mettszete nem ures.
*Tetel:* (Helly tetel) Adott $K_{1}, \dots, K_{n} \subseteq \mathbb{R}^{d}$ konvex halmaz ugy hogy $n \geq d+1$. Ekkor ha barmaly $d+1$ darab halmaz mettszete nem ures, akkor az osszes $n$ darab mettszete sem ures.

### Elvalasztasi tetelek
*Tetel:* Legyen $K \subset \mathbb{R}^{d}$ kompakt konvex halmaz, legyen $p \in \mathbb{R}^{d} - K$ kulso pont. Ekkor letezik $y \in \mathbb{R}^{d}$ es $\alpha \in \mathbb{R}$ melyre $y \cdot p + \alpha > 1$ es $y \cdot x + \alpha \leq 1$.
*Megj.:* Magyarul ez azt jelenti hogy ha van egy kompakt konvex halmaz es egy pont ami ezen kivul van, akkor letezik olyan $y$ normalvektoru hipersik amely elvalasztja a konvex halmazt a kulso ponttol. Tehat a konvex halmaz a hipersik egyik oldalan van, mig a pont a masikon.
*Tetel:* Legyenek $K$ es $L$ diszjunkt kompakt konvex halmazok $\mathbb{R}^{d}$-ben. Ekkor letezik olyan hipersik, mely altal meghatarozott ket nyilt felter egyike $K$-t, a masik $L$-et tartalmazza.

### Konvex halmazok Hausdorff-tavolsaga
*Def.:* Az $X, Y \subseteq \mathbb{R}^{d}$ halmazok Hausdorff tavolsagan a kovetkezo szamot ertjuk:
$$
d(X, Y) := \inf \{ \delta > 0 : Y \subseteq X + B(0, \delta), X \subset Y + B(0, \delta) \}.
$$
*Megj.:* Tehat az $X$ es $Y$ halmazok Hausdorff tavolsaga ugy kepzelheto el mint hogy mennyire tavol van a ket legtavolabbi pont. Avagy mennyire kell felfujnunk $X$-et hogy beleferjen $Y$ es forditva.
*Tetel:* Az $\mathbb{R}^{d}$-beli konvex kompakt halmazokon a Hausdorff tavolsag egy metrika.
*Tetel:* Sot, nem csak metrika hanem teljes metrikus teret alkot.

### Eueler-fele poliedertetel
Minden konvex poliederre fennall a kovetkezo formula:
$$
V - E + F = 2.
$$
Ugyanez a formula fennall minden sikbarajzolhato grafra is, es az ugras poliederekrol sikbarajzolhato grafokra nagyon szep. Rakjuk bele a poliedert egy gombbe es vetitsuk le a polieder oldalait eleit es csucsait a korulotte levo gomb falaira. Ezt a gombot nyissuk ki egy pontjanal es huzzuk szet vegtelenul ameddig nem kapunk egy sikot. Az igy kapott sikon rajta lesz a konvex polieder grafja, ahol a csucsok pontok, az elek elek, az oldalak tartomanyok a grafban.

### Szabalyos poliederek
Olyan konvex poliederek, melyeknek minden oldala egybevago es minden csucsa egyforma, tehat ugynannyi lap talalkozik es ugyanabban a szogben.

### Euklideszi ter
$\mathbb{R}^{n}$ ellatva a skalaris szorzattal

### Projektiv sik
*Def.:* A $V_{\mathbb{F}}$ vektorter projektivizaltja $P(V) = (V \setminus \{ 0 \}) \diagup \sim$, ahol $u, v \in V - \{ 0 \}$ es $u \sim v$ ha $\exists \lambda \in \mathbb{F}: v = \lambda u$.
*Megj.:* Magyarul a fenti definicio azt jelenti hogy a projektiv ter elemei a vektorter origon atmeno egyenesei.
*Def.:* Legyen $U \leq V$ linearis alter, ekkor $P(U)$ projektiv alter, es $\operatorname{dim}P(U) = \operatorname{dim}U - 1$.
*Def.:* Legyen $X \subseteq P(V)$. Ekkor az $X$ altal generalt projektiv alteren az $X$-et tartalmazo legszukebb projektiv alteret ertjuk.
*Tetel:* Tetszoleges $X \subseteq P(V)$ altal generalt projektiv alter egyertelmuen letezik. Jelolesben $\langle X \rangle$.
*Def.:* Legyen $U \leq V$ linearis alter, ekkor $U$ annulatoran $U^{\perp}$ a kovetkezot ertjuk:
$$
U^{\perp} := \{ \alpha \in V^{*}: \alpha|_{U} = 0 \}.
$$
*Hogyan gondoljunk a projektiv sikra?*
1. pontok: $\mathbb{R}^{3}$ origon atmeno egyenesei, egyenesek: $\mathbb{R}^{3}$ origon atmeno sikjai
2. pontok: $S^{2}$ atellenes pont parjai, egyenesek: $S^{2}$ fokorei
3. fogok egy sikot $\mathbb{R}^{3}$-ban, a pontok az origobol indulo sugarak es ezen sik metszetei, a sikok az egy origobol kiindulo sik es a sik metszete. A pontokhoz meg hozza kell venni a sikkal parhuzamos egyeneseket mint idealis pontokat.

### Kvaterniok
$$
i^{2} = j^{2} = k^{2} = ijk
$$
*Tetel:* (Frobenius) Osszesen harom veges dimenzios nullosztomentes asszociativ valos algebra letezik: $\mathbb{R}, \mathbb{C}, \mathbb{H}$.

### SO(3) csoport
Azon ortogonalis $3 \times 3$ matrixok csoportja melyeknek a determinansa $1$. Ezek pont a forgatasok $\mathbb{R}^{3}$-ban.
$$
\begin{aligned}
& R_x(\theta)=\left[\begin{array}{ccc}
1 & 0 & 0 \\
0 & \cos \theta & -\sin \theta \\
0 & \sin \theta & \cos \theta
\end{array}\right] \\
& R_y(\theta)=\left[\begin{array}{ccc}
\cos \theta & 0 & \sin \theta \\
0 & 1 & 0 \\
-\sin \theta & 0 & \cos \theta
\end{array}\right] \\
& R_z(\theta)=\left[\begin{array}{ccc}
\cos \theta & -\sin \theta & 0 \\
\sin \theta & \cos \theta & 0 \\
0 & 0 & 1
\end{array}\right]
\end{aligned}
$$
