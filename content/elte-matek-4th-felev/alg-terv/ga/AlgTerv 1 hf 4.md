### 1.
Oldjuk meg a hátizsák feladatot egy $11$ kapacitású hátizsákkal, $5$ tárggyal, amiknek adatai a következők (az alábbiakban (súly, érték) párokat adunk meg): $(4, 8), (2, 3), (3, 4), (1,2), (5, 10)$. Adjuk meg a választ, a tárgyhalmazt, és a teljes táblázatot!

***Megoldás:***

| 1   | 2   | 3   | 5   | 6   | 7   | 8   | 9   | 10  | 11  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   | 0   |     |


### 2.
Móricka az $1, 2, \dots, n$ számok egy $P$ permutációját kapta húsvétre. Sajnos nem elégedett az ajándékkel: ő inkább a $Q$ permutációt szeretné. Adott $k$ darab jó számpár: $(a_{1}, b_{1}), \dots, (a_{k}, b_{k})$. Móricka a következő műveleteket tudja elvégezni (akárhányszor):
- Az $a_{i}$ és $b_{i}$ helyen álló számok felcserélése, amennyiben $(a_{i}, b_{i})$ jó számpár.
Segíts neki eldönteni, hogy teljesülhet-e a vágya, és megkaphatje-e a $Q$ permutációt. Móricka sajnos kissé lassú felfogású, így olyan algoritmusra van szükség, ami $O(n^{2})$ komplexitású. (*Felhasználhatjuk, hogy minden permutáció fel lehet írni transzpozíciók szorzataként.*)

***Megoldás:***


related: [[AlgTerv 1]]