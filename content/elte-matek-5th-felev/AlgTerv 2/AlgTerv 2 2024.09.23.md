# Medians kereses
rendezes utan konnyu megadni a kozepso elemet
de lehet gyorsabban mint $n\log n$ idoben megadni a medians-t?

**Alapelv:**
- Keressuk meg a $k$-adik elemet, azaz azt az elemet aminel $k-1$ darab kisebb elem van.
- Felteszzuk, hgoy az elemek kulonbozoek.
- Keressunk $x$ elemet, aki nagyjabol kozepen van.

Ket tombbe rendezzuk az adatokat, egy $B$ es egy $J$ tombbe, ahol $\forall y \in B: y < x$ es $\forall y \in J: x < y$ ez megoldhato $n-1$ osszehasonlitassal.

- Ha $\lvert B \rvert = k-1$ akkor keszen vagyunk es $x$ a megoldas.
- Ha $\lvert B \rvert > k-1$ akkor rekurzivan $B$-ben  keressuk a $k$-adik elemet.
- Ha $\lvert B \rvert < k-1$ akor rekurzivan $J$-ben keressuk a $(k- \lvert b \rvert - 1)$-edik elemet.

**$x$ keresese**
1. $5$-os csoportok
2. Minden csoportban vesszuk a kozepso elemet $b_{i}$-t.
	A fenti megteheto $6 \cdot \frac{n}{5}$ osszehasonlitassal, mert egy $5$-os csoportban meg lehet talalni a kozepsot $6$ osszehasonlitassal.
3. Rekurzivan a $b_{i}$-k kozul legyen $x$ a kozepso.

Mostmar meg van nekunk az $x$ ami egy nagyjabol kozepen levo elemt es ezzel mar fel tudjuk bontani $B$ es $J$ reszekre az adatokat.

**Allitas:** Legfeljebb $\frac{7}{10}n$ elem lesz kisebb mint $x$ es nagyobb mint $x$.
*Biz.:* Elkepzeljuk, hogy az otos csoportok egymas ala vannak irva, minden csoport balrol jobbra no, a csoportok ugy rakjuk hogy az elso elem lefelo no.
```python
[
 [a0 < a1 < a2 < a3 < a4],
 [b0 < b1 < b2 < b3 < b4],
 [c0 < c1 < c2 < c3 < c4],
]
a0 < b0 < c0
```

A bal also sarok kisebb mint $x$ es jobb also sarok nagyobb mint $x$.

**Allitas:** Legfeljebb $22n$ osszehasonlitast kell tennunk.
*Biz.:*
$$
T(n) = \max_{n' < n} \max_{k}\{ \# \text{osszehasonlitasok}(n', k) \}
$$
$$
T(n) \leq 6 \cdot \frac{n}{5} + T\left( \frac{n}{5} \right) + n-1 + T\left( \frac{7n}{10} \right)
$$
*(hf)* $T(n) \leq 22n$

# Gyorsrendezes (quicksort)
```
QuickSort(A[p : r]):
	IF p < r THEN 
		q := Partition(A[p : r])
		QuickSort(A[p : q-1])
		QuickSort(A[q + 1 : r])
```

```
Partition(A[p : r]):
	i := RND(low=p, high=r)
	SWAP(A[i], A[r])
	x := A[r]
	i := p - 1
	FOR j = p .. r
		IF A[j] <= x THEN
			i++
			SWAP(A[i], A[j])
```

**Allitas:** A $j$-edik ciklus vegen 

**Tetel:** Az osszehasonlitasoknak a varhato erteke $< 1.39 \cdot n \cdot \log n + O(\log n)$
*Biz:* Vezessuk be a kovetkezo ketto seged fuggvenyt:
- $C(n)$ az osszehasonlitasoknak a varhato erteke $n$ hosszu resztombon
- $C(n, j)$ az osszehasonlitasoknak a varhato erteke, felteve, hogy elsore a $j$-edik legkisebb elemet valasztottuk.

$C(n, j) = n - 1 + C(j-1) + C(n - j)$
$C(n) = \frac{1}{n} (C(n,1) + C(n, 2) + \dots + C(n,n))$
A fenti ket megfigyelesbol kovetkezik, hogy
$$
C(n) = n - 1 + \frac{2}{n}(C(1), C(2), \dots, C(n-1))
$$
$$
\begin{align*}
n C(n) &= n(n-1) + 2(C(1) + C(2) + \dots + C(n-1)) \\
(n-1)C(n-1) &= (n-1) (n-2) + 2(C(1) + C(2) + \dots + C(n-2))
\end{align*}
$$
$$
nC(n) = (n-1)C(n-1) + 2(n-1) + 2C(n-1) = 2(n-1) + (n+1)C(n-1)
$$
legyen $f(n) = \frac{C(n)}{n+1}$
$$
f(n) = \frac{C(n)}{n+1} = \frac{2(n-1)}{n(n+1)} + \frac{C(n-1)}{n} < \frac{2}{n} + f(n-1)
$$
$$
\begin{align*}
f(1) &= 0 \\
f(n) &< 2 \cdot \sum_{i=2}^{n} \frac{1}{i} = 2(\log n  + \gamma - 1 + o(1)) < 2 \log n + o(1)
\end{align*}
$$

*Def.:* $f(n) = o(g(n))$ ha
$$
\frac{f(n)}{g(n)} \to 0 -->\to 0
$$
A fentibol kovetkezik, hogy
$$
C(n) < 2(n+1)\log n + o(n) = 2(n+1) \frac{\log n}{\log e} < 1.39 \cdot n \cdot \log n + O(\log n) + o(n)
$$

# Mintakereses
- van egy veges ABC-enk $\Sigma$ melyre $\lvert \Sigma \rvert = d$
- van egy mintank $\underline{p} = p_{1}, \dots, p_{m} \in \Sigma ^{m}$
- van egy szovegunk $\underline{s} = s_{1}, \dots, s_{n}$

Van az $\underline{s}$ szoveg amiben csinalunk egy $m$ hosszu ablakot $s_{i}, \dots, s_{i+m-1}$ es megnezzuk, hogy az ablak megegyezik-e a mintaval.

1. Bruteforce $O(nm)$
```
FOR i = 1 .. n-m+1
	IF s[i : i+m-1] = p[1 : m] THEN return(i)
```

2. (Horspool) Quicksearch
Elofeldolgozas:
```
FOR b in Sigma
	E[b] := m
FOR j = 1 .. m-1
	E[p[j]] := m-j
```

```
j := m
WHILE j <= n
	IF s[j] = p[m] THEN
		IF s[j-m+1 : j] = p[1 : m] THEN return(j-m+1)
	j := j + E(s[j])
```

3. KMP (Knuth-Morris-Pratt)
*Def.:* Az $y$ az $x$ labfeje, ha $k > 0$ min amire $\exists z, z' : \lvert z \rvert = \lvert z' \rvert = k$ ugy, hogy $x = yz = z'y$
Tehat tudok az elejere irni $k$ betut es megkapom az $x$-et vagy tudok a vegere irni $k$ betut es visszakapom az $x$-et.

Elofeldolgozas:
$\pi_{j} =$ a $p_{1}, \dots, p_{j}$ szo labfejenek a hossza

```
KMP(p, s, pi)
	i := 1
	j := 0
	WHILE i + j <= n
		IF j = m THEN
			print(i)
			i := i + j - pi[j]
			j := pi[j]
		ELSE IF s[i+j] = p[j+1] THEN j := j + 1
			ELSE IF j = 0 THEN i := i + 1
				ELSE
					i := i + j - pi[j]
					j := pi[j]
```


