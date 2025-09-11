try generating a bunch of fbm realizations with python, put them in a db, and make the C env query the db for realizations

try sin with random phase, random amplitude, and with ranom number of peeks

if that works, try with AR(1)

if that does not works fine, then try with a 5th degree polynomial
$$
T(x)=a_0+\sum_{n=1}^N a_n \cos n x+\sum_{n=1}^N b_n \sin n x \quad(x \in \mathbb{R})
$$
$$
a_{n}, b_{n} \sim \operatorname{Bimod}(0, 1)
$$

