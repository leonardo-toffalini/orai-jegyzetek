## I. Függvényminimalizálás lokális Taylor-közelítéssel
**Emlék:**

Egy $f: V \to \mathbb{R}$ kétszer folytonosan differenciálható funkcionál adott rendű lokális közelítése egy $x$ pontban:
* nulladrend: $f(x)$,
* elsőrend: $f(x) + \langle f'(x), y-x \rangle$,
* másodrend: $f(x) +  \langle f'(x), y-x \rangle +  \frac12 \langle f''(x)(y-x), y-x \rangle$.

Itt $f(x) \in \mathbb{R}$, $f'(x) \in V^*$, $f''(x) \in L(V, V^*) \cong V^* \otimes V^*$, továbbá $f''(x)$ szimmetrikus.

### 1. Feladat
Tegyük fel, hogy értelmes a függvényt lokálisan elsőrendben közelíteni. Tegyük fel, hogy szeretnénk egy lépést tenni egy $x$ pontból kiindulva, úgy, hogy ezáltal a függvény értékét minél jobban csökkentsük. Mutassuk meg, hogy a modell szerint ehhez $-f'(x)$ irányba érdemes lépnünk, amennyiben ez nem nullvektor. Mi a modell szerinti ideális lépéshossz?

***Megoldás:***


### 2. Feladat
Tegyük fel, hogy értelmes a függvényt lokálisan másodrendben közelíteni. Tegyük fel, hogy szeretnénk egy lépést tenni egy pontból kiindulva, úgy, hogy ezáltal a függvény értékét minél jobban csökkentsük. Mutassuk meg, hogy a modell szerint, amennyiben $f''(x)$ pozitív (szemi)definit, akkor ehhez egy $d$ irányba érdemes lépnünk, mely megoldása az
$$
f''(x)(d) = - f'(x)
$$
egyenletnek. Mi a modell szerinti ideális lépéshossz?

***Megoldás:***


## II. A Newton-iteráció hagyományos motivációja
Keressük azt az $r$ pontot, melyben egy $f: V \to V$ folytonosan differenciálható függvénynek gyöke van.
Tegyük fel, hogy egy $x$ pontból indulunk ki, és egy lépést szeretnénk tenni a gyökhely felé.

Ekkor
$$
 f(x) - f(r)  = M(x, r) \cdot(x - r).
$$
### 3.* Feladat

Mutassuk meg, hogy a fenti kontextus mellett 

a) 

$$
M(x, r) = \int\limits_0^1 f'\left(tx + (1-t)r\right) \, dt;
$$

továbbá, 

b) amennyiben az $x$ pontból $x+d$ pontba lépünk, akkor az ideális $d = r - x$ vektorra

$$
M(x, r) d = - f(x).
$$


***Megoldás:***


### Newton-iteráció

Amennyiben az $M(x, r)$ kifejezést az $f'(x)$ értékkel közelítjük, akkor megkapjuk a Newton-iterációt, melynek egy lépésének képlete $x \gets x + d$, ahol
$$
    f'(x)d = -f(x).
$$

Minderre tehát úgy is gondolhatunk, hogy egy nemlineáris egyenletrendszer megoldását végessok lineáris egyenletrendszer egymásutáni megoldásával közelítjük meg.

### 4. Feladat

Legyen $f: V \to V$ egy affin függvény, azaz legyen $f(x) = Ax + b$. 

a) Mi lesz az $M(x, r)$ kifejezés?

b) Tegyük fel, hogy $A$ invertálható is. Hány lépés alatt fog célbaérni a Newton-iteráció?

***Megoldás:***


### 5.* Feladat

**Affin-invarianca:** Legyen $\varphi(x) = Ax + b$, és legyen ez invertálható. Az $f$ függvényre alkalmazott Newton-lépést leíró függvényt jelölje $n(f)$, azaz $n(f)(x)$ legyen az $x$ pontból induló Newton-lépés eredménye (korábbról $x+d$), az $f$ függvény esetén. Ekkor mutassuk meg, hogy 

a) teljesül, hogy $$\varphi^{-1}(x) = A^{-1}(x - b); $$

b) a Newton-lépés affin-invariáns a következő értelemben:
$$
\varphi \circ n(f\circ \varphi) = n(f)  \circ \varphi.
$$

c) Oldjuk meg az előző feladat b) részét ezen feladat segítségével, azaz mutassuk meg, hogy
$$n(\varphi) = x \mapsto \varphi^{-1}(0).$$


***Megoldás:***


## III. A Newton-iteráció mint fixpontiteráció

Hogyan készíthetünk az $f(x) = 0$ egyenletből fixpontiterációt?

A lineáris egyenletrendszereknél láthattuk, hogy az $Ax = b$ egyenlrendszert eltranszformáltuk például
$$
\omega^{-1} Ax = \omega^{-1} b,\quad \text{vagy} \quad (I+D^{-1}(L+U))x = Đ^{-1} b
$$
módon. Ez iterációs lépésenként extra műveletek elvégzését jelenti, azonban az eredeti egyenlet megoldásához képest ezek gyorsan végrehajthatók.

Ennek ellenére $\omega$ és $D$ igyekeztek megragadni az eredeti mátrix "lényegét": SZPD esetben a spektrum középpontja lett az optimális $\omega$; $D$ pedig a mátrix főátlójából képezett diagonális mátrix volt.

Nemlineáris esetben, amennyiben a függvényünk szép (pl. folytonosan differenciálható), akkor a függvény "lényegét" egy pontban a függvény deriváltja ragadhatja meg, így motiválható a következő átalakítás:

$$
\begin{align*}
     f(x) &= 0, \\
     -[f'(x)]^{-1} f(x) &= 0, \\
     x - [f'(x)]^{-1} f(x) &= x.
\end{align*}
$$
## IV. Lokális kvadratikus konvergencia

Legyen $f: V \to V$ folytonosan differenciálható függvény, melynek gyöke van az $x^*$ pontban, továbbá tegyük fel, hogy léteznek $m, M$ pozitív konstansok, melyekkel tetszőleges $x$ pontra az $x^*$ egy gömbi környezetéből
$$ m \|h\| \leq \| f'(x) h \| \leq M\| h \| \quad \forall h \in V.$$


### 6. Feladat
Legyen a norma a $\| \cdot \|_2$. Teljesülhet-e a fenti feltétel a $0$ körüli zárt egységgömbön, ha

a)  $f(x,y) = [2x - y, -x + 2y]$;

b) $f(x,y) = [2x^3 + x, y^3 +y]$;

és ha igen, akkor milyen $M,m$ értékekkel?

***Megoldás:***


A feltétel mellett tehát amennyiben $d$ a Newton-lépésbeli eltolásvektor, akkor

$$
\begin{align*}
f'(x) \cdot (x+d - x^*) 
&= f'(x) \cdot (x - x^*) - f(x) \\
&= f'(x) \cdot (x - x^*) - \left( f(x) - f(x^*) \right) \\
&= f'(x) \cdot (x - x^*) -  \int\limits_0^1 f'(tx + (1-t)x^*) \cdot (x - x^*) \, dt \\
&= \int\limits_0^1 \left( f'(x) - f'(tx + (1-t)x^*\right) \cdot (x - x^*) \, dt
\end{align*}
$$

amiből mindkét oldalon normákat véve és kihasználva az $f'$-re vonatkozó feltételeket (a baloldalt alulról, a jobboldalt pedig felülről becsülve) kapjuk, hogy 
$$
m \|x+d - x^*\| \leq  \left|\int\limits_0^1 1-t \, dt \right| M \|x -x^*\|^2,
$$

azaz egy Newton-lépés végeztével az $x^*$-tól való távolság felülről becsülhető a lépés előtti távolság négyzetének konstansszorosával.

**Emlék:** Ha $x^*$ egy $f$ kontrakció fixpontja, akkor egy lépés során általában csak lineáris becslést kapunk:
$$
\| f(x) - x^* \| = \| f(x) - f(x^*) \| \leq L \| x - x^* \|.
$$

### 7. Feladat

Vizsgáljuk meg, hogy az alábbi $x^*$-hoz tartó $(x_n)_n$ valós számsorozatok esetén melyekre teljesül,

* egy lineáris becslés $\| x_{n+1} - x^* \| \leq L \| x_n - x^* \|,$ ahol $0 < L < 1$;

* egy kvadratikus becslés, azaz $\| x_{n+1} - x^* \| \leq q \| x_n - x^* \|^2$, ahol $0 < q$

a) $2^{-n}$

b) $2^{-n^2}$

c) $2^{-2^{n}}$


***Megoldás:***


### 8.* Feladat

Gondoljuk meg, hogy amennyiben egy $\phi: V \to \mathbb{R}$ funkcionál kétszer folytonosan differenciálható, és egy $x^*$ pont körüli gömbi környezetben valamilyen $0 < m \leq M$ konstansokkal,

$$ m h^Th \leq h^T \phi''(x) h \leq M h^Th \quad \forall h \in V,$$

teljesül, valamint $\phi'(x^*) = 0$, akkor a Newton-iterációt a $\phi'$ függvényre alkalmazhatjuk, és a konvergencia lokálisan kvadratikus lesz.

Ekkor egyébként a $\phi$ függvény lokális minimumhelye $x^*$, akörül egyenletesen konvex, és valójában a Newton-iterációval ezt minimalizáljuk.

***Megoldás:***


### 9. Feladat

Teljesülnek ezek a feltételek az $f(x, y) = \sin^2(x) + \sin^2(y)$ függvényre a $0$ körül?

***Megoldás:***


### P/1. Feladat
Gondoljuk meg, hogy az $x_0 = 2^{255}$ pontból indulva az

a) $x_02^{-n}$

b) $x_02^{-n^2}$

c) $x_02^{-2^{n}}$

sorozatok hány lépés alatt érnek be a $0$ pont $\frac12$ sugarú, zárt gömbi környezetébe, majd írjunk programot és mérjük is meg, hogy valóban jól gondolkodtunk.

***Megoldás:***
```python
```

### P/2. Feladat

Alkalmazzuk a Newton-iterációt az $f(x, y) = \sin^2(x) + \sin^2(y)$ függvény $0$-hoz legközelebb eső minimumhelyének meghatározására, ha tudjuk, hogy az a nulla körül konvex, az alábbiak szerint:

a) Számoljuk ki $f$ deriváltját.
 
b) Az $(\frac14, \frac14)$ pontból indítsunk Newton-iterációt az $f'$ (egy) gyökének meghatározására.

***Megoldás:***
```python
```

### P/3. Feladat

Tekinsük az alábbi egyenletrendszert:
$$
\begin{cases}
5 x^2 - y^2 &= 0,\\
y - 0.25(\sin x +\cos y) &= 0.
\end{cases}
$$

Newton-iteráció segítségével keressük ennek a $(\frac12, \frac12)$ pont környezetében lévő megoldását!

***Megoldás:***
```python
```


related: [[NumMod 1]]