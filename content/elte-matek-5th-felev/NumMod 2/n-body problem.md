$$
F = ma
$$
$$
a = \frac{F}{m}
$$
$$
F = \gamma \cdot \frac{m_{1}m_{2}}{r_{12}^{2}}
$$
$$
a_{1} = \gamma \cdot \frac{\frac{m_{1}m_{2}}{r_{12}^{2}}}{m_{1}} = \gamma \cdot \frac{m_{2}}{r_{12}^{2}}
$$
Ez csak a nagysaga a gyorsulasnak, de $a$ egy vektor, ezert ki kell szamolnunk az iranyat is. A gyorsulas iranya az ero iranyaval egyezik meg, ami a masik test fele nez. Tehat az irany
$$
\frac{\vec{x}_{j} - \vec{x}_{i}}{\| \vec{x}_{j} - \vec{x}_{i} \| }
$$

Tehat a gyorsulas vektora a kovetkezo:
$$
a_{i} = m_{j} \frac{\vec{x}_{j} - \vec{x}_{i}}{\| \vec{x}_{j} - \vec{x}_{i} \|^{3} }
$$


Az n-test vonzomozgasat leiro differencial egyenlet a kovetkezo:

$$
x_{i}''(t) = \sum_{i \neq j} m_{j} \frac{\vec{x_{j}} - \vec{x_{i}}}{ \| \vec{x_{j}} - \vec{x_{i}} \|^{3}  }
$$
A fenti masodrendu differencial egyenletet at lehet irni kett elso rendu diff egyenletkent a kovetkezo modon:
$$
\begin{align}
x_{i}'(t) &= v_{i}(t) \\
v_{i}'(t) &= \sum_{i \neq j} m_{j} \frac{\vec{x_{j}} - \vec{x_{i}}}{ \| \vec{x_{j}} - \vec{x_{i}} \|^{3}  }
\end{align}
$$

### Spec. eset: n = 3
$$
\begin{align}
u_{1} &= x_{1},  &u_{2} = x_{1}', \quad &u_{3} = y_{1},  &u_{4} = y_{1}' \\
u_{5} &= x_{2},  &u_{6} = x_{2}', \quad &u_{7} = y_{2}, &u_{8} = y_{2}' \\
u_{9} &= x_{3},  &u_{10} = x_{3}', \quad &u_{11} = y_{3}, &u_{12} = y_{3}'
\end{align}
$$

$$
\begin{bmatrix}
u_{1} \\ u_{2} \\ u_{3} \\ u_{4} \\
\end{bmatrix} =
\begin{bmatrix}
x_{1} \\ x_{1}' \\ y_{1} \\ y_{1}'
\end{bmatrix}
$$

differencial egyenlet:
elso test
$$
\begin{align}
p_{1x}' &= v_{1x} \\
v_{1x}' &= m_{2} \frac{p_{2x} - p_{1x}}{r_{21}^{3}} + m_{3} \frac{p_{3x} - p_{1x}}{r_{31}^{3}} \\
p_{1y}' &= v_{1y} \\
v_{1y}' &= m_{2} \frac{p_{2y} - p_{1y}}{r_{21}^{3}} + m_{3} \frac{p_{3y} - p_{1y}}{r_{31}^{3}} \\
\end{align}
$$

masodik test
$$
\begin{align}
p_{2x}' &= v_{2x} \\
v_{2x}' &= m_{1} \frac{p_{1x} - p_{2x}}{r_{21}^{3}} + m_{3} \frac{p_{3x} - p_{2x}}{r_{32}^{3}} \\
p_{2y}' &= v_{2y} \\
v_{2y}' &= m_{1} \frac{p_{1y} - p_{2y}}{r_{21}^{3}} + m_{3} \frac{p_{3y} - p_{2y}}{r_{32}^{3}} \\
\end{align}
$$

harmadik test
$$
\begin{align}
p_{3x}' &= v_{3x} \\
v_{3x}' &= m_{1} \frac{p_{1x} - p_{3x}}{r_{31}^{3}} + m_{2} \frac{p_{2x} - p_{3x}}{r_{32}^{3}} \\
p_{3y}' &= v_{3y} \\
v_{3y}' &= m_{1} \frac{p_{1y} - p_{3y}}{r_{31}^{3}} + m_{2} \frac{p_{2y} - p_{3y}}{r_{32}^{3}} \\
\end{align}
$$


a vektormezot leiro matrix:
$$ A =
\begin{bmatrix}
0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
a \\
0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
a \\
0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \\
a \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \\
a \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\
a \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 1
\end{bmatrix}
$$

