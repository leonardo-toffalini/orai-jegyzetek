date: 2024.04.22

***Q.:*** Hogyan tudjuk jellemezni, hogy egy közelítő integrál formula mennyire jó?

Egy szempont: Mennyire jól viselkedik polinomokon.

#### Definíció
Azt mondjuk, hogy a kvadratúra formula rendje $n$, ha a formula pontos $\forall f \in P_{n-1}$ polinomra, de létezik olyan $n$-ed rendű polinom amire már nem pontos.

például:
$t(f)$ azaz, a trapéz formula másodrendű
$k(f)$ azaz, a középponti formula is másodrendű

***Q.:*** Hogyan kaphatunk magasabbrendű kvadratúra formulákat?

Alkalmazzuk a $k(f)$ és a $t(f)$ formulákat az $f(x) = x^{2}$ függvényre a $[0, 1]$ intervallumon!

pontos érték: $T = \int _{0}^{1}x^{2} \, dx = \frac{1}{3}$ 
$k(f) = h \cdot f(c) = 1 \cdot \left( \frac{1}{2} \right)^{2} = \frac{1}{4}$ 
$t(f) = h \cdot \frac{f(0) + f(1)}{2} = 1 \cdot \frac{0^{2} + 1^{2}}{2} = \frac{1}{2}$

Hibák:
- $T - k(f) = \frac{1}{3} - \frac{1}{4} = \frac{1}{12}$
- $T - t(f) = \frac{1}{3} - \frac{1}{2} = -\frac{1}{6}$

Észrevehető, hogy a trapéz formula hibája $-2$ -szerese a középponti formula hibájának. Azaz, $T - t(f) = -2 \cdot (T - k(f))$
Kifejezve $T$ értékét:
$$
T = \frac{2k(f) + t(f)}{3}
$$
Az így kapott formula az $f(x) = x^{2}$ függvényre a $[0, 1]$ intervallumon pontos. 
Elnevezés: *Simpson formula* (vagy *parabola formula*):
$$
s(f) = \frac{2}{3}k(f) + \frac{1}{3}t(f) = \frac{2}{3}h \cdot f(c) + \frac{1}{3} \cdot \frac{h}{2}(f(a) + f(b)) = \frac{h}{6} \cdot (f(a) + 4f(c) + f(b))
$$
Figyelem: A rendjét a Simpson formulának még nem tudjuk, csak azért mert egy specifikus másodfokú polinomra pontos egy specifikus intervalliumon.

### Interpolációs típusú kvadratúra formulák

Ötlet: Legyen $f:[a, b] \to \mathbb{R}$ és $x_{0}, x_{1}, \dots, x_{n} \in [a, b]$ és $p$ legyen az $(x_{k}, f(x_{k}))$ pontokra illesztett interpolációs polinom. Ekkor $\int _{a}^{b}f(x) \, dx$ értékét közelítsük $\int _{a}^{b}p(x) \, dx$ értékkel.
$$
p(x) = \sum_{m = 0}^{n} f_{m} \cdot l_{m}(x)
$$
Tehát
$$
\int _{a}^{b}f(x) \, dx \approx \int _{a}^{b}p(x) \, dx = \int _{a}^{b}\sum_{m=0}^{n}f_{m} \cdot l_{m}(x) \, dx 
$$
Azt keressük, hogy az így közelített érték mennyire tér el a pontos értéktől, azaz $\int _{a}^{b}f(x) \, dx - \int _{a}^{b}p(x) \, dx = \; ?$
Alkalmazzuk az interpolációs polinom hibájáról szóló tételt.
Tegyük fel, hogy $f \in C^{n+1}[a, b]$ legyen $x \in [a, b]$  tetszőleges pont. Ekkor $\exists \xi \in (\min\{ x, x_{0} \}, \max\{ x, x_{n} \})$
$$
f(x) - p(x) = \frac{1}{(n + 1)!} \omega_{n}(x) \cdot f^{(n+1)}(\xi)
$$
De minket az intergálok külömbsége érdekel, tehát integráljunk mindkét oldalon!
$$
\int _{a}^{b} f(x) \, dx - \int  _{a}^{b}p(x) \, dx = \int _{a}^{b} \frac{1}{(n + 1)!} \omega_{n}(x) \cdot f^{(n+1)}(\xi)\, dx 
$$
Fontos: nem emelhetjük ki $f^{(n+1)}(\xi)$ számot a jobboldalon az integrandusból, mivel $\xi$ értéke függ $x$ értékétől.

Tekintsük az interpolációs kvadratúra formulát
$$
\int _{a}^{b}p(x) \, dx = \int _{a}^{b}\sum_{m=0}^{n}f_{m} \cdot l_{m}(x) \, dx = \sum_{m=0}^{n}\int _{a}^{b}f_{m} \cdot l_{m}(x) \, dx = \sum_{m=0}^{n} \left( \int _{a}^{b}l_{m}(x) \, dx  \right) \cdot f_{m}
$$

Az átalakítások után azt kapjuk, hogy az illesztett polinom integrálja az egy lineáris kombinációja az $f_{m}$ értékeknek.

#### Definíció
A $\sum_{m=0}^{n} A_{m} \cdot f_{m}$ alakú kvadratúra formulát, ahol $A_{m} \in \mathbb{R}$ *lineáris kvadratúra formulának* nevezzük.

Tehát az interpolációs kvadratúra formula is lineáris, ahol $A_{m} = \int _{a}^{b}l_{m}(x) \, dx, \quad m = 0, \dots, n$

Felmerülhet a kérdés, hogy tudunk-e jobb lineáris kvadratúra formulát kitalálni, mint az interpolációs kvadratúra formula.
#### Tétel
A $\sum_{m=0}^{n}A_{m} \cdot f_{m}$ lineáris kvadratúra formula akkor és csak akkor pontos $\forall f \in P_{n}$ polinomra, ha interpolációs típusú, azaz ha $A_{m} := \int _{a}^{b}l_{m}(x) \, dx, \quad m= 0, \dots, n$

*Bizonyítás:*
Kezdjünk a könnyebb iránnyal, azaz lássuk be azt, hogy az interpolációs kvadratúra formula pontos minden $n$-ed rendű polinomra.
Ez az állítás könnyen következik abból a tényből, hogy $\forall f \in P_{n}$ polinomnak az $n+1$ darab pontra támaszkodó interpolációs polinomja saját maga, tehát a formula pontos.

A nehezebb irány az, hogy ha a formula pontos minden $n$-ed rendű polinomra, akkor az a formula interpolációs típusú.
Tegyük fel, hogy $\sum_{m=0}^{n}A_{m} \cdot f_{m}$ pontos $\forall f \in P_{n}$ polinomra. Be kell látnunk, hogy $A_{j} = \int _{a}^{b}l_{j} \, dx, \quad j = 0, \dots, n$
Tudjuk, hogy $l_{j} \in P_{n}$ azaz a feltételünk szerint ezekre az $l_{j}$ polinomokra pontos a formula. Ekkor $l_{j}$ közelítő integrálja a következő:
$$
\sum_{m=0}^{n}A_{m} \cdot l_{j}(x_{m}) = \int _{a}^{b}l_{j}(x) \, dx 
$$
Mivel az $l_{j}$ polinomok úgy voltak definiálva, hogy $l_{j}(x_{i}) = \delta_{ij}$ azaz $l_{j}(x_{j}) = 1$ és $l_{j}(x_{i}) = 0$ ha $i \neq j$
Tehét a fenti egyenlet baloldalán a szumma majdnem minden tagja kiesik kivéve $l_{j}(x_{j})$ tehát a fenti egyenlet a következőre redukálódik:
$$
\begin{align*}
A_{j} \cdot l_{j}(x_{j}) & = \int _{a}^{b}l_{j}(x) \, dx \\
A_{j} \cdot 1 & = \int _{a}^{b}l_{j}(x) \, dx \\
A_{j} & = \int _{a}^{b}l_{j}(x) \, dx
\end{align*}
$$

#### Definíció
Az interpolációs kvadratúra formulát Newton-Cotes-formulának nevezzük, ha az alappontok egyenlő lépésközönként vannak felvéve.
Ezen belül zárt Newton-Cotes-formulának nevezik azt amikor $x_{0} = a$ és $x_{n} = b$ azaz az intervallum szélei is kontrolpontok.

Speciális esetek:
- $n := 1$
Ekkor csak úgy kaphatunk zárt Newton-Cotes-formulát, ha $x_{0} = a$ és $x_{1} = b$
Ekkor visszakapjuk a trapéz formulát. Azért jó, hogy mostmár tudjuk, hogy a trapéz formula valójában egy interpolációs típusú kvadratúra formula, mert ekkor már van formulánk a formula hibájára.

Most $n = 1$ és az alappontok $x_{0} = a$ és $x_{1} = b$ és $\int _{a}^{b}p(x) \, dx = t(f)$. Ha $f \in C^{2}[a, b]$ akkor
$$
\int _{a}^{b}f(x) \, dx - t(f) = \int_{a}^{b} \frac{1}{2!}(x - a)(x - b)\cdot f''(\xi(x)) \, dx 
$$
Mivel $\frac{1}{2!}(x- a)(x-b)$ Riemann integrálható és végig nem pozitív, és $f''(\xi(x))$ folytonos, ezért az integrál-középérték tétel értelmében $\exists \kappa \in [a, b]$:
$$
\int _{a}^{b}f(x) \, dx - t(f) = f''(\kappa) \cdot \int _{a}^{b} \frac{1}{2} (x - a)(x - b) \, dx = \dots = -\frac{h^{3}}{12} \cdot f''(\kappa)
$$
Ebből látszik, hogy $t(f)$ másodrendű formula, mert elsőrendű $f$ függvény második deriváltja $0$ lesz minden pontba, így a hiba is $0$. 

- $n := 2$
Ekkor az alappontok a következők: $x_{0} = a, \; x_{1} = c = \frac{a+b}{2}, \; x_{2} = b$
Számítsuk ki a $\sum_{m=0}^{2} A_{m} \cdot f_{m}$ formula $A_{0}, A_{1}, A_{2}$ együtthatóit.
$$
\begin{align*}
A_{0} & = \int _{a}^{b}l_{0}(x) \, dx  = \int _{a}^{b} \frac{(x- c) (x - b)}{(a - c)(a - b)} \, dx = \dots = \frac{h}{6} \\
A_{1} & = \int _{a}^{b}l_{1}(x) \, dx = \dots = \frac{2h}{3} \\
A_{2} & = \int _{a}^{b}l_{2}(x) \, dx = \dots = \frac{h}{6}
\end{align*}
$$

A tagokat összeadva:
$$
\sum_{m=0}^{2}A_{m} \cdot f_{m} = A_{0} \cdot f(x_{0}) + A_{1} \cdot f(x_{1}) + A_{2} \cdot f(x_{2}) = \frac{h}{6}(f(a) + 4f(c) + f(b))
$$
Így látszik, hogy ez valójában a Simpson-formula! (Innen következik a másik elnevezése a Simpson-formulának, parabola-formula)

Képlethibája:
Ha $f \in C^{4}[a, b]$, akkor $\exists\kappa \in [a, b]$ melyre:
$$
\int _{a}^{b}f(x) - s(f) \, dx = -\frac{h^{5}}{2880} \cdot f^{(4)}(\kappa)
$$
Innen már látszik, hogy a Simpson formula $4$-ed rendű, mert minden $3$ vagy kevesebb rendű polinomnak a negyedik deriváltja mindenhol $0$.

Probléma még mindig ezekkel a módszerekkel, hogy nem tudjuk tetszőleges pontossággal meghatározni a valós integrál értékét, akkor is ha bármelyik paraméterrel tartuk valahova.

### Összetett kvadratúra formulák
*Ötlet:* lkalmazzuk szakaszonként az előbbi formulákat.

1. **Összetett trapéz formula**
Osszuk fel $m$ darab egyenlő részre az $[a, b]$ intervallumot. Jelölje egy ilyen kis szakasz hosszát $\Delta h := \frac{b - a}{m} = \frac{h}{m}$
$$
\int _{a}^{b}f(x) \, dx \sum_{i = 1}^{m}\int _{x_{i} - 1}^{x_{i}} f(x) \, dx \approx \sum_{i=1}^{m} \frac{\Delta h}{2}(f(x_{i-1}) + f(x_{i})) =: t_{m}(f)
$$

Mit lehet ennek az összetett formulának a hibájáról?
Ha $f \in C^{2}[a, b]$ akkor
$$
\int _{a}^{b}f(x) \, dx - t_{m}(f) = \sum_{i=1}^{m} - \frac{(\Delta h)^{3}}{12} \cdot f''(\kappa_{i})
$$
ahol $\kappa_{i} \in [x_{i-1}, x_{i}]$ 
A fenti képletet kicsit átalakítva úgy, hogy $\Delta h = \frac{h}{m}$-et írunk
$$
= \sum_{i=1}^{m} - \frac{h^{3}}{12m^{2}} \cdot \frac{1}{m} \cdot f''(\kappa_{i}) = -\frac{h^{3}}{12m^{2}} \stackrel{S}{\overbrace{\left( \frac{1}{m} \sum_{i=1}^{m}f''(\kappa_{i}) \right)}} = -\frac{h^{3}}{12m^{2}}f''(\eta)
$$
$f''$ $m$ darab függvény értékének az átlaga és $S \in (\min f'', \max f'')$  és ezt felveszi egy $\eta \in [a, b]$ helyen.




related: [[NumMod 1]]