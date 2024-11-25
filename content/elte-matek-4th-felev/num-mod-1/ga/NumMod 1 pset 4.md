**Cél:** Az $f(x)=0$ egyenlet megoldása, ahol  adott, szép tulajdonságú (pl. folytonosan deriválható) függvény, azaz keressük az  függvény gyökeit/zérushelyeit. Ekvivalensen $g(x)=b$  megoldása az $f = g-b$ függvényre alkamazott gyökkereséssel.

## Intervallumfelezés
Tegyük fel, hogy tudjuk, hogy egy adott $[a,b]$ intervallumon a függvényünknek van egy gyöke; például ezt onnan tudhatjuk, hogy a végpontokban különböző előjelű a függvény, pontosabban: $f(a) \cdot f(b) < 0$. Tegyük fel, hogy ez fennáll és hogy $f(a) > 0, f(b)<0$. Ez utóbbi nem megszorítás, mert $f$ és  $-f$ gyökei ugyanott vannak.

**Alapgondolat**: Vizsgáljuk meg a függvény előjelét az $\frac{a+b}{2}$ pontban! Ha itt pozitív, az azt jelenti, hogy a keresett zérushely az $\left[a,\; \frac{a+b}{2}\right)$ intervallumban van, azaz itt érdemes folytatni a keresést. Ugyanakkor ha itt negatív, akkor a zérushely az $\left( \frac{a+b}{2},\; b\right]$ intervallumban található, és itt kell tovább keresnünk. Ezt követően az előbbi gondolatot folytatjuk az új, kisebb intervallumokon, azaz vagy az $\frac{a+b}{4}$, vagy a $\frac{3 (a+b)}{4}$ pontban vizsgáljuk a előjelet, és így tovább. 
Az algoritmus addig fut, amíg  értéke a vizsgált pontban nulla nem lesz (ez programok esetén a gépi hibák miatt ritkán következik be), vagy amikor a vizsgált intervallum már nagyon kicsi/rövid, de természetesen megadhatunk maximális lépésszámot is, amely után álljon le mindenképpen a program. Határértékben ez a módszer mindenképpen megtalál egy zérushelyet (ha több is van, akkor a zérushelyek közül valamelyiket).

### 1. Feladat
Fibonacci egyik cikkében szerepel az alábbi állítás: az

$$f(x) = x^3 + 2 x^2 + 10 x - 20$$

egyenlet gyöke $x = 1.368808107...$ Ellenőrizzük le az intervallumfelezéses módszerrel, hogy jól számolt-e!
Megoldás: Legyen a toleranciánk $10^{-10}$ és indítsuk az iterációt az $[1,2]$ intervallumon!

***Megoldás:***
*halving.py*
```python
def f(x):
	return x*x*x + 2*x*x + 10*x - 20

def halving(f, a, b, tolerance):
	assert f(a) * f(b) < 0
	if f(a) > 0:
		f = -f

	while a - b > tolerance:
		half = (a + b) / 2
		if f(half) < 0:
			a = half
		else:
			b = half

	return a, b

print(halving(f, 1, 2, 1e-10))
```

```console
$ python3 halving.py
> (1.3688081077998504, 1.368808107858058)
```



### Fixpont-iteráció

**Emlék:** A Banach-féle fixponttétel következtében ha $X$ Banach-tér és $f:X\rightarrow X$ kontrakció $0\leq q<1$ együtthatóval, akkor van $x^*$ fixpontja, amire $f(x^*) = x^*$; továbbá az $x_{n+1} = f(x_n)$ sorozat tetszőleges $X$-beli pontból indítva $x^*$-hoz fog tartani; továbbá $e_n = x_n - x^*$ választással látható, hogy

$$\|e_{n+1}\| = \| x_{n+1} - x^* \| =  \| f(x_{n}) - f(x^*) \| \leq q \|x_n - x^*\| = q \| e_n\|$$
és
$$\|e_n\| = \|  (f\circ \ldots \circ f)(x_0) - (f\circ \ldots \circ f)(x^*) \| \leq q^n\|x_0 - x^*\| = q^n\|e_0\|$$

**Emlék:** Legyen $X$ végesdimenziós valós vektortér, $U \subseteq X$ nyílt halmaz, $f: U \to X$ folytonosan differenciálható és legyen $x, h \in U$ olyan, hogy az $x+h\cdot[0,1] \subseteq U$, azaz az $x$-ből induló $x+h$ végű szakasz része $U$-nak; ekkor

$$f(x+h) - f(x) = \int_{0}^1 f'(x+th) \cdot h\, dt.$$

Ebből kapjuk a középérték-tétel magasabbdimenziós változatát:

$$\|f(x+h) - f(x)\| \leq \left(\sup_{0\leq t \leq 1}\|f'(x+th)\| \right) \|h\|.$$

Ha $K \subseteq U\subseteq X$ és $K$ kompakt, akkor

$$M = \sup_{K}\|f'\|$$

választással $x, y \in K$ esetén ha az $x$ és $y$ pontok által határolt szakasz $K$-ban van (pl. ha  konvex), akkor

$$\| f(x) - f(y) \| \leq M \|x -y\|.$$

Ha $f(K) \subseteq K$ (hívjuk ezt ráképezésnek) és $M<1$, akkor $f|_K:K \to K$ kontrakció. Mivel teljes tér zárt részhalmaza teljes, $K$ ezért teljes, tehát $f|_K$-ra is alkalmazható a Banach-féle fixponttétel. Érdemes lehet megjegyezni, hogy $K$ általában nem vektortér, azonban az eredeti tér normája által generált metrikával a halmaz teljes metrikus tér, tehát a Banach-féle fixponttétel valóban alkalmazható.

### 2. Feladat 
Oldjuk meg a $\cos(x) = x$ egyenletet a valós számok halmazán. Keressünk alkalmas halmazon alkalmas kontrakciót, majd írjunk kódot amivel addig iteráljunk, míg két szomszédos lépés távolsága nem lesz -nél kisebb.

***Megoldás:***
Kell egy Lipschitz fuggveny mely megadja a $\cos x = x$ egyenlet megoldasat.
Erre lehet hasznalni fixpont iteraciot, mert $\cos x$ kontrakcio $[0, \frac{\pi}{2})$ intervallumon

*iteration.py*
```python
from math import cos

def fix_point_iteration(start, f, max_steps, tolerance):
	x = start
	step_counter = 1
	while step_counter < max_steps:
		change = f(x) - x
		x = f(x)
		if abs(change) < tolerance:
			break

		step_counter += 1
	return f"Ended after {steps} iteration with value = {x}"

print(fix_point_iteration(0, cos, 100, 1e-5))
```

```console
$ python3 iteration.py
> Ended after 30 iteration with value = 0.7390822985224023
```


A lineáris esettel analóg módon bizonyos feltételek mellett fixpontiterációt készíthetünk az alábbi átalakítással:

$$
\begin{align}
f(x) &= b\\
0 &= b - f(x) \\
x &= x - f(x) + b \\
\end{align}
$$

Az iterációt ugyanolyan módon el tudjuk végezni mint a lineáris esetben, amíg $f(x)=x-(f(x)-b)$ kontrakció. Ha nem az, akkor valamely $c$ megválasztása mellett még lehet esélyünk arra, hogy az $f_c(x)=x-c(f(x)-b)$ függvény kontrakció legyen, a kérdés, hogy ezt hogy válasszuk meg. 

Egy lehetséges választ kaphatunk erre a kérdésre az alábbi gradiens-módszerre vonatkozó tételben, mely analóg lesz a lineáris esetnél látottakkal, melyek szerint a Richardson iteráció tulajdonképpen egy állandó lépésközű Gradiens-ereszkedésnek felelt meg.

### Gradiens-módszer

A gradiens-módszert is tudjuk alkalmazni nemlineáris feladatokra. A következő tételt alkalmazhatjuk speciális $A$ leképezések esetén. A tételt általános esetben mondjuk ki, egy $A: H\rightarrow H$ Hilbert-tér operátor esetén, az $A(u)=b$ egyenletre.

**Tétel:** Legyen $H$ valós Hilbert-tér (gondolhatunk $H=\mathbb{R}^n$-re is az Euklideszi skalárszorzattal ellátva) és $A:H\rightarrow H$ legyen deriválható minden $u\in H$ pontban, azaz létezik az $A'(u)\in B(H)$ lineáris operátor. Legyen $A'(u)$ önadjungált minden $u\in H$ esetén. Tegyük fel, hogy léteznek $0<m\leq M$ állandók, hogy

$$m\|h\|^2\leq \langle A'(u)h,h\rangle \leq M\|h\|^2 \qquad \forall u,h\in H.$$

Ekkor létezik olyan $\phi: H\rightarrow \mathbb{R}$ funkcionál, amelyre teljesül, hogy $\phi'=A$, és a $\phi$ funkcionál szigorúan konvex, továbbá, mint a lineáris esetben láthattuk:
$A(u^*)=b$ pontosan akkor áll fenn, ha $(\phi(u^*)-\langle b, u^*\rangle)'=0$, azaz ha $u^*$ minimumhelye az $u \mapsto \phi(u)-\langle b,u\rangle$ leképezésnek. Ekkor tetszőleges $u_0$ esetén az

$$u_{n+1}=u_n-\tau(A(u_n)-b)$$

sorozat konvergál az $u^*$-hoz, $\tau=\dfrac{2}{m+M}$ mellett.

**Megjegyzés:** Feladattól függően nem állandó lépésköz is választható, ezt azonban most nem tárgyaljuk.

Ez a tétel valamilyen értelemben analóg a lineáris esetben tanultakkal: a feltételek miatt létezik az egyenletben adott monoton $A$ függvény "primitív függvénye", ami konvex is, így az erre felírt minimalizási feladat az eredeti feladatunk egyértelmű megoldása lesz. 
 


### 3. Feladat
Gondoljuk meg mit jelentenek a tétel feltételei $H=\mathbb{R}^n$ esetén, illetve azt is hogy a képletben milyen dimenziójú objektumok szerepelnek. Gondoljuk meg, hogy a tétel visszaadja a lineáris esetnél látottakat.

***Megoldás:***


### 4. Feladat

Legyen  $H=\mathbb{R}^n$. Ellenőrizzük, hogy ha teljesülnek az előbbi tétel $A$-ra vonatkozó feltételei, akkor $F(u)=u-\tau (A(u)-b)$ kontrakció. Mutassuk meg, hogy bármely $0<\tau<\dfrac{2}{M}$ választás jó.

***Megoldás:***
$$
F(u)=u-\tau (A(u)-b)
$$

*Kell*:
$$
\lvert\lvert F(u) - F(v) \rvert\rvert \leq L \cdot \lvert\lvert u - v \rvert\rvert , \quad l \leq 1
$$
tudjuk:
$$
\lvert\lvert F(u) - F(v) \rvert\rvert  \leq \sup \limits_{u \in \mathbb{R}^{n}} \lvert\lvert F'(u) \rvert\rvert _{2, 2} \cdot \lvert\lvert u - v \rvert\rvert _{2}
$$
$$
F'(u) = I - \tau \cdot A'(u)
$$
$F'(u)$ sajatertekei: $1 - \tau \lambda(A'(u))$, ahol $\lambda(A'(u))$ az $A'(u)$ sajaterteke.
$$
\lvert 1 - \tau \cdot \lambda(A'(u)) \rvert = \max \{ 1 - \tau \cdot \lambda(A'(u)), \; \tau \cdot \lambda(A'(u)) - 1 \} \leq \max \{ 1 - \tau \cdot \lambda_{\min}, \; \tau \cdot \lambda_{\max} - 1 \}
$$
$$
\leq \max \{ 1 - \tau \cdot m, \; \tau \cdot M - 1 \}
$$
Kell, hogy ez $<1$ legyen, ehez eleg hogy
$$
\begin{align}
1 - \tau \cdot m & < 1 \iff 0 < \tau \cdot m  \\
\tau \cdot M - 1 & < 1 \iff \tau < \frac{2}{M}
\end{align}
$$
Tehat belattuk a feladat allitasat, hogy $0<\tau<\dfrac{2}{M}$ valasztas jo.


### 5. Feladat
Legyen $A:\mathbb{R}^n\rightarrow \mathbb{R}^n$ olyan függvény amelyre léteznek valamely $B,C\in\mathbb{R}^{n \times n}$ invertálható mátrixok, amelyekre $B\cdot A'(x)\cdot C$ SZPD mátrix minden $x\in K\subset\mathbb{R}^n$ esetén, egy alkalmas $K$ esetén, ahol $A(K)\subset K$ (vagyis $A$ ráképezés $K$-n). Ennek segítségével hogyan tudjuk megoldani az $A(x)=b$ feladatot iterációval?

Próbáljuk megoldani az $$\begin{cases}
-x(6x^2+2y^2) &= \phantom{-}2\\
\phantom{-}y(3x^2+y^2) &= -2
\end{cases}$$

feladatot.

***Megoldás:***


### 6. Feladat
Keressük meg az $f(x) = x^3 + 2 x^2 + 10 x - 20$ egyenlet gyökét, ha valahonnan sejtjük, hogy a $K=[1,2]$  intervallumban van. Alkalmazzunk fixpont-iterációt és addig iteráljunk, míg a szomszédos iteráltak távolsága $10^{-10}$ alá nem csökken.

***Megoldás:***
```python

```

### 7. Feladat 
Tekintsük az alábbi függvényt, ahol $c \in \mathbb{R}^+$:

$$f(x) = \frac{1}{x} - \frac{x}{c}$$

Keressük a függvény $x^*>0$ zérushelyét fixpont iteráció segítségével! Írjuk fel alkalmas $F(x) $ függvényt, és bizonyítsuk be, hogy valóban konvergál minden $c>0$ esetén! Hová fog tartani?

***Megoldás:***


## Kiegészítés lineáris egyenletrendszerek megoldására: Konjugált gradiens módszer
  
Emlék előadásról: A gradiens módszer helyett, gyakran a konjugált gradiens módszert használjuk, ha lineáris egyenletendszert szeretnénk megoldani. A módszer gyorsabban konvergál és elméletben véges lépés után visszakapjuk a pontos megoldást. A módszer lépései:
  
  1. Adott a kezdeti megoldás $x_0$ és a kezdeti gradiens $p_0=r_0 = Ax_0 - b$, ahol $A$ a mátrix és $b$ a vektor a lineáris egyenletrendszerben.
  2. Ha $x_n$ és $p_n$ ismert
  $$
x_{n+1}=x_n-\alpha_n p_n, \qquad \alpha_n=\dfrac{\langle r_n,p_n\rangle}{\langle Ap_n,p_n\rangle}, \qquad r_{n+1}=Ax_{n+1}-b
$$
  
$$
p_{n+1}=r_{n+1}-\beta_np_n, \qquad \beta_n=\dfrac{\langle Ar_{n+1},p_n\rangle}{\langle Ap_n,p_n\rangle}
$$



### 8. Feladat 
Írjunk programot, amely megold egy egyenletrendszert a konjugált gradiens módszerrel, amelynek bemenetei $A$, $b$ és az iterácók száma, majd oldjuk meg az alábbi egyenletet. Próbáljuk ki úgy is, hogy $1,2$, illetve $3$ iterációs lépést teszünk. 

$$
\begin{cases}
4x + 2y = 7,\\
2x+3y=10.
\end{cases}
$$

***Megoldás:***




related: [[NumMod 1]]