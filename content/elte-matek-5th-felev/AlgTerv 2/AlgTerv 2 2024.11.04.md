## Online algoritmusok / feladatok
### Siberles problema
nem tudjuk elore mennyiszer fogunk elmenni sielni es minden nap el kell dontenunk hogy holnapra veszunk vagy berlunk sifelszerest

berles: $F$ forint
vasarlas: $10F$ forint

$A_{k}$ algoritmus: a $k$. alkalom utan vasarolunk.
$N$: ennyiszer fogunk menni sielni

feladat: melyik $k$ ertekre lesz az $A_{k}$ algoritmus a legjobb?

jeloles:
$\text{cost}_{\text{OPT}}(N) = \min(N, 10) \cdot F$
$$
\text{cost}_{A_{k}}(N) = \begin{cases}
(k + 10)F & \text{ ha } N \geq k \\ \\
NF & \text{ ha } N < k
\end{cases}
$$

Mennyire jo az $A_{k}$ algoritmus:
$$
c_{A_{k}} := \max_{N} \frac{\text{cost}_{A_{k}}(N)}{\text{cost}_{\text{OPT}}(N)}
$$

*All 1.:* $\forall k$ 
$$
c_{A_{k}} \geq \frac{\text{cost}_{A_{k}}(k)}{\text{cost}_{\text{OPT}}(k)} \geq \frac{(k + 10)F}{\min(k, 10)F} \geq 2
$$
*All 2.:*
$$
c_{A_{k}} = 2 \iff k = 10
$$
*Biz.:*
$\implies$ triv.
$\impliedby$ $\forall N$
$$
\frac{\text{cost}_{A_{10}}(N)}{\text{cost}_{\text{OPT}}(N)} = \frac{\min(N, 20)}{\min(N, 10)} \leq 2
$$

*Def.:* Az $A$ online algoritmus $c$-versenkepes, ha $\forall \sigma$ inputra:
$$
\text{cost}_{A}(\sigma) \leq c \cdot \text{cost}_{\text{OPT}}(\sigma) + b
$$
*Def.:* Az $A$ algoritmus versenykepesessegi hanyadosa a kovetkezo:
$$
c_{A} = \min c \text{, amire } A \; c\text{-versenykepes}
$$

### Lapozasi feladat
Van egy cache es egy memoriank.
cache: $1, \dots, k$ lap
memoria: $1, \dots, m$

Feltesszuk, hogy $m > k$ vagy kulonben cache-be betoltenenk az egesz memoria tartalmat es pukk keszen vagyunk.

Keres: $1$ lap a memoriabol
Ha a lap benne van a cache-ben akkor a kiszolgalas koltsege $0$
Ha a lap nincs benne a cache-ben akkor a kiszolgalas koltsege $1$. Ebben az esetben ki kell dobnunk egy reszet a cache-nek es fel kell toltenunk az uj tartalommal.

*Tetel 1:* $\forall A$ online algoritmusra $c_{A} \geq k$.
*Biz.:*
Az ellenseg csak $k+1$ lapot hasznal es mindig amikor ker egy lapot akkor olyat ker ami nincsen benne a cache-ben.

Az igy generalt inputra: $\text{cost}_{A}(\sigma) = \lvert \sigma \rvert$

Legyen $A^{*}$ egy offline algoritmus ami azt dobja ki, aki a jovoben a leheto legkesobb fog jonni.
Ez az $A^{*}$ algoritmus ezen a $\sigma$ inputon:
$$\text{cost}_{A^{*}}(\sigma) \leq \left\lceil  \frac{\lvert \sigma \rvert }{k}  \right\rceil $$
Tehat a hanyados:
$$
\geq k
$$


### Jelolo algoritmusok
fazisokban mukodnek
a fazis elejen minden lap jeloletlen
az algoritmusok minden kerest meg fognak jelolni
ha az aktualis keres nincs benne a cache-ben es:
- van meg jeloletlen a cache-ben, akkor egy tetszoleges jeloletlent kidob es a helyere hozza be a kerest
- ha mar nincs jeloletlen a cache-ben, akkor az aktualis fazist befejezzuk es minden jelolest leveszunk es uj fazist kezdunk es az aktualis kerest ebbe a kovetkezo fazisba vegezzuk el

*Tetel 2:* Minden jelolo algoritmus $k$-versenykepes.
*Biz.:*
Tegyuk fel, hogy az $A$ algoritmus a $\sigma$ inputon $F$ fazist tesz.
Ekkor $\text{cost}_{A}(\sigma) \leq k \cdot F$

*All.:* $\text{cost}_{\text{OPT}}(\sigma) \geq F - 1$
Azt kell belatnunk, hogy az algoritmus minden fazis elso keresetol a kovetkezo fazis elso elemeig bezarolag legalabb $1$-t fizet.

TODO: megerteni


### k-robot feladat
Van $k$ darab robotunk
Legyen $X$ egy metrikus ter, ahol $\lvert X \rvert > k$
Minden robot mindig valamilyen $X$-beli ponton all
A keresek a metrikus ter pontjai
A keres kiszolgalasa az hogy valamelyik robotot odavisszuk
A keres kiszolgalasanak koltsege: $\rho(y, \sigma_{i})$

*Tetel:* Minden $A$ online algoritmusra:
$$
c_{A} \geq k
$$
ha $\lvert X \rvert > k$

*Tetel:* Ha $\lvert X \rvert = k + 1$, akkor letezik $k$-versenykepes algoritmus.
Algo: Mindig azt a robotot viszi oda, amelyiknek a legkisebb lenne az eddigi osszmozgasa miutan kiszolgalja a kerest.

*Tetel:* Ha $\lvert X \rvert \geq k + 1$, akkor letezik $(2k - 1)$-versenykepes algoritmus.









