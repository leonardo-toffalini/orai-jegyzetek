## a)
### Legrovidebb ut feladatok
#### Dijkstra
```python
def dijkstra(G, s):
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

#### Bellman-Ford
```python
def BF(G, c):
  p = [0 for _ in range(n)]
  dist = [float('inf') for _ in range(n)]
  p, dist[s] = s, 0
  for i in range(n - 1):
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

### Kereses
Binaris kereses rendezett tombben $O(\log n)$
```python
def binary_search(arr, val):
  left, right = 0, len(arr) - 1
  while left <= right:
    middle = (left + right) // 2
	if arr[middle] == val:
	  return middle
	elif arr[middle] < val:
	  left = middle + 1
	else:
	  right = middle - 1
  return -1  # not found
```

### BFS $O(\lvert V \rvert + \lvert E \rvert)$
```python
def bfs(graph, start):
  visited = set()
  queue = deque([start])
  visited.add(start)
  while queue:
    node = queue.popleft()
	print(node, end=" ")
	for neighbor in graph[node]:
	  if neighbor not in visited:
	    visited.add(neighbor)
		queue.append(neighbor)
```

### DFS $O(\lvert V \rvert + \lvert E \rvert)$
```python
def dfs(graph, node, visited=None):
  if visited is None:
    visited = set()
    visited.add(node)
    print(node, end=" ")
    for neighbor in graph[node]:
      if neighbor not in visited:
	    dfs(graph, neighbor, visited)
```


## b)
### Parositasok paros grafokban
#### Stabil parositas: Gale–Shapley algoritmus $O(m)$
Fiuk algoritmusa: Minden fiu eloszor megkeri az altala legkedveltebb lanyt, ha az kikosarazza, akkor megkeri a kovetkezot, es igy tovabb addig ameddig nem talal valakit vagy nincs mar senki.

Lanyok algoritmusa: Egy lany az elso kerot elfogadja ideiglenes partnernek, a tovabbi keroknel eldonti melyik a jobb: a mostani partner, vagy az uj kero, a rosszabbikat kikosarazza, es igy tovabb. Mindig az eddigi legjobbat tartja meg (ideiglenes) partnernek, es az osszes tobit kikosarazza.

#### Tartalmazasra maximalis parositas: Konig javito utas algoritmusa $O(\min(n_{1}, n_{2}) \cdot m)$
*Def.:* Legyen $G$ graf es $M$ parositas $G$-ben, es $P : v_{0}, e_{1}, v_{1}, \dots, e_{k}, v_{k}$ egy ut. Ekkor $P$ egy javito ut $M$-re nezve, ha $v_{0}$ es $v_{k}$ nem parositottak, $k$ paratlan es a paros sokadik elek elemei $M$-nek.
Tehat, $P$ minden masodik ele eleme az eredeti parositasnak, es az elso es utolso csucs $P$-nek nem fedett $M$ altal.

*Algoritmus:* Kiindulunk egy tetszoleges parositasbol es amig van javito ut addig csinaljuk a kovetkezot: vegyuk a szimmetrikus differenciajat a parositasnak es a javito utnak es az legyen a kovetkezo parositas.

#### Tartalmazasra maximalis parositas: Hopcroft–Karp algoritmus $O(m \sqrt{ n^{*} })$ ahol $n^{*} = \nu(G) \leq \min(\lvert U \rvert, \lvert V \rvert) \leq n / 2$

### Maximalis sulyu eset
- Maximalis sulyo parositas: Kuhn Magyar modszere $O(\lvert E \rvert^{2} \cdot \lvert S \rvert)$

### Elszinezes
- Ketszinezes: BFS $\to$ BFS szintek, van vagy nincs paratlan kor

## c)
### Halozati folyamok
*Def.:* A $(G, c, s, t)$ negyes egy halozat ahol $G = (V, E)$ egy iranyitott graf es $c : E \to \mathbb{R}$  a kapacitas fuggveny ahol $c(e) \geq 0 \quad \forall e \in E$, valamint $s \neq t \in V$ csucsok ahol $s$ a forras es $t$ a nyelo.

*Def.:* Egy halozaton egy $f : E \to \mathbb{R}$ fuggveny folyam, ha a kovetkezok teljesulnek ra:
- $\forall e \in E: \quad 0 \leq f(e) \leq c(e)$ – tehat a folyam erteke $0$ es a kapacitas kozott van minden elen.
- $\forall v \in V \setminus \{ s, t \}$-re $f_{\text{be}}(v) = f_{\text{ki}}(v)$ ahol $f_{\text{be}}(v)$ a $v$ be-elein levo folyam ertekeinek osszege, hasonloan $f_{\text{ki}}(v)$ a ki-elek folyamanak osszege.

*Megj.:* Azt mondjuk hogy $\lvert f \rvert := f_{\text{ki}}(s) - f_{\text{be}}(t)$ a folyam erteke
Celunk az hogy adjunk egy maximalis erteku folyamot egy halozaton.

*Tetel:* (Ford–Fulkerson)
1. Egy $f$ folyamra $\lvert f \rvert$ maximalis akkor es csak akkor, ha $G'$ maradek halozataban nem letezik $s \leadsto t$ ut.
2. A maximalis folyamertek egyenelo a minimalis vagaskapacitassla. (Max flow - min cut)
3. Ha $c(e)$ egesz minden $e$ elre, akkor van olyan $f$ maximalis folyam, hogy $f(e)$ szinten egesz minden $e$ elre.

### Menger-tetel
*Tetel:* (Menger-el) $G$ iranyitott vagy iranyitatlan grafban az $s \leadsto t$ paronkent eldiszjunkt utak maximalis szama egyenlo a $t$ csucsot az $s$-tol elszeparalo elek minimalis szamaval.

*Tetel:* (Menger-el) $G$ iranyitott vagy iranyitatlan grafban az $s \leadsto t$ paronkent csucsdiszjunkt utak maximalis szama egyenlo a $t$ csucsot az $s$-tol elszeparalo csucsok minimalis szamaval.


### Grafok tobbszoros osszefuggosege
*Tetel:* (Menger-el) $G$ graf $k$-szorosan el-osszefuggo akkor es csak akkor, ha $\forall x \neq y \in V$-re van $k$ darab paronkent el-diszjunk $x \leadsto y$ ut.

*Tetel:* (Menger-csucs) $G$ graf $k$-szorosan csucs-osszefuggo akkor es csak akkor, ha $\forall x \neq y \in V$-re van $k$ darab paronkent csucs-diszjunk $x \leadsto y$ ut.
