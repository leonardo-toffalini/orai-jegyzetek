### 1.
Igazoljuk, hogy a $\left(\mathscr{C}([a, b] ; \mathbb{K}),\|\cdot\|_{\max }\right)$ téren a $\Phi: f \mapsto f\left(x_0\right)$ leképezés folytonos lineáris funkcionált definiál, ha $x_0 \in[a, b]$ tetszőleges rögzített pont. Számítsuk is ki a normáját!

**Megoldás:**
*linearis*: $\Phi (c_{1}f_{1} + c_{2}f_{2}) = c_{1}f_{1}(x_{0}) + c_{2}f_{2}(x_{0})$.
*folytonos*: eleg, hogy korlatos
*korlatos*:
$$
\lvert \Phi f \rvert  \leq M \cdot \lvert\lvert f \rvert\rvert _{\max} \quad \forall f \in C
$$
$$
\lvert f(x_{0}) \rvert \leq M \cdot \lvert\lvert f \rvert\rvert _{\max}
$$
$$
\lvert f(x_{0}) \rvert  \leq M \cdot \max \limits_{I} \lvert f \rvert  \quad \forall f \in C
$$
$M = 1$ jó.

Legyen $f$ a konstans $1$ fuggveny $\implies \lvert c \rvert = 1 \cdot \max \lvert c \rvert = \lvert c \rvert$
Tehat $1$-nel nem is lehet kisebb.

### 2.
Folytonos-e $\mathscr{C}([a, b] ; \mathbb{K})$ fölött az $f \mapsto f\left(x_0\right)$ lineáris funkcionál az $\|\cdot\|_1$ normára nézve? Ha igen, számítsuk ki a normáját!

**Megoldás:**
$$
\exists ? M > 0: \lvert f(x_{1}) \rvert  \leq M \cdot \lvert\lvert f \rvert\rvert _{1} = M \cdot \int _{I}\lvert f \rvert \quad \forall f \in C
$$
$$
f_{n} = \frac{1}{x^{n}}
$$
ellenpelda

### 3.
(a) Igazoljuk, hogy $\left(\mathscr{C}([a, b] ; \mathbb{K}),\|\cdot\|_{\max }\right)$ fölött a $\Phi: f \mapsto \int_a^b f$ leképezés korlátos lineáris funkcionált definiál. Számítsuk is ki a normáját!
(b) Igazoljuk közvetlenül is, hogy a fenti $\Phi$ (sorozat)folytonos, és szemléltessük, hogy a becslés épp a korlátosságon múlik!

**Megoldás:**

### 4.
Legyen $A: \mathscr{C}([a, b] ; \mathbb{K}) \rightarrow \mathscr{C}([a, b] ; \mathbb{K})$ az a lineáris operátor, amelyre $(A f)(x):=\int_a^x f$. Igazoljuk, hogy $A$ folytonos lineáris operátor a $\|\cdot\|_{\max }$ normára nézve. Számítsuk is ki a normáját!

**Megoldás:**
### 5.
Igazoljuk, hogy az $L^2(I)$ téren az $f \mapsto \int_a^b f g$ leképezés folytonos lineáris funkcionált definiál, ha $g \in L^2(I)$ tetszőleges rögzített függvény. Számítsuk is ki a normáját!

**Megoldás:**
### 6.
Jelölje $c$ a $\mathbb{K}$-ban haladó konvergens sorozatok normált terét az $\|x\|:=\sup _{n \in \mathbb{N}}\left|x_n\right|$ normával. Igazoljuk, hogy a $\phi: c \rightarrow \mathbb{K}, \quad \phi(x):=\lim _{n \rightarrow \infty} x_n$ leképezés folytonos lineáris funkcionál! Számítsuk is ki a normáját!

**Megoldás:**
### 7. (szorgalmi)
Igazoljuk, hogy az $A: X \supset \rightarrow Y, \operatorname{dom}(A):=\mathscr{C}^1([0,1] ; \mathbb{R})$ altéren értelmezett $A f:=f^{\prime}$ lineáris operátor nem korlátos, ha $X=Y=\mathscr{C}([0,1] ; \mathbb{R})$ a maximum-normával!

**Megoldás:**

### 8.
Legyen $X$ egy olyan $[0,1] \rightarrow \mathbb{R}$ függvényekből álló vektortér, amelyre $\mathscr{C}^1([0,1] ; \mathbb{R}) \subseteq X$ teljesül.
(a) Legyen $\|\cdot\|$ tetszőleges $X$ fölötti norma. Igazoljuk, hogy az $A: X \rightarrow X, \operatorname{dom}(A):=\mathscr{C}^1([0,1] ; \mathbb{R})$, Af $:=f^{\prime}$ lineáris operátor nem korlátos!
(b) Legyen $X:=\mathscr{C}^1([0,1] ; \mathbb{R})$, ellátva az $\|f\|_{C^1}:=\max _I\left|f^{\prime}\right|+\max _I|f|$ normával, és legyen $Y:=\mathscr{C}([0,1] ; \mathbb{R})$ ellátva a maximum-normával. Mutassuk meg, hogy az $A: X \rightarrow Y, \quad A f:=f^{\prime}$ lineáris operátor folytonos!

**Megoldás:**
related: [[TovFejAnal]]