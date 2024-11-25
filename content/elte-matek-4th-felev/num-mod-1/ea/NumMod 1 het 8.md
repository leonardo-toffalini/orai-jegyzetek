date: 2024.04.08

*Megj*.: $(x_{k}) \subset I$ mikor teljesül?
Négy eset amikor $x_{0}$-t jól megbálaszta, az egész $(x_{k})$ sorozat monoton módon tart $x^{*}$-hoz, es így $(x_{k})$ minden eleme $x_{0}$ és $x^{*}$ között lesz:
1. $f$ konkáv és szigorúan monoton nővő
vegyük fel $x_{0}$-t balra $x^{*}$-tól ($x_{0} < x^{*}$)
![[f konkáv és szig mon nő]]
2. $f$ konkáv és szigorúan monoton szökken
vegyük fel $x_{0}$-t jobbra $x^{*}$-tól ($x_{0} > x^{*}$)

3. $f$ konvex és szigorúan monoton nő
vegyük fel $x_{0}$-t jobbra $x^{*}$-tól ($x_{0} > x^{*}$)

4. $f$ konves és szigorúan monoton csökken
vegyük fel $x_{0}$-t balra $x^{*}$-tól ($x_{0} < x^{*}$)

### Egyenletrendszerek megoldása
**Feladat**: $f: \mathbb{R}^{m} \to \mathbb{R}^{m}$ és $f(x) = 0$
1. Egyszerű iterációt alkalmazzuk
$$
f(x) = 0 \implies F(x) = x
$$

Fixpont-iterációt alkalmazzuk:
$$
x_{t+1} = F(x_{t})
$$
ahol $x_{0}$ valamilyen kezdővektor.

2. Newton-módszer
Skaláris esetben: $x_{t+1} = x_{k} - \frac{f(x_{k})}{f'(x_{k})}$
Ennek analógiájára felírható a következő:
$$
x_{t+1} = x_{t} - J_{f}^{-1}(x_{t}) \cdot f(x_{t})
$$
Megfelelő feltételek esetén másodrendben konvergál.
Az invertálás miatt nagyon költséges.
Lehet ezt a költséget csökkenteni, ha nem minden lépésben számoljuk újra a Jacobi-mátrix inverzét. Szokás például azt használni, hogy minden lépésben az $x_{0}$-beli Jacobi-mátrix inverzét használjuk. Ilyenkor csak elsőrendű konvergencia áll fent! Vagy lehet minen $k$ lépésenként újraszámolni a Jacobi-mátrix inverzét.


## Interpolációs feladatok
### 1. Alapprobléma
Adott $f:\mathbb{R} \to \mathbb{R}$ függvényt csak diszrkét pontokban ismerjük. Például csak diszrkét pontokban vannak méréseink egy adatról.
![[interpolációs alapfeladat]]
$x_{0}, x_{1}, \dots, x_{n}$ - interpolációs alappontok, ($x_{0} < x_{1} < \dots < x_{n}$)
$f_{k} = f(x_{k}), \quad k = 0, \dots, n$ - interpolált értékek

Cél: olyan folytonos függvényt keresünk, amely átmegy az összes ponton.
(Megj.: Azért keresünk folytonos függvényt, mert a legtöbb analízisbeli tétel és állítás folytonos függvényekre szól.)

***Q***.: Milyen típusú függvényt illeszünk?
Különösen kedvező tulajdonságúak a polinomok, tehát illesszünk polinomot.

***Q***.: Hanyadfokú polinomot illesszünk?
Legfeljebb $n$-ed fokú polinomot illesszünk.

*Jel*.: $P_{n}$ jelöli a legfeljebb $n$-ed fokú polinomok halmazát.

$n := 1$
$\exists! p \in P_{1}$ melyre $p(x_{0}) = f_{0}$ és $p(x_{1}) = f_{1}$

$n := 2$
$\exists p \in P_{2}$ melyre $p(x_{0}) = f_{0}$ és $p(x_{1}) = f_{1}$ és $p(x_{2}) = f_{2}$


#### Tétel
$\exists ! p \in P_{n}$ melyre $p(x_{k}) = f_{k} \quad \forall k = 0, 1, \dots, n$

*Bizonyítás*:
1. Létezés (konstruktívan)
Keressünk először olyan $l_{m} \in P_{n}$  függvényt, amelyre
$$
l_{m}(x_{k}) = \begin{cases}
1, \text{ ha } k = m \\
0, \text{ ha } k \neq m
\end{cases}
$$

Mivel $x_{m}$-en kívül az alappontokban el kell tűnnie, tartalmaznia kell az $(x - x_{k}), \quad k \neq m$  gyöktényezőket, vagyi sa következő alakúnak kell lennie $l_{m}(x)$-nek
$$
l_{m}(x) = c_{m} \cdot (x - x_{0})(x - x_{1})\cdot \; \dots \; \cdot (x - x_{n}) \cdot \frac{1}{x - x_{m}} = c_{m} \cdot \prod_{\stackrel{k=0}{k\neq  m}}^{n}(x - x_{k})
$$

Már csak tudnunk kéne, hogy $c_{m}$ micsoda.
$l_{m}(x_{m}) = 1$ tehát legyen
$$
c_{m} \cdot \prod_{\stackrel{k = 0}{k \neq m}}^{n}(x_{m} - x_{k}) = 1 \implies c_{m} = \frac{1}{\prod_{\stackrel{k = 0}{k \neq m}}^{n}(x_{m} - x_{k})}
$$
$$
\implies l_{m} (x) = \frac{1}{\prod_{\stackrel{k = 0}{k \neq m}}^{n}(x_{m} - x_{k})} \cdot \prod_{\stackrel{k = 0}{k \neq m}}^{n}(x - x_{k})
$$
$$
l_{m}(x) = \prod_{\stackrel{k = 0}{k \neq m}}^{n} \frac{x - x_{k}}{x_{m} - x_{k}}
$$



Mindegyik $x_{m}$ alapponthoz tartozik egy ilyen $l_{m}$ függvény.
Ezekből készítsük el a következő $p$ függvényt:
$$
p(x) := \sum_{m = 0}^{n}f_{m} \cdot l_{m}(x)
$$
Ellenőrízzük, hogy ezen $p$ függvény tényleg az amit kerestünk:
$$
p(x_{k}) = \sum_{m = 0}^{n}f_{m} \cdot l_{m}(x_{k}) = f_{k} \cdot l_{k}(x_{k}) = f_{k} \cdot 1 = f_{k}
$$

Kell még, hogy $p \in P_{n}$
Ez igaz, mert $l_{m} \in P_{n}$ és $P_n$ vektortér, tehát a lineáris kombinációjuk is eleme $P_{n}$-nek

2. Egyértelműség
Tegyük fel, hogy $p$ és $q$ függvények is teljesítik a kívánt tulajdonságokat, azaz:
- $p, q \in P_{n}$
- $p(x_{k}) = f_{k} = q(x_{k}), \quad k = 0, \dots, n$

Legyen $d := p - q$
Ekkor $d \in P_{n}$ és $d(x_{k}) = 0 \quad \forall k = 1, \dots, n$ 
Így $d$ egy legfeljebb $n$-ed fokú polinom, melynek van $n+1$ darab különböző zéruzhelye, tehát $d \equiv 0$. Mert egy legfeljebb $n$-edfokú polinomnak legfeljebb $n$ zérushelye lehet, kivéve ha az azonosan a $0$ függvény.


*Elnevezések*:
- $l_{m}$ függvényeket *Lagrange-féle interpolációs alappolinomok*-nak nevezzük
- $p$ függvényt *interpolációs polinomnak*  nevezzük
- $\sum f_{m} \cdot l_{m}$ alakot az interpolációs polinomnak a *Lagrange-féle alak*-jának nevezzük

*Hátrány*: Ha új adatpont ékezik, akkor az összes eddigi munkánk megy a kukába és újra kell kezdeni az interpolációt.

Kiküszöblése ennek a hátránynak megoldható Newton-féle alakkal.

### 2. 
Tegyük fel, hogy egy $f: I \to \mathbb{R}$ folytonos függvényt az egész $I$ intervallumon ismerjük.
Szeretnénk polinommal közelíteni ezt a függvényt, hogy könnyebben tudjunk vele számolni.

*Ötlet*: Vegyünk fel adatpontokat ezen a függvényen és illesszünk interpolációs polinomot a felvett adatpontokra.

***Q***.: Mennyire halad közel az interpolációs polinom az eredeti függvényhez?

#### Tétel
Legyen $f \in C^{n+1}(I)$, és $x_{0}, x_{1}, \dots, x_{n} \in I$ alappontok, $p$ pedig az $(x_{k}, f(x_{k}))$ pontokon átmenő interpolációs polinom.
Ekkor az $x \in I$ pontot és az összes $x_{k}$ alappontot tartalmazó legszűkebb intervallumban van olyan $\xi$ pont, amelyre
$$
f(x) - p(x) = \frac{1}{(n+1)!}\omega_{n}(x) \cdot f^{(n +1)}(\xi)
$$
ahol $\omega_{n}(x) = \prod(x - x_{k})$ az úgynevezett *alappont polinom*.

*Bizonyítás*:
- Ha $x = x_{k}$ (valamelyik alappontra).
Akkor mindkét oldalon $0$ van és bármilyen $\xi$-re fenn áll az egyenlőség

- Ha $x \neq x_{k}$ (bármelyik alappontra).
Tekintsük a következő segédfüggvényt:
$$
g(t) = f(t) - p(t) - c \cdot \omega_{n}(t)
$$
ahol $c$ egy tetszőleges állandó.

$$
g(x_{k}) = f(x_{k}) - p(x_{k}) - c \cdot \omega_{n}(x_{k}) = 0 \quad \forall k = 0, 1, \dots, n
$$

Válasszuk meg a $c$ konstanst úgy, hogy $g(x) = 0$ legyen.
$$
g(x) = f(x) - p(x) - c \cdot \omega_{n}(x) = 0
$$
$$
\implies c = \frac{f(x) - p(x)}{\omega_{n}(x)}
$$
Ezen $c$ mellett $g$-nek van legalább $n+2$ zérushelye ($x_{0}, x_{1}, \dots, x_{n}$ és $x$)

Rolle-tétel emék:
$f \in C[a, b] \cap D(a, b) \quad f(a) = f(b)$ ekkor $\exists c \in (a, b)$ melyre $f'(c) = 0$

Rolle-tétel értelmében $g'$-nek van legalább $n+2 - 1 = n + 1$ darab zérushelye.
Hasonló módan $g^{(n + 1)}$-nek van legalább $n + 1 - n = 1$ darab zérushelye.
Jelölje az egyik ilyen zérushelyet $\xi$

Deriváljuk $g(t)$ függvényt $(n+1)$-szer:
$$
g^{(n+1)}(t) = f^{(n+1)}(t) - p^{(n+1)}(t) - c \cdot (n + 1)! = f^{(n+1)}(t) - 0 - c \cdot (n + 1)! = f^{(n+1)}(t) - c \cdot (n + 1)!
$$
$t= \xi$ pontban:
$$
0 = f^{(n+1)}(\xi) - \frac{f(x) - p(x)}{\omega_{n}(x)} \cdot (n+1)!
$$
$$
\implies f^{(n+1)}(\xi) = \frac{f(x) - p(x)}{\omega_{n}(x)} \cdot (n+1)!
$$







related: [[NumMod 1]]