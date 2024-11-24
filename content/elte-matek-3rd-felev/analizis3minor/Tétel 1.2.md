#tétel-biz 

***Tétel***.:
1. Ha $\gamma$ Lipschitz, akkor rektifikálható.
2. Ha $\gamma \in C^1$ , akkor $L(\gamma) < \infty$ és $L(\gamma) = \int_a^b{\sqrt(\sum \gamma_j ')}$.

***Biz***.:
1. rész
$$
\begin{equation}
	\gamma \text{ Lipschitz } \iff x, y \in [a, b], |\gamma_j(x) - \gamma_j(y)| \le K \cdot |x - y|
\end{equation}
$$
$$
\begin{equation}
 \implies |\gamma(x) - \gamma(y)| = \sqrt {\sum_{j = 1}^d (\gamma_j (x) - \gamma_j(y))^2} \le K\cdot |x - y|
\end{equation}
$$
$$
	\implies \sum_{j = 1}^d | \gamma(t_j) - \gamma(t_{j-1}) | \le \sum_{j=1}^d {dK(t_j - t_{j-1})} = d \cdot K \cdot (b - a)
$$
$$
	\iff \forall \text{beírható poligonra a hossza } \le d \cdot K \cdot (b - a)
$$

2. rész

[[Tétel 1.1]] $\implies$ $\gamma$ Lipschitz, ha $C^1$ $\implies L(\gamma) < \infty$.

[[Lemma 1.2.1]]