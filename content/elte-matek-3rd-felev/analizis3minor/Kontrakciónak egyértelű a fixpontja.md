#áll 

***Áll***.: Adott $(X, \rho)$ metrikus tér, $f:(X, \rho) \to (X, \rho)$ kontrakció.
Ekkor legfeljebb egy fixpontja lehet.


***Biz***.:
Tegyük föl, hogy $x_{1}, x_{2}$ is fixpontjai $f$-nek, azaz $f(x_{1})=x_{1}, f(x_{2}) = x_{2}$.
Ekkor a lemma miatt:
$$
\rho(x_{1}, x_{2}) \leq \frac{1}{1-K}\left( \rho(x_{1}, f(x_{1})) + \rho(x_{2}, f(x_{2})) \right) = \frac{1}{1-K} \left( \rho(x_{1}, x_{1}) + \rho(x_{2}, x_{2}) \right) = \frac{1}{1-K}\left( 0 + 0 \right)  
$$
$$
\implies \rho(x_{1}, x_{2}) \leq 0 \implies x_{1} = x_{2}
$$


***Dependencies***:
- [[Fundamentális kontrakciós egyenlőtlenség]]
- [[Metrikus tér]]
- [[Kontrakció]]