## a) Szamitastudomany
### Veges automatak
*Def.:* $L$ egy nyelv a $\Sigma$ abece felett, ha elemei veges hosszusagu karaktersorozatok (szavak), ahol a karakterek $\Sigma$-bol valoak.

*Def.:* Az $M = (Q, \Sigma, \delta, q_{0}, F)$ veges automata ahol
- $Q$ – allapotok (veges) halmaza
- $\Sigma$ – az abece ami felett ertelmezve van
- $\delta$ – az atmenet fuggvenye, tehat az adott allapotban valamilyen betut olvas akkor hova kerul
- $q_{0}$ – a kezdoallapot
- $F$ – az elfogadott vegellapotok halmaza
- $L(M)$ – azon szavak halmaza, amelyek olvasasara $M$ elfogado allapotba kerul

*Def.:* $M$ felismeri az $L(M)$ nyelvet.
*Def.:* Egy nyelv regularis ha van veges automata ami felismeri.

*Lemma:* (Pumpalos-lemma) $\forall L$ regularis $\exists n \forall z \in L$, $\lvert  z  \rvert \geq n$ $\exists u, v \neq \emptyset$ $w: z = uvw$ es $\lvert uv \rvert \leq n$ es $\forall i \; uv^{i}w \in L$

Szavakban, minden regularis $L$ nyelvre letezik elegge hosszu $z$ szo $L$-ben ami felbonthato $3$ reszre: $z = uvw$ ugy hogy a kozepsot szot barhanyszor leirom, a szo meg mindig $L$-ben lesz, tehat $uv^{i}w \in L$  $\forall i \geq 0$.

<img src="Pumping_Lemma_for_regular_languages_diagram.png" />

*Megj.:* Ha egy nyelv nem pumpalhato akkor nem regularis. Forditva nem igaz, hogy ha egy nyelv pumpalhato akkor regularis.

### Turing gep
*Def.:* Egy $T = (k, \Sigma, \Gamma, \alpha, \beta, \gamma)$ hatos egy Turing-gep, ahol
- $k \in \mathbb{N}$ – szallagok szama
- $3 \leq \lvert \Sigma \rvert < \infty$ es $* \in \Sigma$ – abece
- $\lvert  \Gamma \rvert < \infty$ es $\text{START}, \text{STOP} \in \Gamma$ – allapothalmaz
- $\alpha : \Sigma ^{k} \times \Gamma \to \Gamma$ – allapot atmenetfuggveny
- $\beta : \Sigma ^{k} \times \Gamma \to \Sigma ^{k}$ – iras atmenetfuggveny
- $\gamma : \Sigma ^{k} \times \Gamma \to (-1, 0, 1)^{k}$ – fejek mozgasanak az atmenetfuggvenye

### RAM gep
*Def.:* A RAM-gep all egy vegtelen memoriabol, amelynek cellait $X[i]$-vel jeloljuk, minden cellaban egy $\mathbb{Z}$-beli szam irhato. A RAM-gep ezen kivul tratalmaz egy programtarat, amelybe a kovetkezo programsorok barmilyen kombinacioja irhato:
- $X[i] := 0$
- $X[i] := 1$
- $X[i] := X[i] \pm X[j]$
- $X[i] := X[i] \pm 1$
- $X[i] := X[j]$
- $X[i] := X[X[j]]$
- $X[X[i]] := X[j]$
- $\text{IF } X[i] \leq 0 \text{ THEN GOTO [programsor cime]}$

A RAM-gep outputja a veges memoria tartalma. Kezdetben minden celle $0$-ra van inicializalva.

### Eldonthetetlenseg


### Bonyolultsagi osztalyok


### NP-teljesseg


### Visszavezetesek


## b) Algoritmusok tervezese es elemzese
### Dinamikus programozas
### Adatstrukturak
### Rendezesek
### Grafok tarolasa
- incidencia matrix
- ellista

### Grafok bejarasa (BFS, DFS)
- BFS
- DFS

### Legrovidebb ut
- Dijkstra

### Minimalis koltsegu feszitofak
- Kruskall
- Prim
