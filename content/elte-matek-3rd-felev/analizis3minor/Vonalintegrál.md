#MOC

***Def***.: [[Vektromező]]

***Def***.: [[Görbementi vonalintegrál]]

***[[Tétel 2.1]]***:
1. Ha $\gamma$ görbe rektifikálható és $F$ vektormező folytonos, akkor  létezik a $\gamma$ görbe vonalintegrálja az $F$ vektormezőn.
2. Ha $\gamma$ szakaszonként $C^1$ és $F$ folytonos, akkor $I = \int_a^b{\langle F(\gamma(t))\cdot \gamma'(t) \rangle}dt$.

***Tétel***: [[Vonalintegrál tulajdonságai]]

***Tétel***: [[Triviális becslés]]

***Def***.: [[Vektormező primitív függvénye]]

***Tétel***: [[Newton-Leibniz görbékre]]

***[[Tétel 2.2]]***: A következők ekvivalensek:
1. $F$-nek létezik primitív függvénye.
2. Bármely két görbére, melyeknek a végpontjai megegyeznek, a vonalintegráljaik megegyeznek.
3. Ha $\gamma$ szakaszonként $C^1$ zárt görbe $G$-ben, akkor $\int_{\gamma}F = 0$.
4. Bármely két töröttvonalra, melyek végpontjai megegyeznek, a vonalintegráljaik megegyeznek.
5. Ha $\gamma$ egy zárt töröttvonal, akkor $\int_{\gamma}F = 0$.

***[[Áll 2.1]]***:
1. Ha $f$ primitív függvénye $F$-nek, akkor $f+c$ is primitív függvénye $F$-nek.
2. Ha $f_1, f_2$ is primitív függvényei $F$-nek, akkor $f_2 - f_1 =$ konstans.

***Def***.: [[Konzervatív vektormező]]

***[[Tétel 2.3]]***: $G \subset \mathbb{R}^d$ nyílt, $F: G \to \mathbb{R}^d$  differenciálható, $F = (F_1, \ldots, F_d)$.
Ekkor, ha $F$ konzervatív, akkor $\partial_{x_j}F_i = \partial_{x_i}F_j$

***[[Lemma 2.1]]***: $A\in M_d(\mathbb{R})$, $A = A^T$, $b\in\mathbb{R^d} \implies F(x) = A\cdot x + b$  konzervatív.

***[[Tétel 2.4]]***: $G\subset \mathbb{R^d}$ nyílt, $F:G\to \mathbb{R^d}$ differenciálható, $F' = (F')^T$ (azaz $F$ deriváltja szimmetrikus).
Ekkor $F$ konzervatív.

***Lemma***: [[Goursat Lemma]]

***Def***.: [[Csillagszerű tartomány]]

***[[Áll 2.2]]***: Ha $G\subset\mathbb{R^d}$ csillagszerű tartomány, $F:G\to\mathbb{R^d}$ differenciálható.
Ekkor $F$ konzervatív $\iff$ $\forall x \in G$-re $F'(x) = (F'(x))^T$.