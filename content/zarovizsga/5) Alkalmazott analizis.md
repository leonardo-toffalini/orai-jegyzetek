## a) KDE
### Egzisztencia es unicitas
- Egzisztencia – letezik megoldas az adott fuggveny osztalyon.
- Unicitas – A (letezo) megoldas egyertelmu az adott fuggveny osztalyon.
- Stabilitas – A megoldas folytonosan fugg az adatoktol.

### Egyszeru modellek
### Linearis diff egyenletek es rendszerek megoldasainak eloallitasa
### Harmonikus rezges
### Stabilitasi fogalmakl

## b) PDE es num modszerek
### Kezdeti es peremertek feladatok fogalma
#### Kezdeti feltetel, azaz kezdeti ertek avagy Cauchy-feladat
Van egy kituntettett valtozo, peldaul $t \in [t_{0}, \infty)$ peldaul az ido valtozo. 
Ekkor $t = t_{0}$ esetet peremnek hivjuk ahol meg van adva $u = u(t, x) \leadsto u(t_{0}, x) = \varphi(x)$ peremertek

Na, tehat van egy kituntetett valtozo, ami altalaban az ido es a kezdeti ertek $t_{0}$-ban meg van adva hogy milyen ertekeket vesz fel $u(t_{0}, x) = \varphi(x)$.
Peldaul egy dobozban van valami gaz ami egy parc diff egyenlet alapjan viselkedik es mi megmondjuk hogy amikor elkezdtuk a kiserletet milyen alloptban volt a gaz.

*Def.:* $\Delta$  az ugy nevezett Laplace operator ahol $\Delta u := \partial_{1}^{2}u + \dots + \partial_{n}^{2}u$

*Parabolikus alak* (hovezetesi egyenlet)
$$
\begin{aligned}
	\partial_{t}u - \Delta u &= f \\
	u(0, x) &= \Phi(x) \quad \forall x \in \Omega
\end{aligned}
$$

*Hiperbolikus alak* (hullam egyenlet)
$$
\begin{aligned}
	\partial_{t} ^{2} - \Delta u &= f \\
	u(0, x) &= \Phi(x) \quad \forall x \in \Omega \\
	\partial_{t} u(0, x) &= \psi(x) \quad \forall x \in \Omega
\end{aligned}
$$


#### Peremfeltetel, azaz peremertek feladat
Megadjuk $u$-nak vagy derivaltjanak az erteket egy peremen, azaz $\Omega$ egy korlatos hataran.
Peldaul egy dobozban van valami gaz ami egy parc diff egyenlet alapkan viselkedik es mi a kiserlet soran merjuk a doboz falain a gazt.

- Dirichlet-fele peremertek feladat: $u \mid_{\partial \Omega}$ adott
- Neumann-fele peremertek feladat: $(\partial_{\nu}u) \mid_{\partial \Omega}$ adott
- Vegyes peremertek feladat: $hu \mid_{\partial \Omega} + g(\partial_{\nu}u) \mid_{\partial \Omega}$ adoot
Ha az adott peremertek feltetel nulla az egesz peremen akkor homogennak mondjuk a peremertek feladatot, kulonben inhomogen.

*Megj.:* Lehet kezdeti es perem feltetelt egyszerre is adni. Peldaul a dobozban ismerem hogy mi volt a kezdeti allapot es kozben merem a falakon a gaz allapotat.

*Elliptikus alak* (Poisson egyenlet)
$$
-\Delta u = f
$$

Altalanos eset:
$$
\begin{aligned}
	-\operatorname{div}(p \nabla u) + q u &= f \quad \Omega \text{-n} \\
	g \cdot u\mid _{\partial \Omega} + h \cdot \partial_{\gamma} u \mid_{\partial \Omega} &= \phi \quad \partial \Omega \text{-n}
\end{aligned}
$$

### Fourier modszer vegyes feladatokra
*Vegyes feladat*
$$
\begin{cases}
	\partial_{t}^{2} u + Lu = f \quad & t > 0, \quad x \in \Omega \\
	u(0, x) = \Phi(x) \quad & x \in \Omega \\
	\partial_{t} u(0, x) = \Psi(x) \quad & x \in \Omega
\end{cases}
$$

*Def.:* Egy $L$ operatornak $e_{k}$ sajatfuggvenye $\lambda_{k}$ sajatertekkel, ha $Le_{k} = \lambda_{k} e_{k}$

Keressuk az $u$ megoldast Fourier-sor alakban, azaz
$$
u(t, x) = \sum_{k=1}^{\infty} \xi_{k}(t) e_{k}(x),
$$
ahol $e_{k}(x)$ az $L$ sajatfuggvenye ($e_{k} \in D(L)$). Ekkor $f$ is felirhato ebben bazisban a kovetkezo Fourier-sorral:
$$
f = \sum_{k=1}^{\infty} c_{k} e_{k}
$$
Ha ilyen alakban keressuk akkor nezzuk meg hogyan nez ki a feladat felirasa ezzel a behelyettesitessel:
$$
\partial_{t}^{2} \left( \sum_{k=1}^{\infty} \xi_{k}(t) e_{k}(x) \right) + L\left( \sum_{k=1}^{\infty}\xi_{k}(t) e_{k}(x) \right) = \sum_{k=1}^{\infty} c_{k}e_{k}(x).
$$
A parcialis derivaltat bevihetjuk a szummaba es az operatort is alkalmazhatjuk egyesevel:
$$
\sum_{k=1}^{\infty} \partial_{t}^{2} \xi_{k}(t) e_{k}(x) + \sum_{k=1}^{\infty} \xi_{k}(t) Le_{k}(x) = \sum_{k=1}^{\infty}c_{k}e_{k}(x).
$$
Mivel $e_{k}$ sajatfuggvenye $L$ nek minden $k$-ra, ezert $Le_{k} = \lambda_{k} e_{k}$. Ezt kihasznalva a kovetkezore jutunk:
$$
\sum_{k=1}^{\infty} \xi_{k}''(t) e_{k}(x) + \sum_{k=1}^{\infty} \xi_{k}(t) \lambda_{k}e_{k}(x) = \sum_{k=1}^{\infty} c_{k} e_{k}(x).
$$
Osszevonva a ket szummat es kiemelve $e_{k}$-t a kovetkezot kapjuk:
$$
\sum_{k=1}^{\infty}(\xi_{k}''(t) + \xi_{k}(t)\lambda_{k})e_{k}(x) = \sum_{k=1}^{\infty} c_{k} e_{k}(x).
$$
Most lathatjuk hogy ezekkel a trukkokkel arra redukaltuk a vegye PDE-t, hogy vegtelen sok masodrendu KDE-enk van, tehat $\forall k = 1, 2, 3, \dots$ ertekre kell a kovetkezot megoldanunk:
$$
\begin{cases}
	\xi_{k}''(t) + \xi_{k}(t)\lambda_{k} = c_{k} \\
	\xi_{k}(0) = \Phi_{k} \quad & \text{ahol } \Phi(x) = \sum_{k=1}^{\infty}\Phi_{k}e_{k}(x) \\
	\xi_{k}'(0) = \Psi_{k} \quad & \text{ahol } \Psi(x) = \sum_{k=1}^{\infty}\Psi_{k}e_{k}(x) \\
\end{cases}
$$

Osszegezve a kovetkezok a lepesei a Fourier-modszernek:
1. $L$ operator $\lambda_{k}$ sajatertekeit es $e_{k}$ sajatfuggvenyeit ki kell szamolni.
2. $f, \Phi, \Psi$ fuggvenyeket $e_{k}$ bazis szerint Fourier-sorba fejteni $\implies e_{k}, \Phi_{k}, \Psi_{k}$.
3. KDE megoldasa $\implies \xi_{k}$.
4. Osszerakni a vegso megoldast $u = \sum \xi_{k} e_{k}$.


### Linearis es nemlinearis algebrai rendszerek iteracios megoldasa
Alapfeladat:
$$
Ax = b
$$

#### Gauss eliminacio
Mindenki tudja hogy hogyan mukodik.

#### Jacobi-iteracio
A kovetkezo iteracios megoldok azon az otleten alapulnak hogy ha az $Ax = b$ rendszert at tudjuk alakitani $x = Qx + r$ alakra akkor felhasznalva a Banach fixpont tetelt (felteve hogy teljesulnek a feltetelek) iteralva az $x_{n+1} = Qx_{n} + r$ egyenletet egy fixponthoz fogunk konvergalni.

*Tetel:* (Banach fixpont) Adott $f : \mathbb{R}^{n} \to \mathbb{R}$ fuggveny ha kontrakcio az egesz $\mathbb{R}^{n}$-en $q$ egyutthatoval akkor:
1. $f$-nek egyertelmuen letezik fixpontja, azaz $\exists! x^{*} \in \mathbb{R}^{n}$ ugy hogy  $f(x^{*}) = x^{*}$.
2. A kovetkezokeppen eloallitott sorozat tetszoleges pontbol inditva konvergal az egyetlen fixponthoz: $x_{n+1} = f(x_{n})$.
3. A konvergencia uteme a kovetkezo keplettel adott:
$$
\| x_{k} -  x^{*} \|  \leq \frac{q^{k}}{1 - q} \| x_{1} - x_{0} \| 
$$

*Def.:* Az $f : \mathbb{R}^{n} \to \mathbb{R}$ fuggveny kontrakcio az egesz $\mathbb{R}^{n}$-en $q$ egyutthatoval valamely $\| \cdot \|$ $\mathbb{R}^{n}$-beli normaban, ha letezik $q \in [0, 1)$ egyutthato amelyre:
$$
\| f(x) - f(y) \|  \leq q \| x - y \| \quad \forall x, y \in \mathbb{R}^{n}
$$
Ergo, $f$ Lipscitz $< 1$ egyutthatoval.

Nezzuk meg hogy az $f(x) = Qx + r$ fuggveny mikor kontrakcio:
$$
\| f(x) - f(y) \| = \| Qx + r - Qy - r \| = \| Q(x - y) \| \leq \| Q \|  \cdot \| x - y \| 
$$
Tehat csak akkor kontrakcio a $Qx + r$ fuggveny ha van olyan norma $\mathbb{R}^{n}$-en ami olyan matrix normat indukal amelyben $\| Q \| < 1$.


$$
\begin{aligned}
	Ax &= b\\
	(L + D + U)x &= b \\
	Dx &= -(L + U)x + b \\
	x &= -D^{-1}(L + U)x + D^{-1}b
\end{aligned}
$$
Tehat $Q = -D^{-1}(L + U)$ es $r = D^{-1}b$. Tehat a kovetkezokeppen nez ki a Jacobi-iteracio keplete:
$$
x_{n+1} = -D^{-1}(L + U)x_{n} + D^{-1}b
$$

#### Gauss–Seidel-iteracio
$$
\begin{aligned}
	Ax &= b \\
	(L + D + U)x &= b \\
	(L + D)x &= -Ux + b \\
	x &= -(L + D)^{-1}Ux + (L + D)^{-1}b
\end{aligned}
$$
Tehat $Q = -(L + D)^{-1}U$ es $r = (L + D)^{-1}b$. Tehat a kovetkezokeppen nez ki a Gauss–Seidel-iteracio keplete:
$$
x_{n+1} = -(L + D)^{-1}Ux_{n} + (L + D)^{-1}b
$$

#### Egylepeses iteracio altalanos alakja
Vegyuk eszre hogy a Jacobi-iteraciot at tudjuk irni a kovetkezo alakban:
$$
\begin{aligned}
	x_{n+1} &= -D^{-1}(L + U)x_{n} + D^{-1}b \\
	Dx_{n+1} &= -(L + U)x_{n} + b \\
\end{aligned}
$$
Mivel $A = L + D+ U$ ezert $L + U = A - D$.
$$
\begin{aligned}
	Dx_{n+1} &= -(A - D)x_{n} + b \\
	Dx_{n+1} &= (D - A)x_{n} + b \\
	Dx_{n+1} - Dx_{n} + Ax_{n} &= b \\
	D(x_{n+1} - x_{n}) + Ax_{n} &= b
\end{aligned}
$$

Hasonlokeppen a Gauss–Seidel-iteraciot is at tudjuk irni:
$$
\begin{aligned}
	x_{n+1} &= -(L + D)^{-1}Ux_{n} + (L + D)^{-1}b \\
	(L + D)x_{n+1} &= -Ux_{n} + b \\
	(L + D)x_{n+1} &= -(A - L - D)x_{n} + b \\
	(L + D)x_{n+1} &= (-A + L + D)x_{n} + b \\
	(L + D)x_{n+1} + Ax_{n} - Lx_{n} - Dx_{n} &= b \\
	(L + D)(x_{n+1} - x_{n}) + Ax_{n} &= b
\end{aligned}
$$

*Altalanos egylepeses iteracio:*
$$
B_{n+1} \frac{x_{n+1} - x_{n}}{\tau_{n+1}} + Ax_{n} = b
$$

A fenti jelolessel elve fel tudjuk irni a Jacobi-iteraciot es a Gauss–Seidel iteraciot is a kovetkezo ertekadasokkal.
- Jacobi: $B_{n+1} = D$, $\tau_{n+1} = 1$
- Gauss–Seidel: $B_{n+1} = L + D$, $\tau_{n+1} = 1$
 

#### Gradiens modszer
Valamilyen trukkos modon ha felirunk egy fuggvenyt aminek pont abban az $x$ pontban van minimumhelye ahol $Ax = b$ akkor ennek a fuggvenynek a minumhelyet megkeresve valahogy megkapjuk a megoldast a keresett egyenletrendszerre.
Legyen
$$
\varphi(x) = \frac{1}{2} (x, Ax) - (x, b)
$$

Tobbvaltozos analizisbol tudjuk, hogy $\varphi'(x) = Ax - b$. Tehat ahol $\varphi'(x) = 0$ ott $Ax - b = 0$, azaz $Ax = b$.
Tovabba, ha feltesszuk hogy $A$ szimmetrikus pozitiv definit, akkor $\varphi''(x) = A$ pozitiv definit tehat valoban minimumhely $x$.
Na most ha tudunk egy olyan eljarast ami egy fuggveny minimumhelyet megtalalja akkor megoldottuk az $Ax = b$ egyenletrendszert.


#### Konjugalt gradiens modszer

### Diff egyenletek megoldasa Euler modszerrel
$$
\begin{cases}
y'(t) &= f(t, y(t)), \quad t \in (t_{0}, T) \\
y(t_{0}) &= y_{0}
\end{cases}
$$
#### Explicit Euler-modszer
$$
y_{n+1} = y_{n} + f(t_{n}, y_{n}) \tau
$$

#### Implicit Euler-modszer
$$
y_{n+1} = y_{n} + f(t_{n+1}, y_{n+1}) \tau
$$

