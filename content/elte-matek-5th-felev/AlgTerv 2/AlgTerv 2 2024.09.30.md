# Randomizalt algoritmusok
*Soft error:* Annak a valsege, hogy a kovetkezo mikroszekundumban hibazik az algoritmus.
Ennek a tipikus erteke $\frac{1}{2^{55}}$

A kovetkezo feladatot fogjuk nezni:
Legyen $f$ egy $n$ valtozos $\leq d$-ed foku polinom, van egy orakulum megadva amivel barmikor lekerdezhetjuk az $f$ erteket $n$ helyen.

Feladat: Dontsuk el, hogy $f \stackrel{?}{\equiv} 0$

**Scwartz-Zipper-lemma:** Valasszunk $\alpha_{1}, \alpha_{2}, \dots, \alpha_{n} \in \{ 1, 2, 3, \dots, N \}$ ertekeket egyenletesen fuggetlenul.
Ha $f \not\equiv 0$, akkor 
$$
\mathbb{P}(f(\alpha_{1}, \alpha_{2}, \dots, \alpha_{n}) = 0) \leq \frac{d}{N}
$$
*Biz.:*
**Indukcio $n$-re**
Ha $n=1$ akkor $\leq \frac{d}{N}$ az algebra alaptetele miatt, mert legfeljebb $d$ gyoke lehet egy legfeljebb $d$-ed foku polinomnak.

*Indukcios lepes*
$\underline{x} = (x_{1}, \dots, x_{n}), \quad \underline{y} = (x_{2}, \dots, x_{n})$
$$
f(\underline{x}) = h_{0}(\underline{y}) + h_{1}(\underline{y})x_{1} + h_{2}(\underline{y})x_{1}^{2} + \dots + h_{k}(\underline{y})x_{1}^{k}
$$
ugy, hogy $h_{k}(\underline{y}) \not\equiv 0$ akkor $\leq d$
Ha $f(\underline{\alpha}) = 0$ akkor 
$h_{k}(\alpha_{2}, \dots, \alpha_{n}) = 0$ vagy $h_{k}(\alpha_{2}, \dots, \alpha_{n}) \neq 0$ de $f(\underline{\alpha}) = 0$

i) $\mathbb{P}(h_{k}(\alpha_{2}, \dots, \alpha_{n})=0) \leq \frac{d-k}{N}$

ii) Tetszolegesen lefixaljuk az $\alpha_{2}, \dots, \alpha_{n}$ szamokat ugy, hogy $h_{k}(\alpha_{2}, \dots, \alpha_{n}) \neq 0$.
Az az eset amikor $h_{k}(\alpha_{2}, \dots, \alpha_{n}) = 0$ azt neztuk az i) esetben.
$f$-be behelyettesitjuk ezeket 
Minket az erdekel hogy $f(\alpha_{1}, \alpha_{2}, \dots, \alpha_{n})$ mikor lesz $0$.
$$
f(\alpha_{1}, \alpha_{2}, \dots, \alpha_{n}) = h_{0} + h_{1} \cdot x_{1} + h_{2} \cdot x_{1}^{2} + \dots + h_{k} \cdot x_{1}^{k}
$$
az $x_{1} = \alpha_{1}$ helyen, ahol $h_{i} = h_{i}(\alpha_{2}, \alpha_{3}, \dots, \alpha_{n})$
$x_{1}$ egyvaltozos $k$-ad foku polinomja, ebbol kovetkezik, hogy
$$
\mathbb{P}(f(\alpha_{1}, \dots, \alpha_{n}) = 0) \leq \frac{k}{N}
$$

# Algoritmus
Legyen $N := 2d$
sorsolunk veletlen fuggetlen $\alpha_{i}$-ket es behelyettesitjuk $f$-be es ha $0$-at kapunk akkor a valasz az hogy $f\equiv 0$ kulonben $f \not\equiv 0$

**All.:**
- Ha $f\equiv{0}$  akkor biztosan nem tevedunk.
- Ha $f \not\equiv 0$ akkor legfeljebb $\frac{1}{2}$  valoszinuseggel rossz valaszt fogunk adni.

*Ötlet:* Futtassuk leg $t$-szer az algorimust es ha egyszer is $0$-tol kulonbozo erteket kaptunk akkor a valasz $\not\equiv 0$ kulonben $\equiv 0$

**All.:** 
- Ha $f \equiv 0$ akkor bizotsan nem tevedunk.
- Ha $f \not\equiv 0$ akkor annak a valoszinusege, hogy hibazunk az legfeljebb $1/2^{t}$.


**Alkalmazas:**
$G = (L \cup U, E)$ paros graf ahol $\lvert L \rvert = \lvert U \rvert = n$ es el szeretnenk donteni, hogy van-e teljes parositas.

Legyen $M \in \mathbb{R}^{n \times n}$  aminek az elemei lehetnek akar valtozok is, ahol
$$
M(i, j) = \begin{cases}
x_{ij}  &  \text{ha } l_{i}u_{j} \in E \\
0  &  \text{kulonben}
\end{cases}
$$

**All.:** $\det M$ egy $\lvert E \rvert = m$ valtozos $n$-ed foku polinom.

**Tetel:** Letezik $G$-ben teljes parositas $\iff$ $\det M \not\equiv 0$ 
$\alpha_{i} \in \{ 1, \dots, 2n \}$ 
Vegyuk eszre, hogy ha van egy nem $0$ kifejtesi tag, akkor tudjuk hogy a grafban letezik teljes parositas.
Forditva is igaz, hogy ha letezik egy teljes parositas akkor letezik egy nem $0$  kifejtesi tag.

(megj.: a matrixban egy permutacio megad egy teljes parositast)

**All.:**
- Ha nem letezik teljes parositas, akkor $\det M \equiv 0$ tehat biztosan jo valaszt adunk.
- Ha letezik teljes parositas, akkor legfeljebb $\frac{1}{2}$ valseggel adunk rosz valaszt.


# Min Vagas
$G = (V, E), \quad \lvert V \rvert = n, \quad \lvert E \rvert = m$   multigraf
Vagas: $V = A \cup B, \quad A \neq \emptyset, \; B\neq \emptyset$
Vagas erteke: azoknak az eleknek a szama amelyeknek az egyik vege $A$-ban a masik $B$-ben van.
Cel: minimalis vagas erteke.

Osszehuzas muvelet: $u$ es $v$ csucsokat osszehuzom ha van koztuk el, az osszehuzott csubol azok az elek mennek mint amik $u$ bol es $v$ bol mentek.
jeloles `G/uv`

# Karker algoritmus
```
Krger(G, n):
	IF n > THEN
		uv in E veletlen
		KARGER (G/uv, n-1)
	RETURN (|E|)
```

**Tetel:** Tegyuk fel, hogy $(A, B)$ egy minimalis vagas $c$ ertekkel. Ekkor
$$
\mathbb{P}(\text{Karger algoritmus ezt adja ki}) \geq \frac{1}{n \choose 2}
$$
*Def.:* Azt monmdjuk, hogy $(A, B)$ tulel egy $uv$ osszehuzast, ha $u, v \in A$ vagy $u, v \in B$

$$
\mathbb{P}(\text{elso osszehuzasnal } (A, B) \text{ tulel}) \geq \left( 1 - \frac{2}{n} \right)
$$
A fentibel a valseg-ben $1 - \frac{c}{m}$

**All.:** $m \geq \frac{cn}{2}$, mert minden csucsa foka $\geq c$.

$$
\mathbb{P}(\text{i. osszehuzasnal } (A, B) \text{ tulel } \vert \text{ meg el}) \geq \left( 1 - \frac{2}{n+1-i} \right)
$$
$$
\mathbb{P}(\text{vegig tulel}) \geq \prod \left( 1 - \frac{2}{n+1-i} \right) = \frac{n-2}{n} \cdot \frac{n-3}{n-1} \cdot \ldots \cdot \frac{3}{5} \cdot \frac{2}{4} \cdot \frac{1}{3} = \frac{2}{n(n-1)} = \frac{1}{n \choose 2}
$$


Ismeteljuk meg $n^{2} \log n$ -szer az algorimust. Ekkor
$$
\mathbb{P}(\text{a legjobb} > \min) \leq \left( 1 - \frac{1}{n^{2}} \right)^{n^{2}\log n} \approx \frac{1}{n}
$$



