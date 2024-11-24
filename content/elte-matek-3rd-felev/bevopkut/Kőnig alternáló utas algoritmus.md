#algorithm 

***Scope***: Megkeresi a legnagyobb párosítást az adott $G = (S, T, V)$ páros gráfban.

***Procedure***.: 
1. Induljunk ki egy tetszőleges $M$ párosításból.

2. Irányítsuk meg a $G$ éleit úgy, hogy az $M$-beli élek $S$-ből $T$-be mutatnak, a többi él meg a másik irányba, azaz $T$-ből $S$-be.

3. Jelölje $R_{S}$ azon $S$-beli csúcsok halmazát, melyeket nem fed $M$.
 Hasonlóan, jelölje $R_{T}$ azon $T$-beli csúcsok halmazát, melyeket nem fed $M$.

4. Keressünk egy utat $R_{S}$-ből $R_{T}$-be az irányított gráfban (ezek az alternáló utak).

5. Ha létezik ilyen út, akkor cseréljük le $M$-et az alternáló út és $M$ szimmetrikus differenciájára.
Azaz az út minden páratlanadig élére.
 


***Dependencies***:
- 