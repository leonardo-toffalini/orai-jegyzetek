### linearis egyenletrendszerek
$$
A \in \mathbb{K}^{n \times k}, \quad x \in \mathbb{K}^{k}, \quad b \in \mathbb{K}^{n}
$$
Keressuk $x$-et ugy hogy
$$
Ax = b
$$

### determinans
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

### vektorter
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

### fuggetlenseg

### dimenzio

### linearis lekepzesek es matrixaik

### sajatertek

### diagonalizalhatosag

### normalis

### uniter

### onadjungalt transzformaciok

### kvadratikus alakok
