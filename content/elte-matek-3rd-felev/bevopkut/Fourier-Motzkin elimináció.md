#algorithm 

***Scope***: Adott $Q \in \mathbb{R}^{k \times n}$ és $b \in \mathbb{R} ^{k}$. Az algoritmus eldönti, hogy létezik-e $x \in \mathbb{R}^{n}$ úgy, hogy $Qx \leq b$.

***Procedure***.: $Q \to Q'$ úgy, hogy $Q'$-ben kevesebb nem csupa $0$ oszlop van.
*lépés*:
1. Minden sort osszuk le az első nem csupa $0$ oszlop első elemének az abszolút értékével.
2. Legyenek $I_{+}, I_{-}, I_{0}$ azon sorok halmazai, melyekre az első nem nulla elem $1, -1, 0$.
3. $\forall (s_{+}, s_{-}) \in I_{+} \times I_{-}$ legyen $s' = s_{+} + s_{-}$, tehát összeadjuk a két sort.
4. Ezeket a $s'$ sorokat rakjuk bele egy új $Q'$ mátrixba.
5. Változtatás nélkül rakjuk még hozzá $I_{0}$ sorait is $Q'$ mátrixhoz.

Ezek a lépések után létrehoztunk egy új $Q'$ mátrixot úgy, hogy kevesebb nem csupa $0$ oszlopa van.
Továbbá, ha $x \in \mathbb{R}^{n}$ kielégítette a $Qx\leq b$ egyenlőtlenséget, akkor $\exists x'$ úgy, hogy $Q'x' \leq b'$.




***Dependencies***:
- [[LP feladat]]