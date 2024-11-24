Def. (*vektortér projektivizáltja*):
	$P(V) = (V \setminus \{0\})_ {/\sim}$ 

Def. (*projektív altér*):
	$U \le V$ lineáris altér, ekkor $(U \setminus \{0\})_{/\sim}$  egy projektív altér.

Megj.:
	$P(V)$ **nem** egy vektortér, és így a projektív altér nem egy altere az eredeti vektortér projektivizáltjának.

Def. (*generált projektív altér*):
	$X \subseteq P(V)$. Ekkor $X$ által generált *projektív altér* az $X$-et tartalmazó legkisebb projektív altér.

Jel. (generált projektív altér):
	$X$ által generált projektív altér: $\langle X \rangle$  

Áll.:
	$\forall X \subseteq P(V) \exists ! \langle X \rangle$
	A generált projektív altér létezik és egyértelmű

Def. (*duális tér*):
	$U$ annulátora: $U^\perp$ 
	$U^\perp = \{\alpha \in V^*: \alpha | _U \equiv 0\}$

Emlék:
	$V^* = \{\alpha : V \rightarrow \mathbb{F}\}$ , $\alpha$ egy lineáris leképzés

Meggondolandó:
	$U^\perp \le V^*$

Def. (projektív tér duálisa):
	$P(V)$ duálisa: $P(V^*)$

Tétel (*dimenzió formula*):
	$S, T \le P(V)$ projektív alterek.
	Ekkor: $dim(S\cap T) ! dim(\langle S \cup T \rangle) = dim(S) + dim(T)$ 

Megj.:
	$dim(\emptyset) = -1$ 

Jel.:
	$v$ ekvivalencia osztályai: $[v] = \{u\in V : u \sim v\}$ 

Def. (*homogén koordináták*):
	Adott bázis $V$-ben: $\{u_1, \ldots, u_{d+1}\}$, azaz, $\forall v \in V$, ekkor $\exists ! \alpha_1, \ldots, \alpha_{d+1}\in \mathbb{F}$, úgy hogy $v = \sum_{i=1}^{d+1}{\alpha_{i} \cdot u_i}$
	Ekkor, $[v]$ homogén koordinátái: $[\alpha_1 : \alpha_2 : \ldots : \alpha_{d+1}]$ 

Def. (*projektív bázis*):
	$A_0, A_1, \ldots, A_{d+1} \in P(V)$ projektív bázis, ha léteznek reprezentánsaik $V$-ben úgy, hogy: $[a_0] = A_0, [a_1] = A_1, \ldots, [a_{d+1}] = A_{d+1}$ és $a_0 = \sum_{i=1}^{d+1}{a_i}$ és $a_1, a_2, \ldots, a_{d+1}$ bázis $V$-ben.

Áll. 