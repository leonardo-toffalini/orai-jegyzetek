---
title: Thesis outline
---
# Introduction
Supply a brief summary of the problem at hand. Explain what the problem is and why the reader should care about it. Write about the approach(es) that worked and maybe some that didn't.

# Reinforcement learning quickstart
A short roadmap to get the reader up to date with the most common approaches in Reinforcement Learning.

## Markov decision processes
The formalism behind the RL framework. For more information, see [[MDP]].

## Reinforcement learning algorithms
A reinforcement learning algorithm provides a policy, which is a function that tells us what action to take at each state. An algorithm can either directly learng the policy function or it can learn a value function that maps states to values and the policy will be just to take the action that leads to the highest valued state.

A *policy function*, commonly denoted as $\pi$ is a function that given a state $s \in \mathcal{S}$ it returns a probability distribution over $\mathcal{A}$. Note, that the probability function on $\mathcal{A}$ can be probability $1$ for $a_{i}$ and $0$ for all other actions, meaning that at state $s$ we always take action $a$, in this case the policy function is called deterministic.

A value function, commonly denoted as $v: \mathcal{S} \to \mathbb{R}$ is a function that maps states to values. The value of a state is defined as the expected discounted reward, formally
$$
v_{\pi}(s) = \mathbb{E}_{\pi}\left( \sum_{k=0}^{\infty} \gamma ^{k}R_{t+k} \;\Bigg|\; s_{t-1} = s \right)
$$
where $R_{i}$ denotes the reward received at timestep $i$.

Note, the $\pi$ in the index of the value function, this means that we take the expected discounted reward based on the trivial policy, meaning always taking the action that leads to the highest valued state.


## Value iteration
For more information, see [[Value iteration]].

## Q-learning
For more information, see [[Q-learning]].

## A2C
For more information, see [[A2C]].

## TRPO
For more information, see [[TRPO]].
[paper](https://arxiv.org/pdf/1502.05477v5)

## PPO
For more information, see [[PPO]].

# Optimal trading on stochastic prices
## The problem
[paper](https://arxiv.org/pdf/1501.01506)

# Results
hopefully some nice results here

