### 1.
Consider the following integer programming problem.
$$
\begin{align}
\max & \quad x_{1} + 2x_{2} \\
\text{subject to} & \quad-3x_{1} + 4x_{2} \leq 4 \\
 & \quad 3x_{1} + 2x_{2} \leq 11 \\
 & \quad 2x_{1} - x_{2} \leq 5 \\
 & \quad x_{1}, x_{2} \geq 0 \\
 & \quad x_{1}, x_{2} \in \mathbb{Z}
\end{align}
$$
Use a figure to answer the following questions.
a) What is the optimal cost of the linear programming relaxation? What is the optimal cost of the integer programming problem?
b) What is the convex hull of the set of all solutions to the integer programming problem?

***Megoldás:***
b) Legyen $K := \operatorname{conv}\{ (0,0), (0, 1), (2, 0), (2, 2), (3, 1) \}$. Minden megengedett megoldása az IP feladatnak benne van $K$-ban.

### 2.
A company is manufacturing $k$ different products using $m$ resources. The amounts of available resources are given, together with the requirement of each of them for the different products. The selling price of the products are also known.

a) Write up an IP that aims at maximizing the total profit.
b) Adjust the model if starting the production of product $i$ requires a cost of $s_{i}$.

***Megoldás***:
a)
Legyenek $r_{1}, r_{2}, \dots, r_{m}$ az alapanyagok mennyiségeit jelölő változók.
Legyen az $i$-edik termékhez szükséges alapanyag $g_{i} = \{ y_{1}, \dots, y_{m} \}$, ahol $y_{j}$ jelöli, hogy a $j$-edik alapanyagból mennyi kell (ha nulla kell akkor nem rakjuk bele)
Legyen $c_{i}$ az $i$-edik termék ára.
Jelölje $x_{i}$, hogy az $i$-edik termékből mennyit adunk el.
Ekkor a célunk az, hogy $\sum x_{i} \cdot c_{i}$ maximális legyen valamilyen feltételek mellett.
Feltétel, hogy legyen elég alapanyag az összes termékre, tehát:
$$
\sum_{i: \, y_{j} \in g_{i}} x_{i} \cdot y_{j} \leq r_{j}
$$
Ez az egyenlőtlenség azt jelenti, hogy a $j$-edik alapanyagból van elég.

Tehát az IP feladat a következő:
$$
\begin{align}
\max & \quad \sum_{i = 1}^{k} x_{i} \cdot c_{i} \\
\text{s.t.} & \quad \sum_{i: \, y_{j} \in g_{i}} x_{i} \cdot y_{j} \leq r_{j} \quad \forall j \in \{ 1, 2, \dots, m \} \\
\text{s.t.} & \quad x_{i} \in \mathbb{Z}_{0}^{+} \quad \forall i \in \{ 1, 2, \dots, k \}
\end{align}
$$

b)
Kellenének $z_{1}, \dots, z_{k}$ bináris változók, ahol
$$
z_{i} = \begin{cases}
0 & \text{ha }\; x_{i} = 0 \\
1 & \text{ha }\; x_{i} > 0
\end{cases}
$$
Vegyük hozzá az előző IP feladatunkhoz a következő feltételt:
$$
z_{i} \leq x_{i} \leq N \cdot z_{i}
$$
Ahol $N$ jelöli a legnagyobb ábrázolható számot (lényegében végtelent).

Ha $x_{i} = 0$
$$
z_{i} \leq 0 \leq N \cdot z_{i}
$$
Ekkor $z_{i} = 0$, mert csak ekkor teljesül az egyenlőtlenség, mert $z_{i} = 1$ esetben sérül a $z_{i} \leq x_{i}$ egyenlőtlenség.


Ha $x_{i} \geq 1$ 
$$
z_{i} \leq x_{i} \leq N \cdot z_{i}
$$
Ekkor $z_{i} = 1$, mert ha $z_{i} = 0$, akkor sérül az $x_{i} \leq N\cdot z_{i}$ egyenlőtlenség.
Tehát valóban ponta akkor $1$ a $z_{i}$, ha $x_{i} > 0$ és pont akkor $0$ ha $x_{i} = 0$.

Jelölje $s_{i}$ az $i$-edik termék termelésének indításához szükséges pénzt.
Így a célfüggvény is módosul:
$$
\begin{align}
\max & \quad \sum_{i = 1}^{k} x_{i} \cdot c_{i} - z_{i} \cdot s_{i}
\end{align}
$$
Ekkor pontosan akkor vonjuk le $s_{i}$ pénzt az összegből, ha termelünk az $i$-edik termékből.


related: [[DL-CO]]