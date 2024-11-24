info
Grolmusz Vince
gelmusz.pitgroup.org

# Szamitasi modellek
"megmondom hogy milyen lepeseket lehet hasznalni ha ki akarok szamolni valamit"

# Algoritmusok
"mar meg van a modellem es valamit ki akarok szamolni akkor erre lepesek sorozatat csinalom ebben a modellben es ezekkel a lepesekkel kiszamolom"

# Bonyolultsagelmelet
"van egy algoritmus na de vajon az javithato-e? lehet-e egy ugyesebb algoritmust csinalni?"


peldak:
baratom kitalal egy $32$ bites szamot amit nekem ki kell talalnom minimalis szamu kerdesbol
$x \in \{ 0, 1 \}^{32}$

Algoritmus I:
egyessevel megkerdezem az osszes szamot
koltseg: $2^{32}$

Algoritmus II:
bitenkent lekerdezgetem
koltseg: $32$

Kerdes: Lehet-e kevesebb mint $32$ lepesbol kitalalni?

Tegyuk fel hogy $31$ kerdesol ki tudom talalni.
tehat egy $31$ bites szam kodolja az $x$ erteket
ezekbol a $31$ bites szamokbol csak $2^{31}$ van de az $x$ $2^{32}$ kulombozo szam lehet, tehat lesznek olyan szamok amik nincsenek kodolva

# A szamitogep matematikai definicioja (Turing gep)
*mese:* van par szallag es mindegyik szallaghoz tartozik egy iro-olvaso fej melyeknek van egy kozponti vezerlo programja
mindegyik fej a kovetkezo lepeseket csinalja a kovetkezo sorrendben minden lepesnel
1. atirja az aktualis erteket
2. egyet lep jobbra vagy barlra vagy egyhelyben marad

*Definicio:* A $T$ Turing-gep egy $(k, \Sigma, \Gamma, \alpha, \beta, \gamma)$ hatos, ahol
- $k\in \mathbb{N}$ a szallogok szamat jeloli
- $\Sigma, \Gamma$ veges halmazok, $\Sigma$ neve az ABC, uresjel: $* \in \Sigma$, $\lvert \Sigma \rvert \geq 3$. $\Gamma$ neve az allapothalmaz, START, STOP $\in \Gamma$ 
- $\alpha : \Sigma ^{k} \times \Gamma \to \Gamma$
- $\beta : \Sigma ^{k} \times \Gamma \to \Sigma ^{k}$
- $\gamma: \Sigma ^{k} \times \Gamma \to \{ -1, 0, 1 \}$

Az $\alpha$ az uj allapotot adja meg.
A $\beta$ a szallagra irando jelet adja meg.
A $\gamma$ megadja, hogy hova mozogjon az iro-olvaso fej. `mapping = {-1: "left", 0: "put", 1: "right"}`

A szalagok mindket iranyba vegtelenek es minden pozicioba egy-egy betut lehet irni
Kezdetben a T a START allapotban van
Kezdetben minden szalag minden pozicioja a $*$ jelet tartalmazza, kiveve az elso szalag, a fej alatt kezdodon jobbra folytatba tartalmazhat mas jeleket is.
*Inputnak* hivjuk az elso szalag tartalmat a fejtol az elso elofordulo $*$-ig, azaz az input $\in (\Sigma - \{ * \})^{*}$

*Megj.:* $\Sigma ^{*}$ jeloli a $\Sigma$-bol kepezheto osszes veges sorozat halmazat
$\Sigma_{0} := \Sigma - \{ * \}$  Így az input $\Sigma_{0}^{*}$ eleme

A STOP allapoton a kovetkezok igazak:
- $\forall h \in \Sigma ^{*}$
$$\alpha(h, \text{STOP}) = \text{STOP}$$
$$
\beta(h, \text{STOP}) = h
$$
$$
\gamma(h, \text{STOP}) = (0, 0, \dots, 0)
$$

A T Turing gep outputja az utolso szalag tartalma, ha a gep a STOP allapotba kerul.

A Turing gep egy lepese az egy olvaso lepesbolm az $\alpha, \beta, \gamma$ fuggvenyek kiszamitasabol a szalagon valo reszbol az allapot felulirasabol es a fejek lepesebol all. (more or less)

"Egy Turing-gepet szorostul borostul meg lehet adni ha a fenti $6$ erteket megadom."


*Definicio:* Ha $\Sigma$ egy ABC, $L \subseteq \Sigma ^{*}_{0}$-at nyelvnek nevezem.

*A problema definicioja (inkabb mese)*: Adott egy $x \in \Sigma ^{*}_{0}$ es egy $L \subseteq \Sigma ^{*}_{0}$ a kerdes az hogy $x \stackrel{?}{\in} L$.
*Def.:* Akkor mondom hogy a T Turing-gep felismer egy nyelvet, ha a nyelv elemeira $1$-et ad outputul, kulonben $0$-at.

*Pelda:* $2$ szalagos Turing-gep $T = (2, \Sigma, \Gamma, \alpha, \beta, \gamma)$ amely felismeri a $\Sigma = \{ 0, 1, * \}$ ABC felett az $L = \{ (01)^{l} : l = 1, 2, \dots \}$

T a kovetkezo egyszerusitesekkel fog elni:
- mindig csak az elso szalagrol fog olvasni
- mindig a masodikra ir
- mindig csak az elso feje mozog es mindig csak jobbra (amig meg nem all)

$$
\Gamma = \{ \text{START}, \text{STOP}, \text{N}, \text{NE} \}
$$
$$
\alpha(0, \text{START}) = \text{N}
$$
$$
\alpha(1, \text{START}) = \text{STOP}
$$
$$
\alpha(*, \text{START}) = \text{STOP}
$$
$$
\alpha(0, \text{N}) = \text{STOP}
$$
$$
\alpha(0, \text{NE}) = \text{N}
$$
$$
\alpha(1, \text{NE}) = \text{STOP}
$$
$$
\alpha(*, \text{NE}) = \text{STOP}
$$

$$
\beta(\cdot, \cdot) = 0
$$
$$
\beta(*, \text{NE}) = 1
$$

## Palindroma felismerse $2$-szalagos Turing-geppel
$$
\text{PALINDROMA} = \{ w: w = w^{-1} \quad w \in \Sigma ^{*} \}
$$
ahol $w = (a_{1}, a_{2}, \dots, a_{n})$ es $w^{-1} = (a_{n}, \dots, a_{2}, a_{1})$
legyen $w = \text{RACECAR}$

ket szalagom van
1. lemasolom az elso szalag tartalmat a masodik szalgra (tehat az inputot masolom)
2. az elso fejet visszaleptetem addig ameddig nem talal ures jelet
3. Most a ket fej a szo ket ellenkezo vegen van es elkezdem olvasni ellenkezo iranyokbol es ha minden jel megegyezik addig ameddig ujra nem talalok uresjelet mindket helyen akkor jol ment minden. Amikor eloszor talal nem megegyezo jeleket akkor megal es elutasit.

lepesszam: $n + O(1) + n + O(1) + n + O(1) = 3n + O(1)$ lepes

## Palindroma felismerese $1$-szalagos Turing-geppel
1. Elolvasom az input elso karakteret es az allapotban megjegyzem
2. Elmegyek addig jobbra ameddig nem talalok csillagot es visszalepek egyet hogy az utolso karakteren alljak
3. Osszehasonlitom az allapotban megjegyzet elso karaktert az utolso karakterrel
4. Ha egyeznek akkor visszafele megyek ugyanigy es addig csinalom ameddig el nem fogy a szo, mert mindig amikor beolvasok egy karaktert akkor atirom $*$-ra

lepesszam: $O(n^{2})$ lepes


***Def.:*** Azt mondjuk, ha egy $T = (k+1, \Sigma, \Gamma, \alpha, \beta, \gamma)$ Turing-gep es $p \in \Sigma ^{*}_{0}$ programmal szimulalja az $S = (k, \Sigma, \Gamma_{S}, \alpha_{S}, \beta_{S}, \gamma_{s})$ Turing-gepet, ha a T utolso szallagjara $p$-t irva a $T$ minden $w \in \Sigma ^{*}_{0}$ inputra megall $\iff$ ha $S$ megall $w$-n es megalloskor a T $k$. szalagjan ugyanaz van mint az S $k$. szalagjan.

***Def.:*** Azt mondom, hogy a $T = (k+1, \Sigma, \Gamma, \alpha, \beta, \gamma)$ Turing-gep $\Sigma$ folott $k+1$ -szalagos *univerzalis* Turing-gep, ha minden S $\Sigma$ ABC folotti $k$-szalagos Turing-gephez van egy olyan $p \in \Sigma ^{*}_{0}$ hogy T a $p$-vel szimulalja S-et.



