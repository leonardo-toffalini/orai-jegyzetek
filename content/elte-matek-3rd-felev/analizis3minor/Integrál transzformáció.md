#tétel 

***Tétel***: Adott $H \subset \mathbb{R}^{d}$ Jordan-mérhetó halmaz, $K = H \cup \partial H$.
Létezik $D \subset \mathbb{R}^{d}$ nyílt halmaz úgy, hogy $K \subset D$. Adott $\psi : D \to \mathbb{R}^{d}$ leképezés.
A következő feltételek mellett igaz az állítás:
- $\psi \in C^{1}(D)$
- $\psi$ injektív
- $\psi'$ invertálható

Ekkor:
$\psi(K)$ mérhető és
$$
\int \limits_{\psi(K)} f \, du = \int \limits_{ K } f(\psi(x)) \cdot \lvert \det(\psi) \rvert   \, dx  
$$


***Dependencies***:
- 