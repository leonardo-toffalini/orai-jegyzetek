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

#### Peremfeltetel, azaz peremertek feladat
Megadjuk $u$-nak vagy derivaltjanak az erteket egy peremen, azaz $\Omega$ egy korlatos hataran.
Peldaul egy dobozban van valami gaz ami egy parc diff egyenlet alapkan viselkedik es mi a kiserlet soran merjuk a doboz falain a gazt.

- Dirichlet-fele peremertek feladat: $u \mid_{\partial \Omega}$ adott
- Neumann-fele peremertek feladat: $(\partial_{\nu}u) \mid_{\partial \Omega}$ adott
- Vegyes peremertek feladat: $hu \mid_{\partial \Omega} + g(\partial_{\nu}u) \mid_{\partial \Omega}$ adoot
Ha az adott peremertek feltetel nulla az egesz peremen akkor homogennak mondjuk a peremertek feladatot, kulonben inhomogen.

*Megj.:* Lehet kezdeti es perem feltetelt egyszerre is adni. Peldaul a dobozban ismerem hogy mi volt a kezdeti allapot es kozben merem a falakon a gaz allapotat.

### Fourier modszer vegyes feladatokra

### Linearis es nemlinearis algebrai rendszerek iteracios megoldasa
#### Jacobi-iteracio
#### Gauss–Seidel-iteracio
#### Gradiens modszer
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

