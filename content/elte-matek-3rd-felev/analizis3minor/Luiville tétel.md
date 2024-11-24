#tétel-biz  

***Tétel***: $f \in \mathcal{O}(\mathbb{C})$, $f$ korlátos: $\lvert f \rvert \le M$, ekkor $f \equiv$ konstans.

***Biz***.: $a \in \mathbb{C}, r > 0$
[[CIF deriváltra]] $\implies$
$$
f'(a) = \frac{1}{2\pi i}\int _{\lvert \xi - a \rvert = r} \frac{f(\xi)}{(\xi - a)^{2}} \, d\xi \le \frac{1}{2\pi i} \frac{M}{r^{2}}2\pi r = \frac{M}{ri}
$$
$$
\lvert f'(a) \rvert \le \lim_{ r \to \infty } \frac{M}{ri} = 0
$$
$$
\implies f'(a) = 0 \implies f' \equiv 0 \implies f \equiv \text{ konstans}
$$
