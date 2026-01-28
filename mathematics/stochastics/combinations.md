## Definition
- Given a [[set]] with $n$ elements, a [[combinations|combination]] is a subset of a specified size $k$.
- The difference to a [[permutations|permutation]] is that $(a,b) \neq (b,a)$ but $\{a,b\}=\{b,a\}$
	→the order considered for [[permutations]] but not for [[combinations]] 
- can be interpreted as [[unordered sampling without replacement]]
## Number of [[combinations]]
The number of [[combinations]] of $n$ taken $k$ $C_{n,k}$ is defined as follows.
For each subset of [[cardinality]] $k$ we can build $k!$ different [[permutations]] but only one [[combinations|combination]] thus the number of [[combinations]] is $k!$ times smaller than the number of [[permutations]]. 
### Definition number of [[combinations]]
$$
\begin{split}
C_{n,k} 
&= \frac{P_{n,k}}{k!} \\
&= \frac{n!}{k!(n-k)!} \\
&= {n \choose k} \\
\end{split}
$$
### relationship to the [[binomial coefficient]]
$C_{n,k}$ is equal to the [[binomial coefficient]] $n \choose k$. 
![[binomial coefficient#Properties binomial coefficient]]

# Anki
START
Basic
[[combinations]]
- definition verbal
number of [[permutations]]
- definition verbal
- definition (3)
- [[sampling]] interpretation
Back: 
## Definition
- Given a [[set]] with $n$ elements, a [[combinations|combination]] is a subset of a specified size $k$.
- The difference to a [[permutations|permutation]] is that $(a,b) \neq (b,a)$ but $\{a,b\}=\{b,a\}$
	→the order considered for [[permutations]] but not for [[combinations]] 
- can be interpreted as [[unordered sampling without replacement]]
## Number of [[combinations]]
The number of [[combinations]] of $n$ taken $k$ $C_{n,k}$ is defined as follows:
$$
\begin{split}
C_{n,k} 
&= \frac{P_{n,k}}{k!} \\
&= \frac{n!}{k!(n-k)!} \\
&= {n \choose k} \\
\end{split}
$$
For each subset of [[cardinality]] $k$ we can build $k!$ different [[permutations]] but only one [[combinations|combination]] thus the number of [[combinations]] is $k!$ times smaller than the number of [[permutations]]. This definition is equal to the [[binomial coefficient]] $n \choose k$. 

Tags: mathematics statistics
<!--ID: 1667724226671-->
END