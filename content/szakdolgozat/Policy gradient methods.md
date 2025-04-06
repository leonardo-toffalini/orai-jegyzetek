In policy based algorithms:
- There is no value function during or after training
- We directly learn the policy, as opposed to value based algorithms where we implicitly learn the policy via a learnt value function

Advantages of policy based algorithms:
- Better for action spaces that are huge or continuous
	In Q-learning, at each step we took a max over the actions, this is expensive for action spaces that are huge or continuous

Disadvantage:
- Can get stuck in local optima


Policy based methods are optimization problems, where we aim to maximize the policy for a given objective function.

In policy gradient methods, the policy is parameterized, and apply gradient ascent to find local maxima based on the objective function.

Some examples of objecitve functions:
- If the problem is episodic, meaning that it always starts at state $s_{1}$ and terminates eventually and restarts at $s_{1}$, then the objective function of taking the state value of the starting state makes sense:
$$
J_1(\theta)=V^{\pi_\theta}\left(s_1\right)=\mathbb{E}_{\pi_\theta}\left[v_1\right]
$$
- For continuing environments, that is an environment that does not terminate and restert, but keeps on rolling, the average value of the states weighted by their stationary distribution works:
$$
J_{a v V}(\theta)=\sum_s d^{\pi_\theta}(s) V^{\pi_\theta}(s)
$$
- Still for continuing environments, we can also take the average reward after a single step and weigh it by the stationary distibution:
$$
\begin{equation}
J_{a v R}(\theta)=\sum_s d^{\pi_\theta}(s) \sum_a \pi_\theta(s, a) \mathcal{R}_s^a
\end{equation}
$$


If we can analytically calculate the gradient of the policy, using autograd software (pytorch, tensorflow, tinygrad), we can easily apply gradient ascent.

Note, that in the following equations we will see $\nabla_{\theta} \log \pi_{\theta}(s, a)$, before we get confused we explain where this part comes from:
$$
\begin{equation}
\begin{aligned}
\nabla_\theta \pi_\theta(s, a) & =\pi_\theta(s, a) \frac{\nabla_\theta \pi_\theta(s, a)}{\pi_\theta(s, a)} \\
& =\pi_\theta(s, a) \nabla_\theta \log \pi_\theta(s, a)
\end{aligned}
\end{equation}
$$

As you can see, this is just an algebraic manipulation.

**Policy gradient theorem**
For any differentiable policy $\pi_{\theta}$, for any policy objective function $J$, the policy gradient is the following:
$$
\nabla_{\theta}J(\theta) = \mathbb{E}_{\pi_{\theta}} [\nabla_{\theta}\log \pi_{\theta}(s, a) \cdot Q^{\pi_{\theta}}(s, a)]
$$



