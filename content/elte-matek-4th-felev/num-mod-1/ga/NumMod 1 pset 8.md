### 1. Feladat
$$
f(x)=L_n(x)+\frac{1}{(n+1) !} f^{n+1}(\xi) w_n(x)
$$
$$
L_{n}(x) = \frac{x - x_{0}}{x_{0} - h - x_{0}} \cdot \frac{x - (x_{0} + h)}{x_{0} - h - (x_{0} + h)} \cdot f(x_{0} - h) + \frac{x - (x_{0} - h)}{x_{0} - (x_{0} - h)} \cdot \frac{x - (x_{0} + h)}{x_{0} - (x_{0} + h)} \cdot f(x_{0}) + \frac{x - (x_{0} - h)}{x_{0} + h - (x_{0} - h)} \cdot \frac{x - x_{0}}{x_{0} + h - x_{0}} \cdot f(x_{0} + h)
$$
$$
L_{n}(x) = \frac{(x - x_{0})(x - x_{0} - h)}{2h^{2}} \cdot f(x_{0} - h) - \frac{(x - x_{0} + h)(x - x_{0} - h)}{h^{2}} \cdot f(x_{0}) + \frac{(x - x_{0} + h)(x - x_{0})}{2h^{2}} \cdot f(x_{0} + h)
$$
$$
L_{n}(x) = \frac{1}{2h^{2}} ((x - x_{0})(x - x_{0} - h)f(x_{0} - h)) - 2(x - x_{0} + h)(x - x_{0} - h)f(x_{0}) + (x - x_{0} + h)(x - x_{0})f(x_{0} + h)
$$
$$
f'(x_{0}) \approx L_{n}'(x_{0})
$$

### 2. Feladat
$$
f''(x_{0}) \approx L_{n}''(x_{0})
$$

### 3. Feladat
$$
f(x + h) = f(x) + hf'(x) + \frac{h^{2}}{2}f''(x) + \frac{h^{3}}{6}f'''(x) + O(h^{4})
$$
$$
f(x - h) = f(x) - hf'(x) + \frac{h^{2}}{2}f''(x) - \frac{h^{3}}{6}f'''(x) + O(h^{4})
$$
$$
f(x) = f(x)
$$

(1) + (2) - 2*(3)
$$
f(x + h) + f(x - h) - 2f(x) = h^{2}f''(x) + O(h^{4})
$$
$$
\implies f''(x) = \frac{f(x + h) + f(x-h) - 2f(x)}{h^{2}} + O(h^{2})
$$

### 4. Feladat
$$
f(x + 2h) = f(x) + 2hf'(x) + \frac{4h^{2}}{2}f''(x) + \frac{8h^{3}}{6}f'''(x) + O(h^{4})
$$
$$
f(x - h) = f(x) - hf'(x) + \frac{h^{2}}{2}f''(x) - \frac{h^{3}}{6}f'''(x) + O(h^{4})
$$
$$
f(x) = f(x)
$$
$$
f''(x) \stackrel{?}{\approx} \alpha f(x + 2h) - (\alpha + \beta)f(x) + \beta f(x - h)
$$
(1) + 2*(2)
$$
f(x + 2h) + 2f(x - h) = 3f(x) + 3h^{2}f''(x) + f'''(x) + O(h^{4})
$$

(1) + 2*(2) - 3(3)
$$
f(x + 2h) + 2f(x-h) - 3f(x) = 3h^{2}f''(x) + f'''(x) + O(h^{4})
$$
$$
f''(x) = \frac{ f(x + 2h) + 2f(x-h) - 3f(x) - f'''(x)}{3h^{2}} + O(h^{2})
$$
tehát $\alpha = 1$ és $\beta = -3$ ekkor $-(\alpha + \beta) = -(1 - 3) = -(-2) = 2$ és így tényleg másodrendű az approximáció

### 6. Feladat
$$
D_{0} = \begin{bmatrix}
-2 & 1 & 0 & 0 & \dots & 0 \\
1 & -2 & 1 & 0 & \dots & 0 \\
0 & 1 & -2 & 1 & \dots & 0 \\
0 & 0 & 1 & -2 & \dots & 0 \\
\vdots & \vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & 0 & \dots & -2
\end{bmatrix}
$$




related: [[NumMod 1]]