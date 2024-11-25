#lemma

***Lemma***: $\chi : [\alpha, \beta] \to \mathbb{R}^d$ folytonos $\implies$

$$
\left| \int_{\alpha}^{\beta} {\chi (t) dt} \right| \le \int_{\alpha}^{\beta} \left| \chi (t) \right|dt
$$

***Biz***.:
Legyen $I := \int_{\alpha}^{\beta} {\chi (t) dt}$ és $\xi \in \mathbb{R}^d, |\xi| = 1$.

$$
	\langle I, \xi \rangle = \sum_{i = 1}^d {\left(\int_{\alpha}^{\beta} {\chi_i (t) dt}\right)} \cdot \xi_i = \int_{\alpha}^{\beta}{\sum_{i=1}^d {\xi_i \chi_i(t)}dt} = \int_{\alpha}^{\beta}{\langle \xi, \chi(t) \rangle dt}
$$



