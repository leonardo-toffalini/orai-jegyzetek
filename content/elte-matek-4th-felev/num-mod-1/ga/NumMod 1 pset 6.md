### 1. Feladat
$p(x) = \sum_{k = 0}^{n}c_{k} \cdot x^{k}$
$$
\begin{align}
p(x_{1}) & = f_{1} \\
p(x_{2})  & = f_{2} \\
 & \;\; \vdots \\
p(x_{n}) & = f_{n}
\end{align}
$$
Tehát:
$$
\begin{align}
\sum_{k = 0}^{n}c_{k} \cdot x_{1}^{k} & = f_{1} \\
\sum_{k = 0}^{n}c_{k} \cdot x_{2}^{k} & = f_{2} \\
& \;\;\;\vdots \\
\sum_{k = 0}^{n}c_{k} \cdot x_{n}^{k} & = f_{n}
\end{align}
$$
Legyen $c = (c_{1}, \dots, c_{n})$ és $z(x) = (1, x, \dots, x^{n})$
Ekkor a fenti egyenletrendszer a következő:
$$
\begin{align}
c \cdot z(x_{1}) & = f_{1} \\
c \cdot z(x_{2}) & = f_{2} \\
& \;\;\;\vdots \\
c \cdot z(x_{n}) & = f_{n}
\end{align}
$$
Legyen 
$$
A = \begin{bmatrix}
1 & x_{1} & x_{1}^{2} & x_{1}^{3} & \dots & x_{1}^{n} \\
1 & x_{2} & x_{2}^{2} & x_{2}^{3} & \dots & x_{2}^{n} \\
\vdots & \vdots & \vdots & \vdots & \ddots & \vdots \\
1 & x_{n} & x_{n}^{2} & x_{n}^{3} & \dots & x_{n}^{n}
\end{bmatrix} \quad
b = \begin{bmatrix}
f_{1} \\
f_{2} \\
f_{3} \\
\vdots \\
f_{n}
\end{bmatrix}
$$
Ekkor a fenti egyenletrendszer a következő:
$$
Ac = b
$$

### 2. Feladat
$x_{0} = -1, \quad x_{1} = 0, \quad x_{2} = 1$
$$
l_{0}(x) = \frac{x(x-1)}{(0 + 1)(1 + 1)}
$$
$$
l_{1}(x) = \frac{(x + 1)(x - 1)}{(-1 - 0)(1 - 0)}
$$
$$
l_{2}(x) = \frac{(x+1)x}{(-1 - 1)(0 - 1)}
$$
$f_{0} = 1, \quad f_{1} = 0, \quad f_{2} = 1$
$$
p(x) = 1 \cdot \frac{x(x-1)}{(0 + 1)(1 + 1)} + 0 \cdot \frac{(x + 1)(x - 1)}{(-1 - 0)(1 - 0)} + 1 \cdot \frac{(x+1)x}{(-1 - 1)(0 - 1)} 
$$
$$
p(x) = \frac{x(x-1)}{2} + \frac{x(x+1)}{2}
$$

### 3. Feladat
A hiba:
$$
a_{0} \cdot \omega_{n}(x)
$$




related: [[NumMod 1]]