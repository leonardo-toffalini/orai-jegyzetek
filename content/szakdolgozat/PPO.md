---
title: Proximal Policy Optimisation
---

Define the *Clipped surrogate* objective function to be the following:
$$
L^{CLIP}(\theta) = \hat{\mathbb{E}}_{t} \Big[\min\big(r_{t}(\theta) \hat{A}_{t}, \; \operatorname{clip}(r_{t}(\theta), \; 1 - \varepsilon, \; 1 + \varepsilon \big) \hat{A}_{t}\Big]
$$
where the ratio function $r_{t}$ is define as follows:
$$
r_{t}(\theta) = \frac{\pi_{\theta}(a_{t} \vert s_{t})}{\pi_{\theta_{old}}(a_{t} \vert s_{t})}
$$

Explanation of each part:
- The ratio function $r_{t}$ tells us how much more likely we are to take action $a_{t}$ at state $s_{t}$ with our current policy than with our old policy.
	This is the part we want to clip. If $r_{t}$ is much bigger than $1$ or much smaller than $1$ that means that our policy changed a lot. This is what we don't want to happen so we clip it to fall into the range $[1 - \varepsilon, \; 1 + \varepsilon ]$.
- The advantage function $\hat{A}_{t}$ tells us how much better the action we have taken at timestep $t$ was compared to the mean.

The following table demonstrates how and when the objective function is clipped.
![[Screenshot 2024-10-12 at 9.38.43.png]]


The final *PPO* objective function looks like the following:
$$
L_{t}^{CLIP + VF + S}(\theta) = \hat{\mathbb{E}}_{t} [L_{t}^{CLIP}(\theta) - c_{1}L_{t}^{VF}(\theta) + c_{2}S[\pi_{\theta}](s_{t})]
$$

Where $c_{1}$ and $c_{2}$ are hyperparameters to weigh each part.
$L_{t}^{VF}$ is the Squared-error value loss.
$S[\pi_{\theta}]$ is the entropy bonus to ensure sufficient exploration.