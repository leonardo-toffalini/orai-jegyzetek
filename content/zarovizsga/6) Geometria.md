### Vektorok hasznalata: skalaris, vektorialis es vegyes szorzat
*Def.:* $u, v \in \mathbb{R}^{n}$ a ket vektor skalaris szorzatatan a kovetkezo szamot ertjuk:
$$
u \cdot v =  \sum_{i=1}^{n} u_{i} \cdot v_{i}.
$$
*Megj.:* A skalaris szorzas egy bilinerais szimmetrikus pozitiv szemidefinit fuggveny.
*Tetel:*
$$
u \cdot v = \lvert u \rvert \cdot \lvert v \rvert \cdot \cos \varphi.
$$
*Kov.:* $u \cdot b = 0 \iff u \perp v$.
*Kov.:* Adott $a \in \mathbb{R}^{n}$, minden $v \in \mathbb{R}^{n}$ vektor felbonthato $v = v_{p} + v_{m}$ komponensekre, ahol $v_{p}$ parhuzamos $a$-val es $v_{m}$ meroleges $a$-ra. Tovabba a kovetkezo kepletek adjak a komponenseket:
$$
v_{p} = \lambda a, \quad \text{ahol } \lambda = \frac{a \cdot v}{\lvert a \rvert ^{2}}.
$$

*Def.:* Adott ket $u, v \in \mathbb{R}^{3}$ vektornak a vektorialis szorzatan azt a vektort ertjuk, amit ugy kapunk, hogy a 
$$
\left| \begin{matrix}
i & j & k \\
u_{1} & u_{2} & u_{3} \\
v_{1} & v_{2} & v_{3} \\
\end{matrix} \right|
$$
determinanst az elso sora szerint fejtjuk ki. Jelolesben $u \times v$.
*Megj.:* A vektorialis szorzas egy bilinearis antiszimmetrikus  fuggveny.
*Tetel:*
$$
u \times v = 0 \iff u \parallel v.
$$
*Tetel:* (Computer graphics)
1. $a \times b$ meroleges az $a$ es $b$ altal veszitett sikra.
2. $\lvert a \times b \rvert = \lvert a \rvert \cdot \lvert b \rvert \cdot \sin \varphi$, tehat a vektorialis szorzat altal letrejott vektor hossza pont akkora mint az $a$ es $b$ altal feszitett parallelogramma terulete.
3. Az $a, b, a \times b$ vektorok ebben a sorrendben jobbrendszert alkotnak.

*Def.:* Az $i, j, k$ rendezett bazissal megegyezo iranyitasu vektorok jobbrendszert alkotnak. Jobbkez szabaly.
*Megj.:* A fenti tetel alapveto a szamitogepes grafikaban raszterizalasnal, amikor haromszogek felulet normaljat szamoljuk.

*Def.:* Az $a, b, c \in \mathbb{R}^{3}$ vektorok vegyes szorzatan a $(a, b, c) = (a \times b) \cdot c$ szamot ertjuk.
$$
(a, b, c) = \left| \begin{matrix}
a_{1} & a_{2} & a_{3} \\
b_{1} & b_{2} & b_{3} \\
c_{1} & c_{2} & c_{3} \\
\end{matrix} \right|
$$
*Megj.:* A vegyes szorzas linearis, es az elojele fugg a permutacio elojeletol, tehat $(a, b, c) = (-1)^{\pi} \pi(a, b, c)$.
*Tetel:* $(a, b, c) = 0 \iff a, b, c$ linearisan osszefuggnek.
*Tetel:* Az $a, b, c$ vektorok vegyes szorzata pont az altaluk feszitett paralellepipedon elojeles terfogata.

*Tetel:* (Kifejtesi tetel) ...
*Tetel:* (Jacobi azonossag) ...
*Tetel:* (Lagrange azonossag) ...

### Konvexitas alapfogalmai
### Elvalasztasi tetelek
### Konvex halmazok Hausdorff-tavolsaga
### Eueler-fele poliedertetel
### Szabalyos poliederek
### Euklideszi ter
### Projektiv sik
### Kvaterniok
### SO(3) csoport
