### Linearis egyenletrendszerek
$$
A \in \mathbb{K}^{n \times k}, \quad x \in \mathbb{K}^{k}, \quad b \in \mathbb{K}^{n}
$$
Keressuk $x$-et ugy hogy
$$
Ax = b
$$
*Tetel:*
- Egy linearis egyenletrendszer kibovitett matrixa elemi sorekvivalens atalakitasokkal redukalt lepcsos alakra hozhato.
- Az egyenletrendszer akkor es csak akkor oldhato meg, ha a redukalt lepcsos alakban nincs tilos sor (olyan sor ami csupa nulla de nem nullaval kell egyenlonek lennie).
- Az egyenletrendszernek akkor es csak akkor egyertelmu a megoldasa ha nincs tilos sor es a vezeregyesek szama megegyezik az ismeretlenek szamaval a redukalt lepcsos alakban.
- Ha tobb megoldas van akkor a vezeregyeseket nem tartalmazo oszlopoknak megfelelo ismeretlenek szabad parameterek.

*Cramer-szabaly:* Ha $A \in T^{n \times n}$ es $D = \det A \neq 0$, akkor az $Ax = b$ egyenletrendszernek pontosan egy megoldasa van. A megoldasban $x_{j} = D_{j} /D$ ahol $D_{j}$ determinanst ugy kapjuk hogy a jobboldali konstansokat helyettesitjuk az matrix $j$-edik oszlopaba.
$$
x_{2} = \frac{\left| \begin{matrix}
a_{11} & b_{1} & \dots & a_{1n} \\
a_{21} & b_{2} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & b_{n} & \dots & a_{nn} \\
\end{matrix} \right|}{\left|
\begin{matrix}
a_{11} & a_{1} & \dots & a_{1n} \\
a_{21} & a_{2} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n} & \dots & a_{nn} \\
\end{matrix}\right|
}
$$

### Determinans
*permutaciok*
Egy permutacioban ket elem inverzioban all ha a nagyobbik megelozi a kisebbiket. Egy permutacio elemszama az inverzioban allo elemparok szama. A $\sigma$ permutacio inverzioszama $I(\sigma)$. A $\sigma$ permutacio paritasa $(-1)^{I(\sigma)}$. $n$ elemnek ugyanannyi paros es paratlan inverzioja van.

$$
\det A = \sum_{\sigma} (-1)^{I(\sigma)} a_{1\sigma(1)}a_{2\sigma(2)} \dots a_{n\sigma(n)}
$$
tulajdonsagok:
- a sorok es az oszlopok szerepe felcserelheto es a determinans ugyanaz marad
- diagonalis matrix determinansa a foatlo szorzata
- ha van csupa 0 sor vagy oszlop akkor az egesz determinans 0
- ha egy sor vagy oszlop minden elemet $\lambda$-val megszorozzuk akkor az egesz determinans $\lambda$-val szorzodik
- ha egy sor vagy oszlop minden eleme egy kettagu osszeg akkor a determinans egyenlo a ket determinans osszegevel
- ha ket sor vagy oszlop egyenlo akkor a determinans 0
- ha valamelyik sor vagy oszlop egy masik $\lambda$ szorosa, akkor a determinans 0
- ha egy sorhoz vagy oszlophoz hozzaadjuk egy masik $\lambda$ szorosat akkor a determinans nem valtozik
- ha ket sort vagy oszlopot felcserelunk akkor a determinans elojelet valt
- transzponalt determinansa ugyanaz marad

Egy matrix $(i, j)$ elojeles aldeterminansat, $A_{ij}$-t, ugy kapjuk hogy az $i$-edik sort es a $j$-edik oszlopot elhagyva kiszamoljuk a matrix determinansat es megszorozzuk $(-1)^{i + j}$ -vel.

*Kifejtesi tetel*: Ha egy sor minden elemet megszorozzuk a hozzatartozo elojeles aldeterminanssal, az igy kapott szorzatok osszege a determinanssal egyenlo.
$$
\det A = \sum_{j=1}^{n} a_{ij}A_{ij}
$$
*Ferde kifejtesi tetel*: Ha egy sor minden elemet megszorozzuk egy masik sorhoz tartozo elojeles aldeterminansokkal, az igy kapott szorzatok osszege mindig 0.

### Vektorter
*Def.:* Egy $V$ nemures halmazt vektorternek nevezunk a $T$ test felett, ha az osszeadasra egy Abel csoport es van rajta meg egy skalarral valo szorzas definialva ugy hogy
- $(\lambda + \mu)v = \lambda v + \mu v$
- $\lambda(u + v) = \lambda u + \lambda v$
- $(\lambda \mu)v = \lambda(\mu v)$
- $\forall v \in V: 1_{T}v = v$ ahol $1_{T}$ a $T$ test egysegeleme, azaz $1\lambda = \lambda 1 = 1 \forall \lambda \in T$

*Def.:* Egy $T$ test feletti $V$ vektorter egy nemures $W \subseteq V$ reszhalmazat alternek nevezzuk $V$-ben, ha $W$ maga is vektorter ugyanazon $T$ felett ugyanazokra a $V$-beli muveletekre nezve.

*Tetel:* Egy $T$ test feletti vektorterben egy $W$ nemures reszhalmaz akkor es csak akkor alter ha
- $u, v \in W \implies u + v \in W$
- $v \in W, \lambda \in T \implies \lambda v \in W$
Ergo $W$ zart az osszeadasra es a skalarral valo szorzasra.

### Fuggetlenseg
*Def.:* A $v_{1}, v_{2}, \dots, v_{n} \in V$ vektorok linearisan fuggetlenek, ha $\lambda_{1}v_{1} + \lambda_{2}v_{2} + \dots + \lambda_{n}v_{n} = 0$ csak ugy valosulhat meg, ha mindegyik $\lambda_{i} = 0$.
$$
\lambda_{1}v_{1} + \lambda_{2}v_{2} + \dots + \lambda_{n}v_{n} = 0 \implies \lambda_{i} = 0 \quad \forall i
$$

### Dimenzio
*Def.:* Bazis:
- Linearisan fuggetlen generatorrendszer
- Legkisebb generatorrendszer
- Legnagyobb fuggetlen rendszer

*Tetel:* (Kicserelesi tetel) Legyen $f_{1}, f_{2}, \dots, f_{n}$ fuggetlen rendszer es $g_{1}, g_{2}, \dots, g_{k}$ generatorrendszer. Ekkor barmely $f_{i}$-hez talalhato $g_{j}$ ugy hogy ha kicsereljuk $f_{i}$-t $g_{j}$-ra akkor fuggetlen marad a rendszer.
*Biz.:* TFH $f_{1}$-hez nem letezik $g_{j}$ tehat barmelyik $g_{j}$-re lecserelve a rendszer osszefuggne, tehat mindegyik $g_{j}$ eloall $f_{2}, f_{3}, \dots, f_{n}$ linearis kombinaciojakent. Viszont $g_{1}, g_{2}, \dots, g_{k}$ generatorrendszer tehat a vektorter ossze vektora eloall az o linearis kombinaciojukbal, specialba az osszes $f_{i}$ is. Tehat $f_{i}$-kbol letrejon az osszes $g_{j}$ amikbol meg letrejon az osszes $f_{i}$ tehat $f_{i}$-k nem linearisan fuggetlenek. Ellentmondasra jutottunk tehat $f_{1}$-hez leteznie kell $g_{j}$-nek.

*Tetel:* Egy vektorterben barmely ketto bazis elemszama azonos.

*Def.:* Egy $V$ vektorter dimenzioja egy bazis elemszama. Ha nincs veges generatorrendszer akkor a dimenzio vegtelen. Ha a $V = 0$ akkor $\operatorname{dim} V = 0$.

*Tetel:*
- $W \leq V \implies \operatorname{dim} W \leq \operatorname{dim} V$
- Ha $\operatorname{dim} V < \infty$  es $W \leq V$ es $\operatorname{dim} W = \operatorname{dim} V$ akkor $W = V$

*Def.:* Egy $a_{1}, \dots, a_{n}$ vektorrendszer rangja $r$ ha az $a_{i}$ vektorok kozott talalhato $r$ fuggetlen de $r+1$ nem.

*Tetel:* Az $a_{1}, a_{2}, \dots, a_{n}$ vektorok altal generalt alter dimenzioja a vektorrendszer rangjaval egyenlo.

*Tetel:* Egy linearis egyenletrendszer akkor es csak akkor oldhato meg, ha az egyutthatomatrix rangja megegyezik a kibovitett matrix rangjaval.

### Linearis lekepzesek es matrixaik
*Def.:* Legyen $V_{1}$ es $V_{2}$ ugyanazon $T$ kommutativ test feletti vektorterek. Ekkor azt mondjuk hogy $\mathcal{A}: V_{1} \to V_{2}$ (homogen) linearis lekepezes ha
- $\forall u, v \in V_{1}: \mathcal{A}(u + v) = \mathcal{A}(u) + \mathcal{A}(v)$
- $\forall u \in V_{1}, \forall \lambda \in T: \mathcal{A}(\lambda u) = \lambda \mathcal{A}(u)$

*Def.:*
$$
\operatorname{Im} \mathcal{A} = \{ \mathcal{A}x \mid x \in V_{1} \}
$$

*Def.:*
$$
\operatorname{Ker}\mathcal{A} = \{ x \in V_{1} \mid \mathcal{A}x = 0 \}
$$

*Tetel:* $\operatorname{Im} \mathcal{A}$ alter $V_{2}$-ben es $\operatorname{Ker} \mathcal{A}$ alter $V_{1}$-ben.

*Def.:* Ha $V_{1} = V_{2}$ akkor $\mathcal{A}$-t ugy hivjuk hogy linearis transzformacio.

*Def.:* Egy bijektiv linearis lekepezest izomorfizmusnak nevezunk. Ket vektorter izomorf ha letezik koztuk izomorfuzmus. Jel.: $V_{1} \cong V_{2}$

*Tetel:* Az $\mathcal{A} : V_{1} \to V_{2}$ lekepezos akkor es csak akkor izomorfizmus ha $\operatorname{Ker} \mathcal{A} = 0$ es $\operatorname{Im} \mathcal{A} = V_{2}$.
*Biz.:* $\operatorname{Im} \mathcal{A} = V_{2}$ biztositja hogy $\mathcal{A}$ szurjektiv. TFH $\mathcal{A}u = \mathcal{A}v$ ekkor $0 = \mathcal{A}u - \mathcal{A}v = \mathcal{A}(u - v)$ de $u \neq v$, ellentmondas. Tehat $\mathcal{A}$ injektiv.

*Tetel:*
$$
\operatorname{dim} V_{T} = n \neq 0 \implies V \cong T^{n}
$$

*Tetel:*
$$
U_{T} \cong V_{T} \iff \operatorname{dim} U = \operatorname{dim} V
$$

*Tetel:* Legyen $b_{1}, \dots, b_{n}$ bazis $V_{1}$-ben es $c_{1}, \dots c_{n} \in V_{2}$. Ekkor pontosan egy olyan $\mathcal{A} : V_{1} \to V_{2}$ lekepezes letezik amire
$$
\mathcal{A}b_{i} = c_{i} \quad \forall i
$$

*Tetel:* (dimenzio-tetel)
$$
\operatorname{dim} \operatorname{Im} \mathcal{A} + \operatorname{dim} \operatorname{Ker} \mathcal{A} = \operatorname{dim} V_{1}
$$

*Tetel:* $\operatorname{Hom}(V_{1}, V_{2})$ egy vektorter $T$ felett

*Tetel:* $\operatorname{Hom}(V)$ algebra $T$ felett

*Def.:* Legyen $a_{1}, \dots, a_{n}$ egy bazis $V_{1}$-ben es $b_{1}, \dots b_{k}$ egy bazis $V_{2}$-ben. Ekkor $\mathcal{A} : V_{1} \to V_{2}$ linearis lekepezes matrixa az $a, b$ bazisparba a kovetkezo
$$
[\mathcal{A}]_{a, b} = \begin{bmatrix}
\alpha_{11} & \alpha_{12} & \dots & \alpha_{1n} \\
\alpha_{21} & \alpha_{22} & \dots & \alpha_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
\alpha_{k1} & \alpha_{k2} & \dots & \alpha_{kn} \\
\end{bmatrix}
$$
ahol 
$$
\mathcal{A}a_{i} = \alpha_{1 i}b_{1} + \alpha_{2i} b_{2} + \dots + \alpha_{ki} b_{k} \quad \forall i = 1, \dots, n
$$

*Tetel:*
$$
[\mathcal{A}v]_{b} = [\mathcal{A}]_{a,b} \cdot [v]_{a}
$$

### Sajatertek
*Def.:* Az $\mathcal{A}$ linearis transzformacionak $\lambda \in T$ egy sajaterteke ha letezik olyan $v \in V$ ($v \neq 0$) amelyre
$$
\mathcal{A}v = \lambda v
$$

*Def.:* Az $\mathcal{A}$ linearis transzformacionak $v \in V$ ($v \neq 0$) egy sajatvektora ha letezik olyan $\lambda \in T$ amelyre
$$
\mathcal{A}v = \lambda v
$$

*Def.:* Egy $\mathcal{A}$ linearis transzformacio karakterisztikus polinomja a kovetkezo
$$
k_{\mathcal{A}}(x) = \det([\mathcal{A} - x\mathcal{E}])
$$

*Tetel:* Egy $\lambda \in T$ skalar akkor es csak akkor sajaterteke $\mathcal{A}$-nak ha gyoke $k_{\mathcal{A}}(x)$-nek.
*Biz.:* $\exists v \in V: \mathcal{A}x = \lambda  \iff (\mathcal{A} - \lambda \mathcal{E})x = 0 \iff [\mathcal{A} - \lambda\mathcal{E}] \cdot [x] = [0] \iff \det([\mathcal{A} - \lambda \mathcal{E}]) = 0 \iff k_{\mathcal{A}}(x) = 0$

*Def.:* Az $f$ polinom az $\mathcal{A}$ transzformacio minimalpolinomja, ha $f$ a legkisebb foku olyan polinom, amelynek $\mathcal{A}$ a gyoke. Jelolesben $m_{\mathcal A}$.
*Tetel:* Minden transzformacionak letezik minimalpolinomja, es konstans szorzo erejeig egyertelmu.
*Tetel:* (Cayley-Hamilton) A minimalpolinom osztoja a karakterisztikus polinomnak, tehat
$$
m_{\mathcal A} \mid k_{\mathcal A}.
$$
*Tetel:* Minden $\lambda \in T$-re $m_{\mathcal A}(\lambda) = 0$ pontosan akkor ha $\lambda$ sajaterteke $\mathcal A$-nak. Tehat a minimalpolinom $T$-beli gyokei pontosan a sajatertekek.

### Diagonalizalhatosag
*Tetel:* Egy linearis transzformacio matrixa akkor es csak akkor diagonalis ha a sajatvektorok altal alkotott bazisban irtuk fel. Ekkor a foatloban allo elemek pont a megfelelo bazisvektorokhoz tartozo sajatertekek.
*Biz.:*
$$
[\mathcal{A}]_{a} = \begin{bmatrix}
\lambda_{1} & 0 & \dots & 0 \\
0 & \lambda_{2} & \dots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & \lambda_{n} \\
\end{bmatrix}
$$
pontosan akkor teljesul ha $\mathcal{A}a_{1} = \lambda_{1}, \; \mathcal{A}a_{2} = \lambda_{2}, \; \dots,\; \mathcal{A}a_{n} = \lambda_{n}$

### Normalis transzformaciok
*Def.:* Az $A$ transzformacio normalis, ha $A = A^{*}$.
*Tetel:* Egy veges dimenzios komplex euklideszi terben akkor es csak akkor letezik az mKA transzformacionak ortonormalt sajatvektorokbol allo bazusa, ha $A$ normalis.

### Uniter transzformaciok
$$
AA^{*} = A^{*}A = I
$$
*Tetel:* A fenti definicio ekvivalens a kovetkezokkel:
- $Ax \cdot Az = x \cdot z$
- $\| Ax \| = \| x \|$

### Onadjungalt transzformaciok
$$
A = A^{*}
$$

### Kvadratikus alakok
*Def.:* Bilinearis fuggveny.
*Tetel:*
$$
A(u, v) = [u]^{T}[A][v].
$$
*Def.:* $A$ szimmetrikus ha $A(u,v) = A(v, u)$.
*Tetel:* Szimmetrikus bilinearis fuggvenyhez letezik olyan bazis, melyben a matrixa diagonalis.
*Tetel:* Sot, olyan is amiben a foatloban csak $-1, 0, +1$ elemek vannak.
*Tetel:* (Tehetetlensegi tetel) A szimmetrikus bilinearis fuggveny diagonalis matrixaban a pozitiv, negativ, es nulla elemek szama fuggetlen a bazistol.

*Def.:* Adott $A$ bilinearis fuggveny, ekkor az $\bar{A}(x) = A(x, x)$ fuggvenyt az $A$-hoz tartozo kvadratikus alaknak nevezzuk.
*Tetel:* Adott bazisban
$$
\bar{A}(x) = [x]^{T}[A][x].
$$
*Megj.:* Egy bilinearis fuggveny egyertelmuen meghataroz egy kvadratikus alakot, viszont ez visszafele nem feltetlenul igaz. Csak akkor all fenn visszafele is az allitas ha szimmetrikus a fuggveny.

*Def.:* poz def, neg def, poz szemi def, neg szemi def, indefinit.

