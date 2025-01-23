### todo
- [x] a kek-narancs plot legyen meg `50_000`-re is

- [ ] elkezdunk tanulni az eddigi megszokott modon `500` iteration-ig es utana amikor kilaposodik a kek fuggveny akkor atallunk a utility-re
- [ ] wealth -> utility celfuggveny, folytonosan valami konvex kombincaiokent (ld. excalidraw)
- [ ] reward surusege mozduljon a vegefele, ergo ritkuljon a reward (ld. excalidraw)
- [x] FMBEnv-re kb ugyanaz mint AREnv-re
- [ ] complete FBMEnv implementation $\lambda = 0.01, \quad \alpha = 2$ vagy $\alpha = 1.5$

### recap
- asymptotic training -> $T = 2^1, 2^2, 2^3, ..., 2^{10}$
- asymptotic eval, see InvestML overleaf project technical report
- train eval lefuttatva $50000$-re -> meg rosszabb eredmeny :(
- FBMEnv-en probalkozas -> nem tanul -> LSTM -> meg mindig nem tanul
- kiprobaltam utility alapu celfuggvenyt:
$$
R(t_{i}) = \Delta U(t_{i}) = U(t_{i}) - U(t_{i-1}) = -e^{-w_{i}} + e^{-w_{i-1}}
$$
$$
\implies \sum_{i=1}^{T}R(t_{i}) = \sum_{i=1}^{T}\Delta U(t_{i}) = U(t_{1}) + U(t_{T})
$$
mivel $w_{1}$ fix ezert $U(t_{1})$ is fix es nem baj ha mindig hozzaadunk egy konstanst.

problema: bugok neptune-al float overflow miatt, idealisan `np.float128`-at hasznalnek az extra precizitas miatt, de ez nem json parseable