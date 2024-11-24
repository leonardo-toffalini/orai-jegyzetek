date: 2024.05.13

### Sajátérték-feladatok közelítő megoldása
*Emlék:* Azt mondjuk, hogy az $A \in \mathbb{C}^{n \times n}$ mátrixnak a $\lambda \in \mathbb{C}$ szám sajátértéke, ha $\exists \underline{v} \in \mathbb{C}^{n}, \; \underline{v} \neq \underline{0}$ úgy, hogy $A\underline{v} = \lambda \underline{v}$. Ekkor $\underline{v}$ neve: sajátvektor.

Jelölje $\sigma(A)$ az $A$ mátrix sajátértékeinek a halmazát.

$$
\lambda \in \sigma(A) \iff \det(A - \lambda I) = 0
$$
A fenti egyenletnek a jobboldalát a karakteriszikus egyenletnek hívjuk, ami egy $n$-ed fokú egyenlet. Ha $n > 4$, akkor nem létezik már megoldóképlet. Tehát ha $n > 4$, akkor iterációs módszert kell felépítenünk és így csak közelítő megoldást kapunk.

Az egyszerűség kedvéért a továbbiakban feltesszük, hogy minden a valós számok fölött van. A komplex számokra a kiterjesztést egyszerűen meg lehet oldani, ha már a valósokra tudjuk a dolgokat.

Először tegyük fel, hogy ismerjük az $A \in \mathbb{R}^{n \times n}$ mátrix $\underline{v}$ sajátvektorának egy közelítését: $\tilde{\underline{v}}$. Ekkor, hogyan tudjuk meghatározni a hozzátartozó $\lambda$ sajátértéket?

1. lehetőség: $A \tilde{\underline{v}} \approx \lambda \tilde{\underline{v}}$
$$
\begin{bmatrix}
A
\end{bmatrix} \cdot
\begin{bmatrix}
\tilde{v_{1}} \\
\tilde{v_{2}} \\
\vdots \\
\tilde{v_{n}}
\end{bmatrix}
\approx
\lambda \cdot 
\begin{bmatrix}
\tilde{v_{1}} \\
\tilde{v_{2}} \\
\vdots \\
\tilde{v_{n}}
\end{bmatrix}
$$
ezzel ekvivalens a következő
$$
a_{i 1} \cdot \tilde{v}_{1} + a_{i 2} \cdot \tilde{v}_{2} + \dots a_{i n} \cdot \tilde{v}_{n} = \lambda \cdot \tilde{v}_{i} \quad i = 1, \dots, n
$$

Ha $\tilde{v}_{i} \neq 0$ akkor $\lambda$ az $i$. egyenletből kifejezhető ($\tilde{v} \neq 0 \implies$ legfeljebb egy $i$-re $\tilde{v}_{i} \neq 0$)

Vagy: a többiből/összesből kifejezve átlagolunk

2. lehetőség: $A \tilde{\underline{v}} \approx \lambda \tilde{\underline{v}}$
Szorozzuk meg mindkét oldalt skalárisan $\tilde{\underline{v}}$-al. Ekkor a következőt kapjuk:
$$
(\tilde{\underline{v}}, A \tilde{\underline{v}}) \approx \lambda (\tilde{\underline{v}}, \tilde{\underline{v}})
$$
$$
\lambda \approx \frac{(\tilde{\underline{v}}, A \tilde{\underline{v}})}{(\tilde{\underline{v}}, \tilde{\underline{v}})}
$$
***Kérdés:*** Melyiket alkalmasabb használni a fenti két lehetőségből?

#### Állítás
Legyen $\underline{x} \in \mathbb{R}^{n}, \; \underline{x} \neq \underline{0}, \; A \in \mathbb{R}^{n \times n}$ Ekkor
$$
\min_{\alpha \in \mathbb{R}} \| A \underline{x} - \alpha \underline{x} \| _{2}^{2} = \| A\underline{x} - R(\underline{x}) \cdot \underline{x} \| _{2}^{2}
$$
ahol $R(\underline{x})$ a következő kifejezés
$$
R(\underline{x}) = \frac{(\underline{x}, A\underline{x})}{(\underline{x}, \underline{x})}
$$
*Bizonyítás:*
$$
\| A\underline{x} - \alpha \cdot \underline{x} \| _{2}^{2} = (A\underline{x} - \alpha \cdot \underline{x}, \; A\underline{x} - \alpha \cdot \underline{x}) = (A\underline{x}, A\underline{x}) - 2\alpha(\underline{x}, A\underline{x}) + \alpha ^{2}(\underline{x}, \underline{x})
$$

Ez a kifejezés $\alpha$-ban egy másodfokú polinoma, azaz egy parabola. Mivel $(\underline{x}, \underline{x})$ a főeggyütható, amely nem mindig pozitív, mert $\underline{x} \neq 0$, ezért ennek a másodfokú polinomnak minimuma van, ami ott felvétetik, ahol a deriváltja $0$.

Deriváljunk $\alpha$ szerint:
$$
-2(\underline{x}, A\underline{x}) + 2\alpha (\underline{x}, \underline{x}) = 0
$$
$$
\implies \alpha = \frac{(\underline{x}, A\underline{x})}{(\underline{x}, \underline{x})}
$$

#### Definíció
Legyen $\underline{x} \in \mathbb{R}^{n}, \; x \neq \underline{0}, \; A \in \mathbb{R}^{n \times n}$. Ekkor a következő számot az $\underline{x}$ vektorhoz tartozó Rayleigh-hányadosnak nevezzük:
$$
R(\underline{x})= \frac{(\underline{x}, A\underline{x})}{(\underline{x}, \underline{x})}
$$

*Megjegyzés:* Ha $\| \underline{x} \|_{2} = 1$, akkor $R(\underline{x}) = (\underline{x}, A\underline{x})$, mert $(\underline{x}, \underline{x}) = \| \underline{x} \|^{2} = 1^{2} = 1$.

*Következmény:* Ha $\tilde{\underline{v}} \approx \underline{v}$, akkor a $\underline{v}$-hoz tartozó sajátértéket $R(\tilde{\underline{v}})$-vel érdemes kövezelíteni.


### A hatványmódszer
A gyakorlatban általában nem tudjuk egyik sajátvektort sem, akár közelítőleg sem és így kell meghatároznunk a sajátvektorokat és sajátértékeket.

Legyen $A \in \mathbb{R}^{n \times n}$ $\lambda_{i} \in \mathbb{R}$ $(i = 1, \dots, n)$ sajátértékekkel. Tegyük fel, hogy $A$-nak van egyszeresen domináns sajátértéke, azaz
$$
\lvert \lambda_{1} \rvert  > \lvert \lambda_{2} \rvert \geq \lvert \lambda_{3} \rvert  \geq \lvert \lambda_{4} \rvert  \geq \dots \geq \lvert \lambda_{n} \rvert 
$$

A következő módszer, amit bemutatunk ennek az egyszeresen domináns $\lambda_{1}$ sajátértéknek a meghatorázására fog szolgálni.

Tegyük fel, hogy $A$ normális, azaz kommutál a transzponáltjával, vagy komplex esetben az adjungáltjával, azaz $A \cdot A^{T} = A^{T} \cdot A$. Ekkor van ortonormált sajátvektorendszere. Azaz lehet mondani $n$ darab sajátvektort, melyekre mindegyik hossza $1$ és páronként egymásra merőlegesek.

$$
\underline{v}_{1}, \underline{v}_{2}, \dots, \underline{v}_{n}
$$
ahol $\lambda_{i}$ sajátértékhez tartozó sajátvektor a $\underline{v}_{i}$

Legyen $\underline{x} \in \mathbb{R}^{n}$ olyan kezdővektor, amelynek van $\underline{v}_{1}$ irányú komponense, azaz a következő előállításban $\alpha_{1} \neq 0$
$$
\underline{x} = \alpha_{1} \cdot \underline{v}_{1} + \alpha_{2} \cdot \underline{v}_{2} + \dots + \alpha_{n} \cdot \underline{v}_{n}
$$

$$
\begin{align*}
A^{k}\underline{x} &= A^{k}(\alpha_{1} \cdot \underline{v}_{1} + \alpha_{2} \cdot \underline{v}_{2} + \dots + \alpha_{n} \cdot \underline{v}_{n}) \\
&= \alpha_{1} \cdot A^{k}\underline{v}_{1} + \alpha_{2} \cdot A^{k}\underline{v}_{2} + \dots + \alpha_{n} \cdot A^{k}\underline{v}_{n} \\
&= \alpha_{1} \cdot \lambda_{1}^{k} \underline{v}_{1} + \alpha_{2} \cdot \lambda_{2}^{k}\underline{v}_{2} + \dots + \alpha_{n} \cdot \lambda_{n}^{k}\underline{v}_{n} \\
&= \lambda_{1}^{k} \left( \alpha_{1} \cdot \underline{v}_{1} + \alpha_{2} \cdot \left( \frac{\lambda_{2}}{\lambda_{1}} \right)^{k} \underline{v}_{2} + \dots + \alpha_{n} \cdot \left( \frac{\lambda_{n}}{\lambda_{1}} \right)^{k} \underline{v}_{n} \right)
\end{align*}
$$

Mivel $\lambda_{1}$ a legnagyobb abszolútértékben, ezért a $\left( \frac{\lambda_{i}}{\lambda_{1}} \right)$ kifejezések egyre kisebbek abszolútértékben, ezért a $k$-adik hatványik tart $0$-hoz, ha $k$-val tartunk $\infty$-hez.

Ha $k$-t növeljük, akkor $A^{k}\underline{x}$ vektor egyre inkább a $\underline{v}_{1}$ vektor irányába fog mutatni. Tehát egyre jobb közelítése lesz egy $\lambda_{1}$-hez tartozó sajátvektornak.

Ha $\lambda_{1} \neq \pm 1$ akkor $\lambda_{1}^{k} \to 0$ vagy $\infty$-hez tehát számítógépen előbbútóbb alul- vagy túlcsordulás fog fellépni. Elkerülésére a kapott vektort minden lépésben normáljuk. Jelölésben $\underline{y}^{(k)}$

A megfelelő sajátértéke közelítése:
$$
\nu ^{(k)} := R(\underline{y}^{(k)}) = (\underline{y}^{(k)}, A\underline{y}^{(k)})
$$

***Kérdés:*** Hogyan lehet meghatározni egyéb sajátértékeket és sajátvektorokat?

*például:* A legkisebb abszolót értékűt?

*Emlék:* Tegyük fel, hogy $0 \not \in \sigma(A)$, azaz invertálható az $A$ mátrix, ekkor $\frac{1}{\lambda} \in \sigma(A^{-1})$ mivel
$$
\lambda \in \sigma(A) \implies \exists \underline{x} \neq \underline{0}
$$
$$
\begin{align*}
A\underline{x} &= \lambda \underline{x} \\
\underline{x} &= \lambda A^{-1}\underline{x} \\
\frac{1}{\lambda}\underline{x} &= A^{-1}\underline{x}
\end{align*}
$$

$$
\lvert \lambda \rvert \geq \lvert \lambda_{2} \rvert \geq \dots \geq \lvert \lambda_{n} \rvert \implies \left\lvert  \frac{1}{\lambda_{n}}  \right\rvert \geq \dots \geq \left\lvert  \frac{1}{l_{1}}  \right\rvert
$$

Tehát $\lambda_{n}$ meghatározható, ha $A^{-1}$ mátrixra alkalmazzuk a hatványmódszert, mivel $A^{-1}$ domináns sajátértéke $\frac{1}{\lambda_{n}}$

***Kérdés:*** És a többi sajátértéket hogyan határozzuk meg?

Tegyük fel, hogy $\mu \not \in \sigma(A)$. Ekkor $\det(A - \mu I) \neq 0 \implies \exists (A - \mu I)^{-1}$ 

Legyen $\underline{x}$ sajátvektora $A$-nak, tehát 
$$
A\underline{x} = \lambda_{i} \underline{x} \implies (A - \mu I)\underline{x} = A\underline{x} - \mu \underline{x} = \lambda_{i} \underline{x} - \mu \underline{x} = (\lambda_{i} - \mu)\underline{x}
$$

Tehát ha van egy $\underline{x}$ sajátvektor $\lambda_{i}$ sajátértékkel, akkor $\underline{x}$ sajátvektroa $(A - \mu I)$ mátrixnak is $(\lambda_{i} - \mu)$ sajátértékkel.

Tehát a $(A - \mu I)^{-1}$ mátrix sajétértékeit: $\frac{1}{\lambda_{i} - \mu}$ ahol $i = 1, \dots, n$

Tegyük fel, hogy $A$-nak a $\mu$-höz legközelebbi sajátértéke $\lambda_{j}$. Ekkor az $(A - \mu I)^{-1}$ mátroxnak a domináns sajátértéke a következő
$$
\frac{1}{\lambda_{j} - \mu}
$$

Ezt a domináns sajátértéket már meg tudjuk találni a hatványmódszerrel, ha az $(A - \mu I)^{-1}$ mátrixra alkalmazzuk. Ezt a módszert inverz iterációnak nevezik.

***Kérdés:*** Mennyire számításigényes a fenti módszer?

A $k.$ lépésben
$$
\underline{x}^{(k)} = (A - \mu I)^{-1} \underline{y}^{(k - 1)} \leftrightarrow (A - \mu I)\underline{x}^{(k)} = \underline{y}^{(k-1)}
$$

A fenti egy lináris algebrai egyenletrendszer, amire már tanultunk megoldási módszereket.









related: [[NumMod 1]]