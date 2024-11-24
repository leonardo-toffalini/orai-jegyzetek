*Def.:* RAM-gep futasanak logaritmikus koltsege $U \in \mathbb{N}$
Minden lefutott program sorra:
$$1 + \sum_{\text{szamok a programsorab}}\lceil \log_{2}(\text{szam} + 1) \rceil $$
*peldaul:*
```python
X[4] = X[4] + 1
```

$$1 + 2 \lceil \log_{2}(X[4] + 1) \rceil + 2 \lceil \log_{2}(5) \rceil + 1$$
**Q.:** Miert jo nekunk ez a definicio?
**A.:** Mert igy mar osszemerheto lesz a RAM-gep lepesszama a Turing-gep lepesszamaval.

**Tetel:** Minden RAM-gephez van olyan $T$ Turing-gep, ami ugyanazt szamolja ki, tehat ugyanazokra az inputokra all meg es uganaz a kimenet.
Ha a RAM-gepnek egy konkret inputon a futasanak a logaritmikus koltesege $U$, akkor a $T$ Turing-gep $O(U^{2})$ idoben fut erre az inputra.

*Biz.:* (vazlatosan)
Fo nehezseg egy RAM-gepnel az adattar irasa es olvasasa.
Adattar $1$ szalagon valo szimulalasa.
Ez a szalag kezdetben ures. 
Ha a RAM-gep irna `X[i] := j` akkor a szalagra irja a kovetkezot `*i**j` ahol `i` es `j` binarisan van irva.
Ezen a szalagon sosme fogunk torolni

Kiolvasas (`i` indexet):
Jobbrol -> balra olvas es ha `**` utan az `i` all, akkor a tole jobbra levo szamot kiolvassuk
Koltsege a kiolvassasnak $\leq O(\text{eddigi logaritmikus koltseg})$  

Tegyuk fel, hogy minden programsorhoz gyartunk egy Turing-gepet az adattarszalag segitsegevel. Ezeket osszeillesztjuk.
Egy lepes koltsege $\leq O(\text{eddigi logaritmikus koltseg})$

Osszesen a futasido: $O(U^{2})$

**Plinomialis Church-Turing tezis**
Minden ertelmes szamitasi modell ugyanazt engedi kiszamitani es a szamitasi koltsegek polinomialisan viszonyulnak egymashoz.

*Megj.:* Ez egy hit, semmi konkret.

# Kiszamithatosag elmelet
*Def.:* A $T$ Turing-gep akkor ismeri fel az $L \subseteq \Sigma_{0}^{*}$ nyelvet, ha:
- $T$ minden $w \in \Sigma_{0}^{*}$ szora megall.
- Ha $w \in L$ akkor elfogado allapotban (`1`) all meg.
- Ha $w \not\in L$ akkor elutasito allapotban (`0`) all meg.

*Def.:* $L$ nyelv indikator fuggvenye a kovetkezo keppen definialt:
$$
\chi_{L}(w) = \begin{cases}
1 & w \in L \\
0 & w \not\in L
\end{cases}
$$

*Def.:* $f : \Sigma_{0}^{*} \to \Sigma_{0}^{*}$ fuggveny rekurziv, ha letezik olyan $T$ Turing-gep amire minden $w \in \Sigma_{0}^{*}$ inputon megall es a kimenete $f(w)$

*Def.:* $L$ nyelv rekurziv, ha $\chi_{L}$ rekurziv fuggveny.

**Allitas:** Minden veges nyelv rekurziv.
*Biz.:* Legyen $n$ a leghosszabb $w \in L$ szo. Keszitsunk $n$ melysegu binaris fat (egy szofat). Ekkor minden csucs egy szonak felel meg.
Egy csucs elfogado allapot $\iff$ a neki megfelelo $w$ szora $w \in L$
Turing gep sorban beolvas, lep
Mikozben a Turing-gep olvassa az inputot mi lepdelunk a fan a betuk menten a kovetkezo szoba.

**Allitas:** Majdnen minden nyelv nem rekurziv.
*Biz.:*
$$
\lvert \text{rekurziv nyelvek} \rvert \leq \lvert \text{Turing-gepek} \rvert = \lvert \mathbb{N} \rvert 
$$

Nyelvek szamossaga: $\mathcal{P}(\Sigma_{0}^{*}) = \mathcal{P}(\mathbb{N}) = \lvert \mathbb{R} \rvert$

*Def.:* $L \subseteq \Sigma_{0}^{*}$ rekurziv felsorolhato, ha $L = \emptyset$ vagy $\exists f$ rekurziv fuggveny, melyre $L = \operatorname{Im}(f)$.

**Tetel:** $L$ rekurzivan felsorolhato $\iff$ $\exists T$ Turing-gep, mely pontosan az $L$ szavain all meg.

*Biz.:*
$\implies$:
Vegyunk egy Turing-gepet, mely felsorolja az $L$ elemet.
Ha a felsorolasban megjelenik az input akkor megall.
Ha $L = \emptyset$ akkor sosa all meg.

$\impliedby$:
Ha $L = \emptyset$ akkor trivialis es nem foglalkozunk tobbet vele.
Ha $L \neq \emptyset$ akkor legyen $(w_{i})$ egy felsorolasa a $\Sigma_{0}^{*}$ szavainak

Legyen $T$ olyan Turing-gep, mely ponotsan $L$ szavain all meg.
Futtatjuk a $T$ Turing-gepet a $w_{i - \lfloor \sqrt{ i } \rfloor^{2}}$ inputon $i$ ideig.
- Ha $T$ ennyi ido alat megall, akkor az output $w_{i - \lfloor \sqrt{ i } \rfloor^{2}}$
- Ha $T$ ennyi ido alatt nem all meg, akkor az output $a$.

Ez a Turing-gep kiszamolja az $f(i)$ fuggvenyt. Vilagos, hogy $\operatorname{Im}(f) \subseteq L$

Tehat igy minden $j = i - \lfloor \sqrt{ i } \rfloor^{2}$ -re:
$w_{j}$-re futtatjuk $T$-t:
$(j^{2} + j)$-szer
$(j^{2} + 2j)$-szer
$(j^{2} + 3j)$-szer
$\vdots$
Tetszolegesen hosszan 
$w_{j} \in L \implies t$ ido $T$ $t$ ido alatt megall
$f((j + t)^{2} + j) = w_{j}$ 

**Allitas:** Majdnem minden nyelv nem rekurzivan felsorolhato.
*Biz.:* Ugyanaz mint a hasonlo allitas csak rekurziv nyelvre.

**Allitas:** $A, B$ rekurziv $\implies$ $A \cup B, \; A \cap B, \; A \setminus B$ rekurziv.
*Biz.:* Figyeljuk az indikator fugvenyeit a fenti dolgoknak es trivialisan kijon.

**Allitas:** $A, B$ rekurzivan felsorolhato $\implies$ $A \cup B, \; A \cap B$ rekurzivan felsorolhato.
*Biz.:* $T_{A}$ es $T_{B}$ Turing-gepek melyek pont $A$ es $B$ nyevet ismerik fel.
$T_{A \cup B}$ megall, ha $T_{A}$ vagy $T_{B}$ megall.
$T_{A \cap B}$ megall, ha $T_{A}$ es $T_{B}$ megall

*Megj.:* Vigyazni kell mert $A \setminus B$ nem mindig rekurziv felsorolhato ha $A$ es $B$ rekurziv felsorolhato.

*Def.:* Megallasi problema (Halting-problem)
$(P, W) \in L \iff P$ programu Turing-gep megall a $w$ inputon.

**Allitas:** Nem rekurziv nyelv a fenti.




