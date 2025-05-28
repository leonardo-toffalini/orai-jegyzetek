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

Szavakban, minden regularis $L$ nyelvre letezik elegge hosszu $z$ szo $L$-ben ami felbonthato $3$ reszre: $z = uvw$ ugy hogy a kozepso szot barhanyszor megismetlem, a szo meg mindig $L$-ben lesz, tehat $uv^{i}w \in L$  $\forall i \geq 0$.

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

*Def.:* $L$ egy $\Sigma$ feletti nyelv ha $L \subseteq \Sigma_{0}^{*}$ ahol $\Sigma_{0}^{*}$ a $\Sigma$ abece betuibol kepzett veges sorozatok ($*$ nelkul).

*Def.:* $T$ Turing-gep felismeri az $L \subseteq \Sigma_{0}^{*}$ nyelvet ha $\Sigma_{0}^{*}$ minden elemen megall es $w \in L$ eseten $1$ az output, $w \in \Sigma_{0}^{*} \setminus L$ eseten $0$ az output.

*Def.:* A $T$ $k+1$ szalagos Turing-gep a szimulalja az $S$ $k$ szalagos Turing-gepet a $p \in \Sigma_{0}^{*}$ programmal, ha a $T$ $(k+1)$-edik szalagjara $p$-t irva tetszoleges $w \in \Sigma_{0}^{*}$ inputra $T$ es $S$ ugyanakkor all meg vagy nem all meg $w$-n, es megallaskor a $T$ elso $k$ szalagjan ugyanaz van mint $S$-en.

*Def.:* A $T$ $k+1$ szalagos Turing-gep univerzalis, ha minden $S$ $k$ szalagos Turing-gepehzez letezik $p \in \Sigma_{0}^{*}$ program ugy, hogy $T$ szimulalja $S$-et $p$-vel.

*Tetel:* Minden $k \in \mathbb{N}$ es minden $\Sigma$ abecehez letezik $\Sigma$ feletti $k+1$ szalagos univerzalis Turing-gep.
*Biz.:* Eloszor belatjuk hogy $k+2$ szalaggal tudunk szimulalni barmilyen $k$ szalagos Turing-gepet.
Irjuk fel $T$ $(k+1)$-edik szalagjara az osszes lehetseges parosat a $k$ hosszu szavaknak $u \in \Sigma ^{k}$ es az $S$ lehetseges allapotainak $g \in \Gamma_{s}$. Minden $ug$ parosra odairjuk $S$-nek az atmenet fuggvenyeit is: $\alpha_{s}(u, g), \beta_{s}(u, g), \gamma_{s}(u, g)$.
A $(k+2)$-edik szalagon csak azt taroljuk hogy $S$ eppen milyen allapotban lenne a szimulalaskor.
Igy amikor szimulaljuk $S$-et $T$-n csak annyit kell csinalnunk hogy elkezdjuk olvasni a $(k+1)$-edik szalagot addig ameddig nem talalunk olyan szot ahol $u$ pont az a szo amit olvasunk az elso $k$ szalagrol fentrol lefele. Utana megnezzuk hogy a melle irt allapot megegyezik-e azzal ami a $(k+2)$-edik szalagon van. Ha megtalaltuk azt a bejegyzest a $(k+1)$-edik szalagon amit kerestunk akkor tudjuk hogy $S$ hogyan lepne $u$-t olvasva a $g$ allapotban es ezt tudjuk szimulalni $T$-vel.

Ahoz hogy $k+1$ szalagon is mukodjon a trukk amit csinalunk ugy fogunk tenni mintha ketto fej lenne a $(k+1)$-edik szalagon. Az egyik oldalon $g$-t fogjuk tarolni a masik oldalon az osszes atmenetet. Ahoz hogy tudjunk ket fejet szimulalni egyel ugy trukkozunk hogy minden parosadik cellaba irunk csak betuket mert minden paratlanadikat fentartjuk adminisztraciora. A paratlanadik cellakban $*$ vagy $1$-es van azt jeleolve hogy ott van-e a masik fej van nem, $1$ ha ott van, $*$ ha nem.

*Tetel:* Minden $k$ szalagos $S$ Turing-gephez letezik $1$ szalagos $T$ Turing-gep, amely szimulalja $S$-et a kovetkezo ertelemben
- $\forall w \in \Sigma_{0}^{*}$ inputra $T$ leall akkor es csak akkor ha $S$ leall $w$-n.
- Leallaskor az $S$ $k$-adik szalagjan ugyanaz van, mint $T$ egyetlen szalagjan (az output megegyezik).
- Ha $S$ leallasig $t$ lepest tett meg, akkor $T$ leallasig $O(t^{2})$ lepest tett meg.

*Biz.:* Gongyuljuk fel a $T$ egyetlen vegtelen hosszu szalagjat $2k$ magasra

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

*Tetel:* Minden $\Sigma = \{ 0, 1, 2 \}$ folotti egy szalagos Turing-gephez van olyan program a RAM-gepen ami szimulalja a kovetkezo ertelemben:
- $\forall w \in \Sigma_{0}^{*}$ inputra a Turing-gep megall akkor es csak akkor ha a RAM-gep megall.
- Megallaskor a ket gepen az output ugyanaz.
- Ha a Turing-gep megallasik $t$ lepest tett meg akkor a RAM-gep $O(t)$ programsort hajt vegre megallasig.

*Def.:* Egy RAM-gep programjanak logaritmikus koltsege, avagy futasi ideje $u \in \mathbb{N}$ , ahol $u$-t ugy kapjuk hgoy a vegrehajtott programsorok szamat osszegezzuk a bennuk szereplo szamok binaris hosszaval ($x \to \log x$).

*Tetel:* Minden RAM-gep programhoz an egy olyan $T$ Turing-gep amely azt szimulalja a kovetkezo ertelemben:
- Ugyanazon az inputon allnak meg.
- Ugyanaz az output a ket gepen megallaskor.
- Ha a RAM-gep logaritmikus koltsege $u$ akkor a Turing-gep megallasikg $O(u^{2})$ lepest tesz meg.

### Eldonthetetlenseg
*Def.:* Az $L \subseteq \Sigma_{0}^{*}$ nyelv rekurziv ha van olyan $T$ Turing-gep amely $\Sigma_{0}^{*}$ minden elemen megall es pontosan akkor $1$ az output ha $w \in L$ kulonben $0$.
*Def.:* Az $f$ fuggveny rekurziv ha letezik olyan $T$ Turing-gep amely ot kiszamolja, azaz $\forall w \in \Sigma_{0}^{*}$ inputon leall es leallaskor az output $f(w)$.
*Def.:* Az $L \subseteq \Sigma_{0}^{*}$ nyelv rekurzivan felsorolhato, ha letezik $f$ rekurziv nyelv melyre $L = \operatorname{Im}(f)$
*Def.:* Az $L \subseteq \Sigma_{0}^{*}$ complement rekurzivan felsorolhato, ha $\bar{L}$ rekurzivan felsorolhato.

*All.:* Minden veges nyelv rekurziv.
*Biz.:* Mivel a nyelv veges ezert van leghosszabb elem, ezert felepithetjuk a nyelv szofajat. A szofara mar tudunk Turing-gepet adni.

*Tetel:* Madjnem minden nyelv nem rekurziv.
*Biz.:* Megszamlalhatoan sok Turing-gep van, ezert megszamlalhatoan sok rekurziv nyelv. Viszont continuum sok nyelv van.

*Tetel:* Az $L$ nyelv rekurzivan felsorolhato akkor es csak akkor, ha van olyan Turing-gep amely $\Sigma_{0}^{*}$ elemei kozul pontosan $L$-beli szavakon all meg, a tobbin nem all meg.

*Tetel:* Majdnem minden nyelv nem rekurzivan felsorolhato.
*All.:* Ha $A$ es $B$ rekurziv, akkor $A \cup B$, $A \cap B$, $A \setminus B$ szinten rekurzivak.
*All.:* Ha $A$ es $B$ rekurzivan felsorolhato, akkor $A \cup B$ es $A \cap B$ szinten rekurzivan felsorolhatok.
*Lemma:* $L \in \text{R} \iff L \in \text{RE}$ es $L \in \text{co-RE}$

*Tetel:* Legyen $T$ egy $2$-szalagos univerzalis Turing-gep a $\Sigma$ abece felett, Legyen $L_{T}$ azon $w \in \Sigma_{0}^{*}$ szavak halmaza, melyekre $T$ leall ha mindket szalagjara $w$-t urink. Ekkor $L_{T}$ rekurzive felsorolhato, de nem rekurziv.
*Biz.:* Nyilvan rekurzive felsorolhato ez a nyelv, mert akkor rekurzive felsorolhato egy nyelv ha van Turing-gep amely pontosan a nyelv elemeire all meg, es $T$ pont akkor all meg ha mindket szalagjara $w$-t irunk.
Tehat, az elozo lemma ertelmeben mar csak annyit kell belatnunk hogy $L_{T}$ komplementere nem rekurzive felsorolhato.
**TODO...**

*Kovetkezmeny:* Nincs olyan Turing-gep ami el tudna donteni hogy egy masik Turing-gep leall-e egy szora. Mashogy megfogalmazva, a $(T, w)$ parokat tartalmazo nyelv, ahol $T$ Turing-gep megall $w$-re, nem rekurziv.

*Def.:* A dominonyelv szavai dominokeszletek ahol egy dominokeszlet elemei $(a, b, c, d)$ negyesek.
*Def.:* $L_{\text{KIRAK}}$ azon szavakat tartalmazza a dominonyelvbol amelyekkel lehet parkettazni a sikot.
*Def.:* $L_{\text{NEMKIRAK}}$ azon szavakat tartalmazza a dominonyelvbol amelyekkel nem lehet parkettazni a sikot.

*Lemma:* $V$ rekurziv es $L \subset V$. Ekkor $L$ rekurziv akkor es csak akkor ha $L$ es $V - L$ rekurzive felsorolhato.
*Tetel:* $L_{\text{NEMRAK}}$ rekurzive felsorolhato.
*Lemma:* $w \in L_{\text{KIRAK}} \iff w$-vel kirakhato minden $N \in \mathbb{N}$ szmara a $(2N + 1) \times (2N + 1)$ meretu negyzet.
*Tetel:* $L_{\text{KIRAK}}$ nem rekurzive felsorolhato.

### Bonyolultsagi osztalyok
*Def.:* $\operatorname{time}_{T}(n)$ jeloli a legfeljebb $n$ hosszu inputokon hasznalt lepesszamok maximumat a $T$ Turing-gep altal.
*Def.:* $\operatorname{space}_{T}(n)$ jeloli a legfeljebb $n$ hosszu inputokon hasznalt mezok maximumat a $T$ Turing-gep altal.
*Def.:* $\operatorname{DTIME}(f(n))$ jeloli azon $L$ nyelvek osztalyat, ahol minden $L$-hez letezik $T$ Turing-gep amely felismeri $L$-et es $w \stackrel{?}{\in} L$  kerdest $f(\lvert w \rvert)$ lepesben eldonti.
*Def.:* $\operatorname{DSPACE}(f(n))$ jeloli azon $L$ nyelvek osztalyat, ahol minden $L$-hez letezik $T$ Turing-gep amely felismeri $L$-et es $w \stackrel{?}{\in} L$  kerdest $f(\lvert w \rvert)$ tarban eldonti.
*Def.:*
$$
\operatorname{P} = \bigcup_{i=1}^{\infty} \operatorname{DTIME}(n^{i})
$$
*Def.:*
$$
\operatorname{PSPACE} = \bigcup_{i=1}^{\infty} \operatorname{DSPACE}(n^{i})
$$

*All.:* $k \cdot \operatorname{time}_{T}(n) \geq \operatorname{space}_{T}(n)$. Kovetkezmenykent $\operatorname{DTIME}(f(n)) \subset \cup_{k=1}^{\infty}\operatorname{DSPACE}(k \cdot f(n))$.

*Def.:* $\operatorname{NTIME}(f(n))$ jeloli azon $L$ nyelvek osztalyat, ahol minden $L$-hez letezik $T$ nem determinisztikus Turing-gep amely felismeri $L$-et es $w \stackrel{?}{\in} L$  kerdest $f(\lvert w \rvert)$ lepesben eldonti.
*Def.:* $\operatorname{NSPACE}(f(n))$ jeloli azon $L$ nyelvek osztalyat, ahol minden $L$-hez letezik $T$ nem determinisztikus Turing-gep amely felismeri $L$-et es $w \stackrel{?}{\in} L$  kerdest $f(\lvert w \rvert)$ tarban eldonti.
*Def.:*
$$
\operatorname{NP} = \bigcup_{i=1}^{\infty} \operatorname{NTIME}(n^{i})
$$
*Def.:*
$$
\operatorname{NPSPACE} = \bigcup_{i=1}^{\infty} \operatorname{NSPACE}(n^{i})
$$
*Def.:* $\operatorname{co-NP} = \{ l : \Sigma_{0}^{*} - L \in \operatorname{NP} \}$

*Def.:* Azt mondjuk hogy $w$-nek az $L$-beli tagsagara az $y$ szo polinomialis tanu, ha $L$-hez van olyan $T$ Turing-gep, hogy $w \in L \iff T$ elfogadja a $(w, y)$ part $\lvert w \rvert$-ben polinomialis idoben.

*Tetel:* $L \in \operatorname{NP}$ akkor es csak akkor ha $\forall w \in L$-ra letezik polinomialis tanu.

*Tetel:* (Pratt) $\operatorname{PRIM} \in \operatorname{NP}$

### NP-teljesseg
*Def.:* Az $L$ nyelv NP-teljes, ha $L \in \text{NP}$ es $\forall K \in \text{NP}$-re ihaz hogy polinomialisan visszavezetheto $L$-re. Azaz $\forall K \in \text{NP}: K \propto L$.

*Megj.:* Az hogy $L$ NP-teljes nem azt jelenti hogy nehezebb barmilyen masik NP-beli nyelvnel, hanem csak annyit jelent hogy legalabb annyira nehez. Ha azt akarjuk belatni hogy $L$ NP-teljes ahoz kell talalnunk egy $V$ NP-teljes nyelvet es megmutatnunk hogy $V$ visszavezetheto $L$-re. Igy mivel $V$ NP-teljes ezert minden NP nyelv visszavezetheto ra es $V$ visszavezetheto $L$-re. Roviden $\forall K \in \operatorname{NP}: K \propto V \propto L \implies K \propto L$.

*Tetel:* (Cook) A SAT nyelv NP-teljes.
*Biz.:* Eloszor is $\operatorname{SAT} \in \text{NP}$, mert egy kielegito behelyettesites polinomialis tanu.
Masodszor annyit kell megmutatnunk hogy barmilyen $T$ nem determinisztikus Turing-gephez tudunk konstrualni olyan konjunktiv normal format, ami pont ennek a gepnek a mukodeset tukrozi. Ez a nehezebb resz a bizonyitasban, de az osszes lepes elegge egyertelmu csak vegig kell gondolni az osszes szabalyat a Turing-gepeknek es azt formalizalni konjunktiv normal formaban.

### Visszavezetesek
*Tetel:* H2C NP-teljes
*Tetel:* G3C NP-teljes
*Tetel:* G$k$C NP-teljes
*Tetel:* INDEPENDENT NP-teljes
*Tetel:* SAT-3 NP-teljes
*Tetel:* LEFOG NP-teljes
*Tetel:* LEFED NP-teljes
*Tetel:* K-PART NP-teljes
*Tetel:* PART NP-teljes
*Tetel:* SUBSET-SUM NP-teljes
*Tetel:* Hatizsak feladat NP-teljes

## b) Algoritmusok tervezese es elemzese
### Dinamikus programozas
#### Fibonacci szamok $O(\phi ^{n})$
```python
def fib(n):
  if n <= 1:
    return n
  else:
    return fib(n-1) + fib(n-2)
```

#### Fibonacci szamok DP $O(n)$
```python
def fib(n):
  cache = [0, 1]
  for i in range(2, n+1):
    cache.append(cache[i-1] + cache[i-2])

  return cache[n]
```

#### Hatizsak feladat $O(n \cdot W)$
```python
def knapsack(items, M):
  A = [0 for _ in range(M)]
  for item in items:
	for i in range(M, item.weight, -1):
	  A[i] = max(A[i], A[i - item.weight] + item.value)
  return A[-1]
```

### Adatstrukturak
#### Array
Fix meretu egybefuggo memoria terulet

#### Queue
Dinamikus meretu array, push front $O(1)$

#### Stack
Dinamikus meretu array, push back $O(1)$

#### Linked list


#### Tree
#### Binary search tree
#### AVL tree
#### Graph
#### Heap

### Rendezesek
- bubble sort
- insertion sort
- merge sort
- heap sort
- quick sort

### Grafok tarolasa
- incidencia matrix
- ellista

### Grafok bejarasa (BFS, DFS)
- BFS
- DFS

### Legrovidebb ut
- Dijkstra
- Pert modszer
- Bellman–Ford
- Floyd–Warhsall

### Minimalis koltsegu feszitofak
- Kruskall
- Prim
