date: 2024.02.06

$(\Omega, \mathscr{A}, \mathcal{P})$ parameters statisztikai mezo, $\mathcal{P} \{ \mathbb{P}_{\vartheta} : \vartheta \in \Theta \}$
$(X_{1}, X_{2}, \dots, X_{n})$ minta
1) A $T(X_{1}, X_{2}, \dots, X_{n})$ becsles torzitatlan ha varhato erteke $g(\vartheta)$
2) $T_{1}, T_{2}, \dots$ becslesek sorozata konzisztens a $g(\vartheta)$-ra, ha $T_{n}(\vartheta) \to g(\vartheta), \quad n \to \infty$ eseten stochasztikusan $\forall \vartheta \in \Theta$.

*peldak*:
1) Egy $A$ esemeny $g(\vartheta) = \mathbb{P}_{\vartheta}(A)$ valoszinusegere torzitatlan es konzisztens becsles. 
$$
\frac{\mathbb{1}_{1}(A) + \mathbb{1}_{2}(A) + \dots + \mathbb{1}_{n}(A)}{n}
$$
azaz a relativ gyakorisag a konzisztens a nagy szamok gyenge torvenyebol kovetkezoen.

2) A minta $g(\vartheta) = \mathbf{E}_{\vartheta}(X_{1})$ varhato ertekere $\overline{X}$ torzitatlan es konzisztens (ugyanugy a nagy szamok gyenge torvenye alapja)

4) $X_{1}, X_{2}, \dots, X_{n} \sim \text{ Poisson}(\lambda)$
$\lambda$-nak $\overline{X}$ torzitatlan es konzisztens becslese

4) normalis eloszas: $N(m, \sigma ^{2})$
- $m$-re: $\overline X$ torzitatlan es konzisztens
- $\sigma$-ra: $s_{n}^{*2}$ es $s_{n}^{2}$ konzisztensek, de nem torzitatlanok!
- $\sigma ^{2}$-re: torzitatlan $s_{n}^{*2}$ korrigalt tapasztalati szorasnegyzet
$$
s_{n}^{*2} = \frac{1}{n-1}\sum_{j=1}^{n}(X_{j} - \overline X)^{2} \text{ ez konzisztens}
$$
$$
s_{n}^{2} = \frac{1}{n}\sum_{j=1}^{n}(X_{j} - \overline X)^{2} \text{ ez is konzisztens}
$$

5) Exponencialis eloszlas
surusegfuggveny: $f(x) = \lambda e^{-\lambda x} \cdot \mathbb{1}(x > 0)$, $\mathbf{E}_{\lambda}(X_{1}) = \frac{1}{\lambda}$
$\lambda$-ra konzisztens de nem toriztatlan becsles: $\frac{1}{\overline X}$.

6) $(n + 1) \min \{ X_{1}, X_{2}, \dots, X_{n} \}$ torzitatlan de nem konzisztens


### Maximum likelihood módszer
*pelda*:
1) 
jo tolot $p = 0.9$ valseggel mukodik minden kiprobalasnal
rossz tolto $p = 0.2$ valseggel mukodik minden kiprobalasnal

kivalasztunk egyet es kiprobaljuk $10$-szer.
Adat: $10$-bol $8$-szor mukodott.

$$
\mathbb{P}_{0.9} =  {10 \choose 6}0.9^{8}0.1^{2}
$$

2) 
egy toltonel minden kiprobalasnal a tobbitol fuggetlenul $0 < p < 1$ valseggel mukodik.
minta: $10$-bol $8$-szor mukodott

$$
\mathbb{P}_{p} = {10 \choose 8}p^{8}(1-p)^{2}
$$
A maximum likelihood becsles az a $p$, amire ez az ertek a leheto legnagyobb.

Poisson eloszlas $X_{1}, X_{2}, \dots, X_{n} \sim \text{ Poisson}(\lambda)$ 
$$
n = 95, \quad \sum_{j=1}^{95}X_{j}=131
$$
$$
\mathbb{P}_{\lambda}(X_{1} = 3, \dots, X_{95} = 2) = \prod_{j=1}^{95}\mathbb{P}_{\lambda}(X_{j} = k_{j}) = \frac{e^{-95\lambda}\lambda ^{\sum_{j=1}^{95}k_{j}}}{\prod_{j=1}^{95}k_{j}!} = \frac{e^{-95\lambda}\lambda ^{131}}{\prod_{j=1}^{95}k_{j}!}
$$
***Q***.: milyen $\lambda$-ra lesz ez maximalis?

*Otlet*: A log likelihood fuggvenyt derivaljuk mert osszeget konyebb mint szorzatot derivalni.
$$
\log L_{n, \lambda} = \log \left(\frac{e^{-95\lambda}\lambda ^{131}}{\prod_{j=1}^{95}k_{j}!}\right) = 131 \log\lambda - 95 - \log {\prod_{j=1}^{95}k_{j}!}
$$
$$
(\log L_{n, \lambda})' = \frac{131}{\lambda} - 95 = 0 \iff \lambda = \frac{131}{95} = \overline X
$$
$$
(\log L_{n, \lambda})'' = -\frac{131}{\lambda ^{2}} < 0 \implies \text{ lokalis szelsoertek}
$$
$$
\implies \hat{\lambda} = \overline X \text{ a maximum likelihood becsles}
$$
***Def***.: $(\Omega, \mathscr A, \mathcal P)$ parameteres statisztikai mezo. A $\vartheta$ parameter *maximum likelihood becslese* (MLE-je) az a $\hat{\vartheta}$, amire $\theta \mapsto L_{n, \vartheta}(X_{1}, X_{2}, \dots, X_{n})$ likelihood fuggveny maximalis.

*pelda*:
$X_{1}, X_{2}, \dots, X_{n}$ egyenletes eloszlasu az $[a, b]$ intervallumon.
$$
L_{n, a, b} (X_{1}, X_{2}, \dots, X_{n}) = \prod_{j = 1}^{n}f_{a,b}(X_{j}) = \prod_{j=1}^{n} \frac{1}{b-a} \cdot \mathbb{1}(a \leq X_{j} \leq b) = \frac{1}{(b-a)^{n}}\cdot \mathbb{1}(a \leq X_{1}, \dots, X_{n} \leq b)
$$

*kell*: $a, b$ amire ez a legnagyobb.

$$
\implies a = \min \{ X_{j} \}, \quad b = \max \{ X_{j} \}
$$
### MLE tulajdonsagai
- Nem mindig letezik
- Nem feltetlenul egyertelmu
- $g(\vartheta)$ MLE-je $g(\hat{\vartheta})$
- Az MLE-k elegseges statisztika fuggvenye, azaz, ha $T$ elegseges, $\hat{\vartheta} = h(T(X_{1}, X_{2}, \dots X_{n}))$ alaku.
- Megfelelo feltetelek (eros regularitasi feltetelek) mellett:
	- aszimptotikusan torzitatlan, tehat: $\lim_{ n \to \infty } \mathbf{E}(\hat{\vartheta}) \to \vartheta$
	- aszimptotikusan hatasos
	- aszimptotikusan normalis eloszlasu, pontosabban, $\sqrt{ n }(\hat{\vartheta} - \vartheta)$ normalis eloszlashoz konvergal eloszlasban
- Ha MLE nem letezik, gyakran a $\left(\log L_{n, \vartheta}(X_{1}, X_{2}, \dots, X_{n})\right)' = 0$ egyenlet megoldasat hasznaljak

### Momentum modszer
***Def***.: Az $X$ valoszinusegi valtozo $k$-adik momentuma: $\mathbf{E}(X^{k})$, ha ez letezik.

$(\Omega, \mathscr A, \mathcal P)$ parameteres statisztikai mezo, $\mathbf{E}_{\vartheta}(X_{1}^{k})$ $k$-adik momentum.
A minta $k$-adik tapasztalati momentuma:
$$
\frac{1}{n}\sum_{j=1}^{n}X_{j}^{k}
$$
A momentum modszer egyenletrendszere:
$k = 1$
$$
\frac{1}{n}\sum_{j=1}^{n}X_{j} = \overline X = \mathbf{E}_{\vartheta}(X_{1})
$$
$k=2$
$$
\frac{1}{n}\sum_{j=1}^{n}X_{j}^{2} = \mathbf{E}_{\vartheta}(X_{1}^{2})
$$
$k = k$
$$
\frac{1}{n}\sum_{j=1}^{n}X_{j}^{k} = \mathbf{E}_{\vartheta}(X_{1}^{k})
$$
Addig folytatjuk ameddig a $k$-adik egyenletig nem kapunk egyertelmu megoldast.

*pelda*:
1) Poission$(\lambda)$
$$
\overline X = \mathbf{E}_{\lambda}(X_{1}) = \lambda
$$
$$
\implies \hat{\lambda} = \overline X
$$
2) Normalis eloszlas
$$
\overline X = \mathbf{E}_{m, \sigma}(X_{1}) = m
$$
$$
\frac{1}{n}\sum_{j=1}^{n}X_{j}^{2} = \mathbf{E}_{m, \sigma}(X_{1}^{2}) = m^{2} + \sigma ^{2}
$$
$$
\implies \sigma ^{2} = \frac{1}{n}\sum_{j=1}^{n} X_{j}^{2} - (\overline X)^{2} = s_{n}^{2}
$$
$$
\implies (\hat{m}, \hat{\sigma}) = (\overline X, s_{n})
$$
3) exponencialis eloszlas
$$
\overline X = \mathbf{E}_{\lambda}(X_{1}) = \frac{1}{\lambda}
$$
$$
\implies \hat{\lambda} = \frac{1}{\overline X}
$$


