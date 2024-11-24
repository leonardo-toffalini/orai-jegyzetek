date: 2024.04.23

Emlek:
- nullahalmaz
- majdnem mindenutt
- integralhato fv-ek ($C_{2}$)
	1. $C_{0}$ lepcsos fv-ek halmaza (vektortere)
	2. $C_{1}$ m.m. monoton novo lepcsos fv-ek hatarertekeinek halmaza (nem VT)
	3. $C_{2}$ integralhato fv-ek vektortere, azon fv-ek halmaz, melyek eloallnak ket $C_{1}$-beli kulombesegekent

- Beppo-Levi tetel

#### *Beppo-Levi tetel bizonyitasanak elso lepese:*
1. Ha $(f_{n}) \subset C_{1}$ ekkor megmutatjuk, hogy $\exists f \in C_{1}$ ugy, hogy $f_{n} \to f$ m.m. es $\int f_{n} \, dx \to \int f \, dx$
$$
f_{1} \leq f_{2} \leq \dots \leq f_{n} \leq \leq \dots
$$
$$
\begin{align*}
\varphi_{11} \leq \varphi_{12} \leq \varphi_{13} \leq \dots & \to f_{1} \\
\varphi_{21} \leq \varphi_{22} \leq \varphi_{23} \leq \dots & \to f_{2} \\
& \;\; \vdots \\
\varphi_{n1} \leq \varphi_{n2} \leq \varphi_{n3} \leq \dots & \to f_{n} \\
\end{align*}
$$
$$
\varphi_{n} := \max_{1 \leq i ,\; l \leq n}\varphi_{ik}, \quad n \in \mathbb{N}
$$
Tehat $\varphi_{n}$ a bal felső $n \times n$ -es negyzet maximuma a fenti align environmentben.

Megallapithatjuk, hogy ezek a $\varphi_{n}$-ek is lepcsos fv-ek, mert lepcsos fv-ek maximuma is lepcsos fv:
Belathato az is, hogy $\varphi_{n} \leq \varphi_{n+1}$ m.m. $\forall n \in \mathbb{N}$ 
Masreszt az is belathato, hogy az integraljaik felulrol korlatosak, azaz
$\int \varphi_{n} \, dx \leq A$  ez igaz, minden $\varphi_{ik} \leq f_{i}$ $\forall i, k$ $\implies \int \varphi_{ik} \, dx \leq \int f_{i} \, dx \leq A$
2.Lemma miatt $\exists f \in C_{1}$ fv ugy, hogy $\varphi_{n} \to f$ m.m. es $\int \varphi_{n} \, dx \to \int f \, dx$ 
Nekunk az kell, hogy $f_{n} \to f$ m.m. es $\int f_{n} \, dx \to \int f \, dx$ 
Tudjuk, hogy $\varphi_{ik} \leq \varphi_{k}$ ha $1 \leq i \leq k$ ahol $\varphi_{k} = \max_{1 \leq i ,\; j \leq k} \varphi_{ij}$
$k \to \infty$ ekkor $f_{i} \leq f \quad \forall i$

Masreszt, $\varphi_{n} \leq f \quad \forall n$ ugyanis $\varphi_{ik} \leq f_{i} \leq f_{n} \quad \forall 1 \leq i, \; k \leq n$
Vegyuk ezen $\varphi_{k}$-knak a maximumat: $\max_{1 \leq i, \; k \leq n} = \varphi_{n} \leq f_{n}$
Tehat az elozo ket egyenlotlensegbol kovetkezik, hogy $\varphi_{n} \leq f_{n} \leq f \quad \forall n$
Most tartsunk $n$-el vegtelenbe: $n \to \infty$ es igy a rendorelv ertelmeben $f_{n} \to f$ m.m., mert $\varphi_{n} \to f$ m.m. es $f \to f$ $\implies f_{n} \to f$

Masreszt az integral monotonitasa miatt $\int \varphi_{n} \, dx \leq \int f_{n} \, dx \leq \int f \, dx$ m.m. 
Megint $n$-el tartunk $\infty$-be es megint a rendor elv miatt $\int f_{n} \, dx \to \int f \, dx$

*Megjegyzes:* A masodik lepes az lenne, hogy $(f_{n}) \subset C_{2}$ de ezt nem latjuk be


***Kovetkezmenyek:***
1. Legyen $(f_{n})$ integralhato fv-ek m.m. monoton novo sorozata, amelyekhez $\exists f \in C_{2}$ ugy, hogy $f_{n} \to f$ m.m.
Ekkor $\int f_{n} \, dx \to \int f \, dx$

2. Legyen $\sum f_{n}$ integralhato fv-ekbol allo sor, tegyuk fel, hogy $\sum \int \lvert f_{n} \rvert \, dx$ konvergens.
Ekkor $\exists f \in C_{2}$ ugy, hogy $\sum f_{n} = f$ es $\sum \int f_{n} \, dx = \int \sum f_{n} \, dx = \int f \, dx$

3. Ha $f$ olyan integralhato fv, hogy $\int \lvert f \rvert \, dx = 0$ akkor $f = 0$ m.m.

*Biz.:*
1. Mivel $f_{n} \nearrow f$ m.m. $\implies f_{n} \leq f$ m.m. $\forall n$ $\implies \int f_{n} \, dx \leq \int f \, dx$ $\forall n$
Ezert legyen $A := \int f \, dx$ es igy a Beppo-Levi tetel feltetelei teljesulnek es keszen is vagyunk

2. $f_{n} \geq 0$ $s_{n} = \sum_{k=1}^{n}f_{k}$ m.m. monoton novo $\implies \int s_{n} \, dx \leq \sum_{k=1}^{\infty} \int \lvert f_{k} \rvert \, dx$ es igy a Beppo-Levi tetlbol kovetkezik, hogy $s_{n} \to f$ m.m. es $\int s_{n} \, dx = \sum_{k=1}^{n}\int f_{k} \, dx \to \int f \, dx$
(altalanosan nem bizonyitjuk)

3. Alkalmazzuk a második pontot:
$f_{n} = f$ $\forall n \in \mathbb{N}$  igy $\sum \int \lvert f_{n} \rvert \, dx = \sum 0 = 0$ ekkor a masodik pont ertelmeben $\sum_{n=1}^{\infty}f_{n}=\sum_{n=1}^{\infty}f \implies f \equiv 0$ m.m.


### Lebesgue-dominalt konvergencia tetele
Legyen $(f_{n}) \subset C_{2}$ integralhato fv-ek sorozata, amelyekre igaz, hogy $f_{n} \to f$ m.m. (figyelem: itt $f$ -rol nem teszunk fel semmit) 
(a fenti feltetel annyit jelent, hogy $\lim_{ n \to \infty } f_{n}(x) \in \mathbb{R}$ m.m.)

Tegyuk fel, hogy $\exists g \in C_{2}$ integralhato fv ugy, hogy $\lvert f_{n} \rvert \leq g$ m.m. $\forall n \in \mathbb{N}$ (azaz a sorozat minden tagja egyenletesen majoralhato egy integralhato fv-el)
Ekkor $f$ is integralhato es $\int f_{n} \, dx \to \int  f \, dx$ 

*Megjegyzes:* A fenti majoralasi kriterium nagyon fontos!
*pelda:*
Legyen $f_{n} = \chi_{[n, n+1]}$ $n \in \mathbb{N}$  ekkor konnyen lathato, hogy az elso feltetel teljesul, mert ez pontonkent tart $0$-hoz, de $\int f_{n} \, dx = 1$ $\forall n \in \mathbb{N}$ es ez nem tart $\int 0 \, dx$-hoz. Ez azert van, mert nem letezik integralhato majorans (az azonosan $1$ fuggveny majorans lenne de ez nem integralhato).

*Bizonyitas:*
Alkalmazni akarjuk a Beppo-Levi tetelt, ezert letre kell hoznunk egy monoton novo integralhato fv-ek sorozatat.
Legyen $g_{n} := \sup\{ f_{n}, f_{n+1}, \dots \}$ ez eppen egy monoton csokkeno sorozat es $g_{n} \searrow f$ m.m
Legyen rogzitett $n$-re $g_{nm} := \max\{ f_{n}, f_{n+1}, \dots, f_{m} \}$, $m \geq n$ (ezek integralhato fv-ek)
$$
g_{n,m} \leq g_{n, m+1} \quad \forall m \geq n
$$
$$
g_{n,m} \nearrow g_{n}, \quad m\to \infty \text{ (definiciobol)}
$$
$$
g_{n,m} \leq g_{n} \leq g \implies \int  g_{n,m}  \, dx \leq \int \lvert f_{n} \rvert  \, dx \leq \int g \, dx 
$$
Mostmar alkalmazhato a Beppo-Levi tetel $\implies g_{n}$ integralhato es $\int g_{n,m} \, dx _> \int g_{n} \, dx$ (ez minden $n$-re igaz)

Mivel fent lattuk, hogy $g_{n} \searrow f$ ezert $-g_{n} \nearrow -f$ ezert megprobaljuk a Beppo-Levi tetelt alkalmazni a $-g_{n}$ sorozatra

A feltetelbol kovetkezik, hogy $\lvert g_{n} \rvert \leq g \implies -g_{n} \leq g \implies \int -g_{n} \, dx \leq \int g \, dx$
Beppo-Levi $\implies$ $-f$ integralhato $\implies$ $f$ is es $\int g_{n} \, dx\to \int f \, dx$  

Ahhoz, hogy belassuk, hogy $\int f_{n} \, dx \to \int f \, dx$ vigyuk vegig ugyanezt a $h_{n} := \inf \{ f_{n}, f_{n+1}, \dots \}, \quad n \in \mathbb{N}$ fuggvenysorozattal. Itt $h_{n} \nearrow f \quad n \to \infty$ Eljatszva ugyanezt a kettos indexes undormanyt megkapjuk, hogy $\int h_{n} \, dx \to \int f \, dx$
Vegul azt kapjuk, hogy $h_{n} \leq f_{n} \leq g_{n}$. Kihasznalva az integral monotonitasat azt kapjuk, hogy $\int h_{n} \, dx \leq \int f_{n} \, dx \leq \int g_{n} \, dx$  es a rendorelv ertelmeben keszen vagyunk.


*pelda:*
Legyen
$$
f_{n}(x) := \frac{n \cdot \sin \frac{x}{n}}{x \cdot (1 + x^{2})}, \quad x \neq 0, \; n \in \mathbb{N}^{+}
$$
$$
\lim_{ n \to \infty } f_{n}(x) = \lim_{ n \to \infty } \frac{\sin \frac{x}{n}}{\frac{x}{n}} \cdot \frac{1}{1 + x^{2}} = \frac{1}{1+x^{2}} = f(x)
$$
$$
\int_{-\infty}^{\infty} f(x) \, dx = \frac{\int_{-\infty}^{\infty}1}{1+x^{2}} \, dx = \lim_{ t \to \infty } \arctan t - \lim_{ t \to -\infty } \arctan t = \pi
$$
$$
\lvert f_{n} \rvert \stackrel{?}{\leq} g
$$
Hasznaljuk ki, hogy $\lvert \sin x \rvert \leq \lvert x \rvert$
$$
\lvert f_{n}(x) \rvert \leq \frac{n \cdot \frac{\lvert x \rvert }{n}}{\lvert x \rvert  \cdot (1 + x^{2})} = \frac{1}{1 + x^{2}} = g(x) = f(x)
$$
Lebesgue-dom tetelbol kovetkezik, hogy
$$
\int f_{n}(x) \, dx = \int _{-\infty}^{\infty} \frac{n \cdot \sin \frac{x}{n}}{x(1 + x^{2})} \, dx \to \pi
$$

#### Riesz-Fischer-tetel
Legyen $(f_{n})$ integralhato fv-ek sorozata ugy, hogy $\int \lvert f_{n} - f_{m} \rvert \, dx \to 0$ ha $n, \; m \to \infty$.
Ekkor $\exists f$ integralhato fv ugy, hogy $\int \lvert f_{n} - f \rvert \, dx \to 0$ ha $n \to \infty$

*Megjegyzes:* Ha vesszuk a $C_{2}$ teret es azon vesszuk az $\| \cdot \|_{1}$ fuggvenyt, akkor $f \in C_{2}$ -re $\| f \|_{1} = \int \lvert f \rvert \, dx$ egy norma
1. $\| f \|_{1} = 0 \iff f = 0$ m.m.
2. $\| \lambda f \|_{1} = \lvert \lambda \rvert\| f \|_{1}$
3. $\| f + g \|_{1} \leq \| f \|_{1} + \| g \|_{1}$
$\lvert f + g \rvert \leq \lvert f \rvert + \lvert g \rvert$ es az integral monotonitasabol kovetkezik a haromszog egyenlotlenseg

Tehat a fenti Riesz-Fischer-tetel azt jelenti, hogy $(C_{2}, \; \| \cdot \|_{1})$ Banach-ter! Mivel a Riesz-Fischer tetel az elobb bevezetett $\| \cdot \|_{1}$ normavala a kovetkezokeppen fogalmazhato meg:
Ha $\| f_{n} - f_{m} \|_{1} \to 0$ ha $n, m \to \infty$ akkor $\| f_{n} \|_{1} \to f$ (vagy $f_{n} \xrightarrow{\| \cdot \|_{1}} f$)


related: [[TovFejAnal]]