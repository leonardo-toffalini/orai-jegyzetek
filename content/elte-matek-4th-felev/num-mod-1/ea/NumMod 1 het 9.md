date: 2024.04.15

### Hermite-interpoláció
Eddig az $x_{0}, \dots, x_{n}$ pontokban csak a függvény értéket írtuk elő.
Lehetséges általánosítása ennek a feladatnak, ha nem csak a függvény értékeket írjuk elő, hanem a pontbeli deriváltakat is.
A legegyszerűbb formája ennek a feladatnak, amikor csak minden pontban az első deriváltat írjuk elő, de lehet ezt általánosabban is. Előírhatjuk minden pontban a magasabbrendű deriváltakat is, de ilyenkor elő kell írnunk a legmagasabb deriváltig bezárólag az összes többit. Továbbá, nem feltétlenül kell minden pontban megadni az összes deriváltat.
Tegyük fel, hogy az $x_{k}$ alappontban az $m_{k}$-adikig írjuk elő az összes deriváltat, azaz adottak $f_{k}, f_{k}^{(1)}, \dots, f_{k}^{(m_{k})}$
Összesen $N = n + 1 + m_{0} + m_{1} + \dots + m_{k}$ feltétel van.
Ezek alapján azt várjuk, hogy $N - 1$-ed fokú polinom egyértelműen illeszthető a pontokra.
Ez így is van!
#### Állítás
$\exists! H \in P_{N - 1}$ amelyre $\forall k = 0, \dots, n$ $\forall i = 0, \dots, m_{k}$ számokra $H^{i}(x_{k}) = f_{k}^{(i)}$

Ezt a polinomot Hermite-féle interpolációs polinomnak nevezzük.
Speciálisan, ha $m_{k} = 1$ minden $k$-ra, akkor úgy nevezik, hogy Hermite-Fejér-interpoláció. Ekkor az interpolált polinom fokszáma: $N = 2n + 2 - 1 = 2n + 1$

### Spline-interpoláció
Eddig a pontokra egyetlen polinomot illesztettünk.
Hátránya ennek a megközelítésnek az, hogy ha sok pont van, akkor az illesztett polinom magas fokszámú lesz. Ekkor a deriváltja is magas fokszámú és ennek a szintén magas fokszámú polinomnak sok zérushelye van, ami azt mondja az eredeti polinomról, hogy sok helyen vízszintes a deriváltja. Tehát nagyon hullámos lesz az illesztett polinom sok pont esetén.

Egy megoldás erre a problémára lehet az, hogy ne egy polinomot próbáljunk illesztetni az összes pontra, hanem szakaszonként más-más polinomot illesszünk és ezeket az alacsony fokszámú polinomokat ragasszuk össze. Ebből az ötletből jön a Spline-interpoláció.

Legegyszerűbb, amikor szakaszonként lineáris-interpolációt alkalmazunk és így kapunk egy töröttvonalat, ami összeköti az adatpontjainkat.

#### 1. Lineáris spline-interpoláció
Az $[x_{k-1}, x_{k}]$ szakaszon
$$
s_{k}(x) = f_{k-1} \cdot \frac{x - x_{k}}{x_{k-1} - x_{k}} + f_{k} \cdot \frac{x - x_{k-1}}{x_{k} - x_{k-1}}
$$
a fenti képlet adja meg, hogy milyen értékeket fog felvenni a spline függvény az $x \in [x_{k-1}, x_{k}]$ pontokban.

A teljes spline-függvény viszont a következőképpen néz ki:
$$
s(x) = \begin{cases}
s_{1}(x) & x \in [x_{0}, x_{1}] \\
s_{2}(x) & x \in [x_{1}, x_{2}] \\
\vdots \\
s_{n}(x) & x \in [x_{n-1}, x_{n}]
\end{cases}
$$
Nyílvánvalóan az $s$ spline-függvény folytonos az $[x_{0}, x_{_{n}}]$ intervallumon, viszont az alappontokban csúcsos, tehát nem differenciálható ezekben a pontokban.

Kiküszöbölése a nemdifferenciálhatóságnak az, hogy magasabbfokú interplolációkat használunk szakaszonként.

#### 2. Kvadratikus spline-interpoláció
Az $[x_{k-1}, x_{k}]$ szakaszon $s_{k} \in P_{2}$ legyen.
Ahhoz, hogy másodfokú polinomot illesszünk szakaszonként elő kell írnunk a függvényértékeken túl a pontbeli deriváltakat is ($s'(x_{0}) = d_{0}$)
1. Alkalmazzunk Hermite-interpolációt az $[x_{0}, x_{1}]$ szakaszon:
$$
\begin{align}
s_{1} \in P_{1}: \quad & s_{1}(x_{0}) = f_{0} \\
 & s_{1}'(x_{0}) = d_{0} \\
& s_{1}(x_{1}) = f_{1} \\
\end{align}
$$
2. Hermite-interpoláció az $[x_{1}, x_{2}]$ intervallumon:
$$
\begin{align}
s_{2} \in P_{2}: \quad & s_{2}(x_{1}) = f_{1} \\
& s_{2}(x_{2}) = f_{2} \\
& s_{2}'(x_{1}) := s_{1}'(x_{1})
\end{align}
$$
3. Hasonlóképpen folytatjuk a további $[x_{k-1}, x_{k}]$ intervallumokon.

Ezzel a módszerrel $s$ folytonosan differenciálható lesz.

*Megjegyzés:* Létezik trigonometrikus-interpoláció is.
Tegyük fel, hogy $f$ periodikus függvény $2\pi$ intervallum hosszal, és a következő pontokbab ismerjük a függvény értékeket a $[0, 2\pi]$  intervallumnak az összes $x_{k} = \frac{k}{n+1} \cdot 2\pi$ pontjában.

Keressük azt a 
$$
t_{m}(x) = a_{0} + \sum_{j=1}^{m} a_{k} \cdot \cos(j x) + b_{k} \cdot \sin(j x)
$$
trigonometrikus polinomot, amelyre az igaz, hogy $t_{m}(x_{k}) = f_{k}$ minden $k$-ra.
$a_{0}, a_{k}, b_{k}$ együtthatókat diszkrét Fourier-együtthatóknak nevezzük.

### Legkisebb négyzetek módszere
Felmerülhet az a baj, ha sok pont egy kupacban van és nagyjából egy alakban és pontosan szeretnénk ezekre egy polinomot illesztetni, akkor feleslegesen magasfokú lesz az illesztett polinom és nem is fogja megragadni a pontok alakjának a lényegét.
Ennek orvosolására próbáljuk meg nem pontosan illeszteni polinomot a pontokra, hanem csak legyen az a célunk, hogy minden ponthoz a legközelebb haladjonaz illesztett polinomunk.

Legyenek adva az $(x_{k}, f_{k})$  pontok.
Olyan $P$ polinomot keresünk, amelyre:
1. Adott fokszámú (ezt mi döntjük el).
2. Globálisan az összes ponthoz a legközelebb halad.

Figyelem, ezt nem nevezzük interpolációnak, mert nem megy át minden alapponton az illesztett polinom!

***Q.:*** Hogyan mérjük a költséget?

Lehetne azt csinálni, hogy a költség a következő: $\sum \lvert f_{k} - P(x_{k}) \rvert$ 
Ezzel az lesz a probléma, hogy nem deriválható, továbbá szeretnénk azt is, hogy nagy eltérés nagy hibát jelezzen.

Helyette legyen a költség függvényünk a következő: $\sum (f_{k} - P(x_{k}))^{2}$

Tegyük fel, hogy $p \in P_{1}$ polinomot akarunk illeszteni, tehát $p(x) = c_{0} + c_{1}x$ alakú függvényt szeretnénk illeszteni.
Hogyan kell megválasztani $c_{0}$ és $c_{2}$ együtthatókat, hogy a következő kifejezés minimális legyen:
$$
\sum_{k=0}^{n} (f_{k} - c_{0} - c_{1}x_{k})^{2}
$$
Itt az $x_{k}, f_{k}$ adottak, és a $(c_{0}, c_{1})$ számoktól függő
$$
F(c_{0}, c_{1}) := \sum_{k=0}^{n} (f_{k} - c_{0} - c_{1}x_{k})^{2}
$$
$\mathbb{R}^{2} \to \mathbb{R}$ függvény minimum helyét keressük.
Nézzük meg, hogy hol nulla a gradiens vektora.
$$
\frac{\partial F}{\partial c_{0}} = \sum_{k=0}^{n} 2 (f_{k} - c_{0} - c_{1} x_{k}) \cdot (-1) = 0
$$
$$
\frac{\partial F}{\partial c_{1}} = \sum_{k=0}^{n}2(f_{k} - c_{0} - c_{1} x_{k}) \cdot (-x_{k}) = 0
$$
A következő egyenletrendszerre jutunk:
$$
\begin{align}
\sum_{k=0}^{n}(f_{k} - c_{0} - c_{1} x_{k}) & = 0 \\
\sum_{k=0}^{n} (f_{k}x_{k} - c_{0}x_{k} - c_{1} x_{k}^{2}) & = 0
\end{align}
$$
Ez egy lineáris algebrai egyenletrendszer $(c_{0}, c_{1})$-re.
Mátrix alakban:
$$
\begin{bmatrix}
n + 1 & \sum x_{k} \\
\sum x_{k} & \sum x_{k}^{2}
\end{bmatrix} \cdot 
\begin{bmatrix}
c_{0} \\
c_{1}
\end{bmatrix} = 
\begin{bmatrix}
\sum f_{k} \\
\sum f_{k} x_{k}
\end{bmatrix}
$$
Ezt az alakot már könnyen meg lehet oldani számítógéppel és kapunk egy-egy értéket $c_{0}$ és $c_{1}$-re, amiből megkapjuk a $p = c_{0} + c_{1}x$ illesztett polinomot.
*Megjegyzés:* Ha $n \geq 1$, akkor egyértelműen létezik megoldás és ez tényleg minimum hely lesz.
*Megjegyzés:* Ha $N$-ed fokú polinomot szeretnénk illeszteni, akkor $(N + 1)$ ismeretlenes lineáris algebrai egyenletrendszert kapunk, aminek a megoldása megadja az illesztett polinom együtthatóit.

### Közelítő integrálás
Feladat: Adott egy $f \in R[a, b]$ függvény, melynek szeretnénk az integrálját meghatározni, azaz $\int _{a}^{b}f = \;?$
Tudjuk, ha $f$-nek létezik $F$ primitív függvénye, akkor $\int _{a}^{b}f = F(b) - F(a)$

Gyakran $F$-et nem tudjuk meghatározni, ekkor felmerül a megoldás, hogy hogyan tudjuk közelítőleg integrálni a függvényt.

Ötlet: $\int _{a}^{b}f$ geometriai jelentése a görbe alatti előjeles terület.

Közelítsük a görbe alatti területet egyszerűbb alakzat területével. Ebből az ötleből kapjuk az alapvető kvadratúraformulákat.
Vezessük be az intervallum hosszára  következő változót: $h = b - a$

1. Középponti formula
$c := \frac{a + b}{2}$ pontban megnézzük a függvényértéket.
$k(f) := h \cdot f(c)$ 

2. Trapéz formula
Megnézzük a $(a, b, f(b), f(a))$ pontok által meghatározott trapéz területét.
$t(f) := h \cdot \frac{f(a) + f(b)}{2}$ 




related: [[NumMod 1]]