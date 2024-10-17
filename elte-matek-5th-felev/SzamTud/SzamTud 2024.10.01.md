**Lemma:** $L$ rekurziv $\iff$ $L$ es $\Sigma_{0}^{*} - L$  is rekurzivan felsorolhato.
*Biz.:*
$\implies$ Trivialis: $L$ rekurziv $\iff$ $L - \Sigma_{0}^{*}$ rekurziv
Volt, hogy ha $L$ rekurziv, akkor rekurziv felsorohlato is.

$\impliedby$ $T_{0}, T$ Turing-gepek pontosan $L$ illetve $\Sigma_{0}^{*} - L$ szavain allnak meg
$T$ Turing-gep: Input lemasolasa a $2.$ szalagra
$T_{0}, T$ futtatasa parhuzamosan az elso kesz sdzalagon amelyike eloszor all meg annak az indexet kiirjuk outputkent $\chi_{L}$ kiszamolja


**Tetel:** $T$ $2$ szalagos univerzalis Turing-gep a $\Sigma$ abece felett.
Jelolje $L_{T}$ azon $w \in \Sigma_{0}^{*}$ szavak halmazat, melyekre $T$ leall ha mindket szalagjara $w$-t irunk.
Ekkor $L_{T}$ rekurzive felsorolhato de nem rekurziv.
*Biz.:*
Az hogy rekurzive felsorolhato konnyen belathato mert lezetik olyan Turing-gep ami pont $L_{T}$ szavain all meg.

$L_{T}$ nem rekurziv, mert $\Sigma_{0}^{*} - L_{T}$ nem rekurziv felsorolhato.
Tegyuk fel, hogy $\Sigma_{0}^{*} - L_{T}$ rekurziv felsorolhato, ekkor letezik olyan $k$ szalagos Turing gep amely pontosan $\Sigma_{0}^{*} - L_{T}$ szavain all meg. Ezt a $k$ szalagos Turing gepet meg tudjuk szimulalni egy $1$ szalagos Turing-geppel. Ezt az $1$ szalagos Turing-gepet meg tudjuk az eredeti $2$ szalagos univerzalis Turing-geppel szimulalni, legyen ennek a programja $p$.

$p \stackrel{?}{\in} L_{T}$
Ha $p \in L_{T}$ akkor $T$ megall a $(p, p)$ inputon, ami azt jelenti, hogy az $1$ szalagos Turing-gep megall a $p$ inputon, ami azt jelenti, hogy a $k$ szalgos Turing-gep megall a $p$ inputon. De azt mondtuk hogy a $k$ szalagos Turing-gep pontosan a $\Sigma_{0}^{*} - L_{T}$ szavain all meg.
Tehat ha $p \in L_{T}$ akkor $p \in \Sigma_{0}^{*} - L_{T}$ ami ellentmondas.

*Kovetkezmeny:* A $(T, w)$ parokat tartalmazo nyelv, ahol $T$ Turing-gep leall a $w$ szora nem rekurziv.
*Biz.:* Ha ez rekurziv akkor vegyunk egy $2$ szalagos univerzalis Turing-gepet. Ekkor eldonheto, hogy $T$ megall a $(w, w)$ inputra, tehat eldontheto, hogy $w \in L_{T}$. Az elozo tetel miatt $L_{T}$ nem rekurziv igy nem lehet ilyen.

*Kovetkezmeny:* Azon Turing-gepek leirasa amik megallnak az ures inputon nem rekurziv.
*Biz.:* Vegyuk $T'$ Turing-gepet. Ami a kovetkezot csinalja:
1. Az inputot letorli es rairja $w$-t
2. $T$-t futtatja
Ez megall az ures inputon pontosan akkor, ha $(T, w)$ megall.

*Def.:* Domino problema (Tiling problem)
Adott parketta keszlettel parkettazhato-e a sik?





