### 1.
Igazoljuk a paralelogramma-szabalyt: minden $x, y \in E$ eseten $\lvert\lvert x + y \rvert\rvert^{2} + \lvert\lvert x-y \rvert\rvert^{2} = 2(\lvert\lvert x \rvert\rvert^{2} + \lvert\lvert y \rvert\rvert^{2})$

**Megoldas**:
$$
\lvert\lvert x + y \rvert\rvert ^{2} + \lvert\lvert x - y \rvert\rvert ^{2} := (x + y, x + y) + (x-y, x-y) = \lvert\lvert x \rvert\rvert ^{2} + 2(x,y) + \lvert\lvert y \rvert\rvert ^{2} + \lvert\lvert x \rvert\rvert ^{2} - 2(x,y) + \lvert\lvert y \rvert\rvert ^{2}
$$
$$
= \lvert\lvert x \rvert\rvert ^{2} + \lvert\lvert y \rvert\rvert ^{2} + \lvert\lvert x \rvert\rvert ^{2} + \lvert\lvert y \rvert\rvert ^{2} = 2(\lvert\lvert x \rvert\rvert ^{2} + \lvert\lvert y \rvert\rvert ^{2})
$$

### 2.
Legyen $(x_{k})_{k=1, \dots,n}$ $E$-beli, egymasra paronkent ortogonalis vektorok egy veges neures rendszere. Mutassuk meg, hogy
$$
\left\lvert \left\lvert  \sum_{k=1}^{n}x_{k}  \right\rvert \right\rvert ^{2} = \sum_{k=1}^{n}\lvert\lvert x_{k} \rvert\rvert ^{2}
$$

**Megoldas**:
$$
\left\lvert \left\lvert  \sum_{k=1}^{n}x_{k}  \right\rvert \right\rvert ^{2} := \left( \sum_{k=1}^{n}x_{k}, \sum_{k=1}^{n}x_{k} \right) = \sum_{k=1}^{n}\lvert\lvert x_{k} \rvert\rvert ^{2} + \sum_{i \neq j} (x_{i}, x_{j}) = \sum_{k=1}^{n}\lvert\lvert x_{k} \rvert\rvert ^{2}
$$

### 3.
Szamitsuk ki az alabbi $x,y \in \mathscr{l}_{\mathbb{C}}^{2}$ vektorok normajat, illetve skalarszorzatukat!
a) $x(n) := \frac{1}{2^{n}}, \quad y(n) := \frac{i^{n}}{3^{n}}$
b) $x = (1, 0, 0, 0, \dots), \quad y = (0, 0, 1, 0, 0, \dots) \quad \quad (\text{a } \dots \text{ csupa } 0\text{-t jelol})$

**Megoldas**:
a)
$$
(x, y) := \sum_{k=1}^{\infty}x_{k}y_{k} = \sum_{k=1}^{\infty} \frac{1}{2^{k}} \cdot \frac{i^{k}}{3^{k}} = \sum_{k=1}^{\infty} \frac{i^{k}}{6^{k}} = \frac{1}{1 - \frac{i}{6}} - 1 = -\frac{1}{37} + \frac{6i}{37}
$$
$$
\lvert\lvert x \rvert\rvert := \sqrt{ (x,x) } = \sqrt{ \sum_{k=1}^{\infty} \frac{1}{2^{k}} \cdot \frac{1}{2^{k}} } = \sqrt{ \sum_{k=1}^{\infty}\frac{1}{2^{k+1}} } = \sqrt{ \sum_{k=2}^{\infty} \frac{1}{2^{k}} } = \sqrt{ 1 - \frac{1}{2} } = \sqrt{ \frac{1}{2} } = \frac{\sqrt{ 2 }}{2}
$$
$$
\lvert\lvert y \rvert\rvert := \sqrt{ ( y, y ) } = \sqrt{ \sum_{k=1}^{\infty} \frac{i^{k}}{3^{k}} \cdot \frac{i^{k}}{3^{k}} } = \sqrt{ \sum_{k=1}^{\infty} \frac{(-1)^{k}}{9^{k}} } = \sqrt{ \frac{1}{1 + \frac{1}{9}} -1 } = \sqrt{ \frac{1}{8} } = \frac{\sqrt{ 8 }}{8}
$$

b)
$$
(x,y) := \sum_{k=1}^{\infty}x_{k}y_{k} = \sum_{k=1}^{\infty}0 = 0
$$
$$
\lvert\lvert x \rvert\rvert := \sqrt{ (x,x) } = \sqrt{ \sum_{k=1}^{\infty}x_{k} \cdot x_{k} } = \sqrt{ 1 + 0 + 0 + \dots } = \sqrt{ 1 } = 1
$$
$$
\lvert\lvert y \rvert\rvert := \sqrt{ (y,y) } = \sqrt{ \sum_{k=1}^{\infty} y_{k}y_{k} } = \sqrt{ 0 + 0 + 1 + 0 + 0 + \dots } = \sqrt{ 1 } = 1
$$

### 4.
Adott $n \in \mathbb{Z}$ eseten legyen $f_{n}$ az $[n, n+1]$ intervallum karakterisztikus fuggvenye, vagyis $f_{n}(x) := 1$, ha $n \leq x \leq n + 1$ es $f_{n}(x) := 0$, ha $x < n$ vagy $x > n+1$. Mutassuk meg, hogy $(f_{n})_{n\in \mathbb{Z}}$ ortonormalt rendszer $L^{2}(\mathbb{R})$-ben!

**Megoldas**:
*$TODO*

### 5.
Legyen $H = L^{2}(0, \pi), \; n \in \mathbb{N}^{+}$ adott, $V := \left\{  \sum_{k=1}^{n} c_{k}\sin kx : c_{1}, \dots, c_{n} \in \mathbb{R} \right\}$. (Ez véges dimenzios es iygy zart altere $H$-nak.) Adott $u \in L^{2}(0, \pi)$ eseten adjunk meg $u$-nak $V$-re vett meroleges vetuletet!

**Megoldas:**
*$TODO*

### 6.
Legyen $I = [0, \pi], \; H = L^{2}(I)$ es tekintsuk $H$-n azt az $(e_{n})_{n\in\mathbb{N}}$ teljes ortonormalt sorozat, ahol $e_{n}(x) := \sqrt{ \frac{2}{\pi} }\sin nx$. Legyen $f(x) := x$ az identitasfuggveny.
a) Fejtsuk Fourier sorba $f$-et az $(e_{n})_{n\in\mathbb{N}}$ rendszer szerint!
b) Irjuk fel a Parseval-egyneloseget a fenti sorfejtesre! Mit kapunk? (Basel probem)

**Megoldás:**
Azt hasznaéjuk, hogy a trigonometrikus rendszer ONB $L^{2}(-\pi, \pi)$-ben.
Legyen $f(t) = t \in C[-\pi, \pi] \subset L^{2}(-\pi, \pi)$.
Teljesul a Fourier-sor eloallitas, vagyis
$$
f(t) = \sum_{k=0}^{\infty} (f, e_{k}) \cdot e_{k}
$$
*Parseval-egyenloseg*:
$$
\lvert\lvert f \rvert\rvert ^{2}_{L^{2}} = \sum_{k = 0}^{\infty} \lvert (f, e_{k}) \rvert ^{2}
$$
$$
\lvert\lvert f \rvert\rvert ^{2}_{L^{2}(-\pi, \pi)} = \int _{-\pi}^{\pi}t \cdot t \, dt = \left[  \frac{t^{3}}{3}  \right]_{-\pi}^{\pi} = \frac{\pi ^{3}}{3} + \frac{\pi ^{3}}{3} = \frac{2\pi ^{3}}{3}
$$
$$
(f, e_{0}) = \int _{-\pi}^{\pi} \frac{1}{\sqrt{ 2\pi }}t \, dt = 0 \text{, mert paratlan fuggveny szimmetrikus tartomanyon.}
$$
$$
(f, e_{2k}) = \frac{1}{\sqrt{ \pi }} \int _{-\pi}^{\pi} (\cos kt) \cdot t \, dt = 0 \text{, mert paratlan fuggveny szimmetrikus tartomanyon.}
$$
$$
(f, e_{2k-1}) = \frac{1}{\sqrt{ \pi }} \int _{-\pi}^{\pi} t \cdot \sin kt \, dt = \frac{1}{\sqrt{ \pi }}\left( - \left[t \cdot \frac{\cos kt}{k}\right]_{-\pi}^{\pi} + \int _{-\pi}^{\pi} \frac{\cos kt}{k} \, dt  \right) = 
$$
$$
= \frac{1}{\sqrt{ \pi }}\left( -\left[ t \cdot \frac{\cos kt}{k} \right]_{-\pi}^{\pi} + 0 \right) = -\frac{1}{\sqrt{ \pi }}\left[ t \cdot \frac{\cos kt}{k} \right]_{-\pi}^{\pi} = 
$$
Ha $k$ paros:
$$
= -\frac{1}{\sqrt{ \pi }}\left( \frac{\pi}{k} + \frac{\pi}{k} \right) = -\frac{2\pi}{\sqrt{ \pi }k} = -\frac{2\sqrt{ \pi }}{k}
$$
Ha $k$ paratlan:
$$
= -\frac{1}{\sqrt{ \pi }}\left( -\frac{\pi}{k} - \frac{\pi}{k} \right) = \frac{2\sqrt{ \pi }}{k}
$$

Tehat a jobboldal a kovetkezo:
$$
\sum_{k = 1}^{\infty} \left(\frac{2\sqrt{ \pi }}{k}\right)^{2} = \pi \cdot 4 \sum_{k=1}^{\infty}\frac{1}{k^{2}}
$$

Baloldal:
$$
\frac{2\pi ^{3}}{3}
$$
bal = jobb:
$$
\implies \sum_{k=1}^{\infty} \frac{1}{k^{2}} = \frac{\pi ^{2}}{6}
$$



related: [[TovFejAnal]]