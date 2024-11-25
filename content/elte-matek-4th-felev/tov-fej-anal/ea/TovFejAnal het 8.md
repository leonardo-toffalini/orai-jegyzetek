date: 2024.04.16

## Mertek es integralelmelet
### Lebesgue-integral
Riemann-integrallal van nehany problema:
- Csak korlatos es zart intervallumon ertelmezett fugvenyeken ertelmezett
ellenpelda nem Riemann integralhato fuggvenyre: Dirichlet-fuggveny

Ha $f_{n} \to f$ pontonkent es feltesszuk, hogy $f_{n}$ Riemann integralhato minden $n$-ra, akkor nem feltetlenul kovetkezik, hogy $f$ Riemann integralhato, sot az sem feltetlenul kovetkezik, hogy $\int _{a}^{b}f_{n} \, dx \to \int _{a}^{b}f \, dx$

Ha $f_{n} \to f$ egyenletesen, akkor mar teljesen mas a helyzet.

#### Definicio (nullahalmaz)
$A \subset \mathbb{R}$ azt mondjuk, hogy $A$ nullahalmaz, ha $\forall \varepsilon > 0$ eseten $\exists I_{n, \varepsilon}$ intervallumsorozat amelyre $\sum \lvert I_{n, \varepsilon} \rvert < \varepsilon$ es $A \subset \bigcup I_{n, \varepsilon}$

peldak nullahalmazokra:
1. $A = \emptyset$
2. $A \subset \mathbb{R}$, $A$ megszamlalhato
*Biz.:* $A = \{ a_{n}: n \in \mathbb{N} \}$ adjunk egy $\varepsilon > 0$ -t es fedjuk be a halmazt a kovetkezokeppen:
$$
I_{n, \varepsilon} := \left( a_{n} - \frac{\varepsilon}{2 \cdot 3^{n}}, a_{n} + \frac{\varepsilon}{2 \cdot 3^{n}} \right) \quad n \in \mathbb{N}
$$
nyilvanvalo, hogy $A \subset \cup I_{n, \varepsilon}$
$$
\sum_{n=1}^{\infty}\lvert I_{n, \varepsilon} \rvert = \sum_{n=1}^{\infty} \frac{\varepsilon}{3^{n}} = \varepsilon \sum_{n=1}^{\infty} \frac{1}{3^{n}} = \frac{\varepsilon}{2} < \varepsilon
$$
3. $C$ Cantor-halmaz
$C_{n}$ halmaz az $n$-edik lepesben elojovo halmaz $C_{n} \subset A_{n}$, ahol $A_{n} = \left( \frac{2}{3} \right)^{n}$  osszhosszu veges sok intervallum. Tehat akkor $C \subset A_{n}$ es $\left( \frac{2}{3} \right)^{n} < \varepsilon$ ha $n$ elegge nagy


#### Allitas
1. Legyen $A_{n}, \; n \in \mathbb{N}$ nullahalmaz. Ekkor $\cup A_{n}$ is nullahalmaz.
2. Ha $I$ nem elfajulo intervallum (nem egy pontu vagy ures), akkor $I$ nem nullahalmaz.

*Bizonyitas:*
1. Legyen $\varepsilon > 0$ adott. Kell: $(I_{n})_{n \in \mathbb{N}}$ intervallumrendszer, ahol $\cup A_{n} =: A \subset \cup I_{n}$ es $\sum \lvert I_{n} \rvert < \varepsilon$
Tudjuk, hogy $A_{n}$ nullahalmaz, ezert $\exists (I_{n, k})_{k \in \mathbb{N}}$ ugy, hogy $A_{n} \subset \cup_{k=1}^{\infty}I_{n, k}$ es $\sum_{k=1}^{\infty}\lvert I_{n, k} \rvert < \frac{\varepsilon}{2^{n}}$
$$
\{ I_{n}: n \in \mathbb{N} \} := \{ I_{n, k}: k \in \mathbb{N}, \; n \in \mathbb{N} \}
$$
vilagos, hogy $A \subset I_{n}$ es $\sum \lvert I_{n} \rvert = \sum \sum \lvert I_{n, k} \rvert < \sum \frac{\varepsilon}{2^{n}} < \varepsilon$

2. $\emptyset$ biz.

#### Definicio
Azt mondjuk, hogy az $\mathbb{R}$ egy tulajdonsaga $T(x)$  tulajdonsaga *majdnem mindenutt (m.m.)* ha $A := \{  x \in \mathbb{R}: \neg T(x) \}$ nullahalmaz

#### Definicio
$f: \mathbb{R} \to \mathbb{R}$, $g : \mathbb{R} \to \mathbb{R}$. azt mondjuk, hogy $f = g$ m.m. ha $\{ x \in \mathbb{R}: f(x) \neq g(x) \}$ nullahalmaz.

Pelda: A Dirichlet-fuggveny $D = 0$ m.m., mert csak a racionalis helyeken nem nulla es a racionalis szamok nullahalmazt kepeznek.

#### Definicio
$\varphi : \mathbb{R} \to \mathbb{R}$  *lepcsos* fuggveny, ha $\exists x_{0} < x_{1} < \dots < x_{n} \in \mathbb{R}$ ugy, hogy
$$
\varphi(x) = \begin{cases}
0 & x < x_{0} \\
c_{1} & x_{0} < x < x_{1} \\
\vdots \\
c_{n} & x_{n-1} < x < x_{n} \\
0 & x > x_{n}
\end{cases}
$$
majdnem mindenutt.
(Megj. ha $x = x_{k}$ nincsen $\varphi(x)$ definialva, de mivel csak m.m. szamit ezert ezekben a pontokban lehet barmi az ertek mert ugyis nullahalmazon barmi lehet)

Legyen $C_{0} := \{  \varphi: \mathbb{R} \to \mathbb{R} \mid \varphi \text{ lepcsos fuggveny} \}$

#### Definicio
Ha $\varphi \in C_{0}$, akkor $\int  \varphi \, dx = \int _{\mathbb{R}}\varphi \, dx = \sum_{i=1}^{n} c_{i} \cdot (x_{i} - x_{i-1})$

#### Allitas
1. Ha $\varphi \in C_{0}$ akkor $\int  \varphi \, dx$ erteke nem fugg az $x_{i}$-k megvalasztasatol
2. $C_{0}$ vektorter
3. $\varphi_{1}, \varphi_{2} \in C_{0}$ es $c \in \mathbb{R}$ akkor $\int (\varphi_{1} + \varphi_{2}) \, dx = \int \varphi_{1} \, dx + \int \varphi_{2} \, dx$ es $\int (c \cdot \varphi) \, dx = c \int  \varphi \, dx$ (azaz az integral linearis a lepcsos fuggvenyek vektorteren)
4. Ha $\varphi, \psi \in C_{0}$ es $\varphi \leq \psi$ m.m., akkor $\int \varphi \, dx \leq \int \psi \, dx$
(A linearitas miatt $\int \varphi \, dx \leq \int \psi \, dx \iff \varphi \geq 0 \implies \int \varphi \, dx \geq 0$)

*Bizonyitas:* $\emptyset$ biz.

#### 1. Lemma (Dini-tetele)
Ha $(\varphi_{n}) \subset C_{0}$  olyan amelyre $\varphi_{n}$ monoton csokkeno modon tart $0$-hoz m.m ($\varphi_{n} \searrow 0$ m.m.), akkor $\int \varphi_{n} \, dx \to 0$

*Bizonyitas:* $\emptyset$ biz.

#### 2. Lemma
Legyen $(\varphi_{n})_{n \in \mathbb{N}} \subset C_{0}$ olyan, amely m.m. monoton novo, es $\int \varphi_{n} \, dx \leq A, \; \forall n$ 
Ekkor
$$
\lim_{ n \to \infty } \varphi_{n}(x) = f(x) \text{ m.m. veges}
$$
*Bizonyitas:* 
Legyen $E_{0} := \{ x \in \mathbb{R} : \varphi_{n}(x) \to \infty \}$ Kell: $E_{0}$ nullahalmaz
Legyen $\varepsilon > 0$ adott, az a cel, hogy $E_{0}$-t fedjuk
Felteheto, hogy $\varphi_{n} \geq 0$ m.m., kulonben csereljuk ki $\varphi_{n}$-t $\varphi_{n} - \varphi_{1} \geq 0$-ra ($\implies A \geq 0$)

$$
E_{n, \varepsilon} := \left\{  x \in \mathbb{R} : \varphi_{n}(x) > \frac{A}{\varepsilon}  \right\}
$$
Azt allitom, hogy
$$
E_{0} \subset \bigcup_{n=1}^{\infty}E_{n, \varepsilon}
$$
a vegtelenhez tartas definicioja miatt, ha $x$ olyan, hogy $\varphi_{n}(x) \to \infty$, akkor $\exists N_{\varepsilon}$ kuszobindex, melyre $\forall n \geq N_{\varepsilon}$ eseten $\varphi_{n}(x) > \frac{A}{\varepsilon}$
$$
E_{n-1, \varepsilon} \subset E_{n, \varepsilon}
$$
illetve $\varphi_{n}(x) \geq \varphi_{n-1}(x)$ m.m.
Tekintsuk a kovetkezo halmazt:
$$
E_{n, \varepsilon} \setminus E_{n-1, \varepsilon}
$$
Mivel k$\varphi_{n}$-ek lepcsos fv-ek, ezert
$$
E_{n, \varepsilon} \setminus E_{n-1, \varepsilon} = \bigcup_{k=1}^{K_{n}} I_{n, k}
$$
veges sok intervallum unioja

$$
E_{1, \varepsilon} = \bigcup_{k=1}^{K_{1}} I_{1, k}
$$
belatjuk a kovetkezot: tetszoleges $m \in \mathbb{N}$ eseten ha vesszuk a $\sum_{n = 1}^{m} \sum_{k=1}^{K_{n}} \lvert I_{n, k} \rvert < \varepsilon$

$$
\sum_{n = 1}^{m} \sum_{k=1}^{K_{n}} \frac{A}{\varepsilon} \cdot \lvert I_{n, k} \rvert \leq \int _{E_{1, \varepsilon}} \varphi_{1} \, dx + \sum_{n = 2}^{m} \int _{E_{n, \varepsilon} \setminus E_{n-1, \varepsilon}} \varphi_{n} \, dx  \leq \int _{E_{1, \varepsilon}}\varphi_{m} \, dx + \sum_{n = 2}^{m}\int _{E_{n, \varepsilon} \setminus E_{n-1, \varepsilon}}\varphi_{m} \, dx \leq \int _{\mathbb{R}}\varphi_{m} \, dx \leq A
$$
ahol
$$
\int _{A}\varphi \, dx = \int _{\mathbb{R}} \varphi \cdot \chi_{A} \, dx 
$$
$$
\implies \sum_{n=1}^{m} \sum_{k=1}^{K_{n}} \lvert I_{n , k} \rvert  < \varepsilon \quad \forall m \implies \sum_{n=1}^{\infty}\sum_{k=1}^{K_{n}} \lvert I_{n, k} \rvert  < \varepsilon
$$
masreszt konstrukciobol kovetkezik, hogy 
$$
E_{0} \subset \bigcup_{n=1}^{\infty}  E_{n, \varepsilon} \subset \bigcup_{n=1}^{\infty} \bigcup_{k=1}^{K_{n}} I_{n, k}
$$
#### Definicio
Legyen $(\varphi_{n})_{n \in \mathbb{N}} \subset C_{0}$ m.m. monoton novo sorozat, amelyre $\int \varphi_{n} \, dx \leq A$  (az ilyen sorozatokat *"jo $C_{0}$-sorozatnak"* hivjuk)
A fenti lemma szerint $\exists \lim_{ n \to \infty } \varphi_{n}(x) = f(x) \in \mathbb{R}$ ami veges m.m.
Ekkor az $f: \mathbb{R} \to \mathbb{R}$ fuggveny $C_{1}$-beli es
$$
\int f \, dx := \lim_{ n \to \infty } \int \varphi_{n} \, dx  \in \mathbb{R}
$$
*Bizonyizas:* (Hogy ez az integral tenyleg veges)
$\varphi_{n-1} \leq \varphi_{n}$ m.m. $\implies$ $\int \varphi_{n-1} \, dx \leq \int \varphi_{n} \, dx \leq A$ tehat $\lim_{ n \to \infty } \int \varphi_{n} \, dx$ veges mert monoton korlatos sorozatnak van hatarerteke.

#### Allitas
1. Ha $f \in C_{1}$ akkor $\int f \, dx$ erteke nem fugg a jo $C_{0}$-beli kozelito sorozat valasztasatol.
2. Ha $f \in C_{0}$ akkor a fenti integral ugyanazt adja, mint a lepcsos fuggveny integraljanak a definicioja.
3. Ha $f \in C_{1}$ es $f = g$ m.m. akkor $g \in C_{1}$ es $\int  f \, dx = \int g \, dx$ 
4. Ha $f,g \in C_{1}$ olyanok, hogy $f \leq g$ m.m. akkor $\int  f \, dx \leq \int g \, dx$ 
5. Ha $f, g \in C_{1}$  akkor $f + g \in C_{1}$ es $\int f + g \, dx = \int f \, dx + \int  g \, dx$
6. Ha $f \in C_{1}$ es $c \geq 0$ akkor $c \cdot f \in C_{1}$ es $\int c \cdot f \, dx = c \cdot \int f \, dx$
(Tehat $C_{1}$ nem vektorter)

*Bizonyitas:* 1, 4 $\emptyset$ biz.
2. Az 1., miatt legyen $\varphi_{n} := f, \; n \in \mathbb{N}$  
3. $f = g$ m.m. $\implies$  ha $(\varphi_{n})$ jo $C_{0}$-beli sorozat $f$-hez, akkor ugyanez a $(\varphi_{n})$ jo $C_{0}$-beli sorozat $g$-hez
5. 6. Ha $(\varphi_{n})$ jo $C_{0}$-beli sorozat $f$-hez es $(\psi_{n})$ jo $C_{0}$-beli sorozat $g$-hez es $c \geq 0$ akkor $(\varphi_{n} + \psi_{n})$ jo $C_{0}$-beli sorozat $f + g$ -hez es $(c \cdot \varphi_{n})$ jo $C_{0}$-beli sorozat $c \cdot f$ -hez. Tovabba
$$
\int (\varphi_{n} + \psi_{n}) \, dx = \int \varphi_{n} \, dx + \int \psi_{n} \, dx \to \int f \, dx + \int g \, dx = \int (f + g) \, dx
$$
$$
\int (c \cdot \varphi_{n}) \, dx = c \cdot \int \varphi_{n} \, dx \to c \cdot \int f \, dx \int (c \cdot f) \, dx 
$$
#### Definicio
Azt mondjuk, hogy $f : \mathbb{R} \to \mathbb{R}$  integralhato vagy $C_{2}$-beli, ha $f = f_{1} - f_{2}$ ahol $f_{1}, f_{2} \in C_{1}$. Ekkor
$$
\int f \, dx  := \int f_{1} \, dx  - \int f_{2} \, dx 
$$
#### Allitas
1. $C_{2}$ vektorter
2. $\int f \, dx$ nem fugg $f_{1}$ es $f_{2}$ valasztasatol
3. Ha $f \in C_{2}$ es $f = g$ m.m. akkor $g \in C_{2}$ es $\int  f \, dx = \int g \, dx$
4. Ha $f, g \in C_{2}$ es $f \geq g$ m.m. akkor $\int f \, dx \geq \int g \, dx$

*Bizonyitas:*
1. Legyen $f = f_{1} - f_{2}$ es $g = g_{1} - g_{2}$ ($f, g \in C_{2}$, $f_{1}, f_{2}, g_{1}, g_{2} \in C_{1}$)
Ekkor $f + g = (f_{1} + g_{1}) - (f_{2} + g_{2})$ es $(f_{1} + g_{1}), (f_{2} + g_{2}) \in C_{1}$
Ha $c \geq 0$ es $f \in C_{2}$ es $f = f_{1} - f_{2}$ ahol $f_{1}, f_{2} \in C_{1}$ ekkor $c \cdot f = c \cdot f_{1} - c \cdot f_{2}$ ahol $(cf_{1}), (cf_{2}) \in C_{1}$ ezert $(cf) \in C_{2}$
Ha $c < 0$ es $f \in C_{2}$ es $f = f_{1} - f_{2}$ ahol $f_{1}, f_{2} \in C_{1}$ ekkor $c \cdot f = (-cf_{2}) - (-cf_{1})$ ahol $(-cf_{2}), (-cf_{1}) \in C_{1}$ ezert $(cf) \in C_{2}$

2. Legyen $f = f_{1} - f_{2} = g_{1} - g_{2}$ ahol $f_{1}, f_{2}, g_{1}, g_{2} \in C_{1}$
$$
\implies f_{1} + g_{2} = g_{1} + f_{2}
$$
ahol $(f_{1} + g_{2}), (g_{1} + f_{2}) \in C_{1}$
$$
\implies \int f_{1} + g_{2} \, dx = \int f_{1} \, dx + \int g_{2} \, dx = \int g_{1} \, dx + \int f_{2} \, dx = \int (g_{1} + f_{2}) \, dx 
$$
$$
\implies \int f_{1} \, dx - \int f_{2} \, dx  = \int g_{1} \, dx - \int g_{2} \, dx 
$$
$$
\iff \int  f \, dx  = \int g \, dx 
$$
3. Ha $f \in C_{2}$ es $f = g$ m.m. es $f = f_{1} - f_{2}$ ahol $f_{1}, f_{2} \in C_{1}$ akkor $g = f_{1} - f_{2}$ m.m.
4. $\emptyset$ biz. (szamolos)

#### Beppo-Levi tetel
Legyen $(f_{n})_{n \in \mathbb{N}} \subset C_{2}$  integralhato fuggvenyek sorozata m.m. monoton novo, es $\int  f_{n} \, dx \leq A \quad \forall n \in \mathbb{N}$. Ekkor $\exists f \in C_{2}$ ugy, hogy $f_{n} \to f$ m.m. es $\int  f_{n} \, dx \to \int  f \, dx$

*Bizonyitas:* $\emptyset$ biz.

related: [[TovFejAnal]]