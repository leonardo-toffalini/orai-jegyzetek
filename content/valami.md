$$
\int f_{\alpha}(t) \, dt = K(f_{\alpha}(\cdot))
$$
$$
f_{\alpha}(t) = E\left|S_t\right|^{\frac{\alpha}{\alpha-1}}
$$

$$
Q(T):=\int_0^T E\left|S_t\right|^{\frac{\alpha}{\alpha-1}} d t
$$
$$
\tilde{Q} (T):= \mathbb{E} \left( \int_0^T \left|S_t\right|^{\frac{\alpha}{\alpha-1}}dt \right)
$$

$$
\bar{Q} (T):= \mathbb{E} \left(\int_0^T \left|S_t\right| d t \right)^{\frac{\alpha}{\alpha-1}}
$$


$$
f_{\alpha}(t) \approx 
$$

$$
S_{t} \sim N(0, t^{2H})
$$


- [ ] aszimptotikosan optimalis strategianak a konstansszorzojat keressuk meg binaris keresessel
- [ ] $Q$ market bound-ot tuntessuk fel a train-eval ploton
- [ ] kenyszeritsuk az agentet likvidalasra



Hogyan szamoljuk ki a *market bound*-ot, $Q$-t?
[Ebben](https://arxiv.org/pdf/1209.4340) a cikkben talalhato a kovetkezo formula:
$$
\mathbb{E}[\lvert X \rvert^{\nu} ] = \sigma ^{\nu} 2^{\nu/2} \frac{\Gamma\left( \frac{\nu + 1}{2} \right)}{\sqrt{ \pi }} \cdot \Phi\left( -\frac{\nu}{2}, \; \frac{1}{2},\; -\frac{\mu ^{2}}{2\sigma ^{2}} \right)
$$

Mivel az FBM-nek minden idopontban a varhatoerteke nulla, $\mu = 0$, ezert a kovetkezore egyszerusul a fenti:
$$
\mathbb{E}[\lvert X \rvert ^{\nu}] = \sigma ^{\nu} 2^{\nu/2} \frac{\Gamma\left( \frac{\nu + 1}{2} \right)}{\sqrt{ \pi }}
$$
Tehat mar csak a szorast kell kiszamolni.

A wikipedia szocikkben talalhato, hogy a kovariencia fuggvenye az FBM-nek a kovetkezo:
$$
\mathbb{E}\left[B_H(t) B_H(s)\right] = \frac{1}{2}\left(|t|^{2 H}+|s|^{2 H}-|t-s|^{2 H}\right)
$$

Ha $t = s$ akkor pont a szorast kapjuk meg, mert mindenhol nulla a varhatoertek
$$
\sigma ^{2}(t) = \mathbb{E}[(B_{H}(t) - \mathbb{E}[B_{H}(t)])^{2}] = \mathbb{E}[B_{H}(t)^{2}] = \frac{1}{2}\left(|t|^{2 H}+|t|^{2 H}-|t-t|^{2 H}\right)
$$

Egyszerusitesek utan a kovetkezot kapjuk:
$$
\sigma ^{2}(t) = \lvert t \rvert ^{2H}
$$


Visszaterve a market bound-ra, a kovetkezo objektumot szeretnenk meg mindig kiszamolni, amihez mar meg van az osszes eszkozunk.
$$
Q(T):=\int_0^T E\left|S_t\right|^{\frac{\alpha}{\alpha-1}} d t
$$

$$
Q(T) = \int \limits_{0} ^{T} \sigma ^{\alpha/(\alpha-1)} 2^{\alpha/2(\alpha - 1)} \frac{\Gamma\left( \frac{\alpha}{2(\alpha - 1)} + \frac{1}{2} \right)}{\sqrt{ \pi }}  \, dt 
$$

Behelyettesitve $\sigma ^{2}(t) = \lvert t \rvert^{2H}$ erteket:
$$
Q(T) = \int \limits_{0} ^{T} \lvert t \rvert  ^{2H \cdot \alpha/(\alpha-1)} 2^{\alpha/2(\alpha - 1)} \frac{\Gamma\left( \frac{\alpha}{2(\alpha - 1)} + \frac{1}{2} \right)}{\sqrt{ \pi }}  \, dt 
$$
Legyen $\beta := \frac{\alpha}{\alpha - 1}$

$$
Q(T) = \int \limits_{0} ^{T} \lvert t \rvert ^{2H\beta} 2^{\beta} \frac{\Gamma\left( \frac{\beta + 1}{2} \right)}{\sqrt{ \pi }} \, dt 
$$

$$
Q(T) = 2^{\beta} \frac{\Gamma\left( \frac{\beta + 1}{2} \right)}{\sqrt{ \pi }} \int \limits_{0} ^{T} \lvert t \rvert ^{2H\beta}  \, dt 
$$

$$
\sum_{u=1}^{T+1} \Phi_u\left(S_u-S_{u-1}\right)=-\sum_{u=0}^T \phi_u S_u+S_{T+1} \sum_{u=0}^T \phi_u
$$
$$
-\sum_{u=0}^T \phi_u S_u+ \sum_{u=0}^T S_{u}\phi_u
$$


$$
\Phi_{u+1} - \Phi_{u} := \phi_{u}
$$

$$
\Phi_{t+1} - \Phi_{t} = \phi_{t}
$$
