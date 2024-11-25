# Lassuk be hogy letezik univerzalis Turing-gep
**Tetel:** Mutassuk be, hogy $k \in \mathbb{N}$ es minden $\Sigma$ ABC felett letezik univerzalis $k+1$ szalagos, $\Sigma$ ABC feletti Turing-gep!

Eloszor $k+2$ szallagossal szimulalunk
Tehat van egy $T$ Turing-gepunk ami $k+2$ szalagos es egy $S$ Turing-gepunk ami $k$ szalagos.
Azt szeretnenk, hogy a $T$ gepnek az elso $k$ szalagja futas kozben megegyezzen az $S$ gep $k$ szalagjaval.

$S = (K, \Sigma, \Gamma_{S}, \alpha_{S}, \beta_{S}, \gamma_{S})$
$p:= CONCAT_{\forall g \in \Gamma_{S}, \forall h \in \Sigma ^{k}}(gh\alpha_{S}(g, h) \beta_{S}(g, h) \gamma_{S}(g, h))$

$p$ van irva a $T$ gep $k+1$ -edik sorara (ez a programja a $T$ Turing-gepnek)

A kovetkezoket a $\Sigma$ betuivel kodoljuk:
- $gh$
- $\alpha_{S}(g, h)$

A $\gamma_{S}(g, h)$ -t viszont $\{ -1, 0, 1 \}^{k}$ eleme.

Hogyan szimulalja a $T$ az $S$-et:
A $T$ es az $S$ -beli fejek helyzete megegyezik az elso $k$ szalagon

Mondjuk azt, hogy belattuk a $k+2$ -es esetet.

Hogyan csinalunk $k+2$ szalagosbol $k+1$ szalagosat?

A $k+1$ -edik szalagra irjuk fel az eredetinek $k+1$ -edik szalagja es a $k+2$ -edikg szalagjat egy $*$ -al elvalasztba.
Ha lenne ket fejunk az utolso szalagra akkor trivialis lenne az atallas, de nincs ket fejunk egy szalagra.

Ugyanigy leirjuk a kettot es minden mezot megduplazunk, minden mezo elott szerepel egy $0$ ha nem lenne a kovetkezon a fej es $1$ ha a kovetkezon lenne a fej.
Most egy fej fogja szimulalni ketto mukodeset ugy hogy balrol elindul a fej es elszalad jobbra odaig ameddig nem er el oda ahol lenne a masik fej. Ott elvegzi a teendojet es ujtana visszafut balra oda ahol az elobb volt. Es igy tovabb.

**Church tezis:** Minden ami kiszamolhato az kiszamolhato Turing-geppel is.
*Megj.:* A Church tezis nem egy matematikai tetel, hanem inkabb egy filozofiai hit, mert nincs definialva, hogy mit ertunk 'kiszamolhato' alatt.

**Tetel:** Minden $k$-szalagos $\Sigma$ ABC folotti $S$ Turing-gephez letezik $T$ $1$-szalagos $\Sigma$ ABC folotti Turing-gep, amely az $S$-et helyettesiti a kovetkezo ertelembe:
- adott inputra $S$ leall $\iff$ ugyanarra az inputra $T$ leall
- megallaskor az $S$ utolso szalagjan ugyanaz van, mint a $T$ szalagja
Sot, ha megallasig az $S$ gep $t$ lepest tett meg, akkor $T$ megallasig $O(t^{2})$ lepest tesz meg.
"Minden $k$-szalagos Turing-gepet lehet szimulalni $1$-szalagossal negyzetes lassulassal."

*Mese:* Folhullamoztatom azt az egy szalagomat ugy, hogy $k$ magas legyen minden emelet
```
   _   _   _
  | | | | | |
  | | | | | |
| | | | | |
|_| |_| |_|
```

*Biz.:* $2k$ magasra hullamoztatom fel a szallagomat es mindegyik lefele meno ag szimbolizalja a $k$ szalagot.
Mindegyik lefele meno ag cellai duplazva vannak es minden masodik cella egy seged cella, ami megmondja, hogy hol lenne a $k$-adik fej.

A hullamozott szalag elejere es vegere rakunk akadalyozo jelek, hogy itt az eleje es itt a vege.

$T$ tud szamolni $\mod 2k$ igy fogja tudni, hogy melyik szalagon jar.
Adott lefele meno agban megy ameddig nem talal olyan jelet, hogy az a jel feletti cellaban jar az $m$-edik fej.
Egy lepest $O(t)$ lepesben szimulal.

Problema: Hogyan adjuk meg az inputot ennek az $1$-szalagos Turing-gepnek?
A jo az lenne, ha minden agnak az elso cellajaba lennenek irva az input betui, de ez nem illik a Turing-gep definiciojahoz.
Definiio szerint az inputnak az elso szalagon kell szerepelni, a fej alatt kezdodve.
Fogjuk meg az inputot es a vegso szeleteket mozgassul el mindig $2k$-val igy a vegso szelet elso betuje mar jo helyen lesz.
Ha $n$ hosszu az input, akkor $O(n^{2} \dot{ (2k -1)})$ lepes lesz a mozgatas.

Sajnos ezt a szerencsetlenseget meg kell csinalnom visszafele amikor az outputot irom ki, ez is $O(n^{2})$ idoben megcsinalhato.

# A RAM-gep
*Mese:* Van egy program tar es egy adat tar. Az adat tarban $X[i] \in \mathbb{Z}, \quad i \in \mathbb{Z}$ szamok vannak.
Azert RAM gep mert Random Access Machine tehat az adat tar barmelyik indexu elemet $O(1)$ idoben vissza tudja adni.

*Definicio:* A RAM-gep az all egy adat tarbol es egy program tarbol. Az adat tar elemei a cellak $i \in \mathbb{Z}$ az $i$-edik cellat $X[i]$-vel jeloljuk. Minden $X[i]$-be egesz szam irhato be, kezdetben minden $i$-re $X[i] = 0$.
A program tarban parancs sorok vannak. A megengedett parancsor a kovetkezok:
- $X[i] := 0, 1$
- $X[i] = X[j]$
- $X[i] := X[i] \pm X[j]$
- IF $X[i] \leq 0$ THEN GOTO `<label>`
- $X[i] := X[X[j]]$
- $X[X[i]] := X[j]$

Az input hossza az $X[0]$-ba van irva, az input az $X[1], X[2], \dots, X[X[0]]$ -ba van irva.
Az output az adattar tartalma, ha a gep leall.

*pelda:* Element Distinctness (ED) feladat, ahol $\{ (a_{1}, a_{2}, \dots, a_{n}): n \in \mathbb{N}, \; \forall i\neq j, \; a_{i} \in \mathbb{Z} \}$ a nyelv amit szeretnenk hogy a RAM-gepunk dontson el. Tehat elfogad egy szot ha nincsen benne duplikatum es elutasit egy szot ha van benn duplikatum.

1. Naiv megkozelites: minden part osszehasonlitjuk $O(n^{2})$
2. Rendezunk es utana minden egymas mellettit osszehasonlitunk $O(n\log n) + O(n)$
```
for i = 1 to n
	X[a_i] = i

for i = 1 to n
	if X[a_i] != i
		return False
return True
```

**Tetel:** Minden $T$ Turing-gephez van olyan program a RAM-gepen, hogy minden inputra a RAM-gep megall $\iff$ a Turing-gep megall es megallaskor az output a ket gepen ugyanaz es ha a Turing-gep megallasaig $t$ lepest tett meg akkor a RAM-gep $O(t)$ lepest tesz meg, legfeljebb $O(\log t)$ bites szamokon.

*Biz.:* tegyuk fel, hogy $k = 1$ es $\Sigma = \{ 0=*, 1, 2 \}$
Ket program szegmens lesz: $P_{i}$ es $Q_{ij}$
- $P_{i}$: A $T$ Turing-gep az $i$ allapotban van es olvas
- $Q_{ij}$: A $T$ Turing-gep az $i$ allapotban van es a $j$-t olvasta

Minden pratlanadik cella adminisztaciora van fenntartva.
$X[1]$ A fej helye
$X[3]$ admin

```
P_i = [
	X[3] := X[X[1]]
	IF X[3] <= 0 THEN GO TO label(Q_i0)
	X[3] := X[3] - 1
	IF X[3] <= THEN GO TO label(Q_i1)
	X[3] := X[3] - 1
	IF X[3] <= THEN GO TO label(Q_i2)
]
```

```
Q_ij = [
	FOR _ IN beta(i, g)
		X[3] := 0
		X[3] := X[3] + 1
	
	X[X[1]] := X[3]
	
	# minden masodik helyen vagyunk
	X[1] := X[1] + gamma(i, g)
	X[1] := X[1] + gamma(i, g)

	X[3] := 0
	IF X[3] <= 0 THEN GOTO label(P_alpha(i, g))
]
```



