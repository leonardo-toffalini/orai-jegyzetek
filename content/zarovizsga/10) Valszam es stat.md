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
diszkret eset:
$$
\mathbb{E}[X] = \sum_{j = 1}^{\infty}x_{j} \cdot \mathbb{P}(X = x_{j})
$$

abszolut folytonos eset:
$$
\mathbb{E}[X] = \int _{-\infty}^{\infty}x \cdot f(x) \, dx 
$$

### Szoras
$$
D^{2}[X] = \mathbb{E}[(X - \mathbb{E}[X])^{2}] = \mathbb{E}[X^{2}] - \mathbb{E}[X]^{2}
$$
$$
D[X] = \sqrt{ D^{2}[X] }
$$

### Kovariencia
$$
\begin{align}
\operatorname{cov}(X, Y) & =\mathrm{E}[(X-\mathrm{E}[X])(Y-\mathrm{E}[Y])] \\
& =\mathrm{E}[X Y-X \mathrm{E}[Y]-\mathrm{E}[X] Y+\mathrm{E}[X] \mathrm{E}[Y]] \\
& =\mathrm{E}[X Y]-\mathrm{E}[X] \mathrm{E}[Y]-\mathrm{E}[X] \mathrm{E}[Y]+\mathrm{E}[X] \mathrm{E}[Y] \\
& =\mathrm{E}[X Y]-\mathrm{E}[X] \mathrm{E}[Y] .
\end{align}
$$

### Korrelacios egyutthato
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
*Megj.:* mm. $\centernot{\implies}$ $L^{p}$ es $L^{p}$ $\centernot{\implies}$ mm.

### Nagy szamok torvenye
*Def.:* 
$$
\limsup A_{n} = \bigcap_{n=1}^{\infty} \bigcup_{k = n}^{\infty} A_{k}
$$

*Tetel:* (Borel-Cantelli-lemma)
- Ha $\sum \mathbb{P}(A_{n}) < \infty$ akkor $\mathbb{P}(\limsup A_{n}) = 0$
Ha az esemenyek valoszinusegenek osszege veges, akkor annak a valoszinusege hogy vegtelen sok megortenik az $0$.

- Tegyuk fel, hogy az $A_{n}$ esemenyek fuggetlenek. Ekkor $\sum \mathbb{P}(A_{n}) = \infty$ eseten $\mathbb{P}(\limsup A_{n}) = 1$
Ha a fuggetlen esemenyek valoszinusegenek osszege vegtelen, akkor annak a valoszinusege hogy vegtelen sok megtortenik az $1$.

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

*Biz.:* TODO

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
### Torzitatlansag, hatasossag, konzisztencia
### Hipotezisvizsgalat
### Normalis eloszla parametereire vonatkozo probak
### chi^2 probak
