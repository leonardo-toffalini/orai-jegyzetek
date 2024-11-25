date: 2024.03.26

$X$ normalt ter vegtelen dimenzios, $\sigma_{p}(A) = \{ \lambda : \operatorname{Ker}(A - \lambda I) \neq \{ 0 \} \} = \{ \lambda : A - \lambda I \text{ nem injektiv} \} \subset \sigma(A)$

Mai oran $X$ Banach ter es $A \in \mathcal{L}(X)$!

*Megjegyzes* (Banach fele homeomorfizmus): Ha $X$ Banach ter, akkor $\lambda \in \sigma(A) \iff A - \lambda I$ nem bijektiv

### Tetel
$X$ Banach ter, ekkor $(\mathcal{L}(X), \| \cdot \|)$ is Banach ter, ahol $\| \cdot \|$ az operatornorma

*Bizonyitas*: Nem bizonyitjuk.

***Q.:*** Ebben a $(\mathcal{L}(X), \| \cdot \|)$ Banach terben hogy helyezkednek el az invertalmhato operatorok? Ebbol kepet kapunk arra, hogy mikor lesz $A - \lambda I$ invertalhato es hogy milyen tulajdonsagu $\rho(A)$ illetve $\sigma(A)$.

### Lemma
Legyen $(y_{n}) \subset Y$ Banach terben sorozat, tegyuk fel, hogy 
$$
\| y_{n} \|  \leq c_{n} \in \mathbb{R}_{0}^{+}, \quad n \in \mathbb{N}, \quad \sum c_{n} \text{ konvergens}
$$
Ekkor a $\sum y_{n}$ sor konvergens $Y$-ban.

*Bizonyitas*:
$\sum y_{n}$ konvergens $\stackrel{\text{def}}{\iff} s_{n} := \sum_{k=1}^{n}y_{k}$ konvergens $Y$-ban $\stackrel{\text{Banach terben}}{\iff} s_{n}$ Cauchy sorozat
Tudjuk hogy $\sum c_{n}$ konvergens $\implies S_{n} := \sum_{k=1}^{n} c_{n}$ Cauchy sorozat

Meg kell mutatnunk, hogy $s_{n}$ Cauchy!
$n> m$
$$
\| s_{n} - s_{m} \|  = \| \sum_{k=m+1}^{n}y_{k} \|  \stackrel{\Delta \text{-egy}}{\leq} \sum_{k=m+1}^{n}\| y_{k} \| \stackrel{\text{feltetel}}{\leq} \sum_{k=m+1}^{n}c_{k} \stackrel{\text{def}}{=} S_{n} - S_{m} \to 0
$$
Tehat belattuk, hogy $s_{n}$ Cauchy sorozat.

### Def
$A \in \mathcal{L}(X)$, ekkor $A^{0} := Id_{X}$, $A^{m+1} := A \cdot A^{m} := A \circ A^{m}$

### Tetel (Neumann)
Legyen $A \in \mathcal{L}(X)$ olyan, hogy $\| A \| < 1$. Ekkor $1 \in \rho(A)$ es $(I - A)^{-1} = \sum_{n=0}^{\infty}A^{n}$
(„$\frac{1}{1-a} = \sum_{n=0}^{\infty}a^{n} \quad \lvert a \rvert < 1$” analog allitasa)

*Bizonyitas*:
1.) Megmutatjuk, hogy
$$
B := \sum_{n=0}^{\infty} A ^{n} \in \mathcal{L}(X)
$$
Elozo lemme alapjan eleg megmutatnunk, hogy $\| A^{n} \| \leq c_{n}$ es $\sum c_{n}$ konvergens

volt, hogy $\| A \cdot B \| \leq \| A \| \cdot \|  B \|$  ebbol kovetkezik, hogy $\| A^{n} \| < \| A \|^{n}$. Legyen $c_{n} = \| A \|^{n}$ es a feltetel szerint $\| A \| < 1$ tehat $\sum c_{n}$ konvergens mert ez mar csak egy mertani sor.

2.) Mar csak azt kell megmutatnunk, hogy $B = (I - A)^{-1} \iff B(I - A) = I$ es $(I - A)B = I$

gondoljuk, meg hogy
$$
B = Id + A + A^{2} + \dots
$$
$$
B_{n} := \sum_{k=0}^{n} A^{k}
$$
vizsgaljuk me, hogy mi lesz a $B_{n}(I - A)$?
$$
B_{n}(I - A) = B_{n} - B_{n} \cdot A = B_{n} - \sum_{k = 1}^{n+1}A^{k} = B_{n} - (B_{n+1} - Id)
$$ Hasznaljuk ki, hogy $B_{n} \to B$ definicio szerint
$$
\lim_{ n \to \infty } B_{n} - (B_{n+1} - Id) = B - B + Id = Id
$$
Hasonlo modon ha jobbrol szorzunk, akkor is $(I - A)B_{n} \to Id$

Masreszt azt allitom, hogy $B_{n}(I - A) \to B \cdot (I - A)$, mivel
$$
\begin{align*}
\| B_{n}(I - A) - B (I - A) \|  & = \| (B_{n} - B) \cdot (I - A) \| \\
& \leq \| B_{n} - B \|  \cdot \| I - A \| \to 0
\end{align*}
$$
Mivel $\| B_{n} - B \| \to 0$
Tehat $B \cdot (I - A) = I$ tehat valoban $B$ balinverze $(I - A)$-nak es hasonlo modon meggondolhato hgoy $B$ jobbinverze $(I - A)$-nak.

***Q.:*** Ha van egy invertalhato operatorom, akkor tudunk mondani a terben egy masik invertalhato operatort?

### Allitas
Ha $A, B \in \mathcal{L}(X)$ es $\exists A^{-1}, B^{-1} \in \mathcal{L}(X)$ akkor $\exists (A \cdot B)^{-1} \in \mathcal{L}(X)$ es $(A \cdot B)^{-1} = B^{-1} \cdot A^{-1}$

*Bizonyitas:*
Be kell latni, hogy $(A \cdot B) \cdot (B^{-1} \cdot A^{-1}) = I$
$$
(A \cdot B)\cdot (B^{-1} \cdot A^{-1}) = A \cdot (B \cdot B^{-1}) \cdot A^{-1} = A\cdot A^{-1} = Id
$$
Ugyanigy $(B^{-1} \cdot A^{-1}) \cdot (A \cdot B) = Id$

### Tetel
Legyen $A \in \mathcal{L}(X)$ olyan, hogy $\exists A^{-1} \in \mathcal{L}(X)$, tovabba, legyen $B \in \mathcal{L}(X)$ olyan, hogy
$$
\| A - B \| < \frac{1}{\| A^{-1} \| }
$$
Ekkor $B$ is invertalhato, azaz $\exists B^{-1} \in \mathcal{L}(X)$.

*Bizonyitas:*
Irjuk fel a $B$-t a kovetkezo trukkos modon:
$$
B = A - (A - B) = (I - ( A - B) \cdot A^{-1}) \cdot A
$$
Az elozo allitas miatt eleg belatni, hogy $(I - (A - B))$ invertalhato, mert ha van ket ivnertalhato operator akkor a szorzata is az.

Alkalmazzuk a Neumann-tetelt: eleg megmutatni, hogy $\| (A - B) \cdot A^{-1} \| < 1$
No de 
$$
\begin{align*}
\| (A - B) \cdot A^{-1} \| & \leq \| A - B \| \cdot \| A^{-1} \| \\
& < \frac{1}{\| A^{-1} \|} \cdot \| A^{-1} \| \\
& = 1
\end{align*}
$$
Tehat $B = (I - (A - B) \cdot A^{-1}) \cdot A$ is invertalhato.

*Emlek:* $(X, \rho)$ metrikus terben $H \subset X$ nyilt halmaz, ha $\forall x \in H$ es $\exists r > 0$ ugy, hogy $B(x, r) \subset H$

Ha $(X, \| \cdot \|)$ normalt ter, akkor $H \subset X$ nyilt halmaz ha $\forall x \in H$ eseten $\exists r > 0$ ugy, hogy $\{ y \in X: \| x - y \| < r \} \subset H$
Itt $\{ y \in X: \| x - y \| < r \}$ halamz $B(x, r)$ a norma altal indukalt metrikaval

Az elozo tetel kovetkezmenye
#### Kov
$(\mathcal{L}(X), \| \cdot \|)$ Banach-terben a folytonosan invertalhato linearis operatorok nyilt halmazt alkotnak.

*Bizonyitas:* Legyen $A \in \mathcal{L}(X)$ ugy hogy $\exists A^{-1} \in \mathcal{L}(X)$. Ekor az elozo tetel alapjan $r := \frac{1}{\| A^{-1} \|}$ sugarral
$$
B(A, r) \subset \{ \text{folytonosan invertalhato operatorok} \}
$$
Tehat nyilt halmazt alkotnak a folytonosan invertalhato operatorok.

### Allitas
Ha $A \in \mathcal{L}(X)$ tetszologes. Ekkor $\rho(A) \subset \mathbb K$  nyilt halamz. Kovetkezteteskeppen $\sigma(A)$ zart mert a komplementere nyilt.

*Bizonyitas:* Legyen $\lambda_{0} \in \rho(A)$ megmutatjuk, hogy $\exists r > 0$ melyre
$$
\{ \lambda : \lvert \lambda - \lambda_{0} \rvert < r \} \subset \rho(A)
$$
*Bizonyitas:* Legyen
$$
r = \frac{1}{\| (A - \lambda_{0}I)^{-1} \|}
$$ 
Az elozo tetel alapjan, ha $\lambda \in \mathbb K$ olyan, hogy
$$
\| (A - \lambda I) - (A - \lambda_{0}I) \|  < r \implies A - \lambda I \text{ is invertalhato, vagyis } \lambda \in \rho(A)
$$
baloldal atirva
$$
\| (A - \lambda I) - (A - \lambda_{0}I) \| = \| (\lambda_{0} - \lambda)I \| = \lvert \lambda_{0} - \lambda \rvert 
$$
Tehat ha $\lvert \lambda_{0} - \lambda \rvert < r$ akkor $\lambda \in \rho(A)$, vagyis $B(\lambda_{0}, r) \subset \rho(A)$. Ebbol kovetkezik, hogy $\rho(A)$ nyilt.

### Def
$A \in \mathcal{L}(X)$ spektralsugara a kovetkezo:
$$
r(A) := \inf \{ \| A^{n} \| ^{1/n} : n \geq 1 \}
$$
*Megjegyzes:* $r(A) \leq \| A \|$, mert $\| A^{n} \| \leq \| A \|^{n}$ 

### Allitas
$A \in \mathcal{L}(X)$ tetszoleges. Ekor $\sigma(A) \subset \{ \lambda \in \mathbb K : \lvert \lambda \rvert \leq r(A) \}$
Tehat $\sigma(A)$ korlatos halmaz. Mivel zart is es veges dimenzios ebbol kovetkezik, hogy kompakt.

*Bizonyitas:* Nem bizonyitjuk.

### Tetel
Ha $X$ $\mathbb{C}$ feletti Banach ter, $A \in \mathcal{L}(X)$, akkor $\sigma(A) \neq \emptyset$ es $r(A) = \max \{ \lvert \lambda \rvert : \lambda \in \sigma(A) \}$

*Bizonyitas:* Nem bizonyitjuk.

pelda: Ha $X$ $\mathbb{R}$ feletti Banach-ter, $A \in \mathcal{L}(X)$ akkor elofordulhat, hogy $\sigma(A) =  \emptyset$ 
Legyen $X = \mathbb{R}^{2}$
$$
A = \begin{bmatrix}
0 & 1 \\
-1 & 0
\end{bmatrix}
$$
$$
\det(A - \lambda I) = \lambda ^{2} + 1\neq 0 \quad \forall \lambda \in \mathbb{R} \implies \sigma(A) = \emptyset
$$
related: [[TovFejAnal]]