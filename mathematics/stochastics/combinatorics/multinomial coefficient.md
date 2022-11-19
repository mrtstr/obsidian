Generalized form of the [[binomial coefficient]]

## Definition
- given a [[set]] of $n$ elements
- in how many ways can we split the [[set]] in $k$ different [[set|sets]] with $n_1,...,n_k$ elements
- $n=\sum\limits_{i=1}^{k}n_i$
$$
\begin{split}
&{n \choose n_1}{n-n_1 \choose n_2}...{n-n_1...-n_{k-1} \choose n_k} \\
=& \frac{n!}{n_1!(n-n_1)!} \cdot \frac{(n-n_1)!}{n_2!(n-n_1-n_2)!}
... \cdot \frac{(n-n_1...-n_{k-1})!}{n_k!(n-n_1...-n_{k-1})!} \\
=& \frac{n!}{n_1! n_2! ... n_k!} \\
:=& {n \choose n_1,n_2,...,n_k}
\end{split}
$$
- for the first split of the [[set]] with have $n \choose n_1$ different possibilities for the following split we have ${n - n_1 \choose n_2}$ options and so on. This is equal to $\frac{n!}{n_1! n_2! ... n_k!}$. This is defined as the [[multinomial coefficient]].


# Anki
START
Basic
- given a [[set]] of $n$ elements
- in how many ways can we split the [[set]] in $k$ different [[set|sets]] with $n_1,...,n_k$ elements
- $n=\sum\limits_{i=1}^{k}n_i$
Back: 
$$
\begin{split}
&{n \choose n_1}{n-n_1 \choose n_2}...{n-n_1...-n_{k-1} \choose n_k} \\
=& \frac{n!}{n_1!(n-n_1)!} \cdot \frac{(n-n_1)!}{n_2!(n-n_1-n_2)!}
... \cdot \frac{(n-n_1...-n_{k-1})!}{n_k!(n-n_1...-n_{k-1})!} \\
=& \frac{n!}{n_1! n_2! ... n_k!} \\
:=& {n \choose n_1,n_2,...,n_k}
\end{split}
$$
- for the first split of the [[set]] with have $n \choose n_1$ different possibilities for the following split we have ${n - n_1 \choose n_2}$ options and so on. This is equal to $\frac{n!}{n_1! n_2! ... n_k!}$. This is defined as the [[multinomial coefficient]].

Tags: mathematics, statistics
<!--ID: 1668855069553-->
END


START
Basic
[[multinomial coefficient]]
- definition and interpretation
Back: 
## interpretation
- given a [[set]] of $n$ elements
- in how many ways can we split the [[set]] in $k$ different [[set|sets]] with $n_1,...,n_k$ elements
- $n=\sum\limits_{i=1}^{k}n_i$
## Definition
$$
\begin{split}
&{n \choose n_1}{n-n_1 \choose n_2}...{n-n_1...-n_{k-1} \choose n_k} \\
=& \frac{n!}{n_1!(n-n_1)!} \cdot \frac{(n-n_1)!}{n_2!(n-n_1-n_2)!}
... \cdot \frac{(n-n_1...-n_{k-1})!}{n_k!(n-n_1...-n_{k-1})!} \\
=& \frac{n!}{n_1! n_2! ... n_k!} \\
:=& {n \choose n_1,n_2,...,n_k}
\end{split}
$$
- for the first split of the [[set]] with have $n \choose n_1$ different possibilities for the following split we have ${n - n_1 \choose n_2}$ options and so on. This is equal to $\frac{n!}{n_1! n_2! ... n_k!}$. This is defined as the [[multinomial coefficient]].

Tags: mathematics, statistics
<!--ID: 1668855069559-->
END


START
Basic
Suppose that 18 red beads, 12 yellow beads, eight blue
beads, and 12 black beads are to be strung in a row. How
many different arrangements of the colors can be formed?
Back: 
[[multinomial coefficient]]:
$$
{n \choose n_1,n_2,...,n_k} = \frac{n!}{n_1! n_2! ... n_k!}
$$

$$
\frac{50}{{18}! {12}! {12}! {8}!}
$$
- the 50 positions on the row can be interpreted as elements of a [[set]] and we have to split them up in 4 groups...
Tags: mathematics, statistics
<!--ID: 1668855069562-->
END


START
Basic
Suppose that two committees are to be formed in an
organization that has 300 members. If one committee is
to have five members and the other committee is to have
eight members, in how many different ways can these
committees be selected?
Back: 
[[multinomial coefficient]]:
$$
{n \choose n_1,n_2,...,n_k} = \frac{n!}{n_1! n_2! ... n_k!}
$$

$$
\frac{300}{{8}! {5}! {287}!}
$$

Tags: mathematics, statistics
<!--ID: 1668855069565-->
END