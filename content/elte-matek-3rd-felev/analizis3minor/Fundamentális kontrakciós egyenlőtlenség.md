#lemma 

***Lemma***: Adott $(X, \rho)$ metrikus tér, $f: (X, \rho) \to (X, \rho)$ kontrakció $0 < K < 1$ paraméterrel.
Ekkor:
$$
\forall x_{1},x_{2}\in X: \rho(x_{1}, x_{2}) \leq \frac{1}{1-K} \left( \rho (x_{1}, f(x_{1})) + \rho(x_{2}, f(x_{2})) \right) 
$$


***Biz***.: 
$$
\rho(x_{1}, x_{2}) \leq \rho(x_{1}, f(x_{1})) + \rho(f(x_{1}), x_{2}) \leq \rho(x_{1}, f(x_{1})) + \rho(f(x_{1}), f(x_{2})) + \rho(f(x_{2}), x_{2})
$$
$$
\rho(f(x_{1}), f(x_{2})) \leq K \cdot \rho(x_{1},x_{2}) \implies \rho(x_{1}, x_{2}) \leq \rho(x_{1}, f(x_{1})) + K \cdot \rho(x_{1},x_{2}) + \rho(f(x_{2}),x_{2})
$$
$$
\implies (1 - K) \cdot \rho(x_{1},x_{2}) \leq \rho(x_{1}, f(x_{1})) + \rho(x_{2}, f(x_{2}))
$$
$$
\implies \rho(x_{1}, x_{2}) \leq \frac{1}{1-K} \left( \rho(x_{1}, f(x_{1})) + \rho(x_{2}, f(x_{2})) \right) 
$$


***Köv***.: [[Kontrakciónak egyértelű a fixpontja]]

***Dependencies***:
- [[Metrikus tér]]
- [[Kontrakció]]