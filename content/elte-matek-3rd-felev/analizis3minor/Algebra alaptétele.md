#tétel-biz 

***Tétel***: $p(z) = a_{0} + a_{1}z + a_{2}z^{2} + \dots + a_{n} z^{n}$, $n\ge 1$, $a_{n}\ne_{0}$, $a_{j} \in \mathbb{C} \implies \exists \alpha \in\mathbb{C}: p(\alpha) = 0$

***Biz***.: Indirekt, tegyük föl, hogy $\nexists \alpha \in \mathbb{C}: p(\alpha) =0, p \neq 0$
$p \in \mathcal{O}(\mathbb{C}) \implies f(z) = \frac{1}{p} \in \mathcal{O}(\mathbb{C})$

***Áll***.: $f$ korlátos.
***Biz***.: $p(z) = z^{n}\left( a_{n} + \frac{a_{n-1}}{z} + \frac{a_{n-2}}{z^{2}} + \dots + \frac{a_{0}}{z^{n}} \right)$
Ha $\lvert z \rvert \to \infty \implies \left\lvert  \frac{a_{n-1}}{z}  \right\rvert \to 0 \implies \frac{a_{n-1}}{z}\to_{0}$
Ha $\lvert z \rvert\to \infty \implies \left\lvert  \frac{a_{n-2}}{z^{2}}  \right\rvert \to 0 \implies   \frac{a_{n-2}}{z^{2}}   \to 0$
$\vdots$
Ha $\lvert z \rvert\to \infty\implies \left\lvert  \frac{a_{0}}{z^{n}}  \right\rvert \to 0 \implies \frac{a_{0}}{z^{n}} \to 0$o

$\implies \lim_{ \lvert z \rvert \to \infty } \left( \frac{a_{n-1}}{z} + \dots + \frac{a_{0}}{z^{n}} \right) = 0$

$\implies \exists r_{0}: \forall r > r \text{-ra}: \frac{a_{n-1}}{z} + \dots + \frac{a_{0}}{z^{n}} \in B\left( 0, \left\lvert  \frac{a_{n}}{2}  \right\rvert \right)$


$\implies \lvert p(z) \rvert = \lvert z^{n} \rvert\left\lvert  a_{n} + \frac{a_{n-1}}{z} + \dots \frac{a_{0}}{z^{n}} \right\rvert \geq \lvert z^{n}\rvert\cdot \frac{\lvert a_{n} \rvert}{2}$

$\implies \lvert z \rvert \geq r_{0} \text{-ra}: \lvert f(z) \rvert = \left\lvert  \frac{1}{p(z)}  \right\rvert \leq \frac{2}{\lvert a_{n} \rvert}\cdot \frac{1}{\lvert z^{n} \rvert} \leq \frac{2}{\lvert a_{n} \rvert}\cdot \frac{1}{r_{0}^{n}}$
$\bar{B}(0, r_{0})$ kompakt, ezen $\lvert f \rvert$ folytonos.

$K = \max _{\xi \in \bar{B}(0, r_{0})} \lvert f(z) \rvert \implies \lvert f(z) \rvert \leq \max\left( K, \frac{z}{\lvert a_{n} \rvert}, \frac{1}{r_{0}^{n}} \right)$
Tehát $f$ korlátos, tehát teljesülnek a [[Luiville tétel]] feltételei.
$\implies f \equiv 0$  ellentmondás!
