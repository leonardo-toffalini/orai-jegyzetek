#lemma 

***Lemma***: Adott $(X, \rho)$ metrikus tér, $f:(X, \rho) \to (X, \rho)$ kontrakció.
Ekkor az $a_{n} = f^{[n]}(a)$ sorozat Cauchy.


***Biz***.:
$n,m > N$
$$
\rho(a_{n}, a_{m}) = \rho \left(f^{[n]}(a), f^{[m]}(a) \right) \leq \frac{1}{1-K} \left(\rho \left( f^{[n]}(a), f(f^{[n]}(a)) \right) \right) + \rho \left( f^{[m]}(a), f(f^{[m]}(a)) \right)
$$
$$
= \frac{1}{1-K} \left( \rho \left( f^{[n]}(a), f^{[n+1]}(a) \right) + \rho \left( f^{[m]}(a), f^{[m+1]}(a) \right)  \right) \leq \frac{1}{1 - K} \left( K^{n} \rho \left( a, f(a) \right) + K^{m} \rho \left( a, f(a) \right)   \right)
$$
$$
= \frac{K^{n} + K^{m}}{1 - K} \rho(a, f(a)) \to 0 \text{, ha } N \to \infty
$$


***Dependencies***:
- [[Cauchy sorozat]]
- [[Iterált függvény]]
- [[Metrikus tér]]
- [[Kontrakció]]
- [[Fundamentális kontrakciós egyenlőtlenség]]