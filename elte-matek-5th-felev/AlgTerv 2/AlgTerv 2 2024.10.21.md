Minimalis koltsegu lefogo csucshalmaz
Minden csucsnak van egy nem negativ koltsege: $w : V \to \mathbb{N}$

legyen valtozok: $x_{v}  \forall v \in V$
$$
\begin{align}
x_{u} + x_{v} &\geq 1 \quad &\forall uv \in E \\
x_{v} &\geq 0 \quad &\forall v \in V \\
x_{v} &\in \mathbb{N} \quad &\forall v \in V \\
\min & \sum w(v) \cdot x_{v}
\end{align}
$$

Ennek az IP feladatnak az LP relaxaltja (tort relaxaltja) csak annyi, hogy elhagyjuk az egeszsegi feltetelt.

IP feladat optimalis megoldasas: $\text{OPT}$
LP feladat optimalis megoldasa: $\text{OPT}^{*}$

Eszrevetel 1: $\text{OPT}^{*} \leq \text{OPT}$
legyen $x_{v}$ a kovetkezo:
$$
x_{v} = \begin{cases}
1,  & \text{ha } x^{*}_{v} \geq \frac{1}{2} \\
0,  & \text{kulonben}
\end{cases}
$$

Eszrevetel 2: $\forall uv \in E: \quad x_{u} + x_{v} \geq 1$
Eszrevetel 3: $\forall v: \quad x_{v} \leq 2 \cdot x_{v}^{*}$
$$
\text{OPT}^{*} \leq \text{OPT} \leq \sum w(v) \cdot x_{v} \leq \sum 2 \cdot w(v) \cdot x_{v}^{*} = 2 \cdot \text{OPT}^{*}
$$
Tehat ez egy $2$-kozelito algoritmus.

## Fixed parameter Tractable (FPT)
Input: $(x, k)$ ahol $x$ egy $n$ bites szam (vagy egy $n$ csucsu graf), es $k \in \mathbb{N}$  egy parameter.

peldaul: Kapunk egy $G$ grafot es egy $k \in \mathbb{N}$ paramteret es a kerdes az hogy van e legalabb $k$ hossz ut a $G$ grafban.

*Def.:* XP azon feladatok halmaza, melyeket meg tudunk oldani polinomialis idoben minden fix $k$-ra.

*Def.:* FPT $\subseteq$ XP ahol FPT azon feladatok halmaza, melyekre $\exists O(f(k) \cdot n^{c})$ ideju algoritmus ami megoldja.

```
VC(G', k'):
	IF k' < 0 THEN return False
	let v in V such that d(v) is maximal
	IF d(v) = 0 THEN return {}  // case: empty graph
	IF k' = 0 THEN return False
	IF d(v) = 1 THEN return tau(G')
	
	T_1 := VC(G' - v, k' - 1)
	IF T_1 != False THEN return (T_1 U {v})
	
	T_2 := VC(G' - v, k' - d(v))
	IF T_2 != False THEN ...
```

Legyen $T(k)$ a rekurziv hivasok szama $k$-ra
Ekkor lathato, hogy $T(k) \geq T(k-1) + T(k-2)$

Tehat $O(\phi ^{k} \cdot m)$  a futasi ido, mert egy lepest minding meg tudunk csinalni $m$ idoben es a rekurziv hivasok szama a fenti eszrevetel miatt a fibonacci sorozat altal korlatozott.

Tudjuk egy kicsit javitani az algoritmus ugy, hogy atcsereljuk a kovetkezo sort: `IF d(v) = 1 ...` arra, hogy `IF d(v) = 2 ...` es igy a rekurziv lepesek szamara igaz, hogy $T(k) \geq T(k - 1)  + T(k-3)$
Igy a futasi ido $O(1.466^{k} \cdot m)$


*Def.:* Egy $(G, k)$ inputu feladat $g(k)$*-kernele*:
polinomialis idoben elkeszitunk egy $(G', k')$ inputot, amire:
- Az eredeti feladatra "Igen" a valasz $\iff$ A vesszos feladatra "Igen" a valasz
- $\lvert G' \rvert \leq g(k)$
- $k' \leq k$


*Kernel keszites a lefogo csucshalmaz feladatra*
Feladat: Keszitsunk egy $k$ csucsu lefogo csucshalmazt.
Ha $\exists v : d(v) > k \implies (G', k') := (G - v, k - 1)$ 

*Megj.:* Ha $k<0$ akkor megallunk es az a valaszunk, hogy "Nem lefoghato".
*Megj.:* Az izolalt csucsokat toruljuk.

Legyen $k'$ a vegso $k$ es $G'$ a vegso graf.
Ha $G'$-nek tobb mint $k'^{2}$ ele van, akkor megallunk es az a valaszunk, hogy "Nem lefoghato".
Ha $G'$-nek tobb mint $k'^{2} + k'$ csucsa van, akkor megallunk es az a valaszunk, hogy "Nem lefoghato".

Ha ezek utan meg mindig nem alltunk meg, akkor $(G', k')$ lesz a kernelunk ahol $\lvert V' \rvert \leq k'^{2} + k'$ es $\lvert E' \rvert \leq k'^{2}$
Ezt a kissebb grafot a fenti algorimussal meg lehet mar oldani $O(1.466^{k} \cdot k^{2})$ lepesben es a kernelt el tudjuk kesziteni $O(m + n)$ idoben.


*Def.:* $G$ korona-felbontasa: $V = C \cup H \cup B$ (crown, head, body)
1. $C$ fuggetlen
2. $\not\exists bc \in E$ ha $b \in B$ es $c \in C$
3. A $(C, H)$ paros grafban letezik $H$-t fedo parositas

*Korona redukcio:*
$$
(G, k) \to (G[B], k - \lvert H \rvert )
$$
ahol $G[B]$ a $G$ graf megszoritasa a $B$ halmazra.

*All.:* $\tau(G) \leq k \iff \tau(G[B]) \leq k - \lvert H \rvert$
*Biz.:*
$\impliedby$ Ha van egy $T \subseteq B$ csucshalmazom, ami lefogja $G[B]$ eleit es $\lvert T \rvert \leq k - \lvert H \rvert$, akkor $T \cup H$ lefogja $G$ eleit.

$\implies$ Legyen $T \subseteq V$ egy $G$ eleit lefogo csucshalmaz, amire $\lvert T \rvert = k$.
Ekkor letezik $T'$ ugy, hogy $\lvert T' \rvert = k$ es $T' \cap C = \emptyset$ es $H \subseteq T'$, mert a korona felbontas 3. pontja szerint letezik $H$-t fedo parositas a $(C, H)$ paros grafban.


$2k$ csucsu kernel
$G \mapsto P = (V_{1} \cup V_{2}, E')$

$P$-ben $M$ legnagyobb parositas, $T$ legkisebb lefogo, ha $\lvert M \rvert \geq 2k + 1$ akkor megallunk. $O(k \cdot m)$

$$
H := \{ v \in V : v_{1} \in T, v_{2} \in T \}
$$
$$
B := \{ v \in V : v_{1} \in T - H_{1}, v_{2} \in T - H_{2} \}
$$
$$
C := V - H - B = \{ v \in V : v_{1} \not\in T, v_{2} \not\in T \}
$$

*Allitasok:*
1. $C$ fuggetlen
2. nem letezik $cv$ el, ahol $c \in C$ es b inn B
3. Az $M$ a $H_{1}$-et felparositja $C_{2}$-be
Igy $G$-ben is \*pipa\*

$$
\lvert B \rvert  + 2 \lvert H \rvert = \lvert T \rvert \leq 2k \to \lvert B \rvert \leq 2k
$$
Igy $(G[B], k - \lvert H \rvert)$ a kernelunk.






