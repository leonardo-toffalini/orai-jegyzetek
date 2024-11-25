
### 1.
Norma-e $\| \cdot \|_1\left(\|f\|_1:=\int_\alpha^b|f|\right)$ a Riemann-integrálható függvények $R[a, b]$ vektorterén?
Válasz:
Nem, mivel tudunk alkotni egy olyan $g$ függvényt, mely mindenhol azonosan $0$ kivéve $\frac{a+b}{2}$-ben, ahol 1. Látszik, hogy ennek a függvénynek az $[a, b]$ intervallumon az integrálja $0$ de mégsem az azonosan $0$ függvény.

### 2. 
(a) Legyen $n \in \mathbb{N}$ rögzitett. Számítsuk ki az alábbi függvények $\| \cdot \|_1$ és $\|\cdot\| _{\max} \left(\|f\|_{\max }:=\max _{x \in D_f}|f(x)|\right)$ szerinti normáját a $\mathscr{C}([0,1] ; \mathbb{R})$ térben!
		a) $f_n(x):=x^n$
		b) $f_n(x):=e^{-n x}$

$$
\lvert\lvert x^{n} \rvert\rvert_{1} = \int _{0}^{1}\lvert x^{n} \rvert  \, dx  \int _{0}^{1}x^{n} \, dx \left[ \frac{x^{n+1}}{n+1} \right]_{0}^{1} = \frac{1}{(n+1)} 
$$
$$
\lvert\lvert x^{n} \rvert\rvert _{\max} = \max_{x \in [0, 1]} \lvert x^{n} \rvert = 1
$$
$$
\lvert\lvert e^{-nx} \rvert\rvert_{1}  = \int _{0}^{1}\lvert e^{-nx} \rvert  \, dx = \int _{0}^{1}e^{-nx} \, dx = \left[ -\frac{e^{-nx}}{n} \right]_{0}^{1} = -\frac{e^{-n}}{n} + \frac{1}{n} = \frac{1-e^{-n}}{n}
$$
$$
\lvert\lvert e^{-nx} \rvert\rvert _{\max} = \max_{x \in [0, 1]} \lvert e^{-nx} \rvert = 1
$$

(b) Igaze a fenti $\left(f_n\right)_{n \in \mathbb{N}}$ fuiggvénysorozatokra, hogy ha $n \rightarrow \infty$, akkor $f_n \rightarrow 0$ a $\left\| \cdot\right\|_1$, illetve $\| \cdot \|_{\text {max}}$ normák szerint a $\mathscr{C}([0,1] ; \mathbb{R})$ térben?

Ahhoz, hogy igazuljuk a $f_{n}(x) \xrightarrow{\lvert\lvert \cdot \rvert\rvert_{1}} 0$ kifejezest ahhoz be kell látnunk, hogy $\lvert\lvert f_{n}(x) - 0 \rvert\rvert_{1} \to 0$.
$$
\lvert\lvert x^{n} - 0 \rvert\rvert _{1} = \lvert\lvert x^{n} \rvert\rvert _{1} = \frac{1}{n+1} \to 0 \text{ ha } n \to \infty
$$
$$
\lvert\lvert e^{-nx} 0 \rvert\rvert _{1} = \lvert\lvert e^{-nx} \rvert\rvert _{1} = \frac{1-e^{-n}}{n} \to 0 \text{ ha } n \to \infty
$$

Ahhoz, hogy igazuljuk $f_{n}(x) \xrightarrow{\lvert\lvert \cdot \rvert\rvert_{\max}} 0$ kifejezest ahhoz be kell látnunk, hogy $\lvert\lvert f_{n}(x) - 0 \rvert\rvert_{\max} \to 0$.
$$
\lvert\lvert x^{n} - 0 \rvert\rvert_{\max} = \lvert\lvert x^{n} \rvert\rvert _{\max} = 1 \neq 0
$$
$$
\lvert\lvert e^{-nx} - 0\rvert\rvert _{\max} = \lvert\lvert e^{-nx} \rvert\rvert _{\max} = 1 \neq 0
$$

Tehát a fenti két függvény sorozat $\lvert\lvert \cdot \rvert\rvert_{1}$ normában konvergens az azonosan $0$ függvényhez, viszont $\lvert\lvert \cdot \rvert\rvert_{\max}$ normában nem konvergálnak.


### 3.
Jelölje $\mathscr{C}^1([a, b] ; \mathbb{R})$ az $[a, b]$ intervallumon értelmezett, valós értékü folytonosan differenciálható függvények vektorterét.
(a) Mutassuk meg, hogy az alábbi $\|\cdot\|_{C^1}: \mathscr{C}^1([a, b] ; \mathbb{R}) \rightarrow \mathbb{R}$,
$$
\left.\|f\|_{C^1}:=\|f\|_{\max }+\left\|f^{\prime}\right\|_{\max }, \quad f \in \mathscr{C}^{1}([ a, b] ; \mathbb{R}\right)
$$leképezés norma!
1. $\lvert\lvert f \rvert\rvert_{C_{1}} \geq 0 \text{ és } \lvert\lvert f \rvert\rvert_{C^{1}} = 0 \iff f \equiv 0$
	Az első rész nyilvánvaló, mivel $\lvert\lvert \cdot \rvert\rvert_{\max}:\mathscr{C} \to \mathbb{R}_{0}^{+}$ egy norma, tehát két nemnegatív szám összeg is nemnegatív.
	Továbbá $\lvert\lvert f \rvert\rvert_{C^{1}} = 0 \iff \lvert\lvert f \rvert\rvert_{\max} = 0 \text{ és } \lvert\lvert f' \rvert\rvert_{\max} = 0$. Szintén, mivel $\lvert\lvert \cdot \rvert\rvert_{\max}$ egy norma ezen a halmazon, ezért $\lvert\lvert f \rvert\rvert_{\max} = 0 \iff f \equiv 0$ és ekkor a derivált normája is $0$. Ezzel beláttuk az első részt.
2. $\lvert\lvert \lambda f \rvert\rvert_{C^{1}} = \lvert \lambda \rvert\cdot \lvert\lvert f \rvert\rvert_{C^{1}}$
$$
\lvert\lvert \lambda f \rvert\rvert_{C^{1}} = \lvert\lvert \lambda f \rvert\rvert_{\max} + \lvert\lvert (\lambda f)' \rvert\rvert_{\max} = \lvert\lvert \lambda f \rvert\rvert_{\max} + \lvert\lvert \lambda f' \rvert\rvert_{\max} = \lvert \lambda \rvert\cdot \lvert\lvert f \rvert\rvert_{\max} + \lvert \lambda \rvert \cdot \lvert\lvert f' \rvert\rvert_{\max} = \lvert \lambda \rvert\cdot \lvert\lvert f \rvert\rvert_{C^{1}}
$$
3. $\lvert\lvert f + g \rvert\rvert_{C^{1}} \leq \lvert\lvert f \rvert\rvert_{C^{1}} + \lvert\lvert g \rvert\rvert_{C^{1}}$
$$
\lvert\lvert f + g \rvert\rvert _{C^{1}} = \lvert\lvert f + g \rvert\rvert _{\max} + \lvert\lvert (f + g)' \rvert\rvert _{\max} = \lvert\lvert f + g \rvert\rvert _{\max} + \lvert\lvert f' + g' \rvert\rvert _{\max} \leq \lvert\lvert f \rvert\rvert _{\max} + \lvert\lvert g \rvert\rvert _{\max} + \lvert\lvert f' \rvert\rvert _{\max} + \lvert\lvert g' \rvert\rvert _{\max}
$$
$$
= ( \lvert\lvert f \rvert\rvert _{\max} + \lvert\lvert f' \rvert\rvert _{\max} ) + ( \lvert\lvert g \rvert\rvert _{\max}  + \lvert\lvert g' \rvert\rvert _{\max}) = \lvert\lvert f \rvert\rvert _{C^{1}} + \lvert\lvert g \rvert\rvert _{C^{1}}
$$
$$
\implies \lvert\lvert f + g \rvert\rvert _{C^{1}} \leq \lvert\lvert f \rvert\rvert _{C^{1}} + \lvert\lvert g \rvert\rvert_{C^{1}}
$$

(b) Igazoljuk továbbá, hogy $\left(\mathscr{C}^1([a, b] ; \mathbb{R}),\|\cdot\| _{C^{1}}\right)$ Banach-tér!
Be kell látnunk, hogy $\rho_{C^{1}}: \mathscr{C}[0, 1] \times \mathscr{C}[0, 1] \to \mathbb{R}, \quad \rho_{C^{1}}(f, g) := \lvert\lvert g - f \rvert\rvert_{C^{1}}$ metrikával $(\mathscr{C}[a, b], \rho_{C^{1}})$ teljes metrikus teret alkot, azaz minden Cacuhy-sorozat konvergens.
Használjuk fel tudásunkat, hogy $(\mathscr{C}[a, b], \lvert\lvert \cdot \rvert\rvert_{\max})$ Banach-tér.
$$
\lvert\lvert f_{n} - f_{m} \rvert\rvert_{C^{1}} \to 0 \xRightarrow{?} \lvert\lvert f_{n} - f \rvert\rvert_{C^{1}} \to 0
$$
$$
	\lvert\lvert f_{n} - f_{m} \rvert\rvert _{\max} + \lvert\lvert (f_{n} - f_{m})' \rvert\rvert_{\max} \to 0 \xRightarrow{?} \lvert\lvert f_{n} - f \rvert\rvert _{\max} + \lvert\lvert (f_{n} - f)' \rvert\rvert _{\max} \to 0
$$
Mivel $(\mathscr{C}[a, b], \lvert\lvert \cdot \rvert\rvert_{\max})$ Banach-tér, ezért:
$$
\lvert\lvert f_{n} - f_{m} \rvert\rvert _{\max} \to 0 \implies \lvert\lvert f_{n} - f \rvert\rvert _{\max} \to 0
$$
$$
\lvert\lvert (f_{n} - f_{m})' \rvert\rvert _{\max} \to 0 \implies \lvert\lvert (f_{n} - f)' \rvert\rvert _{\max} \to 0
$$
A kettőt összevetve kapjuk, hogy $\left(\mathscr{C}^1([a, b] ; \mathbb{R}),\|\cdot\| _{C^{1}}\right)$  valóban Banach-tér. Mivel $\lvert\lvert f_{n} - f_{m} \rvert\rvert _{\max} + \lvert\lvert (f_{n} - f_{m})' \rvert\rvert_{\max} \to 0$ csak úgy teljesülhet, hogy tagonként tart $0$-hoz, mert mindkét tag nemnegatív.


### 4.
Legyen $\mathcal{L}([-2,2], \mathbb{R})$ a $[-2,2]$-n értelmezett lineáris, valós értékü fuggvények egy dimenziós vektortere. Jelölje $\mathcal{M}_1$ az $\left(\mathcal{L}([-2,2], \mathbb{R}), \|\cdot\| _{\text {max }}\right)$ tér $f \equiv 0$ körüli, 1 sugarủ zárt gömbjét, $\mathcal{M}_2$ az $\left(\mathbb{R}^2, \|\cdot\|_2\right)$ tér origó kōcéppontí, $\frac{1}{4}$ sugarú zárt gömbjèt, $\mathcal{D}$ pedig a $\left(\mathbb{R}^2, \|\right. \cdot \left.\|_{\max }\right)$ tér $(0,-4)$ köcéppontú, $4$ sugarú gömbfelszinét. Abrázoljuk a sikon a $\left\{(f(x), x) \in \mathbb{R}^2: f \in \mathcal{M}_1\right\} \cup \mathcal{M}_2 \cup \mathcal{D}$ halmazt!

![[tov-fej-anal-p-2-4-a]]
![[tov-fej-anal-p-2-4-b]]
![[tov-fej-anal-p-2-4-c]]

related: [[TovFejAnal]]