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

### Sajatertek

### Diagonalizalhatosag

### Normalis transzformaciok

### Uniter transzformaciok

### Onadjungalt transzformaciok

### Kvadratikus alakok
