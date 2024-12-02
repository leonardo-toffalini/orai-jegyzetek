---
title: 12. Útkeresés
date: 2024-12-02
---
###  Autopalya hierarchiak
$G_{0}$ az input es majd sorba fel fogunk egyre kisebb grafokat epeiteni, a csucsoknak egy-egy reszahlmaza egyre kisebb halmazon. Tehat felepitjuk valahogyan a  $G_{0}, G_{2}, \dots$ grafokat ugy hogy $V_{0} \supset V_{1}\supset V_{2}\supset \dots\supset V_{l}$ ahol $\lvert V_{l} \approx \sqrt{ \lvert V_{0} \rvert } \rvert$, ahol $V_{i}$ a $G_{i}$ graf csucshalmaza.

$G_{1}' = (V_{0}, E_{1}')$ ahol $E_{1}'$ az autopalya elek halmaza.
Azt mondjuk, hogy $uv$ autopalya el ha
1. Letezik $s, t \in V_{0}$ ugy hogy a legrovidebb $s \to t$ ut atmegyen az $uv$ elen
2. $v$ nincs kozel $s$-hez
3. $u$ nincs kozel $t$-hez

*Megj.:* Figyeljuk meg, hogy ha csak 1.-et tennenk fel akkor majdnem minden el autopalya el lenne, a zsakutcakon kivul.

*Megj.:* Az, hogy $v$ es $s$ kozel vannak az itt ugy van definialva, hogy elinditunk egy Dijkstra algoritmust $s$-bol es ha $k$ lepes utan (ahol $k$ egy elore rogzitett konstans) elerjuk $v$-t akkor kozel vannak, kulonben nem.


$V_{1}$-et a kovetkezo keppen kapjuk:
1. Kitoroljuk az izolalt csucsokat es zsakutcak vegeit.
2. Osszehuzzuk a $2$ foku csucsokat, amit azt jelenti, hogy ha van $u$ csucs amibol ket ut megy $c_{1}$ es $c_{2}$ sulyokkal akkor ahelyett egy $c_{1} + c_{2}$ sulyo utat allitunk elo es kitoroljuk $u$-t.

Igy megkapjuk a $G_{1}$ grafot. Ezt az eljarast iteralva megkapjuk az algoritmust.

Igy megkaptuk a $G_{1}, G_{2}, \dots$ grafokat amelyek egyre kevesebb csucsokat tartalmznak. Ha $G_{i}$-ben elerunk egy autopalya csocsot akkor $G_{i+1}$-be fellepunk $0$ koltseggel es ott is folytatjuk a keresest.


### Tranzit csucsok
 Legyen $T \subseteq V$ a tranzit csucsok halmaza. Minden $v$-hez $A(v)$ hozzarendelt tranzit csucsok halmaza.

*Kell:* Minden $s, t$-re nem nem *lokalis* csucsokra, letezik $a \in A(s)$ es $b \in A(t)$ ugy, hogy a legrovidebb $s \to t$ ut atmegy ezeken.

Peldaul lehet $T = \bigcup A(v)$

Eltaroljuk $\forall u, v \in T$ $d(u,v)$ es $\forall v \in V$ $A(v)$ elemeit es $d(v, a)$


### Osszehuzasi hierarchiak
Góbor Dániel 2013 Bsc. szakdolgozat, 2015 Msc. szakdolgozat

*Elofeldolgozas:* Adott $v$ csucsot szeretnenk osszehuzni. $\forall u, w$ csucsra, melyek szomszedai $v$-nek, megnezzuk a legrodivedebb $u \to w$ ut hosszatt, amely nem hasznalja $v$-t, legyen ez $d_{G - v}(u, w)$.

*$v$ osszehuzasa:*
- Ha $d_{G-v} \leq c(uv) + c(vw)$ akkor nyugodtan kitorolhetjuk $v$-t.
- Kulonben hozzunk letre egy uj $uw$ elt, aminek a sulya legyen $c(uw) = c(uv) + c(vu)$.

```
FOR i = 1..n
	choose vertex v_i and collapse it
```

$\tilde{G} = (V, \tilde{E})$ $\forall$ regi es behuzott el
$G_{\uparrow} = (V, E_{\uparrow})$ ahol $v_{i}v_{j} \in E_{\uparrow}$ ha $i < j$ es $v_{i}v_{j} \in \tilde{E}$
$G_{\downarrow} = (V, E_{\downarrow})$ ahol $v_{i}v_{j} \in E_{\downarrow}$ ha $i > j$ es $v_{i}v_{j} \in \tilde{E}$

Igy az eredeti grafot szetszedtuk ket aciklikus grafra.

Legyen $P$ $\tilde{G}$-ben egy olyan legrovidebb $s \to t$ ut, ami a legrovidebb keresett elbol all.

*All1.:* $P$-ben nem lehet olyan hogy hatra utan elore el jon.

*pelda:* Nem lehet olyan hogy $v_{8}$-bol elmegyunk $v_{6}$-ba es utana $v_{9}$-be.

*All2.:* $P$-ben legfeljebb egyszer johet elore utan hatra.

*pelda:* Legfeljebb egyszer lehet olyan hogy $v_{6}$-bol elmegyunk $v_{9}$-ba es utana $v_{8}$-be.

*All3.:*
$$
d(s,t) = \min_{u}(d_{\uparrow}(s, u) + d_{\downarrow}(u, t))
$$
$\forall u$ duplan vegl. kesz, $d_{\min}$

Leallhatunk, ha vegl. $w$: $d_{\uparrow}(s, w) > d_{\min}$




