# Tételek, lépésszámok
**Itt csak pontosan ki kell mondani a kért állításokat, bizonyítani nem!**

### 1.
*Írja le az összehasonlításos rendezésekről szóló alsó becslést!*

***Tétel:*** A rendezési feladatnál az algoritmus döntéseit leíró fának legalább $n!$ levele van és így a fa mélysége $\geq \log(n!) \geq n \log n - \frac{3}{2} n$. Következtetésképpen minden olyan algoritmusnak, mely összehasonlításokat használva rendez $n$ elemet, legalább $n \log n - \frac{3}{2}n$ összehasonlítást kell tennie a legrosszabb esetben.

### 2.
*Írja le a modulo $m$ hatványozásról szóló tételt!*

***Állítás:*** Legyenek $a, b$ és $m$ legfeljebb $n$ bites természetes számok, valamint $a < m$ és $b < m$. Ekkor $a^{b} \mod m$ hatvány kiszámítható $O(n^{3})$ lépésben (minden szorzás után cisnálunk egy maradékos osztást).

### 3.
*Mennyi az Euklideszi algoritmus lépésszáma?*

***Tétel:*** Az euklideszi algoritmus során maximum $2n$ darab maradékos osztást végzünk el, tehát a lépésszám $O(n^{3})$.

### 4.
*Mennyi a szélességi keresés lépésszáma? Soroljon fel 3 alkalmazását a szélességi keresésnek!*

Amennyiben az input szomszédsági mátrixszal volt megadva, akkor $O(n^{2})$. Ha éllistával akkor $O\left( \sum_{u \in V} (d(u) + 1) \right) = O(2m + n)$, ami $= O(m)$, ha nincs a gráfban izolált csúcs.

*Alkalmazások:*
1. Összefüggőség tesztelése.
2. Nem súlyozott gárfban adott csúcsból legrövidebb utak meghatározása.
3. Kétszínezés.

### 5.
*Írja le egy gráf összefüggőségének eldöntéséről tanult alsó becsléseket!*

***Tétel:*** A szomszédsági mátrixszal adott gráf összefüggőségének eldöntéséhez kell $n\choose 2$ input olvasás.
***Tétel:*** Éllistával adott gráf összefüggőségének eldöntéséhez kell legalább $m$ olvasó lépés.

### 6.
*Írja le a szélességi keresésről szóló (öt állítást tartalmazó) tételt!*

***Tétel:*** Legyen $G$ összefüggő. A szélességi keresés lefutása után:
a) $\{ \{ p(v), \; v \} \mid v \neq s \}$ élek feszítőfát adnak.
b) Ha $uv \in E$, akkor $\lvert SZ(u) - SZ(v) \rvert \leq 1$.
c) $\forall u \in V$ a legrövidebb $s \leadsto u$ út hossza $SZ(u)$.
d) $\forall u \in V$  az egyik legrövidebb $s \leadsto u$ út: $s, \dots, p(p(u)), p(u), u$.
e) $\forall v \in V$ csúcsra $p(v) > 0$

### 7.
*Írja le az irányítatlan gráfok mélységi kereséséról szóló tételt!*

***Tétel:*** Irányítatlan gráfban mélységi keresés után $uv \in E \implies u$ őse $v$-nek vagy fordítva (azaz nincs keresztél).
$u$ őse $v$-nek $\iff MSZ(u) \leq MSZ(v)$ és $BSZ(u) \geq BSZ(v)$.

- MSZ: *mélységi szint*, azaz mikor láttuk először
- BSZ: *befelyezési szint*, azaz mikor láttuk utoljája

### 8.
*Mennyi a Prim-algoritmus lépésszáma $d$-edfokú kupacokkal?*

***Állítás:*** Prim algoritmusának lépésszáma $d$-edfokú kupaccal $O(m\log _{d}n + dn\log_{d}n)$. Ez $d^{*} = \max\left( 2, \left\lceil  \frac{m}{n}  \right\rceil \right)$ esetén $O(m\log_{d^{*}}n)$. Még jobb kupaccal (Fibonacci, nem tanultuk) Prim algoritmusának lépésszáma $O(m + n\log n)$.

### 9.
*Mennyi a Johnson-algoritmus lépésszáma?*

Lépésszám: $O(n^{2} \cdot \log n + n \cdot m)$
$$
O(n^{2}\cdot \log n + n \cdot m) = 
\begin{cases}
1 \times \text{Bellman-Ford: } & O(n \cdot m) \\
n \times \text{Dijktra: } & O(n^{2} \cdot \log n)
\end{cases}
$$

### 10.
*Írja le az AVL-fák mélységéről szóló tételt!*

***Tétel:*** Egy $d$ mélységű AVL-fának $\geq F_{d+3} - 1$ csúcsa van, ezért egy $n$ csúcsú AVL-fa mélysége $\leq 1.44 \cdot \log n$.
(Itt a költő valószínűleg arra gondolt, hogy $\leq F_{d+3} - 1$ csúcsa van)

### 11.
*Vödrös (láncolt) hashelésnél mennyi a keresések várható lépésszáma?*

***Tétel:*** A sikeres keresés várható lépésszáma a vödrös (láncolt) hashelésnél: $1 + \frac{\alpha}{2}$, ahol $\alpha := \frac{N}{M}$, (itt $N$ a tárolt szótár mérete, $M$ pedig a láncolt listák száma).
A sikertelen keresés, illetve a beszúrás várható lépésszáma a vödrös (lánvolt) hashelésnél: $1 + \alpha$.

### 12.
*Írja le a Hopcroft-Karp-algoritmus lépésszámáról tanult tételt!*

***Tétel:*** Az algoritmus $2 \sqrt{ n' }$ fázis után véget ér, ahol $n' = \nu(G) \leq \min\{ \lvert S \rvert, \lvert T \rvert \} \leq \frac{n}{2}$. Mivel egy fázis végrehajtható $O(m)$ lépésben így az algoritmus lépésszáma $O(m \sqrt{ n })$.


related: [[AlgTerv 1]]