---
title: Markov Decision Process
---
A *markov decision process*, **MDP** for short,  is defined by the tuple $(\mathcal{S}, \; \mathcal{A}, \; \mathcal{P}_{a}, \; \mathcal{R}_{a})$ where
- $\mathcal{S}$ is the set of all possible states, also called the *state space*
- $\mathcal{A}$ is the set of all possible actions, also known as the *action space*
- $\mathcal{P}_{a}$ is a probability function on $\mathcal{S} \times \mathcal{S}$ such that $\mathcal{P}_{a}(s, s')$ is the probability of endig up in state $s'$ upon taking action $a$ at state $s$. *(todo, this could be explained in more detail)*
- $\mathcal{R}_{a} : \mathcal{S} \times \mathcal{S} \to \mathbb{R} \quad \forall a \in \mathcal{A}$ such that $\mathcal{R}_{a}(s, s')$ represents reward recieved after taking action $a$ at state $s$ that lead to gettting to state $s'$.

Note, that in a markov decision process the next state is only reliant the previous state, all the other states that have come before are not taken into count.