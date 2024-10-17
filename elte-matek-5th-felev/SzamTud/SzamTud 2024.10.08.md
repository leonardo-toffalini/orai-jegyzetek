# Tar es ido

*Def.:* Legyen $T$ egy Turing-gep, amely minden inputon megall. Ekkor
$$
\text{time}_{T}(n) = \max_{\lvert W \rvert \leq n}\{ T \text{ futasa } W\text{-n} \}
$$
$$
\text{space}_{T}(n) = \max_{\lvert W \rvert \leq n}\{ T \text{ tar felhasznalasa a } W\text{-n} \}
$$

*Def.:* 
$$
\text{DTIME}(f(n)) = \{ L : L \text{ nyelv, } \exists T \text{ Turing-gep, mely feismeri } L\text{-et es time}_{T}(n)\leq f(n)  \}
$$
ahol $f : \mathbb{N} \to \mathbb{N}$
$$
\text{DSPACE}(f(n)) = \{ L : L \text{ nyelv, } \exists T \text{ Turing-gep, mely feismeri } L\text{-et es space}_{T}(n)\leq f(n)  \}
$$

*Def.:*
$$
\text{P} = \bigcup_{i=1}^{\infty} \text{DTIME}(n^{i})
$$
$$
\text{PSPACE} = \bigcup_{i=1}^{\infty}\text{DSPACE}(n^{i})
$$

Miert szeretjuk a polinomialis korlatot?
- Mert robusztus.
- Praktikus


## Polinomialis ideju algoritmusok
**Euklideszi algoritmus**
*input:* $a,b \in \mathbb{N}$
*output:* legnagyobb kozos osztoja $a$-nak es $b$-nek: $(a, b) \in \mathbb{N}$

input merete: $\log a + \log b$ mert binarisan reprezentalom
futasi ido: $2 \cdot \log (\max\{ a, b \})$

**Hatvanyozas**
*input:* $a, b, m \in \mathbb{N}$
*output:* $a^{b} \mod m$

**All.:** Ha $T$ egy $k$ szalagos Turing-gep, akkor $k \cdot \text{time}_{T}(n) \geq \text{space}_{T}(n)$ teljesul.

**Tetel:** 
$$
\text{DTIME}(f(n)) \subseteq \bigcup_{i=1}^{\infty}\text{DSPACE}(k \cdot f(n))
$$
*Biz.:* $L \in \text{DTIME}(f(n)) \implies \exists T$ ami felismeri

*Def.:* Egy $T$ Turing-gep konfiguracioja a kovetkezo:
$$
(g, p_{1}, \dots, p_{k}, h_{1}, \dots, h_{k})
$$
Ahol $g \in \Gamma$ a Turing-gep jelenlegi allapota, $p_{i} \in \mathbb{N}$ a fejek pozicioja, $h_{i} \in \Sigma_{0}^{*}$ azon mezok tartalma, ahol a fejek jartak mar, illetve az input.

**All.:** Ha egy $T$ Turing-gep leall az osszes inputra $L$-ben, akkor minden konfiguraciot legfeljebb egyszer vesz fel.
*Biz.:* Tegyuk fel, hogy felvesz egy konfiguraciot ketszer. Ekkor egy vegtelen ciklucba kerul es nem all le. Ellentmondas!

**Tetel:**
$$
\text{DSPACE}(f(n)) \subseteq \bigcup_{c=1}^{\infty} \text{DTIME}(c^{f(n)})
$$
*Biz.:* Legyen a $T$ Turing-gep olyan, hogy minden inputra megall es felismeri az $L \in \text{DSPACE}(f(n))$ nyelvet es ekozben legfeljebb $f(n)$ tarat hasznal. Ekkor legfeljebb $c \cdot f(n)^{k} \cdot \lvert \Sigma \rvert^{f(n)}$ konfiguracio lehetseges, ha csak $f(n)$ tarat hasznalhat.

**Tetel:** Legyen $f: \mathbb{N} \to \mathbb{N}$ rekurziv fuggveny, melyre $f(n) \geq n$. Ekkor $\exists L$ nyelv ami rekurziv es $L \not\in \text{DTIME}(f(N))$.
*Biz.:* Legyen $T$ egy $2$-szalagos univerzalis Turing-gep. Legyen tovabba,
$$
L = \{ w : T \text{ Turing-gep leall a } (w, w) \text{ inputra legfeljebb } f(\lvert w \rvert )^{3} \text{ lepesben}   \}
$$
Ez az $L$ nyelv pont jo lesz nekunk. Be kell eloszor latnunk, hogy $L$ rekurziv. Egy masik Turing-geppel szamoljuk ki a $f(\lvert w \rvert)^{3}$ erteket es ennyi idejig futtassuk a $T$ univerzalis Turing-gepunk a $(w, w)$ inputon. Ha leall ennyi ido alatt, akkor $w \in L$ kulonban $w \not\in L$.

Mostmar csak be kell latni, hogy $L \not\in \text{DTIME}(f(n))$. Tegyuk fel, hogy $L \in \text{DTIME}(f(n))$. Ekkor $\exists R$ Turing-gep mely felismeri $L$-et $f(n)$ lepesben. Ezt az $R$ Turing-gepet tudjuk negyzetes lassulas mellett szimulalni egy egy-szalagos Turing-geppel, legyen ez az $S$ Turing-gep. Tehat az $S$ Turing-gep felismeri $L$-et $c\cdot f(\lvert w \rvert)^{2}$ lepesben, tehat kelloen hosszi unputra legfeljebb $f(\lvert w \rvert)^{3}$ lepesben ismeri fel.
Rendeljunk $S$-hez egy egy-szalagos $Q$ Turing-gepet, amely vegtelen ciklusba kerul ha $S$ elfogad es megall ha $S$ elutasit. Tegyuk fel, hogy $p$ a $Q$ programja, ha felirjuk a $T$ $2$-szalagos univerzalis Turing-gepen.
Ha $p \in L$ akkor $T$ leall a $(p, p)$ inputon $f(\lvert w \rvert)^{3}$ lepesben, tehat $Q$ leall a $p$ inputon, tehat $S$ elutasitotta $p$-t mert nem volt benne $L$-ben. Ellentmondas, mert azt allitottuk, hogy $p \in L \implies p \not\in L$.
Hasonlokeppen ha $p \not\in L \implies p \in L$.

**Tetel (linearis gyorsitasi tetel):** Legyen $f: \mathbb{N} \to \mathbb{N}$ fuggveny, melyre $f(n) \geq n$. Tegyuk fel, hogy a $T$ Turing-gep felismeri az $L$ nyelvet $f(n)$ idoben, azaz $\forall w \in \Sigma_{0}^{*}$-ra $T$ leall legfeljebb $f(\lvert w \rvert)$ lepesben es kiszamolja $L$ karakterisztikus fuggvenyet $w$-ben.
Ekkor $\forall c > 0: \exists \hat{T}$ Turing-gep, ami ugyanezen $L$ nyelvet ismeri fel es $\text{time}_{\hat{T}}(n)\leq c f(n) + 2n$.

*Biz.:* Otlet: multithreading.

## Nemdeterminisztikus Turing-gepek
Eddig vegig determinisztikus Turing-gepekrol beszultunk, ezeknek a konfiguraciot lehet abrazolni egy iranyitott grafon. Egy determinisztikus Turing-gepnek a konfiguracios grafja vagy egy veges hosszu ut, vagy egy vegtelen hosszu ut vagy tartalmaz egy kort.
Egy nemdeterminisztikus Turing-gepnek a konfiguracios grafja olyan, hogy egy csucsbol nem csak egy masik csucsba vezet ut, hanem tobb masikba is vezethet. Figyelem itt az atmenet nem veletlen, nem eloszlas szerint jarjuk be a grafot.





