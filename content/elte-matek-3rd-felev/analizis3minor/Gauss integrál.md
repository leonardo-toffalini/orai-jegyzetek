#tétel-biz  

***Tétel***:
$$
\int_{-\infty}^{\infty}  e^{-x^{2}} \, dx = \sqrt{ \pi }
$$


***Biz***.: 
$$
\left( \int _{-\infty}^{\infty}e^{-x^{2}} \, dx  \right) ^{2} = \left( \int _{-\infty}^{\infty}e^{-x^{2}} \, dx  \right) \cdot \left( \int _{-\infty}^{\infty}e^{-y^{2}} \, dy  \right) = \int _{-\infty}^{\infty}\int _{-\infty}^{\infty}e^{-x^{2}-y^{2}} \, dx  \, dy 
$$
$$
= \int _{0}^{2\pi}\int _{0}^{\infty}e^{-r^{2}}r \, dr  \, d\theta = \int _{0}^{2\pi} -\frac{1}{2} \int _{0}^{\infty} -2re^{-r^{2}} \, dr  \, d\theta = \int _{0}^{2\pi} - \frac{1}{2} \left[ e^{-r^{2}} \right]_{0}^{\infty}  \, dx 
$$
$$
= - \frac{1}{2}\left[ e^{-r^{2}} \right] _{0}^{\infty} \cdot 2\pi = - \frac{\lim_{ r \to \infty } e^{-r^{2}}}{2} 2\pi + \frac{1}{2}2\pi = - \frac{0}{2} + \pi = \pi
$$
$$
\implies \left( \int _{-\infty}^{\infty}e^{-x^{2}} \, dx  \right) ^{2} = \pi \implies \int _{-\infty}^{\infty}e^{-x^{2}} \, dx = \sqrt{ \pi }
$$

***Dependencies***:
- [[Polár koordinátás transzformáció]]