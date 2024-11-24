#algorithm 

1. Kiindulunk egy tetszőleges $\pi$ lefogó súlyozásból
2. Legyen $G_\pi (S, T, E_\pi)$ a pontos élek halmaza (azaz azok az élek, ahol $\pi(u) + \pi(v) = c(uv)$)
3. Kiindulunk $G_\pi$-nek egy teszőleges párosításából
4. Megirányítjuk az összes $M$-beli élt $T$-ből $S$-be
5. Minden más $G_\pi$-beli élt ellenkező irányba megirányítjuk
6. Jelölje $R_S$, illetve $R_T$ az $S$-beli, illetve $T$-beli $M$ által fedetlen pontok halmazát
7. Jelölje $Z$ az $R_S$ pontjaiból az így kapott irányított gráfban irányított úton elérhető csúcsok halmazát
8. Ha $R_T$-nek van pontja $Z$-ben, akkor kapunk egy olyan $R_S$-t és $R_T$-t összekötő $P$ utat, amely $M$-ben alternál
9. Az $M$ és $P$ szimmetrikus differenciája egy $M$-nél eggyel több élből álló $M'$ párosítást alkot
10. Folytatjuk a 2. lépéstől $M'$-vel
11. 