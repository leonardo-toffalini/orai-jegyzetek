### Bayes halok mire jok?
- Megtortent egy esemeny es tudni szeretnenk hogy egy elozo esemeny mennyit jatszott ennek a megtorteneseben.
- Megtortent egy esemeny es szeretnenk tudni, hogy egy masik mennyi valoszinuseggel fog bekovetkezni.
### Alkalmazasok
- tunetek -> betegsegek
- dokumentum klasszifikacio
- spam filter

### Markov takaró
Motiváció: Adott egy esemény, amitől feltételesen függ a maradék gráf. Melyik csúcsokat kell felfedni ahhoz, hogy feltételesen független legyen a gráftól.

***Definíció***: Egy $D(V,A)$ irányított gráfnak $\alpha \in V$ csúcsnak *markov takarója* a $\mathcal N (\alpha), \operatorname{sz}(\alpha), \mathcal N(\operatorname{sz}(\alpha))$. Ahol $\operatorname{sz}(v)$ azon csúcsok jelöli, melyek szülői $v$-nek és $\mathcal N(v)$ azon csúcsokat jelöli, melyek szomszédai $v$-nek, tehát megy beléjük él $v$-ből.

***Állítás***: $\alpha \in V$ csúcsnak a markov takarójában lévő csúcsokat kell ahoz tudni, hogy $\alpha$ feltételesen független legyen a gráftól.
***Bizonyítás***: (csak vázlatosan)
jelölés $\mathbb{P}(V) = \mathbb{P}(x_{1}, \dots, x_{n})$
$$
\mathbb{P}(\alpha \mid V \setminus \{ \alpha \}) = \frac{\mathbb{P}(V)}{\sum \limits_{\alpha} \mathbb{P}(V)} = \frac{\prod \limits_{j = 1}^{n}\mathbb{P}(x_{j} \mid \operatorname{sz}(x_{j}))}{\sum \limits_{\alpha} \prod \limits_{j = 1}^{n}\mathbb{P}(x_{j} \mid \operatorname{sz}(x_{j}))} 
$$

Észrevétel: $\alpha$ szerepel a $\mathbb{P}\big(\mathcal N(\alpha) \mid \operatorname{sz}(\mathcal N(\alpha))\big)$ tényezőben és a $\mathbb{P}\big(\alpha | \operatorname{sz}(\alpha)\big)$ tényezőben a nevezőben, minden mással lehet egyszerűsíteni. Tehát $\mathbb{P}(\alpha | V \setminus \{ \alpha \})$ csak a $\mathcal N (\alpha), \operatorname{sz}(\alpha), \mathcal N(\operatorname{sz}(\alpha))$ csúcsoktól függ, azaz $\alpha$ markov takarójától.
