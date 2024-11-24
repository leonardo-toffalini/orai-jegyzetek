
### 1. Feladat

Gondoljuk meg, hogy
$$
    \sup_{x\neq 0}\frac{\|Ax\|''}{\|x\|'} = 
    \sup_{\|x\|' = 1} \|Ax\|'' =  \sup\limits_{\|x\|'\leq 1} \|Ax\|''.
$$
#### Sol.:
$$
\sup_{x \neq 0} \frac{\lvert \lvert Ax \rvert  \rvert ''}{\lvert \lvert x \rvert  \rvert '} = \sup_{x \neq 0} \left\lvert  \left\lvert  A \frac{x}{\lvert \lvert x \rvert  \rvert' }  \right\rvert   \right\rvert'' = \sup_{x = 1} \lvert \lvert Ax \rvert  \rvert '' = \sup_{x \leq 1} \lvert \lvert Ax \rvert  \rvert 
$$

### 2. Feladat
Legyen $(V, \|\,\|')$ normált tér. Jelöljük $\|\,\|$-vel az $L(V, V)$ téren indukált operátornormát. Mutassuk meg, hogy ez utóbbi szubmultiplikatív, azaz $A, B \in L(V,V)$ esetén
$$
\| AB \| \leq \| A \| \| B \|.
$$

#### Sol.:
$$
\lvert \lvert AB \rvert  \rvert = \sup_{\lvert\lvert x \rvert\rvert = 1} \lvert \lvert ABx \rvert  \rvert  \leq \sup_{\lvert \lvert x \rvert  \rvert =1} \lvert \lvert A \rvert  \rvert \cdot \lvert \lvert Bx \rvert  \rvert  \leq \lvert \lvert A \rvert  \rvert \cdot \lvert \lvert B \rvert  \rvert 
$$
Mert: $\lvert \lvert Ax \rvert \rvert \leq \lvert \lvert A \rvert \rvert \cdot \lvert \lvert x \rvert \rvert$

### 3. Feladat

Legyen $(V, \| \, \|)$ normált tér. Az eddigiek felhasználásával definiáljunk egy $\| \, \|_*$ leképezést, amivel $(V^*, \| \, \|_*)$ is normált tér.

#### Sol.:
$$
\lvert\lvert v^{*} \rvert\rvert_{*} = \sup_{\lvert\lvert x \rvert\rvert = 1} \lvert v^{*} \cdot x \rvert 
$$
$$
v^{*} \in \mathbb{R}^{n} \implies v^{*} \cdot x \in \mathbb{R}
$$

### 4. Feladat

**Duális norma**

A $\| \, \|_*$ leképezést szokás a $\| \, \|$ duális normájának hívni.

Mutassuk meg, hogy a $\| \, \|_2$ duális normája önmaga.

#### Sol.:
$$
\text{Kell: }\lvert\lvert \cdot \rvert\rvert  _{2} \text{ dualisa } \lvert\lvert \cdot \rvert\rvert _{2}
$$
Definiciobol:
$$
\lvert\lvert x^{*} \rvert\rvert_{2} :=  \sup_{\lvert\lvert v \rvert\rvert _{2} = 1} \lvert x^{*} \cdot v \rvert =? \lvert\lvert x^{*} \rvert\rvert _{2}
$$
Cauchy Schwartz:
$$
\lvert x^{*} \cdot v \rvert  \leq \lvert\lvert x^{*} \rvert\rvert _{2} \cdot \lvert\lvert v \rvert\rvert _{2} \leq \lvert\lvert x^{*} \rvert\rvert _{2}
$$
Mert $\lvert\lvert v \rvert\rvert_{2} = 1$.

Tehat felulrol korlatoztuk, most be kene latni hogy el is tudjuk erni ezt a korlatot.

All.: $v := \frac{x}{\lvert\lvert x \rvert\rvert_{2}}$ -et valasztva el is erheto. Ekkor:
$$
x^{*}\cdot v = \frac{x^{*}x}{\lvert\lvert x \rvert\rvert _{2}} = \frac{\lvert\lvert x \rvert\rvert _{2}^{2}}{\lvert\lvert x \rvert\rvert _{2}} = \lvert\lvert x \rvert\rvert _{2}
$$
### 5. Feladat

Mutassuk meg, hogy $\| \, \|_1$ és $\| \, \|_\infty$ egymás duális normái.

#### Sol.:
Holder egyenlotlenseggel megoldhato (gyakon nem volt).


**Rayleigh-hányados**

Legyen az $A$ mátrix önadjungált $(A^* = A)$. Ekkor a sajátértékei valósak (miért?). Egy $x \neq 0$ vektor esetén a

$$
R_A(x) = \frac{x^*Ax}{x^*x}
$$

kifejezést Rayleigh-hányadosnak nevezzük.

### 6. Feladat
Mutassuk meg, hogy ha $A$ önadjungált, akkor tetszőleges $x \neq 0$ vektorra 

$$
\lambda_{\min}(A) \leq R_A(x) \leq \lambda_{\max}(A).
$$
#### Sol.:
$$
\lvert\lvert A \rvert\rvert _{2}^{2} = \sup_{\lvert\lvert x \rvert\rvert _{2} = 1} \lvert\lvert Ax \rvert\rvert _{2}^{2} = \sup_{\lvert\lvert x \rvert\rvert _{2} = 1} x^{*}A^{*}Ax = \sup_{x\neq 0} \frac{x^{*}A^{*}Ax}{x^{*}x} = \sup_{x \neq 0} R_{A^{*}A}(x)
$$

Mivel $A \in \mathbb{C}^{n \times m}$ onadajungalt, tehat $A^{*} = A$
$A = S\Lambda_{n} S^{-1} = Q\Delta Q^{*}$ a diagonalizacioja, ahol $QQ^{*} = I$.

$$
R_{A}(x) = \frac{x^{*}(Q\Lambda Q^{*})x}{x^{*}x} = \frac{(x^{*}Q)\Lambda(Q^{*}x)}{x^{*}x} =
$$
$$
(y := Q^{*}x)
$$
$$
= \frac{y^{*}\Lambda y}{y^{*}Q^{*}Qy} = \frac{y^{*}\Lambda y}{y^{*}y} = R_{\Lambda}(y) = R_{\Lambda}(Q^{*}x)
$$

tfh $\lvert\lvert y \rvert\rvert = 1$, ekkor:
$$
R_{\Lambda}(Q^{*}y) = y^{*}\Lambda y = y^{*} 
\begin{bmatrix}
\lambda_{1} && \dots && \dots&& 0 \\
0 && \lambda_{2} && \dots && 0 \\
\vdots &&  \vdots  && \vdots  && \vdots \\
0 &&  \dots && \dots && \lambda_{n}
\end{bmatrix}
y
=
\lambda_{1}\bar{y}_{1}y + \dots + \lambda_{n}\bar{y}_{n}y_{n} \leq \lambda_{\max}
$$
Továbbá, $R_{\Lambda}(Q^{*}y) \geq \lambda_{\min}$.

Tehát $\lambda_{\min}(A) \leq R_{A}(x) \leq \lambda_{\max}(A)$

### 8. Feladat

Mutassuk meg, hogy a kettes vektornorma által indukált mátrixnorma invariáns unitér mátrixszal való szorzásra, azaz: ha $U, V$ unitér mátrixok $(U^*U = I = UU^*)$, akkor
$$\| VAU \|_{2,2} = \sup_{\lvert\lvert x \rvert\rvert _{2}=1} \lvert\lvert VAUx \rvert\rvert _{2} = \| A \|_{2,2}.$$


#### Sol.:
Eloszor lassuk be hogy $\lvert\lvert Ux \rvert\rvert = \lvert\lvert x \rvert\rvert$ igaz, mert
$$
\lvert\lvert Ux \rvert\rvert ^{2} = (Ux)^{*}(Ux) = x^{*}U^{*}Ux = x^{*}(U^{*}U)x = x^{*}Ix = x^{*}x = \lvert\lvert x \rvert\rvert ^{2}
$$
Tehat valoban $\lvert\lvert Ux \rvert\rvert = \lvert\lvert x \rvert\rvert$.

Tovabba:

$$
\sup_{\lvert\lvert x \rvert\rvert _{2}=1}\lvert\lvert VAUx \rvert\rvert_{2} = \sup_{\lvert\lvert x \rvert\rvert _{2}=1} \lvert\lvert AUx \rvert\rvert _{2} = \sup_{\lvert\lvert Ux \rvert\rvert = \lvert\lvert x \rvert\rvert =\lvert\lvert y \rvert\rvert =1} \lvert\lvert Ay \rvert\rvert _{2} = \lvert\lvert A \rvert\rvert _{2}
$$

### 9. Feladat

Tegyük fel, hogy $A = U\Sigma V^*$ alakba írható, ahol $U, V$ unitér mátrixok, $\Sigma$ pedig diagonális mátrix, $\sigma_1 \geq \sigma_2 \geq \ldots \geq \sigma_n \geq 0$ főátlóbeli elemekkel.

Mutassuk meg, hogy ekkor
$$
\| A \|_{2,2} = \sigma_1,
$$

továbbá, amennyiben $\sigma_n > 0$, akkor $A$ invertálható és 
$$
\| A^{-1} \|_{2,2} = \sigma_n^{-1}.
$$

#### Sol.:



**Kondíciószám**
  
Ha az $A$ mátrix invertálható, akkor adott $\|\,\|$ indukált norma szerinti kondíciószáma alatt az
$\|A \| \|A^{-1}\|$ kifejezést értjük. Ennek motiválásához legyen $Ax = b, Ay = c$. Ekkor
$$
\| b \| \| x - y \| = \| Ax \| \| A^{-1}(b - c) \| \leq \| A \| \|x\| \|A^{-1}\| \|b - c\|  = \|x\| \|b - c\| \operatorname{cond}_{\|\, \|}(A).
$$
Ha $x \neq 0$, akkor $b \neq 0$. Ekkor normáikkal átosztva adódik, hogy
$$
\frac{\| x - y \|}{\| x \|} \leq  \frac{\|b - c\|}{\| b \|} \operatorname{cond}_{\|\, \|}(A).
$$

Egy következmény, hogy ha egy $Ax = b$ egyenletrendszer jobboldala nem pontosan (például mérési hibákkal terhelten) áll rendelkezésünkre, akkor az így kapott hibás $Ay = c$ rendszer $y$ megoldásának relatív hibája az adott $\|\cdot \|$ norma szerint az eredeti rendszer $x$ megoldásához képest legfeljebb az $A$ mátrixtól és az alkalmazott normától függõ konstansszorosa lehet a $c$ vektor $b$-hez képest vett relatív hibájának.


### 10. Feladat
Tegyük fel, hogy $A$ önadjungált.

a)  Adjunk egy egyszerű formulát az $\| A \|_{2,2}$ kifejezésre.
Tudjuk, hogy a kettes norma altal indukalt matrixnormara: $\| A \|_{2,2} = \sqrt{\lambda_{\max}(A^*A)}$
Mivel $A$ ondajungalt, ezert $A = A^{*}$, tehat $\lvert\lvert A \rvert\rvert_{2, 2} = \sqrt{ \lambda_{\max}(A^{2}) }$.

b) Tegyük fel, hogy $A$ invertálható is. Adjunk egy egyszerű formulát az $\| A^{-1} \|_{2,2}$ kifejezésre.
Szinten mivel $A$ ondajungalt, ezert $A = A^{*}$, tehat $I = A^{-1}A^{*}$ es $(A^{*})^{-1} = A^{-1}$.
Ekkor $\lvert\lvert A^{-1} \rvert\rvert_{2, 2} = \sqrt{ \lambda_{\max}(A^{-1} (A^{-1})^{*}) } = \sqrt{ \lambda_{\max} (A^{-1} A^{-1}) }$.

### 11. Feladat

Gondoljuk meg, hogy ez a két formula az $1$-es és $\infty$-normák esetén az $(1, n)$ méretű mátrixokon, azaz sorvektorokon, a várt, $\infty$-es és $1$-es normákat adják vissza.


### 12. Feladat

Legyen $u, v$ két vektor. Mik a sajátértékei és sajátvektorai az $uv^*$ mátrixnak?

### 17. Feladat

Mutassuk meg, hogy $\operatorname{cond}_{\|\cdot\|} \geq 1.$

#### Sol.:
$$
\operatorname{cond}_{\|\cdot\|} = \lvert\lvert A \rvert\rvert \cdot \lvert\lvert A^{-1} \rvert\rvert  \geq \lvert\lvert A \cdot A^{-1} \rvert\rvert  = \lvert\lvert I \rvert\rvert  = 1
$$


### 18. Feladat

Legyen $U$ unitér mátrix. Mennyi $\operatorname{cond}_2(U)$?

#### Sol.:
$$
\operatorname{cond}_{2}(U) = \lvert\lvert U \rvert\rvert _{2} \cdot \lvert\lvert U^{-1} \rvert\rvert _{2} = \lvert\lvert U \rvert\rvert  \cdot \lvert\lvert U^{*} \rvert\rvert = 1 \cdot 1 = 1
$$


### 19. Feladat

Legyen $A = U \Sigma V^*$, ahol $U,V$ unitér és $\Sigma$ diagonális mátrix $\sigma_1 \geq \sigma_2 \geq \ldots \geq \sigma_n > 0$ főátlóbeli elemekkel. Adjunk egy egyszerű formulát a
$\operatorname{cond}_{2}(A)$ mennyiségre.


#### Sol.:
(9. feladatra epit)



### 25. Feladat

Írjunk programot az

$$
A_n = \left(\matrix{2 & -1 & 0 & \dots & 0\cr -1 & 2 & -1 & \dots & 0 \cr 0 & -1 & 2 & \dots & 0 \cr \vdots & \ddots & \ddots & \ddots& \vdots \cr 0 & \dots & 0 & -1 & 2}\right)
$$

és a

$$
H_n = \left(\matrix{1 & 1/2 & 1/3 & \dots & 1/n \cr 1/2 & 1/3 & 1/4 & \dots & 1/(n+1) \cr 1/3 & 1/4 & 1/5 & \dots & 1/(n+2) \cr \vdots & \vdots & \vdots & \vdots& \vdots \cr 1/n & 1/(n+1) & 1/(n+2) & \dots & 1/(2n-1)}\right)
$$

mátrixok megkonstruálására, majd számíttassuk is ki ezek 1-es, illetve 2-es norma szerinti kondíciószámát egy megfelelő parancs segítségével.



related: [[NumMod 1]]