Egy Texasi kiskocsmaban, Billie-nek a konyvelonek van egy gepe amin vannak billentyuk (0, ..., 9, space) amin le kell konyvelnie, hogy melyik ugyfel mennyit fizetett.

Kitor egy lovoldozes a kiskocsmaban es kilovik Billienek az egyik billentyujet. Na de most hogyan konyveljen Billie.
Megolda: Egy kisebb szamrendszerben konyvel es a kimarado billentyu jatsza majd a szerepet a kilott billentyunek.

Folytatodik a sztori es sorba lovik ki a tobbi billentyut is. Egeszen addig ameddig csak a 0, 1, 2 billentyuk maradnak.

Kilovik a 2-es billentyut is. Mostmar csak 0 es 1-es billentyuk vannak.

- Leir annyi 1-est amennyit fizettek es a 0-as lesz a valaszto karakter.
- mapping: {0: 00, 1: 11, 2: 01} es igy csinalja ugyanazt amit csinalt 3 szamjeggyel

Kilovik az 1-es billentyut is :'(
- kodolja el az egyik elozo kodolasban es irjon le annyi 0-ast amekkora az a szam volt

Tegyuk fel, hogy a fizetesek: $\alpha_{1}, \alpha_{2}, \dots$ ezekbol letrehozza a $\prod p_{i}^{\alpha_{i}}$ szamot es ezt kodolja

## Kovetkezo feladat
$x \in \{ 0, 1 \}^{n}$
$\sum x_{i} = k$
tehat van egy $n$ bites szamunk ahol $k$ darab $1$-es van es ezt szeretnenk lekodolni

Elso eset: $n, k$ fixek/rogzitettek, ekkor eleg $\log$${n}\choose{k}$ bit mivel $n \choose k$ helyen lehet a $k$ darab $1$-es es ezeket kell csak kodolni

Masodik eset: nem ismerjuk egyiket sem
Ekkor le kell eloszor kodolni az $n$-et utana le kell kodolnunk a $k$-t utana $n \choose k$ -t 
igy ugy fog kinezni, hogy $n$ kodolva 'vesszo' $k$ kodolva 'vesszo' utolso tag kodolva
a vesszoket el lehet hagyni ha a fenti mappinget hasznaljuk (az utolso tagot nem kell duplazni, mert ott mar nincsen vesszo)
igy fog kijonni a $2\log n$, $2\log k$, $\log (n alatt k)$

ugyesebb megoldas:
elso $2\log \log n$ bit kodolja az $n$ kodolosanak a hosszat
$01$
$2 \log \log k$ bit kodolja a $k$ kodolajanak a hosszat
$01$
$n + k + n \text{ alatt } k$

osszesen: $\log (n \text{ alatt } k) + \log n + \log k + 4 \log \log n + 4$

legyen $p = \frac{k}{n}$ ($0 < p < 1$)
ebben az esetben a fenti ('osszesen') $< (-p \log p - (1 - p)\log (1-p)) \cdot n + O(\log n)$


Legyen $\underline{p} = (p_{1}, p_{2}, \dots, p_{m}) \quad 0 < p_{i} \leq 1 \quad \sum p_{i} = 1$

***Def.:***  A kovetkezo mennyiseget a $p$ eloszlas *entropiajanak* nevezzuk: $H(\underline{p}) := \sum -p_{i}\log p_{i}$ 

*Megj.:* Valamilyen ertelemben ha egy bitosorozatnak kicsi az entropiaja akkor azt jol lehet kodolni.

***All.:*** Ha $n$ rogzitett, akkor a $H(\underline{p})$ a legnagyobb az $\left( \frac{1}{m}, \dots, \frac{1}{m} \right)$ eloszlason es itt $H(\underline{p}) = \log m$

Tegyuk fol, hogy van egy $n$ alapu ABC, tehat $\lvert \Sigma \rvert = n, \quad \forall h \in \Sigma \to p_{h}$ relativ gykorlisag

***Tetel:*** $x \in \Sigma ^{n}$ elkodolhato $\leq \frac{H(\underline{p})}{\log m} \cdot n + O\left( \frac{m \log n}{\log m} \right)$ bittel.

***Informacioelmeleti also korlat***
$N$ kulonbozo dolog elkodolasakor (injektiven) letezik egy olyan kod, ami $\geq \log N - 1$ bit
Mivel $\sum_{i=0}^{n}2^{i} = 2^{n+1}-1$


# Grafok kodolasa
1. Tegyuk fel, hogy $n$ ismert, tovabba, hogy egyszeru es iranyitatlan a graf. Ekkor $n \choose 2$ bittel el lehet kodolni (az adjecencia matrix felso haromszoga).
2. Tegyuk fel, hogy $m \ll n$ ebbol nagyjabol az kovetkezik, hogy $m \cdot \log$$n \choose 2$
	2.a Ha $n$ ismert, akkor a fentit ki tudjuk szamolni es igy el tudjuk kodolni $m$ darab $\log {n \choose 2}$ kodolossal ami megmondja, hogy az $i$.-edik el melyik ket csucsot koti ossze.
	2.b Ha $n$ nem ismert, akkor $k := \log {n \choose 2}$ es $2\log k + 2$ bittel kodoljuk a $k$-t es utana a 2.a szerint kodolunk. Igy $m \cdot k + 2 \log k + 2$ bit eleg.


# Huffman
A Huffman kod egy betukod, azaz az ABC minden elemehez hozzarendelek invjektiven egy kodot.
$c: \Sigma \to \{ 0, 1 \}^{*}$ inkektiv

Most azt szeretnenk hogy a gyakorli betuknek legyen rovidebb a kodja.

***Def.:*** $c$ kod prefix mentes, ha barhogy veszek ket kukonbozo betut $\forall a \neq b \in \Sigma$ akkor $c(a)$ nem prefixe $c(b)$-nek.

Szotar: gyokeres binaris fa es helyenkent vannak levelei. A levelekhez hozzarendelem az ABC elemeit.

Huffman kod:
$\Sigma = \{ a_{1}, a_{2}, \dots, a_{m} \}$, $a_{i}$ betu gyakorisaga $p_{i}$ tehat $r_{i} = p_{i} \cdot n$ darab van $a_{i}$-bol a szovegben

Kodolo algoritmus:
Letrehozza az $m$ darab levelet egy faban es alulrol folfele csinalunk fat.
Minden $a_{i}$ level melle irjuk, hogy mennyi van belole, $r_{i}$
Menet kozben a gyokereken tarolunk prios szamokat.
$\forall$gyokerre $\geq \max(\alpha, \beta)$
az $\alpha$ es a $\beta$ gyokereket egy kozos uj gyoker ala hozzuk es az uj gyoker melle irjuk az $\alpha + \beta$ piros szamot

***Tetel:*** A Huffman kod hossza minimalis a prefixmentes betukodok kozott


