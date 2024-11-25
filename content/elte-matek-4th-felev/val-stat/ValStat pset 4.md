### 1.
Definiáljuk az alábbi diszkrét eloszlást: $\mathbb{P}(X = -1) = c, \; \mathbb{P}(X = 1) = 3c, \; \mathbb{P}(X = 2) = 1 - 4c$, ahol $0 < c < \frac{1}{4}$ az ismeretlen paraméter. A $-1$, $1$ és $2$-es értékekből rendre a következő mennyiségűt kaptuk egy $20$ elemű mintában: $4, 10, 6$. Határozzuk meg $c$ maximumlikelihood-, illetve momentummódszeres becslését!

***Megoldás:***
*MLE:*
$$
\begin{align}
L_{c}(X_{1}, \dots, X_{20}) & = \prod_{j = 1}^{20}\mathbb{P}(X_{j} = k_{j}) \\
 & = c^{4}\cdot(3c)^{10}\cdot(1-4c)^{6} \\
 & = 3^{10} \cdot c^{14} \cdot (1 - 4c)^{6}
\end{align}
$$
Ennek keressük a maximumját, tehát deriváljunk!
$$
\begin{align}
0 = L_{c}'(X_{1}, \dots, X_{20}) & = 14 \cdot 3^{10} c^{13} \cdot (1 - 4c)^{6} + 3^{10} \cdot c^{14} \cdot (-4) \cdot 6(1 - 4c)^{5} \\
0 & = (1 - 4c)^{5} \bigg( 14 \cdot 3^{10} \cdot c^{13} \cdot (1 - 4c) - 3^{10} \cdot 24 \cdot c^{14} \bigg)
\end{align}
$$
Első eset: $(1 - 4c)^{5} = 0 \implies c = \frac{1}{4}$, de ez nem lehet, mert a feladat leírásában $c < \frac{1}{4}$.
Második eset: $14 \cdot c^{13} \cdot (1 - 4c) - 24 \cdot c^{14} = 0$
$$
\iff 14(1 - 4c) -24c = 0 \quad \text{(le lehet osztani }c\text{-vel, mert } c > 0\text{)}
$$
$$
\begin{align}
14 - 56c - 24c & = 0 \\
14 & = 80c
\end{align}
$$
$$
\implies \boxed{\frac{7}{40} = c}
$$

*Momentummódszer*:
$$
\begin{align}
\mathbb{E}_{c}(X_{1}) & = \frac{1}{20}\sum_{j=1}^{20}X_{j} \\
\mathbb{E}_{c}(X_{1}^{2}) & = \frac{1}{20}\sum_{j=1}^{20}X_{j}^{2} \\
\mathbb{E}_{c}(X_{1}^{3})  & = \frac{1}{20}\sum_{j=1}^{20}X_{j}^{3} \\
& \;\;\; \vdots
\end{align}
$$
$$
\mathbb{E}_{c}(X_{1}) = -1 \cdot c + 1 \cdot 3c + 2 \cdot (1 - 4c) = 2 - 6c
$$
$$
\frac{1}{20}\sum_{j=1}^{20}X_{j} = \frac{1}{20}(-1 \cdot 4 + 1 \cdot 10 + 2 \cdot 6) = \frac{9}{10}
$$
$$
\begin{align}
\implies 2 - 6c & = \frac{9}{10} \\
\frac{11}{10} & = 6c \\
\end{align}
$$
$$
\implies \boxed{\frac{11}{60} = c}
$$

*Megfigyelés*: Az ML-módszer szerint $c = \frac{7}{40} = 0.175$, viszont a momentummódszer szerint $c = \frac{11}{60} = 0.18\overline{3}$.