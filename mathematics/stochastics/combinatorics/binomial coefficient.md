## Definition
The [[binomial coefficient]] is defined as follows:
$$
\begin{split}
{n \choose k}
&= \frac{n!}{k!(n-k)!} \\
&= C_{n,k} \\
&= \frac{P_{n,k}}{k!} \\
\end{split}
$$
- it is equal to the number of [[combinations]] of $n$ taken $k$
- it is equal to the number of [[permutations]] divided by $k!$

## Properties [[binomial coefficient]]
1) $n$ over $0$ and $n$ over $n$ are equal to one because only the empty set / the original set of $n$ elements satisfy the condition
$${n \choose 0} = {n \choose n} = 1$$
2) 
$$
{n \choose k} = {n \choose {n-k}}
$$
proof:
$$
{n \choose n-k}
= \frac{n!}{n-k!(n-(n-k))!}
= \frac{n!}{k!(n-k)!}
= {n \choose k}
$$
# Anki
START
Basic
binomial coefficient
- definition
- relationship to the number of [[combinations]]
- relationship to the number of [[permutations]]
- properties (1 + 1 with proof)
Back: 
## Definition
The [[binomial coefficient]] is defined as follows:
$$
\begin{split}
{n \choose k}
&= \frac{n!}{k!(n-k)!} \\
&= C_{n,k} \\
&= \frac{P_{n,k}}{k!} \\
\end{split}
$$
- it is equal to the number of [[combinations]] of $n$ taken $k$
- it is equal to the number of [[permutations]] divided by $k!$

## Properties
1) $n$ over $0$ and $n$ over $n$ are equal to one because only the empty set / the original set of $n$ elements satisfy the condition
$${n \choose 0} = {n \choose n} = 1$$
2) 
$$
{n \choose k} = {n \choose {n-k}}
$$
proof:
$$
{n \choose n-k}
= \frac{n!}{n-k!(n-(n-k))!}
= \frac{n!}{k!(n-k)!}
= {n \choose k}
$$

Tags: mathematics statistics
<!--ID: 1667724226677-->
END



START
Basic
Probability of a full house in a deck of 13 number times 4 colors.
Back: 
$$
\frac{13 \cdot 12 \cdot {4 \choose 3}{4 \choose 2}}{{52 \choose 5}}
$$
Tags: mathematics statistics
<!--ID: 1673374513139-->
END

START
Basic
Probability of a flush in a deck of 13 number times 4 colors.
Back: 
$$
\frac{4 \cdot {13 \choose 5}}{{52 \choose 5}}
$$
Tags: mathematics statistics
<!--ID: 1673374513146-->
END