---
title: Q-learning
---

A value iteration algoritmusban kell tudnunk az egész Markov láncot és minden lépéshez és állapothoz rendelt jutalmat. Ezt nem mindig tehetjük meg, például tipikusan ha van egy ügynökünk egy valós környezetben, akkor az egész Markov lánc ismerete azt jelentené, hogy tökéletes modellünk van a valóságra, amit még sajnos nem ért el a fizika tudománya.

Ennek a problémának orvosolására vezetjük be a Q-learning algoritmust, ahol már nem kell ismernünk az egész állapotteret és az összes jutalmat, hanem elég tudnunk, hogy hol jártunk és ott milyen jutalmat kaptunk. Így minnél jobban felderítjük az állapotteret, annál jobban közelíti az algoritmus majd a Value iteration algoritmust.