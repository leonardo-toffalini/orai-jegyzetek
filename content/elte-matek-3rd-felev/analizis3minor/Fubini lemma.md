#lemma 

***Lemma***: Legyen $\mathbb{P}^{1}$ felosztás az $x$-tengely mentén és $\mathbb{P}^{2}$ felosztás az $y$-tengely mentén.
Tehát $\mathbb{P}^{1} := \{ a = x_{0}, x_{1}, \dots, x_{n} = b \}$ és $\mathbb{P}^{2} := \{ c = y_{0}, y_{1}, \dots, y_{n} = d \}$.
Ekkor $\mathbb{P} = (\mathbb{P}^{1}, \mathbb{P}^{2})$-re:
$$
s(f, \mathbb{p}) \leq s(A, \mathbb{P}^{1}) \leq S(A, \mathbb{P}^1) \leq S(f, \mathbb{P})
$$


***Biz***.: Elég belátni, hogy $S(A, \mathbb{P}^{1}) \leq S(f, \mathbb{P})$.
$$
T_{ij} = [x_{i-1}, x_{i}] \times [y_{j-1}, y_{j}]
$$
$$
M_{ij} := sup \{ f(x, y) : (x, y) \in T_{ij} \}
$$
$$
\implies S(f, \mathbb{P}) = \sum M_{ij} \cdot t_{2}(T_{ij}) = \sum M_{ij} \cdot (x_{i} - x_{i-1})(y_{j} - y_{j-1})
$$
$$
x \in [x_{i-1}, x_{i}], y \in [y_{j-1}, y_{j}] \implies f(x, y) \leq M_{ij}
$$
$$
\implies \int _{y_{j-1}}^{y_{j}} f(x,y) \, dy \leq M_{ij} \cdot (y_{j} - y_{j-1}) 
$$
$$
\implies A(x) := \int _{c}^{d} f(x, y) \, dy \leq \sum_{j=1}^{m} M_{ij} \cdot (y_{j}-y_{j-1})
$$
$$
M_{i} := sup \{ A(x): x \in [x_{i-1}, x_{i}] \} \leq \sum_{j=1}^{m}M_{ij} \cdot (y_{j}-y_{j-1})
$$
$$
\implies M_{i}\cdot(x_{i}-x_{i-1}) \leq \sum_{j=1}^{m} M_{ij} \cdot (y_{j}-y_{j-1})(x_{i}-x_{i-1})
$$
$$
\implies \sum_{i=1}^{n} M_{i} \cdot (x_{i}-x_{i-1}) \leq \sum_{i=1}^{n}\sum_{j=1}^{m}M_{ij}\cdot(x_{i}-x_{i-1})(y_{j}-y_{j-1}) \iff
$$
$$
\iff S(A, \mathbb{P}) \leq S(f, \mathbb{P})
$$


***Dependencies***:
- [[Tégla felosztása]]
- [[Integrál közelítőérték]]