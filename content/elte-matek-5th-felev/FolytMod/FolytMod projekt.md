## Lorenz modell 

Edward Lorenz 1963-ban írta fel az azóta róla elnevezett alábbi egyenletrendszert, amikor a konvekcióval történö hőáramlást leíró parciális egyenletrendszert vizsgálta. Legyenek $x, y, z: \mathbb{R}_0^{+} \rightarrow \mathbb{R}$ ismeretlen függvények és $\alpha, \beta, \gamma \in \mathbb{R}$ paraméterek:

*Note:* The originial Lorenz modell is defined by $\sigma, \rho, \beta$ parameters. In the following equation the orignal parameters have the following mapping:
$$
\begin{align}
\sigma &= \alpha \\
\rho &= \beta \\
\beta &= \gamma
\end{align}
$$


(4)
$$
\begin{aligned}
x^{\prime}(t) & =\alpha(y(t)-x(t)) \\
y^{\prime}(t) & =x(t)(\beta-z(t))-y(t) \\
z^{\prime}(t) & =x(t) y(t)-\gamma z(t)
\end{aligned}
$$

*a) Számítsuk ki a (4) Lorenz-modell egyensúlyi helyzeteit, valamint azok stabilitását a következő paraméterek értékei mellett. (Szükség lehet a harmadfokú egyenlet Cardano-féle megoldóképletére.)*
(5)
$$
\alpha=10, \quad \beta=28, \quad \gamma=8 / 3
$$
 
**TODO**

$$
\begin{cases}
x' = \alpha y - \alpha x = 0 \\
y' = x(\beta - z) - y = 0 \\
z' = xy - \gamma z = 0
\end{cases}
$$


*b) Nézzünk utána, milyen paraméterértékek esetén fordul elő bifurkáció a rendszerben, és annak milyen a típusa, mi jellemzi.*

**TODO**
Some simulations in `LorenzAttractorBifurcation` 

*c) Oldjuk meg a (4) feladatot numerikusan, és hasonlítsuk össze a $t \mapsto(x(t), y(t), z(t))$ pályákat a paraméterek (5)-ben szereplő és a következő értékekre:*

$$
\alpha=13, \quad \beta=10, \quad \gamma=8 / 3
$$
**Done** See `LorenzAttractorDiffParams` currently the initial states are $[10 + n\varepsilon, 10 + n\varepsilon, 10 + n\varepsilon]$ where $n \in \{ 0, 1, \dots, 10 \}$ and $\varepsilon = 1e-5$ 
What are the initial states?

*d) A paraméterek (5) értékeire vizsgáljuk meg két, közelről indított pálya időbeli lefolyását. Például:*

$$
\begin{array}{lll}
x_0=2, & y_0=5, & z_0=10 \\
\widetilde{x}_0=2,1, & \widetilde{y}_0=5,1, & \widetilde{z}_0=10,1
\end{array}
$$


Mit tapasztalunk? Nézzünk utána a Lorenz-modell kezdeti feltételekre való érzékenységének.

**Done**
Animations in: `downloads/videos/manim`

