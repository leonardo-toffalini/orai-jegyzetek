---
title: Q-learning
---
In the value iteration algorithm we must know the entire MDP and all the rewards for each action at each state. In general, we can't assume this knowledge, since knowing the entire MDP would assume a perfect modell of the real world in most cases which is unachievable.

Q-learning solves this problem by only assigning a value to the visited states, thus leading to a better modell of the environment upon further iterations. In this framework the only thing we need to know is the reward recieved upon taking action $a$ at state $s$. The Q-learning algorithm approaches the Value iteration algorithm.

