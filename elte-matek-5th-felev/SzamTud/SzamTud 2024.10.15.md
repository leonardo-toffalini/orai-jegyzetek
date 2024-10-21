*Def.:* A $T$ nem determinisztikus Turing-gep a $(k, \Sigma, \Gamma, \Phi)$ negyesen, ahol $k, \Sigma, \Gamma$ ugyanaz mint a rendes Turing-gepnel.
$$
\Phi \subseteq (\Sigma ^{k} \times \Gamma) \times (\Sigma ^{k} \times \Gamma \times \{ -1, 1, 0 \}^{k})
$$
$\Phi$ valtozo az ugynevezett *atmenetrelacio*.
Ha $T$ a $g$ allapotban a $b = (b_{1}, \dots, b_{k})$ betuket olvassa, ezutan $g'$ allapotba kerul, a $b'$ betuket irja, es a fejek $\varepsilon \in \{ -1, 0, +1 \}^{k}$ iranyokva mozognak, akkor megengedett (legalis) egy lepes, ha $((b, g), (b', g', \varepsilon)) \in \Phi$.
Azt mondjuk, hogy a $T$ nemdeterminisztikus Turing-gep $t$ lepesben elfogad egy inputut, ha letezik megengedett lepeseknek olya $t$ hosszu sorozata, amely vegen megall, es kiirja, hogy $1$.

*pelda:* G3C (graf szinezheto-e 3 szinnel) felismerese megy linearis idoben nemdeterminisztikus Turing-geppel.
$$
\text{G2C} = \{ G : \chi(g) \leq 2 \} \in P
$$
$$
\text{Hamilton} = \{ G : G\text{-nek van Hamilton kore} \}
$$

*Def.:*  $L \in \text{NTIME}(f(n))$ ha $L$-hez letezik $T$ nemdeterminisztikus Turing-gep, amely $L$-et felismeri $f(\lvert w \rvert)$ lepesben, minden mast elutasit.

*Def.:* $L \in \text{NSPACE}(f(n))$ ha $L$-hez letezik $T$ nemdeterminisztikus Turing-gep, amely felismeri $L$-et $f(\lvert w \rvert)$ tarban, minden mast elutasit.

$$
\begin{align}
\text{NP} &=\bigcup_{i=0}^{\infty} \text{NTIME} \left(n^i\right) \\ \\
\text{NPSAPCE} &=\bigcup_{i=0}^{\infty} \text{NSPACE} \left(n^i\right)
\end{align}
$$

*Def.:* Azt mondjuk, hogy a $w \in \Sigma_0^*$-nek az $L$ beli tagságára az $y$ szó polinomiális tanú, ha $L$-hez van olyan $T$ (determinisztikus) Turing-gep, hogy $w \in L \iff T$ elfogadja a $(w, y)$ párt $|w|$-ben polinomiális idóben.

*Tetel:* $L \in \text{NP} \iff L$-nek van polinomialis tanuja.
*Biz.:* 
$\implies$ Adott $w \in L$ eseten legye $y$ a $T$ nemdeterminisztikus Turing-gep elfogado lepeseinek sorozata.
Adjunk meg egy $w$ inputot, a $T$ leirasat, es az $y$ elfogado lepesek sorozatat egy Turing-gepnek ami ellenorzi hogy $y$ valoban elfogado lepesek sorozata-e.
$\impliedby$ Legyen $T$ egy nemdeterminisztikus Turing-gep
- nemdeterminisztikus fazis: folir egy $y \in \Sigma_{0}^{*}$ szot, ahol $\lvert y \rvert \leq \lvert w \rvert^{c}$
- determinisztikus faizs: ellenorzi, hogy $w, y$ jo-e, azaz $y$ valoban polinomialis tanu-e $w$-hez

*Def.:*
$$
L \in \text{co-NP} \iff \Sigma_{0}^{*}-L \in \text{NP}
$$

*Tetel:* (Pratt, 1975) $\text{PRIM} \in \text{NP}$
*Biz.:* jegyzet 18. oldal alja





