## a) Valoszinuseg szamitas
### Valoszinusegi mezo
*Def.:* A $(\Omega, \mathcal{A}, \mathbb{P})$ harmas Kolmogorov-fele valoszinusegi mezo, ha:
- $\Omega$ nemures halmaz
- $\mathcal{A} \subseteq \mathcal{P}(\Omega)$ egy $\sigma$-algebra
- $\mathbb{P}$ egy mertek azzal a plusz feltetellel hogy $\mathbb{P}(\Omega) = 1$

Elnevezesek:
- $\Omega$ - esemenyter
- $\omega \in \Omega$ - elemi esemeny
- $\mathcal{A}$ - esemenyek halmaza
- $A \in \mathcal{A}$ - esemenyek
- $\mathbb{P}$ - valoszinuseg
- $\Omega \in \mathcal{A}$ - biztos esemeny
- $\emptyset \in \mathcal{A}$ - lehetetlen esemeny

### Valoszinusegi valtozok
*Def.:* Valoszinusegi valtozonak az olyan $X : \Omega \to \mathbb{R}$ fuggvenyeket nevezzuk, melyre $\mathbb{P}(a < X \leq b)$ ertelmes minden $a < b$ valos szamra.

### Varhato ertek
*Def.:*
- diszkret eset:
$$
\mathbb{E}[X] = \sum_{j = 1}^{\infty}x_{j} \cdot \mathbb{P}(X = x_{j})
$$

- abszolut folytonos eset:
$$
\mathbb{E}[X] = \int _{-\infty}^{\infty}x \cdot f(x) \, dx 
$$

### Szoras
*Def.:* Masodik centralis momentum:
$$
D^{2}[X] = \mathbb{E}[(X - \mathbb{E}[X])^{2}] = \mathbb{E}[X^{2}] - \mathbb{E}[X]^{2}
$$
$$
D[X] = \sqrt{ D^{2}[X] }
$$

### Kovariencia
*Def.:*
$$
\begin{align}
\operatorname{cov}(X, Y) & =\mathrm{E}[(X-\mathrm{E}[X])(Y-\mathrm{E}[Y])] \\
& =\mathrm{E}[X Y-X \mathrm{E}[Y]-\mathrm{E}[X] Y+\mathrm{E}[X] \mathrm{E}[Y]] \\
& =\mathrm{E}[X Y]-\mathrm{E}[X] \mathrm{E}[Y]-\mathrm{E}[X] \mathrm{E}[Y]+\mathrm{E}[X] \mathrm{E}[Y] \\
& =\mathrm{E}[X Y]-\mathrm{E}[X] \mathrm{E}[Y] .
\end{align}
$$

### Korrelacios egyutthato
*Def.:*
$$
\operatorname{cor}(X, Y) = \frac{\operatorname{cov}(X, Y)}{D(X)D(Y)}
$$

### Valoszinnusegi valtozok konvergenciaja
*Def.:* $\xi_{n} \to \xi$ eloszlasban ha $F_{\xi_{n}}(x) \stackrel{n \to \infty}{\to} F_{\xi}(x)$ minden pontban ahol $F_{\xi}$ folytonos.
*Def.:* $\xi_{n}\to \xi$ sztochasztikusan, ha $\mathbb{P} (\lvert \xi_{n} - \xi \rvert \geq \varepsilon) \stackrel{n \to \infty}{\to} 0$ minden $\varepsilon > 0$ -ra.
*Def.:* $\xi_{n}\to \xi$ majdnem mindenutt (1-valseggel) ha $\mathbb{P}(w : \xi_{n}(w) \to \xi(w)) = 1$
*Def.:* $\xi_{n} \to \xi$ $L^{p}$-ben ha $\mathbb{E}\lvert \xi_{n} - \xi \rvert^{p} \stackrel{n \to \infty}{\to} 0$

*Tetel:* mm. $\implies$ sztoch.
*Tetel:* $L^{p}$ $\implies$ sztoch.
*Tetel:* sztoch $\implies$ eloszlasban
*Megj.:* m.m.-bol nem kovetkezik $L^{p}$ vagy forditva

### Nagy szamok torvenye
*Def.:* 
$$
\limsup A_{n} = \bigcap_{n=1}^{\infty} \bigcup_{k = n}^{\infty} A_{k}
$$

*Tetel:* (Borel–Cantelli-lemma)
- Ha $\sum \mathbb{P}(A_{n}) < \infty$ akkor $\mathbb{P}(\limsup A_{n}) = 0$
Ha az esemenyek valoszinusegenek osszege veges, akkor annak a valoszinusege hogy vegtelen sok megortenik az $0$.

- Tegyuk fel, hogy az $A_{n}$ esemenyek fuggetlenek. Ekkor $\sum \mathbb{P}(A_{n}) = \infty$ eseten $\mathbb{P}(\limsup A_{n}) = 1$
Ha a fuggetlen esemenyek valoszinusegenek osszege vegtelen, akkor annak a valoszinusege hogy vegtelen sok megtortenik az $1$.

*Biz.:*
$$
\mathbb{P}(\limsup A_{n}) = \mathbb{P} \left(\bigcap_{n=1}^{\infty} \bigcup_{k = n}^{\infty} A_{k} \right) \leq \mathbb{P}\left(  \bigcup_{k=n}^{\infty}A_{k}  \right) \leq \sum_{k=n}^{\infty}\mathbb{P}(A_{k})
$$
Az utolso egyenlotlensegben kihasznaltuk hogy $\mathbb{P}$ egy mertek es ezet $\sigma$-szubadditiv. Minel az osszegben $n$-et barmennyire novelhetjuk, ezert tetszolegesen kicsi lehet az osszeg erteke.

Eleg igazolni hogy a komplementer esemeny valoszinusege $0$. A de Morgan-azonossag miatt
$$
\overline{\limsup A_{n}} = \bigcap_{n=1}^{\infty} \bigcup_{k=n}^{\infty} \overline{A_{k}}
$$

Azt kell belatni hogy $\mathbb{P}(\cap_{k=n}^{\infty} \overline{A_{k}}) = 0$
$$
\mathbb{P}\left(  \bigcap_{k=n}^{N} \overline{A_{kj}} \right) = \prod_{k=n}^{N} \mathbb{P}(\overline{A_{k}}) = \prod_{k=n}^{N} (1 - \mathbb{P}(A_{k})) \leq \prod_{k=n}^{N} e^{-\mathbb{P}(A_{k})} \leq \exp\left( - \sum_{k=n}^{N}\mathbb{P}(A_{k}) \right)
$$
Ha $N\to \infty$ akkor a jobb oldal tart $0$-hoz.

*Tetel:* (Nagy szamok gyenge torvenye) $X_{1}, X_{2}, \dots$ i.i.d. valoszinusegi valtozok. Tegyuk fel, hogy $D(X_{1}) < \infty$. Ekkor $\forall \varepsilon >0$ eseten
$$
\mathbb{P}(\lvert \overline{X_{n}} - \mathbb{E}(X_{1}) > \varepsilon \rvert ) \to 0 \quad (n \to \infty)
$$
azaz $\overline{X_{n}} \to \mathbb{E}(X_{1})$ sztochasztikusan.

*Tetel:* (Nagy szamok eros torvenye veges szorassal) $X_{1}, X_{2}, \dots$ i.i.d. valoszinusegi valtozok. Tegyuk fel, hogy $D(X_{1}) < \infty$. Ekkor
$$
\overline{X_{n}} \to \mathbb{E}(X_{1})
$$
teljesul $1$ valoszinuseggel (m.m.) $n \to \infty$ eseten.

*Biz.:* Legyen $S_{n} = X_{1} + X_{2} + \dots + X_{n}$. Eloszor csak azt az esetet vizsgaljuk ahol minden $X_{i}$ nemnegativ.
Legyen $\varepsilon >0$ es $A(n) = \left\{  \left\lvert  \frac{S_{n}}{n} - \mathbb{E}X_{1}  \right\rvert > \varepsilon \right\}$. Mivel $S_{n}/n$ szorasa vegtelen, mert $X_{1}$ szorasa az, ezert lehet hasznalni a Csebisev-egyenlotlenseget
$$
\mathbb{P}(A(n^{2})) \leq \frac{D^{2}(S_{n^{2}} / n^{2})}{\varepsilon ^{2}} \leq \frac{D^{2}(X_{1})}{n^{2}\varepsilon ^{2}}
$$

$$
\sum \mathbb{P}(A(n^{2})) \leq \sum \frac{D^{2}(X_{1})}{n^{2} \varepsilon ^{2}} = \frac{D^{2}(X_{1})}{\varepsilon ^{2}} \sum \frac{1}{n^{2}} < \infty
$$
ezert a Borel–Cantell-lemma miatt $1$ a valoszinusege annak hogy az $A(n^{2})$ csak veges sok $n$-re teljesul, tehat van olyan nagy $n$ amire
$$
\left\lvert  \frac{S_{n^{2}}}{n^{2}} - \mathbb{E}X_{1}  \right\rvert \leq \varepsilon
$$
ami pont azt jelenti hogy $1$ valseggel 
$$
\limsup_{n\to \infty} \left\lvert  \frac{S_{n^{2}}}{n^{2}} - \mathbb{E}X_{1}  \right\rvert  \leq \varepsilon
$$
Legyen $n = \lfloor \sqrt{ n } \rfloor$ ekkor $m^{2} \leq n < (m + 1)^{2}$. Mivel minden $X_{i}$ nem negativ, ezert egy tobb $S_{m^{2}} \leq S_{n} \leq S_{(m+1)^{2}}$ tovobba
$$
\left( \frac{m}{m+1} \right)^{2} \frac{S_{m^{2}}}{m^{2}} \le \frac{S_{n}}{n} \leq \left( \frac{m+1}{m} \right)^{2} \frac{S_{(m+1)^{2}}}{(m+1)^{2}}
$$
Ha $n\to \infty$ akkor $m$ is tart vegtelenben es igy a rendor elv miatt $S_{n} / n$ is ugyanugy tart $\mathbb{E}X_{1}$-hez ahogyan a ket szele az egyenlotlensegnek.

Altalanos esetben minde $X_{i}$-t bontsuk fel a pozitiv es a negativ reszere: $X_{i} = X_{i}^{+} - X_{i}^{-}$, igy $X_{i}^{+}$ es $X_{i}^{-}$ is mar nemnegativ.
$$
\frac{1}{n} \sum_{i=1}^{n}X_{i} = \frac{1}{n} \sum_{i=1}^{n}X_{i}^{+} - \frac{1}{n}\sum_{i=1}^{n}X_{i}^{-}
$$
A baloldali tag tart $\mathbb{E}(X_{1}^{+})$-hez es a jobbolali tag tart $\mathbb{E}(X_{1}^{-})$-hoz mert mindketto nemnegativ es igy az elobb belatott allitas ervenyes rajuk.
Tovabba, $\mathbb{E}(X_{1}) = \mathbb{E}(X_{1}^{+}) - \mathbb{E}(X_{1}^{-})$ es igy belattuk hogy $\overline{X_{n}} \to \mathbb{E}(X_{1})$ $1$-valoszinuseggel.

*Tetel:* (Kolmogorov-fele nagy szamok torvenye) $X_{1}, X_{2}, \dots$ i.i.d. valoszinusegi valtozok
- Ha $\mathbb{E}(X_{1})$ veges  akkor $S_{n} / n \to \mathbb{E}(X_{1})$ $1$ valoszinuseggel (m.m.).
- Ha $S_{n} / n$ pozitiv valoszinuseggel konvergal egy veges szamhoz, akkor $\mathbb{E}(X_{1})$ veges.

### Centralis hatareloszlas tetel
*Tetel:* $X_{1}, X_{2}, \dots$ i.i.d. melyekre $\mathbb{E}(X_{1}) = m$ es $D(X_{1}) = \sigma < \infty$. Ekkor minden $x \in \mathbb{R}$-re
$$
\mathbb{P}\left(  \frac{X_{1} + X_{2} + \dots + X_{n} - n \cdot m}{\sigma \sqrt{ n }} \leq x  \right) \to \Phi(x) \quad (n \to \infty)
$$
ahol $\Phi(x)$ a standard normalis eloszlas eloszlasfuggvenye. Azaz $Z \sim N(0, 1)$
$$
\Phi(x) = \mathbb{P}(Z \leq x) = \int _{-\infty}^{x} \frac{1}{\sqrt{ 2\pi }}\exp\left( - \frac{s^{2}}{2} \right) \, ds 
$$

Szavakban annyit jelent a fenti tetel hogy i.i.d. val. valtozok osszege eloszlasban konvergal a standard normalis eloszlashoz, ha az atlagot $0$-hoz igazitjuk es a szorast lenormaljuk.

## b) Statisztika
### Becslesek es tulajdonsagaik
*Def.:* (likelihood fuggveny)
- diszkret eset
$$
L_{n, \vartheta}(k_{1}, \dots, k_{n}) = \prod_{j=1}^{n}\mathbb{P}_{\vartheta}(Y_{j} = k_{j})
$$

- abszolut folytonos eset
$$
L_{n, \vartheta}(t_{1}, \dots, t_{n}) = \prod_{j=1}^{n}f_{j, \vartheta}(t_{j}) \quad (t_{1}, \dots, t_{n} \in \mathbb{R})
$$

*Def.:* A $\vartheta$ maximum likelihood becslese az $X_{1}, \dots, X_{n}$ mintabol $\hat{\vartheta}$ ha $\hat{\vartheta}$ maximalizalja a $L_{n, \vartheta}(X_{1}, \dots, X_{n})$ fuggvenyt. Ahol $L_{n, \vartheta}$ a minta likelihood fuggvenye.

*pelda:* (normalis eloszlasra)
$$
L_{n, m, \sigma} = \prod_{j=1}^{n}f_{j, m, \sigma} = \prod_{j=1}^{n} \left[  \frac{1}{\sqrt{ 2 \pi \sigma ^{2} }} \exp\left( - \frac{(X_{j} - m)^{2}}{2 \sigma ^{2}} \right)  \right]
$$

*ML becsles tulajdonsagai:*
- nem minden statisztikai mezon letezik
- nem feltetlenul egyertelmu
- nem feltetlenul torzitatlan
- a $g(\vartheta)$ fuggveny ML-becslese $g(\hat{\vartheta})$ ahol $\hat{\vartheta}$ ML-becsles $\vartheta$-ra
- Eros regularitasi feltetelek mellet az ML-becsles aszimptotikusan torzitatlan:
$$
\lim_{ n \to \infty } \mathbb{E}(\hat{\vartheta}) = \vartheta
$$
- Eros regularitasi feltetelek mellet az ML-becsles aszimptotikusan hatasos.
- Gyakran eleg a kovetkezo egyenletet megoldani a ML-becsles megtalalasahoz:
$$
l_{m, \vartheta} = \frac{\partial}{\partial \vartheta} \log L_{m, \vartheta} = 0
$$

*Def.:* (Momentum modszer) Irjuk fel az alabbi egyenleteket a legkisebb olyan $k$-ig, amire az egyenletrendszer egyertelmuen meghatarozza $\vartheta$-t:
$$
\mathbb{E}_{\vartheta}(X_{1}^{m}) = \frac{1}{n} \sum_{j=1}^{n}X_{j}^{m} \quad m = 1, \dots, k
$$
*Momentum modszer tulajdonsagai:*
- nem mindig letezik
- nem mindig egyertelmu
- nem feltetlenul hatasos
- nem feltetlenul torzitatlan

### Torzitatlansag, hatasossag, konzisztencia
*Def.:* A $T$ statisztika torzitatlan becsles $g$-re, ha $\forall \vartheta \in \Theta$-ra
$$
\mathbb{E}_{\vartheta}(T(X_{1}, \dots, X_{n})) = g(\vartheta)
$$

*Def.:* Legyenek $T_{1}, T_{2}$ torzitatlan becslesei $g(\vartheta)$-nek. Azt mondjuk hogy $T_{1}$ hatasosabb $T_{2}$-nel, ha
$$
D_{\vartheta}^{2}(T_{1}) \leq D_{\vartheta}^{2}(T_{2})
$$
teljesul $\forall \vartheta \in \Theta$.

*Def.:* A $T_{1}$ becsles hatasos $g(\vartheta)$-ra, ha torzitatlan, es minden masik torzitatlan becslesnel hatasosabb.

*Def.:* A $T_{n} = T_{n}(X_{1}, X_{2}, \dots, X_{n})$ becslessorozat konzisztens $g(\vartheta)$-ra, ha $\forall \vartheta \in \Theta$-ra
$$
T_{n}(X_{1}, X_{2}, \dots, X_{n}) \to g(\vartheta)
$$
$n \to \infty$ eseten sztochasztikusan.

*All.:* $T_{n}$ konzisztens becslessorozat $g(\vartheta)$-ra ha
$$
\mathbb{E}_{\vartheta}(T_{n}(X)) \to g(\vartheta) \quad \text{es} \quad D_{\vartheta}(T_{n}(X)) \to 0
$$
minden $\vartheta \in \Theta$-ra.
*Biz.:* Azt kell belatni hogy $\forall \varepsilon >0$-ra
$$
\mathbb{P}_{\vartheta}(\lvert T_{n} - g(\vartheta) \rvert > \varepsilon ) \to 0 \quad (n \to \infty)
$$
Az elso feltetel miatt $\forall \varepsilon / 2 > 0$ letezik elegge nagy $n$ melyre $\lvert \mathbb{E}_{\vartheta}(T_{n}(X)) - g(\vartheta) \rvert \leq \varepsilon /2$.
$$
\mathbb{P}_{\vartheta}(\lvert T_{n}(X) - g(\vartheta) \rvert \geq \varepsilon) = \mathbb{P}_{\vartheta}(\lvert T_{n}(X) - \mathbb{E}_{\vartheta}(T_{n}(X)) + \mathbb{E}_{\vartheta}(T_{n}(X)) - g(\vartheta) \rvert \geq \varepsilon )
$$
$$
\leq \mathbb{P}_{\vartheta}(\lvert T_{n}(X) - \mathbb{E}_{\vartheta}(T_{n}(X)) \rvert \geq \varepsilon ) \leq \frac{D^{2}(T_{n}(X))}{(\varepsilon / 2)^{2}}
$$
A masodik feltetel miatt minden eleg nagy $n$-ra a szamlalo legfeljeb $\varepsilon ^{3} /4$, ilyenkor a hanyados legfeljebb $\varepsilon$, amivel belattuk azt amit akartunk.

### Hipotezisvizsgalat
Legyen $(\Omega, \mathcal{A}, \mathcal{P})$ parameteres statisztikai mezo, azaz $\mathcal{P} = \{ \mathbb{P}_{\vartheta}: \vartheta \in \Theta \}$ valamilyen $\Theta$ parameterterrel. $\Theta = \Theta_{0} \cup ^{*} \Theta_{1}$
Nullhipotezis - $H_{0}: \vartheta \in \Theta_{0}$
Ellenhipotezis - $H_{1}: \vartheta \in \Theta_{1}$

Legyen a mintater $B \subseteq \mathbb{R}^{n}$, es ezt is diszjunkt uniora bontjuk: $B = B_{0} \cup ^{*} B_{1}$.
Elfogadasi tartomany: Ha $(X_{0}, \dots, X_{n}) \in B_{0}$ akkor elfogadjuk $H_{0}$.
Elutasitasi (kritikus) tartomany: Ha $(X_{0}, \dots, X_{n}) \in B_{1}$ akkor elutasitjuk $H_{0}$.

Elsofaju hiba: $H_{0}$ igaz de mi elutasitottuk.
Masodfaju hiba: $H_{0}$ nem igaz de mi elfogadtuk.

*Def.:* Egy proba szignifikancia szintje (terjedelme) a legnagyobb valoszinuseg amivel elsofaju hibat vetunk, azaz
$$
\alpha = \sup_{\vartheta \in \Theta_{0}} \mathbb{P}_{\vartheta}(\underline{X} \in B_{1})
$$

*Def.:* Egy proba erofuggvenye annak a valoszinusege hogy elutasitjuk $H_{0}$-t ha az nem igaz, azaz
$$
\beta(\vartheta) = \mathbb{P}_{\vartheta}(\underline{X} \in B_{1}) \quad (\vartheta \in \Theta_{1})
$$

*Def.:* Egy hipotezisvizsgalati feladatban a $p$-ertek a legnagyobb olyan szignifikancia szint, ami mellett $H_{0}$-t elfogadjuk.

Tehat ha $\alpha$ a szignifikancia szint, akkor
- $p < \alpha$ eseten elutasitjuk $H_{0}$-t, azaz szignifikans elteres van $H_{0}$-tol.
- $p \geq \alpha$ eseten elfogadjuk $H_{0}$-t, azaz nincs szignifikans elteres $H_{0}$-tol, tehat nem volt eleg bizonyitek $H_{1}$-re.


### Normalis eloszla parametereire vonatkozo probak
#### z-proba
Normalis eloszlas varhatoertekere vonatkozo proba ismert szoras mellett.
$$
z = \frac{\overline{X} - m_{0}}{\sigma} \sqrt{ n }
$$
- Egyoldali proba
	Ha $z > \Phi ^{-1}(1 - \alpha)$ akkor elvetjuk a nullhipotezist, kulonben elfogadjuk.
	Ilyenkor a $p$-ertek $1 - \Phi(z)$
- Ketoldali proba
	Ha $\lvert z \rvert > \Phi ^{-1}(1 - \alpha / 2)$ akkor elvetjuk a nullhipotezist, kulonben elfogadjuk.
	Ilyenkor a $p$-ertek $2 - 2\Phi(\lvert z \rvert)$

#### t-proba
Normalis eloszlas varhatoertekere vonatkozo probam ismeretlen szoras mellett.
$$
t = \frac{\overline{X} - m_{0}}{s_{n}^{*}} \sqrt{ n }
$$
- Egyoldali proba
	Ha $t > \bar{t}_{n-1, \alpha}$, azaz $p < \alpha$ akkor elutasitjuk a nullhipotezist, kulonben elfogadjuk.
	Ahol $\bar{t}_{n-1, \alpha}$ az $f = n-1$ szabadsagi foku $t$-eloszlas felso $1-\alpha$ kvantilise.

|            | Egy mintas  | Ket mintas      |
| ---------- | ----------- | --------------- |
| Egy oldali | $m < m_{0}$ | $m_{1} < m_{2}$ |
| Ket oldali | $m = m_{0}$ | $m_{1} = m_{2}$ |

#### F-proba
Fuggetlen normalis eloszlasu mintak szorasanak osszehasonlitasara alkalmas proba.
$$
F = \frac{s_{n_{1}}^{*2}}{s_{n_{2}}^{*2}}
$$
Ketoldali proba: $H_{0}: \sigma_{1} = \sigma_{2}$, $H_{1}: \sigma_{1} \neq \sigma_{2}$
	Ha $F > F_{n_{1} - 1, n_{2}-1}$ vagy $1 / F > F_{n_{2}-1, n_{1}-1}$ akkor elvetjuk a nullhipotezist, kulonben elfogadjuk.
	Ahol $F_{f_{1}, f_{2}}$ az $f_{1}, f_{2}$ szabadsagi foku $F$-eloszlas $1 - \alpha / 2$ kvantilise.


### chi^2 probak
#### Illeszkedes vizsgalat
- Tiszta illeszkedes vizsgalat:
$$
H_{0}: \mathbb{P}(A_{k}) = p_{k} \quad \forall k
$$
$$
H_{1}: \exists k: \mathbb{P}(A_{k}) \neq p_{k}
$$
Ha $\chi ^{2} > c_{\text{krit}}$ akkor elutasitjuk $H_{0}$-t. Ahol $c_{\text{krit}}$ az $f= r-1$ szabadsagi foku $\chi ^{2}$-eloszlas $1-\alpha$ kvantilise.

- Becsleses illeszkedes vizsgalat:
$$
H_{0}: \mathbb{P}(A_{k}) = \hat{p}_{k} \quad \forall k
$$
$$
H_{1}: \exists k: \mathbb{P}(A_{k}) \neq \hat{p}_{k}
$$
ahol $\hat{p}_{k}$ a becsult parameterbol szarmazo valoszinuseg.
Ha $\chi ^{2} > c_{\text{krit}}$ akkor elutasitjuk $H_{0}$-t. Ahol $c_{\text{krit}}$ az $f= r - 1 - d$ (a becsult parameter $d$-dimenzios) szabadsagi foku $\chi ^{2}$-eloszlas $1-\alpha$ kvantilise.

probastatisztika:
$$
\chi ^{2} = \sum_{k=1}^{r} \frac{(N_{k} - n \cdot p_{k})^{2}}{n \cdot p_{k}}
$$

#### Fuggetlenseg vizsgalat
$A_{1}, \dots, A_{r}$ es $B_{1}, \dots, B_{s}$ teljes esemenyrendszerek.
$H_{0}$: a ket szempont fuggetlen egymastol, azaz $\mathbb{P}(A_{i} \cap B_{i}) = \mathbb{P}(A_{i}) \cdot \mathbb{P}(B_{i})$ minden $i, j$-re.
$H_{1}$: $\exists i,j$ amire $\mathbb{P}(A_{i} \cap B_{i}) \neq \mathbb{P}(A_{i}) \cdot \mathbb{P}(B_{i})$

probastatisztika:
$$
\chi ^{2} = \sum_{i=1}^{r} \sum_{j=1}^{s} \frac{\left(N_{ij} - \frac{N_{i \cdot} N_{\cdot j}}{n}\right)^{2}}{\frac{N_{i \cdot} N_{\cdot j}}{n}}
$$
A fenti probastatisztika $f = (r-1)(s-1)$ szabadsagi foku $\chi ^{2}$ eloszlashoz tart.
Ha $\chi ^{2} > c_{\text{krit}}$ akkor elutasitjuk $H_{0}$-t, tehat az adatok szignifikans osszefuggest mutatnak.
Ha $\chi ^{2} \leq c_{\text{krit}}$ akkor elfogadjuk $H_{0}$-t, tehat nem talaltunk szignifikans osszefuggest a szempontok kozott.

#### Homogenitas vizsgalat
Van $X_{1}, \dots, X_{n}$ es $Y_{1}, \dots, Y_{m}$ fuggetlen mintank az osszes adatot $r$ diszjunkt osztalyba soroljuk, ahol az $i$-edik osztaly valoszinusege $p_{i}$ az elso mintaban es $q_{i}$ a masodik mintaban. Az elso mintaban az osztalyok gyakorisaga $\nu_{i}$, mig a masodik mintaban az osztalyok gyakorisaga $\mu_{i}$.
$H_{0}$: A ket eloszlas megegyezik, tehat $p_{i} = q_{i}$ minden $i$-re
$H_{1}$: Van olyan $i$ amire $p_{1} \neq q_{1}$

probastatisztika:
$$
\chi ^{2} nm \sum_{i=1}^{r} \frac{\left(  \frac{\nu_{i}}{n} - \frac{\mu_{i}}{m}  \right)^{2}}{\nu_{i} + \mu_{i}}
$$
A fenti probastatisztika $f = r -1$ szabadsagi foku $\chi ^{2}$ eloszlashoz tart.
