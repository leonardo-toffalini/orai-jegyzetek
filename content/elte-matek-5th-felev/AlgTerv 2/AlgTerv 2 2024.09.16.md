# **SzóFa**
$\lvert \Sigma \rvert = d, \quad S \subseteq \Sigma ^{*}$

minden csucsnak van legfeljebb $d$ ele amik egyesevel az ABC betuit jelolik
a szófa minden csucsahoz hozzatartozik egy szo, csak elkezdjuk olvasni az elek menten a betuket a gyokertol kezdve
minden csucshoz tartozik egy kulonleges *spec* pointer ami jeloli hogy a csucshoz tartozo szo benne van-e a szotartban vagy sem (ha nincs benne akkor *nil* pointert olvasunk)

# **Lempel-Ziv-Welch** (LZW)
fix $\Sigma$ ABC, szo-kod fix hosszal (pl 12 bit)
tehat mindegyik szonak lesz egy kodja ami 12 bites lesz

[wikipedia cikk LZW](https://hu.wikipedia.org/wiki/LZW#K%C3%B3dol%C3%A1s)


# Melysegi kereses
Elvegzunk egy melysegi keresest egy iranyitatlan grafon, ebool kapunk egy iranyitott erdot
milyen elek lehetnek az eredeti grafban?
- elore el: az iranyitott erdoben egy csucsbol az egyik leszarmazottjaba mutato el
- vissza el: az iranyitott erdoben egy csucsbol az egyik osebe mutato el
- kereszt el: az iranyitott erdoben jobbrol balra mutato el (komponenseken keresztul, ksebobbi komponensbol korabbiba)

**Tetel:** $xy \in E$ akkor
- vissza el, ha $MSZ(y) < MSZ(x)$ es $BSZ(y) > BSZ(x)$
- fa vagy elore el, ha $MSZ(y) > MSZ(x)$ es $BSZ(y) < BSZ(x)$
	ezen ket tipus kozul a fa el, ha $p(y) = x$ azaz $y$ szuloje az $x$

- kereszt el, ha $MSZ(y) < MSZ(x)$ es $BSZ(y) < BSZ(x)$

**All.:** Egy $G$ graf aciklikus $\iff$ nem letezik benne viszzael
*Biz.:* $\implies$ trivi.
$\impliedby$ a melysegi kereses utan a befejezesi szam egy forditott topologikus sorrendet ad

**Reszfa-lemma:**
$x \in V$
$S_{x} = \{ y \in V : \exists x \to y \text{ ut, melnyek } \forall v \text{ csucsara } MSZ(v) \geq MSZ(x) \}$
$T_{x} = \{ y \in V : y \text{ leszarmazottja az } x \text{-nek a melysegi erdoben} \}$

A lemma azt mondja ki, hogy $S_{x} = T_{x}$

*Biz.:*
$T_{x} \subseteq S_{x}$ trivialis, mert a faelek menten csak nohet a melysegi szam
$S_{x} \subseteq T_{x}$ inderekten feltesszuk, hogy $\exists y \in S_{x} \setminus T_{x}$
Ez azt jelenti, hogy letezik olyan $P$ ut mely $x$-bol $y$-ba vezet es $\forall w \in P: MSZ(w) \geq MSZ(x)$ 
legyen $v'$ az elso olyan csucs az uton amelyik nem eleme a $T_{x}$-nek, ilyen van mert $y \not\in T_{x}$
legyen $v$ a $v'$ szuloje a $P$ uton

$T_{x}$ beli csucsoknak a melysegi szama egy osszefuggo sorozatot alkot pl $\{ k, k+1, \dots, k+m \}$
$v'$ nincs benne ebben az osszefuggo sorozatban, es csak nagyobb lehet mert a szuloje $v$ benne van
ebbol kovetkezik, hogy $MSZ(v') > MSZ(v)$ amibol kovetzkezik, hogy $vv'$ fa, vagy elore el tehat $v' \in T_{x}$ ELLENTMONDAS

*Def.:* $G$ iranyitott graf $x \sim y$, ha $\exists x \to y$ es $y\to x$ ut
*All.:* Ez egy ekvivalencia relacio.

*Def.:* Ennek az ekvivalencia relacionak az osztalyait hivjuk eros komponenseknek.

**All.:** Legyen $K \subseteq V$ egy eros komponens  es vegyuk ennek ket csucsat $x, y \in K$. Ekkor:
1. $\exists x \to y$ ut melynek minden csucsa $K$-beli.
2. $\forall x \to y$ utnak minden cucsa $K$-beli.

Legyen $P$ az $x\to y$ ut es $v \in P$
indirekt tegyuk fel, hogy $v \not\in K$ 
Ekkor letezik $v$-bol $y$-ba ut es $y$-bol $x$-be ut ezert letezik $x$-bol $v$-be ut tehat $x \sim v$ $\implies v \in K$

*Def.:* Redukalt graf (jel.: $red(G)$) ugy kapjuk, hogy minden eros komponenst osszehuzunk egy csucsa. Tehat minden eros komponensnek lesz egy reprezentativ csucsa melynek azok a masik reprezentativ csucsok a szomszedai amelyik komponensbe megy el a jelen komponensbol.

**All.:** Tetszoleges $G$ iranyitott grafnak a redukaltja aciklikus.
*Biz.:* Ha van komponenseknek egy sorozata mely kort alkot akkor ezen kor menten minden komponens egy nagy komponenst alkot.

**Algoritmus:**
1. Csinalunk egy DFS-t a $G$ grafon, $B(i) = \{ v : BSZ(v) = i \}$
2. Eloallitjuk a $G'$ forditott grafot
3. Csinalunk egy DFS-t a $G'$ forditott grafon
FOR $i = n \dots 1$ ($-1$)
	IF $p(i) = 0$ THEN $MB_{G'}(i)$

**Tetel:** A 3. pont fenyoi az eros komponensek, tovabba a sorrendjuk megadja a $red(G)$-nek a topologikus sorrendjet
*Biz.:*
I.) Ha $K$ egy eros komponens, akkor a csucsai a 2. melysegi keresesnel egy fenyobe kerulnek
altalban igaz, hogy ha $K$ eros komponens, akkor minden melysegi kereses utan 1 fenyobe lesznek a csucsai

$v := K$-nak a legkisebb melysegi szamu csucsa
Azt allitom, hogy $K \subseteq S_{v}$ hiszen $v$-bol mindenkibe vezet egy ut a $K$-n belul, de ha $v$ a legkisebb melysegi szamu akkor ennek az utnak minden myelsegi szama nagyobb
Reszfa lemme miatt $S_{v} = T_{v}$ tehat $K \subseteq T_{v}$ 

II.) Legyen $v$ a 3.) pontu melysegi keresesben egy gyoker.
Ekkor a $G'$ forditott grafban $T'_{v} \subseteq T_{v}$
Tehat aki az elso keresesben a $v$ leszarmazottja az a masodik keresesben is a $v$ leszarmazottja.

Ebbol az kovetkezik, hogy $\forall y \in T'_{v}: \quad v \sim y$

Valasszunk ki egy tetszoleges $x \in T'_{v}$ csucsot, ekkor $\exists P \subseteq T'_{v}$ ut $G$-ben mely $x$-bol $v$-be megy az eredeti grafban
a) $\forall w \in P: BSZ(w) \leq BSZ(v)$ (az eredeti grafban az elso keresesnel)

Legyen $x'$ az a csucs a $P$ ut menten melynek a melysegi szama minimalis
Mivel $x'$ a legkisebb a melysegi szama a $P$-ben ezert $P$ menten az $x' \to x$ uton mindegyik csucs eleme $S_{x'}$-nek, ezert $v \in S_{x'}$
A reszfa lemma miatt $S_{x'} = T_{x'}$ ezert a $v$ leszarmazottja $x'$ -nek ezert $BSZ(x') \geq BSZ(v)$

Tehat $x' = v$ mert csak ekkor lehet $BSZ(x') = BSZ(v)$

Meg annyit kell belatnunk, hogy $P \subseteq T_{v}$ 
$y \in P$
$MSZ(y) \geq MSZ(v) = MSZ(x')$
$BSZ(y) \leq BSZ(v)$
$\implies v$  ose $y$-nak





