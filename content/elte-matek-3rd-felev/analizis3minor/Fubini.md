#tétel-biz 

***Tétel***: Adott $Q = [a, b] \times [c,d]$ tégla és ezen a téglán értelmezett $f: Q \to \mathbb{R}^{2}$ integrálható függvény, azaz $f \in R_{Q}$.

1. *verizó*
Ekkor, ha $\forall x \in [a, b]: f_{x} \in R_{[c, d]}$, ahol $f_{x}(y) = f(x, y)$, tehát $y \mapsto f(x, y)$:
$$
A(x) := \int _{c}^{d} f_{x}(y) \, dy
$$
Ekkor $A \in R_{[a, b]}$ és
$$
\int \limits_{Q} f(x, y) \, du = \int _{a}^{b} A(x) \, dx = \int _{a}^{b} \left( \int _{c}^{d}f(x, y) \, dy  \right)  \, dx  
$$

2. *verzió*
Ekkor, ha $\forall y \in [c, d] : f_{y} \in R_{[a, b]}$, ahol $f_{y}(x) = f(x, y)$, tehát $x \mapsto f(x, y)$:
$$
B(y) := \int _{a}^{b} f_{y}(x) \, dx 
$$
Ekkor $B \in R_{[c, d]}$ és
$$
\int \limits_{Q} f(x, y) \, du = \int _{c}^{d} B(y) \, dy = \int _{c}^{d}\left( \int _{a}^{b}f(x, y) \, dx  \right)  \, dy   
$$
*Kettő együtt*:
$$
\int \limits_{Q} f(x, y) \, du = \int _{a}^{b} \int _{c}^{d} f(x, y) \, dy  \, dx = \int _{c}^{d} \int _{a}^{b} f(x, y) \, dx  \, dy   
$$


***Biz***.: 
$f \in R_{Q} \implies \Omega(f, \mathbb{P}) < \varepsilon$
Lemma $\implies \Omega (A, \mathbb{P}^{1}) \leq \Omega(f, \mathbb{P}) \implies \Omega(A, \mathbb{P}^{1}) < \varepsilon$, tehát $A \in R_{[a, b]}$.

$k \in \mathbb{N}$, legyen $\mathbb{P}$ olyan felosztás, hogy:
$$
\int \limits_{\bar{Q}} f(x,y) \, dx - \frac{1}{k} < s(f, \mathbb{P})
$$
És legyen $\mathbb{P}'$ olyan felosztás, hogy:
$$
\int \limits_{Q} ^{-} f(x, y) \, dx + \frac{1}{k} > s(f, \mathbb{P}') 
$$
Legyen $\mathbb{P}^{*}$ közös finomítása $\mathbb{P}$ és $\mathbb{P}'$-nak, ekkor:
$$
\int \limits_{Q} f(x,y) \, dx - \frac{1}{k} = \int \limits_{\bar{Q}} f(x,y) \, dx - \frac{1}{k} < s(f, \mathbb{P}) \leq s(f, \mathbb{P}^{*}) \leq s(A, \mathbb{P}^{*1}) \leq
$$
$$
\leq S(A, \mathbb{P}^{*1}) \leq S(f, \mathbb{P}^{*}) \leq S(f, \mathbb{P}') \leq \int \limits_{Q} ^{-} f(x, y) \, dx + \frac{1}{k} = \int \limits_{Q} f(x,y) \, dx + \frac{1}{k} 
$$
$$
\implies \int \limits_{Q} f(x,y) \, dx - \frac{1}{k} \leq \int \limits_{\bar{a}} ^{b} A(x) \, dx \leq \int \limits_{a} ^{\underline{b}} A(x)  \, dx \leq \int \limits_{Q} ^{-} f(x, y) \, dx + \frac{1}{k} 
$$
$$
\implies \int \limits_{Q} f(x,y) \, dx = \int _{a}^{b}A(x) \, dx  
$$

Hasonló módon a másik oldal is belátható.


***Dependencies***:
- [[Fubini lemma]]
- [[Közös finomítás]]
- [[Finomítás jobban közelít]]
- [[Felső, alsó integrál]]