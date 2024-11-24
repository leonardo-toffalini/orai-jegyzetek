#lemma 

***Lemma***: 
$$
\exists x : Ax \leq b \iff \nexists 0 \leq y : yA = 0, yb < 0,
$$


***Biz***.: 
$\implies$
Ha a baloldal megoldható, akkor bármilyen nemnegatív lineáris kombinációja a soroknak is megoldható, tehát nem létezhet ilyen $y$.

$\impliedby$
t.f.h $\exists x, y$, ekkor:
$yAx = y(Ax) \leq yb < 0$
$yAx = (yA)x = 0$
$\implies 0 = yAx < 0$ ellentmondás.


***Dependencies***:
- [[Fourier-Motzkin elimináció]]