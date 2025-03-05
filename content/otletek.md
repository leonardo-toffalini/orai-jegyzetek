1. add moving weighted penalization of share count
$$
P = \frac{t}{T} \cdot X^{1}_{t} \cdot c
$$
where $c$ is the base weight


$$
P = \frac{t}{T} \cdot \lambda \cdot {X_{t}^{1}}^{\alpha} \cdot c
$$
where $X_{t}^{1}$ is the risky asset at timestep $t$
$$
P = \beta ^{T-t} \cdot \lambda \cdot {X_{t}^{1}}^{\alpha} \cdot c
$$
where $\beta \in [0,1]$

$R_{\text{new}} = R_{\text{old}} - P$

1. strip out the price and only try to learn liquidation
	1. $\pm Z$ reszveny az elejen $\to$ test env: arfolyam $A \sim N(0, 1)$ , kezdoreszveny $Z \sim N(0, \text{nagy szam})$, kulonben sima FBM stepes reward
	2. arfolyam: $t \to t^{\kappa}$ where $\kappa \sim  U(0, 1)$ , kulonben sima FBM step es reward
