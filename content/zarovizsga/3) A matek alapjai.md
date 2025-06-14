### Naiv halmazelmelet
Ha $T$ valamilyen tulajdonsag, akkor van az a halmaz amely tartalmaz mindent melyre igaz $T$.
Mas szavakkal, ha $T$ egy tulajdonsag, akkor $\{ x : T(x) \}$ azon $x$-ek halmaza melyekre teljesul $T$.

Ezzel a felepitessel sok dolog mukodik, de vannak nagyon alapveto problemak vele, mint peldaul a Russel paradoxon.

### Russel paradoxon
Legyen $A = \{ x : x \not \in x \}$. Ekkor $A \in A \iff A \not \in A$.
Szavakban: Legyen $A$ azon halmazok halmaza melyek nem tartalmazzak magukat. Ekkor $A$ csak akkor eleme onmaganak, ha nem eleme onmaganak. Mert ha $A \in A$ akkor $A$ egy olyan halmaz ami tartalmazza magat, tehat $A \not \in A$. Viszont, ha $A \not \in A$, akkor $A$ egy olyan halmaz ami nem tartalmazza magat, tehat $A \in A$.

### Axiomatikus halmazelmet alapjai
0. Egyenlosegi axioma - Ha ket halmaznak ugyanazok az elemei, akkor egyenloek:
1. Letezesi axioma - Letezik halmaz. (Letezik a nullhazlmaz.)
2. Reszhalmaz axioma - Ha $A$ egy halmaz es $T(x)$ egy tulajdonsag, akkor $\{ x \in A : T(x) \}$ is egy halmaz.
3. Par axioma - Tetszoleges $x$ es $y$-hoz letezik olya halmaz, mely csak oket tartalmazza, ergo letezik a $\{ x, y \}$ halmaz.
4. Unio axioma - Ha $A_{i}$ halmazok, akkor $\cup A_{i}$ is halmaz.
5. Hatvany axioma - Ha $A$ halmaz, akkor $\mathcal{P}(A)$ is halmaz.
6. Vegtelen axioma - Van vegtelen halmaz. (Def.: Az $A$ halmaz vegtelen, ha van vegtelen reszhalmaza.)

### Kivalasztasi axioma
*Def.:* Az $f : I \to \cup A_{i}$ fuggvenyt kivalasztasi fuggvenynek nevezunk, ha $f(i) \in A_{i} \quad \forall i \in I$.
*Axioma:* A kivalasztasi axioma azt mondja, hogy ha $A_{i} \quad i \in I$ nemures halmazok, akkor letezik kivalasztasi fuggveny.
*Megj.:* A kivalasztasi axioma szavakban azt mondja, hogy tetszoleges halmazokbol tudunk *egyszerre* valasztani egy-egy elemet minden halmazbol.

### Szamossagok
*Def.:* $\lvert A \rvert = \lvert B \rvert$, ha letezik $A \to B$ bijekcio.
*Def.:* $\lvert A \rvert < \lvert B \rvert$, ha letezik $B \to A$ injekcio, de nem letezik $A \to B$ injekcio.

### Muveletek szamossagokon
$\lvert A \rvert = a$, $\lvert B \rvert = b$
Ha $A \cap B = \emptyset$, akkor $\lvert A \cup B \rvert = a + b$.
$\lvert A \times B \rvert = a \cdot b$.

### Cantor tetele
*Tetel:* Minden $A$ halmazra $\lvert A \rvert < \mathcal{P}(A)$. Azaz, minden halmaznak a szamossagi kisebb mint a hatvany halmazae.

### Ismert halmazok szamossaga
*Def.:* Azt mondjuk, hogy ha egy halmaz szamossaga egyenlo $\lvert  \mathbb{N} \rvert$-vel, akkor megszamolhato.
*Def.:* Azt mondjuk, hogy ha egy halmaz szamossaga egyenlo $\lvert  \mathbb{R} \rvert$-vel, akkor megszamlalhatatlan.
*Tetel:* (Cantor) $\lvert \mathbb{N} \rvert < \lvert \mathbb{R} \rvert$.
*Tetel:* $\lvert  \mathbb{Q} \rvert = \lvert \mathbb{N} \rvert$.
*Tetel:* $\lvert \mathbb{Q}^{*} \rvert = \lvert \mathbb{R} \rvert$.
*Tetel:* Folytonos $\mathbb{R} \to \mathbb{R}$ fuggvenyek szamossaga $\lvert \mathbb{R} \rvert$.
*Tetel:* Monoton $\mathbb{R} \to \mathbb{R}$ fuggvenyek szamossaga $\lvert \mathbb{R} \rvert$.
*Tetel:* $[0,1] \sim [0,1] \times [0,1] \sim \mathbb{R}$.

### A valos szamok felepitese
*Def.:* (Dedekind szelet) Legyen $A \subset \mathbb{Q}$ es $A \neq \emptyset$ es $A \neq \mathbb{Q}$ racionalis szamok nemures valodi reszhalmaza. Azt mondjuk, hogy az $A$ halmaz dedekind szelet, ha lefele zart es nincs legnagyobb eleme, azaz
- ha $x \in \mathbb{Q}$, $y \in A$ es $x < y$, akkor $x \in A$,
- ha $x \in A$, akkor $\exists y \in A$ ugy, hogy $y > x$.

Ezekkel a szeletekkel tudjuk reprezentalni a valos szamokat, pl a $A = \{  a \in \mathbb{Q}: a^{2} < 2, \text{ vagy } a < 0 \}$ reprezentalja a $\sqrt{ 2 }$ szamot.

### Rendezes, jojlrendezes
*Def.:* A $<$ muveletet rendezesnek hivjuk az $A$ halmazon, ha
- irreflexiv, azaz $\not \exists a \in A$, melyre $a < a$,
- tranzitiv, azaz $a, b, c \in A$ es $a < b$ es $b < c$, akkor $a < c$,
- trichotomia: $a, b \in A$ akkor a kovetkezo harom kozul pontosan egy teljesul: $a < b$, $a > b$, $a = b$.
*Def.:* Az $(A, <)$ parost rendezett halmaznak hivunk.
*Def.:* Az $(A, <)$ rendezett halmzt jol rendezettnek hivunk, ha minden nemures reszhalmazanak van legkisebb eleme.
*Tetel:* Minden halmaz jolrendezheto.
*Megj.:* Ez ekvivalens a kivalasztasi axiomaval.

### Igazszagfuggvenyek
*Def.:* Egy $f : \{ i, h \}^{n} \to \{ i, h \}$ fuggvenyt igazsag fuggvenynek nevezunk, ahol $i$ igazat jelol es $h$ hamisat.
*Jelolesek:* 
- $\land$ - logikai es
- $\lor$ - logikai vagy
- $\to$ - ha ... akkor ...
- $\oplus$  - xor
- $\leftrightarrow$ - xnor
- $|$ - nand

### Kijelenteslogika
*Tetel:* Nevezetes azonossagok, tulajdonsagok
- $\neg(\neg A) = A$
- $\neg A \land A = h$
- $\neg A \lor A = i$

kommutativ:
- $A \lor B = B \lor A$
- $A \land B = B \land A$
reflexiv:
- $A \lor A = A$
asszociativ:
- $(A \lor B) \lor C = A \lor (B \lor C)$
- $(A \land B) \land C = A \land (B \land C)$
elnyeles:
- $(A \lor B) \land A = A$
- $(A \land B) \lor A = A$
disztributivitas:
- $A \land (B \lor C) = (A \land B) \lor (A \land C)$
- $A \lor (B \land C) = (A \lor B) \land (A \lor C)$
de Morgan azonossagok:
- $\neg(A \lor B) = \neg A \land \neg B$
- $\neg(A \land B) = \neg A \lor \neg B$

### Igazsagtablazatok
*Def.:* Egy $f : \{ i, h \}^{n} \to \{ i, h \}$ $n$ valtozos igazsagfuggvenyt lehet reprezentalni egy tablazattal, melynek $2^{n}$ sora van van es $n+1$ oszlopa. Az elso $n$ oszlopban szerepel az osszes $2^{n}$ lehetseges $\{ i, h \}^{n}$ ertek, mig az utolso oszlapban szerepel a fuggveny erteke arra az igaz-hamis ertekadasnak.

*Pelda:* xor igazsagtablazata

| $x_{1}$ | $x_{2}$ | $x_{1} \oplus x_{2}$ |
| ------- | ------- | -------------------- |
| i       | i       | h                    |
| i       | h       | i                    |
| h       | i       | i                    |
| h       | h       | h                    |

### Teljes diszjunktiv normalforma
*Def.:* A
$$
(y_{1_{1}} \land \dots \land y_{1_{k}}) \lor (y_{2_{1}} \land \dots \land y_{2_{k'}}) \lor \dots \lor (y_{n_{1}} \land \dots \land y_{n_{1_{k''}}})
$$
alakot teljes diszjunktiv normalformanak hivunk, ahol $y_{i} = x_{l}$ vagy $y_{i} = \overline{x_{l}}$.
*Tetel:* Minden nem konstans hamis igazsag fuggveny eloall teljes diszjunktiv normal formaban.

### Teljes rendszerek
*Def.:* Muveletek egy halmaza teljes rendszer, ha tetszoleges igazsag fuggvenyt elo tudunk allitani ezen muveletek valamilyen kombinaciojakent.
*Peldaul:* $\{ \neg, \land, \lor \}$ teljes rendszer, mivel a de Morgan azonossagokkal elo tudjuk allitani $\land$-et $\neg$ es $\lor$ hasznalataval, es forditva, ezert $\{ \neg, \land \}$ es $\{ \neg, \lor \}$ es teljes rendszerek.

*Tetel:* (Post-Jablonszkij) Igazsagfuggvenyeknek egy $\mathcal{F}$ rendszere pontosan akkor teljes, ha nem reszrendszere $K_{i}, K_{h}, U, \mathcal{L}, \mathcal{M}$ egyike sem.
*Tetel:* Minden teljes rendszerbol kivalaszthato legfeljebb $5$ eleme teljes reszrendszer.

### Kovetkeztetesek
*Def.:* Egy formula tautologia, ha minden igazsagertekeles eseten igaz.
*Tetel:* A kovetkezo formulak mind tautologiat adnak:
- $A \to (B \to A)$
- $(A \to (B \to C)) \to ((A \to B) \to (A \to C) )$
- $(\neg A \to B) \to ((\neg A \to \neg B) \to A)$

*Def.:* A fenti tautologiakat a nulladrendu logika axiomasemajanak nevezzuk.
*Def.:* Azt mondjuk, hogy egy $\alpha$ formula levezetheto a $\Sigma$ formulahalmazbol, ha letezik formulaknak $\alpha_{1}, \alpha_{2}, \dots, \alpha_{n} = \alpha$ veges sorozata, ahol minden $\alpha_{i}$ vagy axioma, vagy eleme $\Sigma$-nak, vagy letezik ket korabbi $\alpha_{j}, \alpha_{k}$ melyekkel $\alpha_{k} = \alpha_{j} \to \alpha_{i}$. Jelolesben $\Sigma \vdash \alpha$.
*Megj.:* Az utolsot ugy hivjuk hogy *modus ponens* es azt jelenti, hogy ha van egy olyan allitasunk, hogy $A$-bol kovetkezik $B$ es tudjuk hogy $A$ igaz akkor $B$-nek is igaznak kell lennie.

*Tetel:* (indirekt bizonyitas) $\{ \neg \alpha \to \neg \beta, \beta \} \vdash \alpha$.
Ha $\alpha$ tagadasabol kovetkezik $\beta$ tagadasa, mikozben $\beta$ igaz, akkor $\alpha$ igaz.

*Tetel:* $\{ \varphi, \neg \varphi \} \vdash \psi$ tetszoleges $\psi$-re.

### Elsorendu nyelvek
*Def.:* $\mathcal{L}$ elsorendu nyelv, ha
- valtozojelek - $v_{0}, v_{1}, v_{2}, \dots$
- konstansjelek - $c_{0}, c_{1}, c_{2}, \dots$
- fuggvenyjelek - $f_{0}, f_{1}, f_{2}, \dots$
- relaciojelek - $R_{0}, R_{1}, R_{2}, \dots$
- logikai jelek - $\neg, \land, \lor, \to$
- kvantorok - $\forall, \exists$
- segedjelek - "$($" es "$)$" es "$,$"
mindegyikhez tartozik egy pozitiv egesz szam, hogy hany valtozos.
Szokasosan $R_{0}$ egy $2$ valtozos relaciojel, ami az egyenloseg.

*Def.:* A kovetkezoket hivjuk kifejezeseknek:
- minden valtozojel kifejezes
- minden konstansjel kifejezes
- ha $f$ egy $n$ valtozos fuggveny jel, es $t_{1}, \dots, t_{n}$ kifejezesek, akkor $f(t_{1}, \dots, t_{n})$ kifejezes

*Def.:* A kovetkezoket hivunk formulaknak:
- (kifejezesek relacioja formula) ha $R$ egy $n$ valtozos relaciojel, es $t_{1}, \dots, t_{n}$ kifejezesek, akkor $R(t_{1}, \dots, t_{n})$ formula 
- (formulak vagyolasa formula) ha $\varphi$ es $\psi$ formulak, akkor $\varphi \lor \psi$ is formula 
- (formula tagadasa formula) ha $\varphi$ formula, akkor $\neg \varphi$ formula 
- ha $v_{i}$ valtozojel es $\varphi$ es formula, akkor $\exists v_{i}\varphi$ formula
