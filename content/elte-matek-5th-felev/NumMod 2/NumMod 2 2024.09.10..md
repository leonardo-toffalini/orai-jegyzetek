# Runge-Kutta modszerek (1901)
$$
\begin{align*}
y'(t) &= f(t, y(t)) \\
y(t_{0}) &= y_{0}
\end{align*}
$$

$$
\int _{t_{n}}^{t_{n+1}} y'(t) \, dt = \int _{t_{n}}^{t_{n+1}}f(t, y(t)) \, dt 
$$
Newton-Leibniz:
$$
y(t_{n+1}) - y(t_{n}) = \int _{0}^{\tau}f(t_{n} + s, y(t_{n} + s)) \, ds
$$
$$
y(t_{n+1}) = y(t_{n}) + \tau \cdot \int _{0}^{1}f(t_{n} + \xi \tau, y(t_{n} + \xi \tau)) \, d\xi
$$
legyen a fenti kifejezesben $f(\dots) = g(\xi)$

interpolaljuk a $g(\xi)$ fuggvenyt: $g(\xi) \approx \sum_{i=1}^{s}g(c_{i})\cdot l_{i}(\xi)$

$$
\begin{align*}
y(t_{n+1}) &\approx y(t_{n}) + \tau \cdot \int _{0}^{1} \sum_{i=1}^{s}g(c_{i}) \cdot l_{i}(\xi) \, d\xi \\
&= y(t_{n}) + \tau \sum_{i=1}^{s} g(c_{i}) \cdot \int _{0}^{1} l_{i}(\xi) \, d\xi
\end{align*}
$$
legyen $b_{i} = \int _{0}^{1}l_{i}(\xi) \, d\xi$
$$
y(t_{n+1}) \approx y(t_{n}) + \tau \cdot \sum_{i=1}^{s}b_{i} \cdot f(t_{n} + c_{i}\tau, y(t_{n} + c_{i}\tau))
$$

na de itt meg mindig nem tudjuk az $y(t_{n} + c_{i}\tau)$ ertekeket mert a legkesobbi ertek amit tudunk az a $y(t_{n})$
Megolda: Vegezzuk el a Runge-Kutta modszert ezekre a pontokra is.

osszesitve
$$
\begin{align}
y_{n+1} & = y_{n} + \tau \cdot \sum_{i=1}^{s}b_{i} \cdot f(t_{n} + c_{i}\tau, Y_{n, i}) \\
Y_{n,i} & = y_{n} + \tau \sum_{j=1}^{s}a_{ij} \cdot f(t_{n} + c_{j}\tau, Y_{n, j}) \quad j = 1, \dots, s
\end{align}
$$

Amikor $b_{i}$ es $a_{ij}$ tetszolegesek akkor mar ugy nevezzuk, hogy $s$ lepeses Runge-Kutta modszer (adott $s \in \mathbb{N}$ es $c_{i} \in [0, 1]$ mellett)

pelda:
$s= 1, \quad c_{1}=0, \quad b_{1} = 1, a_{11} = 0$

$$
\begin{align}
y_{n+1} &= y_{n} + \tau \cdot \sum_{i=1}^{1}b_{i}\cdot f(t_{n} + c_{i}\tau, Y_{n,i}) \\
&= y_{n} + \tau \cdot b_{1} \cdot f(t_{n} + c_{1}\tau, Y_{n, 1}) \\ \\
&= y_{n} + \tau \cdot f(t_{n}, Y_{n, 1})
\end{align}
$$
$$
\begin{align}
Y_{n,1} &= y_{n} + \tau \cdot \sum_{j=1}^{s} a_{ij}f(t_{n}+c_{j}\tau, Y_{n,j}) \\
&= y_{n} + 0
\end{align}
$$
behelyettesitve a fentibe a most kijott eredmenyt
$$
y_{n+1} = y_{n} + \tau f(t_{n}, y_{n})
$$
Es visszakaptuk az Explicit-Euler modszert!

Hogyan lesz egy Runge-Kutta modszer explicit?
Ha elkepzeljuk az $A = (a_{ij})$ egyutthato matrixot akkor ha ez a matrix felso haromszog matrix akkor a kapott RK modszer explicit lesz.

## Butcher tablo
$$
\begin{align}

\begin{bmatrix}
c_{1}  \\
c_{2} \\
\vdots  \\
c_{s}
\end{bmatrix}
&
\begin{bmatrix}
a_{11}  & a_{12} & \dots & a_{1s} \\
a_{21}  & a_{22} & \dots & a_{2s} \\
\dots  \\
a_{s1}  & a_{s2} & \dots & a_{ss} \\
\end{bmatrix} \\
& 
\begin{bmatrix}
b_{1} & b_{2} & \dots & \dots & b_{s}
\end{bmatrix}
\end{align}
$$

*pelda:*
Javitott Euler (Runge)
$$
y_{n+1} = y_{n} + \tau f\left( t_{n} + \frac{\tau}{2},\, y_{n} + \frac{\tau}{2}f(t_{n}, y_{n}) \right)
$$





