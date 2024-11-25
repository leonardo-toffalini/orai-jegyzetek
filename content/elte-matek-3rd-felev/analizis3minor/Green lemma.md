#lemma 

***Lemma*** Ha $K$ egy I. típusú normáltartomány, $K \subset D \subset \mathbb{R}^{2}$ nyílt.
$P \in C^{1}(D)$, $\vec{E}_{1} = (P, 0)$ vektormező.
Ekkor:
$$
\int \limits_{\partial K} \vec{E_{1}} = \int \limits_{\partial K} P \, dx = \iint \limits_{K} -\partial_{y}P \, dxdy 
$$

***Biz***. (Lemma):
Bal oldala a Lemmabeli egyenletnek:
![[Green lemma excali]]
$c_{1}: [a, b] \to \mathbb{R}^{2}, x \mapsto (x, h(x))$
$$
\int \limits_{c_{1}} \vec{E_{1}} = \int _{a}^{b}(\vec{E_{1}}(c_{1}(t))) \cdot c_{1}'(t)  \, dt = \int _{a}^{b} \left( P(c_{1}(t)), 0 \right) \cdot c_{1}'(t) \, dt = \int _{a}^{b} \left( P(x, h(x)), 0 \right) \cdot (1, h'(x)) \, dx =
$$
$$
 = \int _{a}^{b} P(x, h(x)) \, dx 
$$

$c_{3}^{-}:[a, b] \to \mathbb{R}^{2}, x\mapsto(x,g(x))$
$$
\int \limits_{c_{3}} \vec{E_{1}} = - \int \limits_{c_{3}^{-}} \vec{E_{1}} = -\int _{a}^{b} P(x, g(x)) \, dx 
$$
$c_{2}:[h(b), g(b)] \to \mathbb{R}^{2}, y \mapsto (b, y)$
$$
\int \limits_{c_{2}} \vec{E_{1}} = \int _{h(b)}^{g(b)} \left( P(b, y) \right) \cdot (0, 1) \, dy = \int _{h(b)}^{g(y)} 0 \, dy = 0 
$$
Hasonló módon $\int \limits_{c_{4}} \vec{E_{1}}  = 0$
$$
\implies \int \limits_{\partial H} \vec{E_{1}} = \int _{a}^{b}P(x, h(x)) \, dx - \int _{a}^{b}P(x,g(x)) \, dx
$$

Jobb oldala a Lemmabeli egyenletnek:
$$
-\iint \limits_{H} \partial_{y}P \, dxdy = - \int _{a}^{b}\int _{h(x)}^{g(x)}\partial_{y}P \, dy  \, dx \stackrel{\text{Newton Leibniz}}{=} -\int _{a}^{b} P(x, g(x)) - P(x, h(x) \, dx =
$$
$$
= \int _{a}^{b}P(x, h(x)) - P(x, g(x)) \, dx \implies \text{ baloldal } = \text{ jobboldal}
$$

***Dependencies***:
- [[Normáltartomány]]