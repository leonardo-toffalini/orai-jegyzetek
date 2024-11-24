# Algoritmusok
**Mindig kell a lépésszám is!**

### 1.
*Írjon le két algoritmust a legnagyobb elem megtalálására!*

$O(n)$
```python
def max_1(A):
	max_index = 0
	for i in range(1, n):
		if A[i] > A[max_index]:
			max_index = i
	return max_index
```

$O(n)$
```python
def max_2(A): # dumb way to write recursion, but this is in the book...
	n = len(A)
	if n = 0:
		return 0
			
	j = max_2(A[:-1])
	if A[j] > A[-1]:
		return j
	else:
		return n-1

def max_2(A): # better, tail recursive, more elegant way of writing recursion
	def helper(A, maximal):
		if len(A) == 1:
			return A[0]
		hd, tl = A[0], A[1:]
		return helper(tl, max(hd, maximal))
	return helper(A, A[0])
```

```ocaml
let max_list list =
	let rec aux list maximal =
		match list with
		| [] -> 0
		| hd :: tl -> aux tl (max hd maximal)
	in
	aux list (List.hd list)
```

### 2.
*Írja le az összefésülő rendezés algoritmusát!*

$O(n \log n)$
```python
def mergesort(A):
	if len(A) == 1:
		return A
	mid = len(A) // 2
	B = mergesort(A[:mid])
	C = mergesort(A[mid:])
	return merge(B, C)

def merge(B, C):
	result = []
	p, q = len(B), len(C)
	i, j = 1, 1
	while i < p and j < q:
		if B[i] <= C[j]:
			result[i + j + 1] = B[i]
			i += 1
		else:
			result[i + j + 1] = C[j]
			j += 1
	if i > p:
		for k in range(j, q):
			result[q + k] = B[k]
	else:
		for k in range(i, p):
			result[q + k] = C[k]

	return result
```

### 3.
*Hogyan megy kupacokban a MINTÖRLÉS?*

$O(\log n)$
```python
class Heap:
	def __init__(self, lst=None):
		if lst is None:
			self.lst = []
		else:
			self.lst = lst
		self.end = -1

	def min_pop(self):
		swap(self.lst[0], self.lst[self.end])
		self.end -= 1
		self.sink_down(i = 0)
		return self.lst[self.end + 1]

	def sink_down(self, i):
		num = self.lst[i]
		j = 2*i + 1
		while j < self.end + 1:
			if self.lst[j - 1] < self.lst[j]:
				j -= 1
			if self.lst[j] < num: # num is greater than the smaller child
				self.lst[i] = self.lst[j]
				i = j
				j = 2*i + 1
			else:
				break # we are done
		j -= 1
		if j < self.end + 1 and self.lst[j] < num:
			self.lst[i] = self.lst[j]
			i = j
		self.lst[i] = num

```

Beszúrás:
Becseréljük az első elemet az utolsóval.
Megjegyezzük az utolsó elemet és utána töröljük
Lebillegtettjük az első elemet.
Vissza adjuk a megjegyzett elemet

Lebillegtetés:
Megnézzük, hogy a két gyerek közül melyik a kisebb és azzal összehasonlítjuk a szülőt.
	Ha a szülő kisebb, mint a kisebbik gyerek akkor mindkettőnél kisebb és készen vagyunk
	Ha a szűlő nagyobb, mint a kisebbik gyerek akkor a kisebbik gyereket felemeljük a szülő helyére és a szülőt levisszük a gyerek helyére.
		Tovább folytatujuk a levitt szülővel az iterálást, míg le nem állunk

### 4.
*Hogyan megy a gyors kupacépítés és a kupacos rendezés?*

kupacrendezés: $O(n \log n)$
kupacépítés: $O(n)$
```python
def heap_sort(lst):
	h = Heap()
	base_list = []
	for x in lst:
		base_list.append(x)
	h = Heap(base_list)
	for i in range(len(h.lst) // 2, 0, -1):
		h.sink_down(i)
	result = []
	while h.end > -1:
		result.append(h.min_pop())
	return result
```

### 5.
*Írja le a leszámláló és a számjegyes rendezés algoritmusait!*

$O(n + m)$
```python
def lesz_rend(A, m):
	aux = [0 for _ in range(m + 1)]
	for j in range(n):
		aux[A[j]] += 1

	for i in range(1, m + 1):
		aux[i] += aux[i - 1]
		   
	res = [-1 for _ in range(n)]
	for j in range(n, 0, -1):
		res[aux[A[j]]] = j
		aux[A[j]] -= 1
	return res
```

***Számjegyes rendezés:*** Adot $a_{1}, a_{2}, \dots, a_{n}$ természetes számok, ahol minden $i$-re $a_{i} = \overline{b_{i}^{k-1}b_{i}^{k-2}\dots b_{i}^{0}}$ valamilyen $m$ alapú számredszerben.
$O(k(n+m))$

A számjegyes rendezés annyit csinál, hogy az inputot leszáláló rendezéssel rendezi először a legszignifikánsabb számjegy alapján aztán a következő alapján stb.

### 6.
*Írja le Euklidesz algoritmusát!*

$O(n^{3})$ bitműveletekben
```python
def gcd(a, b):
	if a == 0:
		return b
	return gcd(b % a, a)
```

```ocaml
let gcd a b =
	match a with
	| 0 -> b
	| _ -> gcd (b mod a) a
```

### 7.
*Írja le a hátizsák feladat megoldására tanult algoritmust!*

$O(n \cdot M)$
```python
def knapsack(items, M):
	A = [0 for _ in range(M)]
	for item in items:
		for i in range(M, item.weight, -1):
			A[i] = max(A[i], A[i - item.weight] + item.value)
	return A[-1]
```

### 8.
*Írja le Prim algoritmusát!*

$O(m + n\log n)$

```
PSEUDOCODE

funtion prim(G, c):
  P = {1}; S = {}; M = V - {1}
  K[1] = 0
  T = {} // minimum spanning tree

  while P != {}:
      u = argmin{K[v] for v in P}
      P.remove(u)
      S.insert(u)

      if u != 1:
          T = T + {u, u.parent()}

      for v in u.neighbors():
          if v in P and c(u, v) < K(v):
              K(v) = c(u, v)
              p(v) = u

          if v in M:
              K(v) = c(u, v)
              p(v) = u
              M.remove(v)
              P.insert(v)
  return T
```

```python
def prim(G, c):
    P, S, M = {0}, set(), G.vertices - {0}
    K = [float("inf") for _ in G.vertices]
    p = [-1 for _ in G.vertices]
    K[0] = 0
    T = set()  # the minimum spanning tree (set of edges)

    while len(P) != 0:
        u, _ = min([(v, K[v]) for v in P])

        P.remove(u)
        S.add(u)

        if u != 0:
            T.add((u, p[u]))

        for v in G.neighbors(u):
            if v in P and c(u, v) < K[v]:
                K[v] = c(u, v)
                p[v] = u

            if v in M:
                K[v] = c(u, v)
                p[v] = u
                M.remove(v)
                P.add(v)
```

### 9.
*Írja le Dijkstra algoritmusát!*

$O(m + n\log n)$

```
 PSEUDOCODE
 
 function dijkstra(G, s):
     P = {s}; S = {}; M = V - {s}; K[s] = 0; p(s) = s
     while P != {}:
         u = argmin(K(v) for v in P)
         P.remove(u)
         S.insert(u)

         for v in u.neighbors():
             if v in P and K[u] + c(u, v) < K[v]:
                 K[v] = K[u] + c(u, v)

             if v in M:
                 K[v] = K[u] + c(u, v)
                 p(v) = u
                 M.remove(v)
                 P.insert(v)
```

### 10.
*Írja le Bellmann és Ford algoritmusát!*

$O(mn)$

```python
def BF(G, c):
	p = [0 for _ in range(n)]
	dist = [float('inf') for _ in range(n)]
	p, dist[s] = s, 0
	for i in range(n-1):
		for u in range(n):
			for v in u.neighbors():
				if dist[u] + c(u, v) < dist[v]:
					dist[v] = dist[u] + c(u, v)
					p[v] = u

	# test if change happens after n-1 iterations, if so, non conservative weights
	for u in range(n):
		for v in u.neighbors():
			if dist[u] + c(u, v) < dist[v]:
				p[v] = u
				return "non conservative", K, p, v
	return "conservative", K, p, s
```

### 11.
*Írja le Johnson algoritmusát!*

$O(n^{2}\log n + nm)$

I. Futtassunk el egy Bellman-Ford algoritmust, mely ad nekünk egy $K = \pi$ megengedett pontenciált, azaz $\forall (uv) \in E: \pi(v) - \pi(u) \leq c(uv)$.

II. Módosítsuk az élek súlyozását a következő módon: $c'(uv) = c(uv) + \pi(u) - \pi(v)$
Ez a súlyozás már nemnegatív lesz, mert $\pi$ egy megengedett potenciál, ami pont azt jelenti, hogy a jobb oldal nem kisebb, mint $0$.

III. Futtassunk minden csúcsból Dijkstra algoritmust a $c'$ súlyozás szerint

IV.  Vakarjuk ki a végeredményből a kívánt eredményt a következő módon:
Ha $d'(u,v)$ a legrővidebb $c'$ szerinti út hossza $u$ és $v$ között, akkor $d(u, v) = d'(u,v) - \pi(u) + \pi (v$) a legrövidebb $c$ szerinti út hossza $u$ és $v$ között.

### 12.
*Írja le azt az algoritmust, amely legrövidebb utat keres tetszőleges súlyozású irányított aciklikus gráfban! Feltehető, hogy minden csúcs elérhető $s$-ből, és hogy a topologikus sorrendet már meghatároztuk.*

$O(m)$

```python
def acikl_dijkstra(G):
	TS = G.topsort()
	P = [s]
	seen = []
	M = V - {s}
	dist[s] = 0
	p[s] = s
	for i in range(n):
		u = TS[i]
		P.remove(u)
		seen.add(u)
		for v in u.neighbors():
			if v in P and dist[u] + c(u, v) < dist[v]:
				dist[v] = dist[u] + c(u, v)
				p[v] = u
			if v in M:
				dist[v] = dist[v] + c(u, v) 
				p[v] = u
				M.remove(v)
				P.add(v)
```

Topologikus sorrend alapján iterálunk
	Ha már vizsgált akkor megpróbáljuk frissíteni
	Ha még nem vizsgált akkor inicializáljuk

related: [[AlgTerv 1]]