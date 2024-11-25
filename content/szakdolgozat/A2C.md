---
title: Advantage Actor Critic
---
A2C is a policy based reinforcement learning algorithm where there is an Actor netwrk and a Critic network.

The **Actor network** takes as input the the *state* of the environment and outputs an *action*.
The **Critic network** takes as input a *state-action pair* and outputs a value of how 'good' it is to take said action at given state.

Let $N_{A}: \mathcal{S} \to \mathcal{A}$ be the Actor network and $N_{C}: \mathcal{S} \times \mathcal{A} \to \mathbb{R}$ be the Critic network.
Define the output of the Critic network $N_{C}$ to be the following $N_{C}(s, a) = \hat{q}_{w}(s, a)$ where $w$ denotes the weights of the Critic network.

Let $\theta$ represent the parameters of the Actor network.
The update of the parameters of the Actor network is given by the following equation:
$$
\Delta \theta = \alpha \nabla_{\theta} (\log \pi_{\theta}(s, a)) \hat{q}_{w}(s, a)
$$
where $\pi_{\theta}$ denotes the current policy with parameters $\theta$.

The update of the parameters of the Critic network is given by the following equation:
$$
\Delta w = \beta \nabla_{w} \hat{q}_{w}(s, a) \cdot \stackrel{\text{TD error}}{\overbrace{(R(s, a) + \gamma \hat{q}_{w}(s_{t+1}, a_{t+1}) - \hat{q}_{w}(s_{t}, a_{t})}}
$$
where $\text{TD error}$ means *Temporal Difference error* and represents how much the Critic network is off on the estimation of the value of the state-action pair.

Define the *Advantage function* to be the following:
$$
A(s, a) = Q(s, a) - V(s)
$$
where $Q(s, a)$ represents the Q-value of action $a$ at state $s$ and $V(s)$ represents the average value of the sate, meaning the mean reward.
In other words the Advantage function tells us how good action $a$ is at state $s$ compared to the mean at state $s$. If $A(s, a) > 0$ then action $a$ is good in sate $s$, otherwise it is bad.

The problem is that we don't know the Q-value function, otherwise we wouldn't be trying to estimate it with the Critic network. THe remedy this problem we approximate the Q-value function the following way:
$$
Q(s, a) \approx R(s, a) + \gamma V(s')
$$

Substituting this approximation back into the Advantage function we get the following:
$$
A(s, a) = Q(s, a) - V(s) \approx R(s, a) + \gamma V(s') - V(s)
$$
The right side of the above equation looks just like the previously mentioned TD error except that before we didn't use $V$ but used it's approximation $\hat{q}_{w}$. We will call this TD error too.
