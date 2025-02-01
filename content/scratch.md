### todo
- [x] elkezdunk tanulni az eddigi megszokott modon `500` iteration-ig es utana amikor kilaposodik a kek fuggveny akkor atallunk a utility-re
- [x] wealth -> utility celfuggveny, folytonosan valami konvex kombincaiokent (ld. excalidraw)
- [ ] reward surusege mozduljon a vegefele, ergo ritkuljon a reward (ld. excalidraw)
- [x] FMBEnv-re kb ugyanaz mint AREnv-re
- [x] complete FBMEnv implementation $\lambda = 0.01, \quad \alpha = 2$ vagy $\alpha = 1.5$

- [ ] make a way to look inside the trading of the agent during and after training, capture video is not good enough
- [ ] 

### recap
- added feature for yaml config parsing: `--config-fpath <file-path>`
- implemented FBMEnv with the correct trading dynamics, see the plot
- implemented reward function to be changed during training


$$
v_{\pi}(s) = \mathbb{E}[G_{t} \mid s]
$$
$$
q_{\pi}(s, a) = \mathbb{E}[G_{t}, \mid s, a]
$$

$$
\sum_{a\in A} \pi(a|s)q_\pi(s,a) = \mathbb{E} [q_{\pi}(s, a) \mid s] = \mathbb{E}[\mathbb{E}[G_{t}, \mid s, a], \mid s] \stackrel{\text{tower rule}}{=} \mathbb{E}[G_{t} \mid s] = v_\pi(s)
$$

