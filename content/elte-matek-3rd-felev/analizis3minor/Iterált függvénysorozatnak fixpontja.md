#áll 

***Áll***.: Adott $(X, \rho)$ metrikus tér, $f: (X, \rho) \to (X, \rho)$ folytonos függvény.
Legyen $a_{n} = f^{[n]}(a)$.
Ekkor, ha $a_{n}$ konvergens és $\lim_{ n \to \infty } a_{n} = p$, akkor $f(p) = p$.


***Biz***.: 
$$
p = \lim_{ n \to \infty } a_{n} = \lim_{ n \to \infty } a_{n+1} = \lim_{ n \to \infty } f(f^{[n]}(a)) = \lim_{ n \to \infty } f(a_{n}) = f(p)
$$
$$
\implies p = f(p)
$$


***Dependencies***:
- [[Fixpont]]
- [[Metrikus tér]]