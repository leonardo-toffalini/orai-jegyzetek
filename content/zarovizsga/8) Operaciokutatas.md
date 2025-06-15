### Lienaris egyenletrendszerek
*Tetel:* Egy $Ax = 0$ homogen egyenletrendszer megoldas-halmaza eloall $\{ yB : y \in \mathbb{R}^{2} \}$ alakban.
*Tetel:* Ha $Ax = b$ egyenletrendszernek $x_{0}$ egy megoldasa, akkor a megoldashalmaz eloall $\{ yB + x_{0} : y \in \mathbb{R}^{n} \}$ alakban.

*Tetel:* (Fredholm alternativa tetel) Az $Ax = b$ rendszernek akkor es csak akkor van megoldasa, ha nem letezik olyan $y$, amelyre $yA = 0$ es $yb \neq 0$.
*Megj.:* A Gauss eliminacio vegen vagy egy redukalt lepcsos alakot kapunk vagy van tilos sor.

### Linearis egyenlotlensegrendszerek tulajdonsagai

### Bazismegoldasok, eros bazismegoldasok

### Alkalmazasai

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

### Politopok
*Def.:* Veges sok pont konvex burka politop.

### Poliederek
*Def.:* Veges sok felter metszete polieder.

### Felbontasi tetelek
### Dualitas
### Farkas-lemma
*Tetel:* (Farkas lemma) Az $\{ Ax = b : x \geq 0 \}$ rendszernak pontosan akkor van megoldasa, ha az $\{ yA \geq 0: yb < 0 \}$ rendszernek nincs.

### Szimplex modszer


### Teljesen unimodularis (TU) matrixok
*Def.:* Azt mondjuk, hogy a $Q$ egeszerteku matrix teljesen unimodularis, ha minden aldeterminansa $0$, $-1$, vagy $+1$.
*Tetel:* Ha $Q$ TU matrix, akkor $(Q, I)$ is TU matrix, ahol $(A, B)$ azt jeloli hogy $A$ belle konkatenaljuk $B$-t.
*Tetel:* Ha $Q$ TU matrix, akkor $(Q, -Q)$ is TU matrix.
*Tetel:* Digraf incidencia matrixa TU matrix.
*Tetel:* Paros graf incidencia matrixa TU matrix.

### TU matrixok alkalmazasai
*Tetel:* Tetszoleges $M$ TU matrixszal megadott egyenlotlenseg rendszer eseten, ha a $b$ jobboldali korlatozo vektor egesz ($Ax \leq b$), akkor minden eros bazis megoldas egesz

