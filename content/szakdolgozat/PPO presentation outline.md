## What is Reinforcement Learning?
Quick informal recap of what RL is, for the audience to get the vibe

## Recap
### Reminder of MDPs
Remind the audience of the basic structure of an MDP
- S: state space
- A: action space
- P: state transition probability function
- R: reward function

### Policy
A policy is just a mapping from states to actions, it can be deterministic or it van be stochastic

### Value functions
- return
$$
G_{t} = R_{t} + \gamma R_{t+1} + \gamma ^{2} R_{t+2} + \dots
$$
- state value:
$$
v_{\pi}(s) = \mathbb{E}_{\pi}[G_{t} \mid s_{t} = s]
$$

- action value:
$$
q_{\pi}(s, a) = \mathbb{E}_{\pi}[G_{t} \mid s_{t} = s, \; a_{t} = a]
$$

### Value functions visual representation
insert graphic of one step lookahead

## Algorithms
### Value based
learn a value function, and derive a policy from the values (e.g. $\varepsilon$-greedy)

we will not talk about these, only the pros and cons

pros:
- easy to understand
- easy to implement
cons:
- really hard for high dimensional state and/or action spaces
- hard to learn stochastic policy

### Policy based
Directly learn a policy, no need for intermediary value function

pros:
- easily adaptable for high dimensional state and/or action spaces
cons:
- can get stuck in local optima

### Value based vs Policy based
insert infographic

### Policy gradient
Define a loss function and change the parameters of the policy in the steepest direction

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

### Policy gradient theorem
The following theorem is provided *as is*

For any differentiable policy $\pi_{\theta}$, for any policy objective function $J$, the policy gradient is the following:
$$
\nabla_{\theta}J(\theta) = \mathbb{E}_{\pi_{\theta}} [\nabla_{\theta}\log \pi_{\theta}(s, a) \cdot Q^{\pi_{\theta}}(s, a)]
$$

where $Q^{\pi_{\theta}}(s, a)$ is the long-term value of a state action pair.

### Actor Critic
Approximate $Q^{\pi_{\theta}}$ (Critic) some way and use the approximate $Q$ to update the parameters of the Actor

We will not explain how to approximate $Q$ in this presentation

### Baseline function
The policy gradient theorem still holds if we subtract a baseline function from $Q$
$$
\nabla_{\theta}J(\theta) = \mathbb{E}_{\pi_{\theta}} [\nabla_{\theta}\log \pi_{\theta}(s, a) \cdot (Q^{\pi_{\theta}}(s, a) - B(s))]
$$

we can take the state value function as a baseline: $B(s) = V^{\pi_{\theta}}(s)$

### Advantage function
$$
A^{\pi_{\theta}}(s, a) = Q^{\pi_{\theta}}(s, a) - V^{\pi_{\theta}}(s)
$$
$$
\nabla_{\theta}J(\theta) = \mathbb{E}_{\pi_{\theta}} [\nabla_{\theta}\log \pi_{\theta}(s, a) \cdot A^{\pi_{\theta}}(s, a)]
$$

### Estimating the advantage function
$$
Q^{\pi_{\theta}}(s, a) = \mathbb{E}[G_{t} \mid s, a] = \mathbb{E}_{\pi_{\theta}} [r + \gamma V^{\pi_{\theta}}(s') \mid s, a]
$$

$$
A^{\pi_{\theta}}(s, a) = \mathbb{E}_{\pi_{\theta}} [r + \gamma V^{\pi_{\theta}}(s') \mid s, a] - V^{\pi_{\theta}}(s)
$$

introduce the td error:
$$
\delta ^{\pi_{\theta}} = r + \gamma V^{\pi_{\theta}}(s') - V^{\pi_{\theta}}(s)
$$

$$
\mathbb{E}_{\pi_{\theta}}[\delta ^{\pi_{\theta}} \mid s, a] = A^{\pi_{\theta}}(s, a)
$$
so the td error is an unbiased estimator of the advantage function

### Generalized Advantage Estimator
A single step TD error may result in high variance, thsu we introduce the following:
$$
A^{(k)}_{t} = \sum_{m=0} ^{k-1} \gamma ^{m} \delta ^{\pi_{\theta}}_{t+1} = -V^{\pi_{\theta}}(s_{t}) + r_{t} + \gamma r_{t+1} + \gamma ^{2}r_{t+2} + \dots + \gamma ^{k}V^{\pi_{\theta}}(s_{t+k})
$$
as $k$ increases, the variance decreases

$$
A^{\text{GAE}}_{t} = (1 - \lambda)\left(A^{(1)}_{t} + \lambda A^{(2)}_{t} + \lambda ^{2}A^{(3)}_{t} + \dots\right)
$$

### Clipped Surrogate Objective
$$
L^{\text{CLIP}}(\theta)=\hat{\mathbb{E}}_t\left[\min \left(r_t(\theta) \hat{A}_t, \operatorname{clip}\left(r_t(\theta), 1-\epsilon, 1+\epsilon\right) \hat{A}_t\right)\right]
$$

### PPO (finally)
for each iteration, run the $N$ parallel environments for $T$ timesteps ($T \neq$ episode length), optimize the loss function $L$ with respest to $\theta$ for $K$ epochs and minibatch size $M$


