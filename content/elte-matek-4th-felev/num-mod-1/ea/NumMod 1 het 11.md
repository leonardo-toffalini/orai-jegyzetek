date: 2024.04.29

Előző óra végén kijöt, hogy
$$
\int _{a}^{b}f \, dx - t_{m}(f)  = -\frac{h^{3}}{12m^{2}}f''(\eta)
$$

***Következmény:***
1. Ha $f \in P_{1}$ akkor a formula pontos mert elsőfokú polinom második deriváltja mindig nulla
2. Feltétel szerint $f \in C^{2}[a, b]$ ebből következik, hogy $f'' \in C[a, b]$ és ebből meg következik, hogy felülről korlátos, azaz $\exists K > 0$ úgy, hogy $\lvert f'' \rvert \leq K$. Ebből következik, hogy
$$
\left\lvert  \int _{a}^{b}f \, dx - t_{m}(f)  \right\rvert = \frac{h^{3}}{13m^{2}} \cdot \lvert f''(\eta) \rvert  \leq \frac{h^{3}}{12m^{2}} \cdot K
$$
A fenti képletbe becsempészve $\Delta h := \frac{h}{m}$ kifejezést:
$$
= \frac{h}{12}K (\Delta h)^{2}
$$
Legyen $\frac{h}{12}K := \tilde{K}$ és így a fenti képlet végső alakja:
$$
\left\lvert  \int _{a}^{b}f \, dx -t_{m}(f)  \right\rvert \leq \tilde{K}(\Delta h)^{2}
$$
Tehát ha $m$ elég nagy (azaz $\Delta h$ eléggé kicsi), akkor a hiba tetszőlegesen kicsi lesz.

***Kérdés:*** Ha $\Delta h \to 0$, milyen gyorsan tart ez a hibakorlát $0$-hoz?

#### Definíció
Tegyük fel, hogy $g : K(0) \to \mathbb{R}$ olyan nulla körül értelmezett függvény, amelyhez $\exists \tilde{p} \in \mathbb{N}^{+}$ és $K \in \mathbb{R}$, hogy a $0$-hoz kellően közeli $t$ pontokban igaz a következő:
$$
\lvert g(t) \rvert \leq K \cdot \lvert t \rvert ^{\tilde{p}}
$$
Ekkor jelölje $p$ a legnagyobb ilyen tulajdonságú $\tilde{p}$ számot. Ekkor ez a bizonyos $g$ függvény $p$-ad rendben tart $0$-hoz a $0$-ban.
Jelölés: $g(t) = O(t^{p})$ ("ordó $t^{p}$")

Az előző eredményre visszatérve, a fenti ordó jelöléssel azt mondhatjuk, hogy
$$
\left\lvert  \int _{a}^{b}f \, dx - t_{m}(f)  \right\rvert = O((\Delta h)^{2})
$$

| $\Delta h$           | $\tilde{K}(\Delta h)^{2}$                        |
| -------------------- | ------------------------------------------------ |
| $\frac{\Delta h}{2}$ | $\tilde{K}\left( \frac{\Delta h}{2} \right)^{2}$ |
|                      |                                                  |
|                      |                                                  |
### 2. Összetett Simpson-formula
Az $[a, b]$ intevallumot felbontjuk $m$ kisebb intervallumra és minden $m$ darab kicsi intervallumban felveszünk egy segédpontot (például a kisintervallum felezőpontjá) és ebben a kisintervallumban lévő $3$ pontra illesztünk parabolát amit integrálunk. A végén összeadjuk a sok kicsi intevallumon illesztett parabola integrálját és ez lesz a közelítés az $\int _{a}^{b}f \, dx$ értékre.

Ha $f \in C^{4}[a, b]$,a akkor $\exists \eta \in [a, b]$ úgy, hogy
$$
\left\lvert  \int _{a}^{b}f \, dx - s_{m}(f)  \right\rvert = \left\lvert  -\frac{h^{5}}{2880m^{4}}f^{(4)}(\eta)  \right\rvert \leq \dots \leq \tilde{\tilde{K}} \cdot (\Delta h)^{4} = O((\Delta h)^{4})
$$

### Gauss kvadratúrák
(bevezető szóban)
Továbbra is interpolációs formulákról lesz szó. Mit is mondtunk arról, hogy az alappontokat hgoyan kell felvenni. Eddig csak azt mondtuk, hogy az $[a, b]$ intervallumon vegyük fel őket, de nem mondtunk semmiféle megszorítás. Speciális ha egyenlő távolságú felosztást veszünk, akkor azt könnyű leprogramozni.
Kérdés, hogy jobb rendet is el tudunk-e érni mint általában, ha jól megválasztjuk az adatpontokat.

(táblán bevezető)
Eddig az interpolációs kvadratúra formuláknál adottnak vettük az alappontokat: $x_{0}, x_{1}, \dots, x_{n}$ és láttuk, hogy a $\sum_{m=0}^{n}A_{m} \cdot f_{m}$ interpolációs kvadratúra formula pontos $\forall f \in P_{n}$ függvényre. Tehát a formula alapból legalább $n+1$ rendű, azaz annyi a rendje ahány alappont van.

***Kérdés:*** Növelhető-e a rend az alappontok megfelelő megválasztásával?

*Emlék:* A középponti formula $k(f)$ is interpolációs formula, ahol egy alappont van (az intervallum felezőpontja $c$) és konstans függvényt illesztünk. Itt láttuk, hogy a középponti formula pontos elsőfokú polinomokra is, de a tételünk azt mondja, hogy csak elsőrendű a formula. Tehát ez azt jelenti, hogy ha konstans függvénnyt illesztünk, akkor ha a középpontot választjuk alappontnak, akkor magasabb rendű módszert kapunk.

A simpson-formulánál is hasonló eredmény jött ki. Csak három alappont van tehát azt várnánk, hogy harmadrendű legyen, de ha a középpontot választjuk harmadik alappontnak, akkor negyedrendet érünk el.

Tegyük fel, hogy $2$ alappont van $x_{0}$ és $x_{1}$. Kérdés: hogyan válasszuk meg ezeket, hogy minnél nagyobb rendű legyen a kvadratúra formulánk?
És legyen az egyszerűség kedvéért $[a, b] := [-1, 1]$
Ekkor az interpolációs formula a következőképpen néz ki:
$$
\sum_{m=0}^{1}A_{m} \cdot f_{m} = A_{0} \cdot f(x_{0}) + A_{1} \cdot f(x_{1})
$$
ahol
$$
A_{0} = \int _{-1}^{1}l_{0}(x) \, dx = \int _{-1}^{1} \frac{x - x_{1}}{x_{0} - x_{1}} \, dx = \frac{1}{x_{0} - x_{1}} \cdot \left[ \frac{x^{2}}{2} - x_{1} \cdot x \right]_{-1}^{1} = \frac{1}{x_{0} - x_{1}} \cdot \left( \frac{1}{2} - x_{1} - \frac{1}{2} - x_{1} \right) = \frac{2x_{1}}{x_{1} - x_{0}}
$$
$$
A_{1} = \int _{-1}^{1}l_{1}(x) \, dx = -\frac{2x_{0}}{x_{1} - x_{0}}
$$

Tehát tetszőleges $x_{0}$ és $x_{1}$ esetén ez a formula pontos $\forall f \in P_{1}$ függvényre.

***Kérdés:*** Meg lehet megválasztani $x_{0}$ és $x_{1}$-et úgy, hogy magasabb fokú polinomokra is pontos legyen?

*Nyilvánvalóan:* Egy kvadratúra formula pontos $\forall f \in P_{q}$  polinomra $\iff$ pontos az $f(x) = x^{0}, x^{1}, x^{2}, \dots x^{q}$ függvényekre.

Mikor lesz pontos $\forall f \in P_{2}$ függvényre a fenti formula?
$$
A_{0} \cdot x_{0}^{2} + A_{1} \cdot x_{1}^{2} = \int _{-1}^{1}x^{2} \, dx = \frac{2}{3}
$$
Behelyettesítve az előbb kiszámolt $A_{0}$ és $A_{1}$ értékeket a következő egyenletet kapjuk:
$$
\begin{align*}
\frac{2x_{1}}{x_{1} - x_{0}} \cdot x_{0}^{2} - \frac{2x_{0}}{x_{1} - x_{0}} \cdot x_{1}^{2} &= \frac{2}{3}\\
\frac{x_{0}x_{1}}{x_{1} - x_{0}} \cdot (x_{0} - x_{1}) &= \frac{1}{3}\\
x_{0}x_{1} &= -\frac{1}{3}
\end{align*}
$$
Mikor lesz pontos $\forall f \in P_{3}$ polinomra? Ha pontos az $f(x) = x^{3}$ függvényre is.
$$
\begin{align*}
\frac{2x_{1}}{x_{1} - x_{0}} \cdot x_{0}^{3} - \frac{2x_{0}}{x_{1} - x_{0}} \cdot x_{1}^{3} &= \int _{-1}^{1}x^{3} \, dx  = 0\\
\frac{x_{0}x_{1}}{x_{1} - x_{0}}(x_{0}^{2} - x_{1}^{2}) &= 0 \\
\frac{x_{0}x_{1}}{x_{1} - x_{0}}(x_{0} + x_{1})(x_{0} - x_{1}) &= 0\\
\end{align*}
$$
A fenti kifejezés csak akkor $0$ ha $x_{0} + x_{1} = 0$, azaz $x_{0} = -x_{1}$

A két egyenlet megoldása:
$$
-x_{1}^{2} = -\frac{1}{3} \leadsto x_{1} = \frac{1}{\sqrt{ 3 }} \implies x_{0} = -\frac{1}{\sqrt{ 3 }}
$$
$A_{0}, A_{1} = \; ?$
$$
\begin{align*}
A_{0} &= \frac{2x_{1}}{x_{1} - x_{0}} = \frac{\left( 2 \cdot \frac{1}{\sqrt{ 3 }} \right)}{\frac{2}{\sqrt{ 3 }}} = 1 \\
A_{1} &= \dots = 1
\end{align*}
$$

Tehát a formula: $f\left( -\frac{1}{\sqrt{ 3 }} \right) + f\left( \frac{1}{\sqrt{ 3 }} \right) \approx \int _{-1}^{1}f \, dx$ és ez pontos $\forall f \in P_{3}$ polinomra.

***Megjegyzés:*** $n + 1$ alappont esetén a rend legfeljebb $(n + 1)$-el növelhető meg.

***Megjegyzés:*** Ha $n = 2$ (azaz $3$ alappont)
$$
x_{0} = -\sqrt{ \frac{3}{5} }, \quad x_{1} = 0, \quad x_{2} = \sqrt{ \frac{3}{5} }
$$
$$
A_{0} = \frac{5}{9}, \quad A_{1} = \frac{8}{9}, \quad A_{2}=\frac{5}{9}
$$
***Megjegyzés:*** Ha $[a, b] \neq [-1, 1]$ akkor az $[a, b]$ intervallumot átranszformáljuk a $[-1, 1]$ intervallumra és ott felvesszük a Gauss-kvadratúra alappontokat, majd visszatranszformáljuk a $[-1, 1]$ intervallumot az $[a, b]$ intervallumra.


### Numerikus deriválás
Legyen $f : I \to \mathbb{R}$ és $x_{0}, x_{1}, \dots, x_{n} \in I$ és $x_{i+1} = x_{i} + h$ ahol $i = 0, 1, \dots, n-1$
***Kérdés:***
$f'(x_{i}) \approx \; ?$ az $f(x_{0}), f(x_{1}), \dots, f(x_{n})$ függvényértékek segítségével
$f'(x_{i}) \approx \; ?$ az $f(x_{0}), f(x_{1}), \dots, f(x_{n})$ függvényértékek segítségével

### Az első derivált közelítése
Derivált definíciója:
$$
f'(x_{i}) = \lim_{ x \to x_{i} } \frac{f(x) - f(x_{i})}{x - x_{i}}
$$
Tehát
$$
f'(x_{i}) \approx \frac{f(x_{i} + h) + f(x_{i})}{h} =: \Delta f_{+}
$$
úgynevezett jobboldali differencia hányados.

Ha az $x_{i}$ ponttol van balra is értékünk:
$$
f'(x_{i}) \approx \frac{f(x_{i}) - f(x_{i} - h)}{h} =: \Delta f_{-}
$$
úgynevezett baloldali differencia hányados.

Ha már ezt a kettőt bevezettük, akkor vizsgáljuk a számtani közepüket:
$$
\Delta f_{c} := \frac{\Delta f_{+} + \Delta f_{-}}{2} = \frac{f(x_{i} + h) - f(x_{i} - h)}{2h}
$$
úgynevezett centrális (vagy központi) differenciahányados.

***Kérdés:*** Mennyire jók ezek a közelítések?

#### Definíció
Jelölje $f$ valamelyik deriváltját az $x_{i}$ pontban $Df$ és annak közelítését $\Delta f(h)$
Azt mondjuk, hogy a közelítés rendhe $p$, ha
$$
\lvert Df - \Delta f(h) \rvert = O(h^{p})
$$
#### Állítás
A bal- és a jobboldali differenciahányados is elsőrendben közelíti egy $f$ függvény első deriváltját $x_{i}$-ben, ha $f \in C^{2}(I)$.

*Bizonyítás:* Csak a jobboldali differenciahányadosra.
Fejtsük Taylor-sorba $f$-et $x_{i}$ körül:
$\exists \eta \in [x_{i}, x_{i} + h]$ úgy, hogy
$$
f(x_{i} + h) = f(x_{i}) + h \cdot f'(x_{i}) + \frac{h^{2}}{2}f''(\eta)
$$
Innen a következőképpen alakíthatjuk az egyenletet:
$$
\frac{f(x_{i} + h) - f(x_{i})}{h} = f'(x_{i}) + \frac{h}{2}f''(\eta)
$$
$$
\implies \lvert f'(x_{i}) - \Delta f_{+} \rvert = \frac{h}{2}\lvert f''(\eta) \rvert  \leq K \cdot h
$$
ahol $K = \frac{1}{2}\lvert f''(\eta) \rvert$

#### Állítás
A $\Delta f_{c}$ centrális differenciahányados másodrendben közelíti $f'(x_{i})$-t, ha $f \in C^{3}(I)$.

*Bizonyítás:*
$\exists \eta_{1} \in [x_{i}, x_{i} + h]$ és $\eta_{2} \in [x_{i} - h, x_{i}]$ úgy, hogy:
$$
\begin{align*}
f(x_{i} + h) &= f(x_{i}) + h \cdot f'(x_{i}) + \frac{h^{2}}{2}f''(x_{i}) + \frac{h^{3}}{6}f'''(\eta_{1}) \\
f(x_{i} - h) &= f(x_{i}) - h \cdot f'(x_{i}) + \frac{h^{2}}{2}f''(x_{i}) - \frac{h^{3}}{6}f'''(\eta_{2})
\end{align*}
$$
$$
\implies \Delta f_{c} = \frac{f(x_{i} + h) - f(x_{i} - h)}{2h} = f'(x_{i}) + \frac{h^{3}}{6} \cdot \frac{f'''(\eta_{1}) + f'''(\eta_{2})}{2h}
$$
Mivel $f''' \in C(i)$ ezért $\frac{f'''(\eta_{1}) + f'''(\eta_{2})}{2} = f'''(\eta)$  ahol $\eta \in [x_{i} - h, x_{i} + h]$

Tehát
$$
\lvert f'(x_{i} - \Delta f_{c}) \rvert = \frac{h^{2}}{6} \cdot \lvert f'''(\eta) \rvert 
$$
tehát a centrális differenciahányados valóban másodrendű közelítés.


related: [[NumMod 1]]