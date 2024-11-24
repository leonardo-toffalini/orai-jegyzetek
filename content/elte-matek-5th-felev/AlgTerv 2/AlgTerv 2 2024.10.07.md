**feladat:** $8$ kiralyno a sakk tablan ugy hogy egyik sem uti a masikat. Van ilyen felallas es ha van akkor hany?
*Brute force:* osszes felallast kiprobaljuk, ez $64 \choose 8$ esetet kell leellenorizni
*Heurisztika 1:* Minden oszlopba csak egy kiralnyot rakhatunk, igy mar csak $8^{8}$ esetet kell leellenorizni.
*Heurisztika 2:* Minden soronkent is csak egy kiralynot rakhatunk, igy mar csak $8!$ lehetoseg van.
*Backtracking:* Addig rakjuk a kiralnyoket ameddig el nem rontjuk, ha elrontjuk akkor visszalepunk.


**feladat:** Ki lehet-e szinezni a grafot $3$ szinnel, azaz $\chi(G) \stackrel{?}{\leq} 3$
$\forall X \subseteq V$-re lehet-e $X$ a pirosak halmaza? Ha $\exists a, b \in X$ ugy, hogy $ab \in E$ akkor nem lehet $X$ a pirosak halmaza.
Meg eldontendeo, hogy a maradek csucsok, azaz $G - X$ kiszinezheto-e $2$ szinnel.
Tehat igy osszesen $2^{\lvert V \rvert}$-szer kell futtatni egy $2$-szinezhetoseget, mert az elso lepesben mindn $X \subset V$ -re futtatni kell.


**feladat:** Mennyi az $\alpha(G)$ szama a grafnak, azaz mekkora a maximalis fuggetlen csucshalmaza.

Ha $\Delta(G) \leq 2$ akkor $\alpha(G)$ konnyen szamithato $O(m)$ idoben
Egy ilyen $G$ grafnak minden komponense a kovetkezo $3$ lehet - izolalt csucs, ut vagy kor.

**All.:** Ha egy komponensnek $l$ csucsa van, akkor a kovetkezo ket eset van:
- ut $\implies$ $\alpha(G) = \left\lfloor  \frac{l+1}{2}  \right\rfloor$
- kor $\implies$ $\alpha(G) = \left\lfloor  \frac{l}{2}  \right\rfloor$

Keressuk az $I$ maximalis fuggetlen csucshalmazt.
```
MFTL(G):
	I := {}
	IF Delta(G) <= 2 THEN
		Szelessegi G -> I'
		RETURN (I U I')
	ELSE
		// x benne van a max ftl csucshalmazban
		x := legalabb 3-ad foku csucs
		I := I + x
		I_1 := MFTL(G - x - N(x))
		I := I - x

		// x nincs benne a max ftl csucshalmazban
		I_2 := MTFL(G - x)

		IF |I_1| + 1 > |I_2| THEN
			I = I U I_1
		ELSE
			I = I U I_2
		RETURN I
```

Legyen $T(n)$ a rekurziv hivasok szama, igy a vegso futasi ido $O(T(n)m)$ lesz mert minden rekurziv hivasban $O(m)$ lepest csinalunk.
$$
T(n) = T(n-4) + T(n-1)
$$
**All.:** $T(n) < c \cdot \gamma ^{n}$
$$
\gamma ^{n} = \gamma ^{n-4} + \gamma ^{n-1}
$$
$$
\gamma ^{4} = 1 + \gamma ^{3} \implies \gamma < 1.381
$$

Tehat a vegso futasi ido $O(1.381^{n} \cdot m)$


**feladat:** Mennyi a $\tau(G)$ szama a grafnak, azaz a legkisebb lefogo csucshalmaz merete.

**Tetel (Gallai):** $\alpha(G) + \tau(G) = n$

INPUT: $G$ graf, $k \in \mathbb{N}$ 
OUTPUT: Letezik-e $k$ csucsu lefogo csucshalmaz $G$-ben

```
INIT:
	G' := G
	k' := k

// Vertex Cover
VC(G', k'):
	IF k' < 0 THEN RETURN False
	IF |E(G')| = 0 THEN RETURN {}
	IF k' = 0 THEN RETURN False

	uv in E
	T_1 := VC(G' - u, k' - 1)
	IF T_1 != False THEN RETURN (T_1 U {u})
	
	T_2 := VC(G' - v, k' - 1)
	IF T_" != False THEN RETURN (T_2 U {v})

	RETURN False
```

futasi ido: $O(2^{k} \cdot n)$

```
INIT:
	G' := G
	k' := k

// Vertex Cover
VC2(G', k'):
	IF k' < 0 THEN RETURN False
	IF |E(G')| = 0 THEN RETURN {}
	IF k' = 0 THEN RETURN False

	v := G' egyik max foku csucsa
	IF d(v) <= 2 THEN
		T := legkisebb lefogo spec esetben
		IF |T| <= k' THEN 
			RETURN T
		ELSE
			RETURN False

	T_1 := VC2(G' - v, k' - 1)
	IF T_1 != False THEN RETURN (T_1 U {v})

	T_2 := VC2(G' - v - N(v), k' - d(v))
	IF T_2 != False THEN RETURN (T_2 U N(v))

	RETURN False
```


Legyen $T(k)$ a rekurziv hivasok szama. Ekkor
$$
T(k) \leq T(k-1) + T(k-3)
$$
$$
\implies T(k) < 1.466^{k}
$$
Tehat a vegso futasi ido $O(1.466^{k} \cdot m)$


**Meta heurisztikak**
- Simulated annealing
- Tabu search
- Flood fill
- Go with the winners
- Genetic algorithms





