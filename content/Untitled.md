$$
\begin{aligned}
q_{\pi}(s, a) &= \mathbb{E}[G_{t} \mid s_{t} = s, a_{t} = a] \\
&= \mathbb{E}[R_{t+1} + \gamma G_{t+1} \mid s_{t}=s, a_{t}=a] \\
&= \mathbb{E}[R_{t+1} + \gamma \mathbb{E}[G_{t+1} \mid s_{t+1}=s', a_{t+1}=a'] \mid s_{t}=s, a_{t}=a] \\
&= \mathbb{E}[R_{t+1} + \gamma q_{\pi}(s_{t+1}, a_{t+1}) \mid s_{t}=s, a_{t}=a]
\end{aligned}
$$