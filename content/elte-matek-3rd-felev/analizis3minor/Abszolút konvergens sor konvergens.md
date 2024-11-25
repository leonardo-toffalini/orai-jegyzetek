#tétel-biz  

***Áll***.: Ha $\sum{a_{k}}$ abszolút konvergens, akkor konvergens is, és $\left\lvert  \sum a_{j}  \right\rvert \le \sum \lvert a_{j} \rvert$

***Biz***.: $\forall z \in \mathbb{C}: Re(z) \le \lvert z \rvert, Im(z) \le \lvert  z \rvert$
$$
\implies \sum \lvert z \rvert \ge \sum \mathrm{Im}(z) \implies \sum \mathrm{Re}(z) \text{ abszolút konvergens} \implies \text{konvergens}
$$
$$
\implies \sum \lvert u \rvert \ge \sum \mathrm{Re}(z) \implies \sum \mathrm{Re}(z) \text{ abszolút konvergens} \implies \text{konvergens}
$$
$$
\sum z = \sum \mathrm{Re}(z) + i \sum \mathrm{Im}(z) \implies \sum z \text{ konvergens}
$$

Továbbá:
$$
\lvert s_{n} \rvert = \left\lvert  \sum_{j=0}^{n}{a_{j}}  \right\rvert \le \sum_{j=0}^{n}{\lvert a_{j} \rvert } \le \sum_{j = 0}^{\infty}{\lvert a_{j} \rvert } \implies \left\lvert \sum_{j = 0}^{\infty} a_{j} \right\rvert =  \lvert \lim_{ n \to \infty } s_{n} \rvert \le \sum_{j = 0}^{\infty}{\lvert a_{j} \rvert }
$$
