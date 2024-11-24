date: 2024.05.06

### A második derivált közelítése
Definícióból a következőt jelenti a második derivált:
$$
f''(x_{i}) = \lim_{ x \to x_{i} } \frac{f'(x) - f'(x_{i})}{x - x_{i}}
$$
Kis $h$ esetén a második deriváltat a következőképpen tudjuk jól közelíteni:
$$
f''(x_{i}) \approx \frac{f'(x_{i} + h) - f'(x_{i})}{h}
$$
Általában, amikor a második deriváltat kívánjuk közelíteni, az első deriváltat sem ismerjük. Így az első deriváltat is valahogyan közelítenünk kell. Szerencsére az előző fejezetben az első derivált közelítésével foglalkoztunk.

Közelítsük az első deriváltakat az előbb tanult módszerekkel.

Például mindkettőt a baloldali differenciahányadossal közelítjük

Így kapjuk a következő közelítést a második deriváltra:
$$
f''(x_{i}) \approx \frac{\frac{f(x_{i} + h) - f(x_{i})}{h} - \frac{f(x_{i}) - f(x_{i} - h)}{h}}{h} = \frac{f(x_{i} + h) - 2f(x_{i}) + f(x_{i} - h)}{h^{2}} =: \Delta ^{2}f_{c}
$$
A fenti jelölésben a $c$ alső index a centrális szóbol ered.

***Q.:*** Mi mondható a fenti közelítés rendjéről?

#### Állítás
Ez a bizonyos séma másodrendben közelíti $f''(x_{i})$-t, ha eléggé sima függvény, azaz $f \in C^{4}(I)$
(Nem bizonyítjuk.)

### A lépéstávolság dillemája
A következőkben arra a kérdésre próbálunk választ adni, hogy hogyan érdemes megválasztani a lépéstávolságokat, hogy minnél jobb közelítést érjünk el.

Hibaképletekből következik, hogy kisebb $h$ esetén kisebb hibát várunk.

Az $f(x_{i})$ értéket gyakorlatban általában hibával terheltek (pl.: számábrázolási hiba, mérési hiba, stb.)

Mi következik ebből?

Tekintsük a $\Delta f_{c}$ központi sémát:
$$
\Delta f_{c} := \frac{f(x_{i} + h) - f(x_{i} - h)}{2h}
$$
Tegyük fel, hogy $f(x_{i} + h)$ és $f(x_{i} - h)$ értéket valamilyen hibával terhelve ismerjük csak, ezért $\tilde{f}_{i-1}$ és $\tilde{f}_{i+1}$ értékekkel számolunk helyettük.
$$
\Delta \tilde{f}_{c} = \frac{\tilde{f}_{i+1} - \tilde{f}_{i-1}}{2h}
$$
és itt $f(x_{i} + h) = \tilde{f}_{i+1} + \varepsilon_{i+1}$ és $f(x_{i} - ) = \tilde{f}_{i-1} + \varepsilon_{i-1}$

Továbbá, tegyük fel, hogy $\lvert \varepsilon_{i + 1} \rvert, \lvert \varepsilon_{i-1} \rvert \leq \varepsilon > 0$

Ekkor a következő összefüggést írhatjuk fel:
$$
\Delta f_{c} = \frac{f(x_{i} + h) - f(x_{i} - h)}{2h} = \frac{\tilde{f}_{i+1} + \varepsilon_{i+1} - \tilde{f}_{i-1} - \varepsilon_{i-1}}{2h} = \stackrel{\Delta \tilde{f}_{c}}{\overbrace{\frac{\tilde{f}_{i+1} - \tilde{f}_{i-1}}{2h}}}+ \frac{\varepsilon_{i+1} - \varepsilon_{i-1}}{2h}
$$
$$
f'(x_{i}) + \frac{h^{2}}{6}f''(\eta) = \Delta \tilde{f}_{c} + \frac{\varepsilon_{i+1} - \varepsilon_{i-1}}{2h}
$$
$$
\implies \lvert f'(x_{i}) - \Delta \tilde{f}_{c} \rvert \leq \stackrel{g(h)}{\overbrace{\frac{h^{2}}{6}M_{3} + \frac{2\varepsilon}{2h}}}
$$
ahol $M_{3} := \sup \lvert f'' \rvert$

Látható, hogy a hibára felső korlátot adő $g(h)$ függvényben a második tag nő, ha csökken $h$. Tehát, $h$ nem választhatő sem túl negynak, sem túl kicsinek.

***Q.:*** Mi lesz az optimális $h$ lépésköz?

$g(h)$-nak ott lehet minimuma, ahol a deriváltja $0$, azaz $g'(h) = 0$
$$
g'(h) = \frac{1}{3}hM_{3} - \frac{\varepsilon}{h^{2}} = 0
$$
$$
h^{3} = \frac{3\varepsilon}{M_{3}} \implies h_{\text{opt}} = \left( \frac{3\varepsilon}{M_{3}} \right)^{1/3}
$$

## KDE-k megoldása
Megoldandó:
$$
\text{(1)} \quad y'(t) = f(t, y(t)), \quad t \in [t_{0}, T]
$$
$$
\text{(2)} \quad y(t_{0}) = y_{0}
$$
A fenti egy úgynevezett Cauchy-feladat.

Felmerül a probléma, hogy a pontos megoldást nem tudjuk mindig zárt alakban felírni

### Véges külömbséges módszerek
(1)(2) egyenleteket diszkretizáljuk. Azaz, a $[t_{0}, T]$ intervallumon definiáljuk a következő rácshálót:

Legyen $N \in \mathbb{N}^{+}$ és jelöljük $\omega_{\tau}$-val a következő halmazt:
$$
\omega_{\tau} := \left\{  t_{n} = t_{0} + n \cdot \tau : \quad n = 0, 1, \dots, N, \quad \tau = \frac{T - t_{0}}{N}  \right\}
$$
Egy folytonos függvény helyett egy olyan függvényt fogunk válaszul adni, mely csak ezeken a rácspontokon értelmezett. Gyakorlatilag egy vektort fogunk kapni, ahol az $i$-edik koordináta az $i$-edik rácsponton felvett függvényértéket jelképezi.

A megoldást csak az $\omega_{\tau}$ pontjaiban közelítjük. Tehát a numerikus megyoldás egy rácspontfüggvény lesz.

Jelölje a $t_{n}$ rácspontban a numerikus megoldást $y_{n}$. Szeretnénk, hogy ez köztel legyen a pontos megoldáshoz, azaz $y(t_{n})$ értékhez.

***Q.:*** Hogyan konstruálhatunk egy, a megoldást közelítő rácspontfüggvényt?

### Explicit Euler-módszer (EE)
Az elejéről építjük fel a rácshálót.

$t_{0}$-ban $y(t_{0}) = y_{0}$ adva van.
$$
y_{1} = \; ?
$$
Fejtsük sorba az $y$ pontos megoldást a $t_{0}$ körül. Ha $y \in C^{2}[t_{0}, T]$ akkor a következőt állíthatjuk:
$$
y(\stackrel{t_{1}}{\overbrace{t_{0} + \tau}}) = y(t_{0}) + y'(t_{0}) \cdot \tau + O(\tau ^{2}) = y_{0} + f(t_{0}, y(t_{0})) \cdot \tau + O(\tau ^{2}) = y_{0} + f(t_{0}, y_{0}) \cdot \tau + O(\tau ^{2})
$$
Tehát, ha $\tau$ kicsi, akkor $O(\tau ^{2})$ tag elhanyagolható és a következő közelítést kapjuk:
$$
y(t_{1}) \approx y_{0} + f(t_{0}, y_{0}) \cdot \tau =: y_{1}
$$
Ezután iteráljuk az eljárást: $y_{1} \leadsto y_{2} \leadsto \dots \leadsto y_{N}$
$$
y_{n+1} = y_{n} + f(t_{n}, y_{n}) \cdot \tau
$$
*Megjegyzés:* Ez úgy is megkapható, hogy az (1)-es egyenletben az $y'$-t jobboldali differenciahányadossal közelítjük:
$$
\frac{y_{n+1} - y_{n}}{\tau} = f(t_{n}, y_{n})
$$
Ezt átrendezve valóban az előbb kapott képletet visszakapjuk.

Grafikusan az implicit Euler-módszer azt jelenti, hogy az $y_{n}$ pontból az $y_{n+1}$ pontba úgy jutunk el, hogy a $t_{n}$ pontban az $y$ pontos megoldásnak a meredekségével lépünk előre $\tau$ hosszút az $y_{n}$ ponttól. Azaz a megoldás iránymező alapján lépkedünk mindig $\tau$ hosszúakat a mező irányába.

Ezt a módszert azért híváják *explicit* módszernek, mert eggyoldalra rendezve ki lehet fejezni $y_{n+1}$ értéket.

### Implicit Euler-módszer (IE)
Az EE-módszer képletében $f$-et ne $(t_{n}, y_{n})$-ben, hanem $(t_{n+1}, y_{n+1})$-ben értékeljük ki:
$$
y_{n+1} = y_{n} + f(t_{n+1}, y_{n+1}) \cdot \tau
$$
A fenti képletben felmerül a probléma, hogy $y_{n+1}$ kiszámításához kéne tudni $y_{n+1}$ értéket, mert szerepel a jobboldalon $f$  függvény hasában.

Tekinstünk a fenti képletre mint egy egyenletre és oldjuk meg $y_{n+1}$-re.

Jelölje $x := y_{n+1}$. Megoldandó: $x$-re a következő egyenlet:
$$
x = y_{n} + f(t_{n+1}, x) \cdot \tau
$$
Ezt az egyenletet midnen időlépésben meg kell oldanunk.

Az egyenletet meg tudjuk oldani előző fejezetekben tanult iterációs módszerekkel, például Newton-iterációval.

Rendezzünk $0$-re az egyenletet:
$$
\stackrel{F(x)}{\overbrace{x - y_{n} - f(t_{n+1}, x) \cdot \tau}} = 0
$$
Válasszunk $x_{0}$ kezdőértéket
$$
x_{k+1} = x_{k} - \frac{F(x_{k})}{F'(x_{k})}
$$
Érdemes meggondolni, hogy $F'(x)$ hogyan írható fel.
$$
F'(x) = 1 - \partial_{x}f(t_{n+1}, x) \cdot \tau
$$

### Runge-Kutta módszerek
Egy fokkal bonyolultabb módszer:
Azt csináljuk, hogy az $y(t_{n})$ pontban megnézzük a meredekséget és csak $t_{n} + \frac{\tau}{2}$ ponttig megyünk el és megnézzük itt is a meredekséget és miután ezt kiszámoltuk, ezzel a meredekséggel fogunk $y_{n}$-ből lépni.

Jelölje $k_{1} = f(t_{n}, y_{n})$
$y_{n} + k_{1} \cdot \frac{\tau}{2}$
Így $k_{2} = f\left( t_{n} + \frac{\tau}{2}, y_{n} + k_{1} \frac{\tau}{2} \right)$
$y_{n+1} = y_{n} + k_{2} \tau$

összegezve:
$$
y_{n+1} = y_{n} + f\left( t_{n} + \frac{\tau}{2}, y_{n} + f(t_{n}, y_{n}) \cdot \frac{\tau}{2} \right) \cdot \tau
$$
Ez egy kétlépcsős Runge-Kutta módszer. Lehet általánosabban $s$ lépcsős Runga-Kutta módszert is definiálni.

$[t_{n}, t_{n+1}]$ intervallumon $s$ pontban számítjuk ki a meredekséget és ezeket súlyozzuk és végül ezen súlyozott meredekségek összegével lépünk $y_{n}$-ből $y_{n+1}$-be.

A legelterjettebb Runge-Kutta módszer az RK4 módszer, amely $4$ lépcsős.

A következő a képlete:
$$
\begin{align*}
k_{1} &= f(t_{n}, y_{n}) \\
k_{2} &= f\left( t_{n} + \frac{\tau}{2}, y_{n} + k_{1} \frac{\tau}{2} \right) \\
k_{3} &= f\left( t_{n} + \frac{\tau}{2}, y_{n} + k_{2} \frac{\tau}{2} \right) \\
k_{4} &= f( t_{n} + \tau, y_{n} + k_{3} \tau) \\
y_{n+1} &= y_{n} + \tau\left(  \frac{1}{6}k_{1} + \frac{1}{3}k_{2} + \frac{1}{3}k_{3} + \frac{1}{6}k_{4} \right)
\end{align*}
$$





related: [[NumMod 1]]