# Definition
Given a [[set]] $A$ with a [[cardinality]] $n$ "a [[permutations|permutation]] of $n$ taken $k$" is an **ordered selection without replacement** with a size of $k$.

## Number of [[permutations]] $P_{n,k}$
The selection of a [[permutations|permutation]] can be interpreted as a [[random experiment]] consisting of $k$ partial [[random experiment|experiments]]. The first part is the selection of the first element out of $n$ possible elements. The second part is the selection of the second element out of the $n-1$ remaining elements, and so on. 
$$
\begin{split}
P_{n, k} 
&= 

\overbrace{(n)}^\text{first pick} \cdot \overbrace{(n-1)}^\text{second pick}  \cdot...\cdot  \overbrace{\left(n-(k-1)\right)}^\text{kth pick} \\
&= \prod\limits_{i=0}^{k-1} (n-i) \\
&= \frac{n!}{(n-k)!} \\
\end{split}
$$
We can define it using the [[factorial]]. 
Proof:
$$
\begin{split}
\frac{n!}{(n-k)!}
&= \frac{\prod\limits_{i=1}^{n} i}{\prod\limits_{i=1}^{n-k} i}
= \frac{
\overbrace{
\left(\prod\limits_{i=1}^{n-k} i\right)
}^{1 \cdot 2 \cdot ... \cdot (n-k)}
\overbrace{
\left( \prod\limits_{i=0}^{k-1} (n-i)\right)
}^{(n-k+1)(n-k+2)...n}
}{\prod\limits_{i=1}^{n-k} i}
\\
&= \prod\limits_{i=0}^{k-1} (n-i) \\
\end{split}
$$

START
Basic
[[permutations]]
- definition verbal
number of [[permutations]]
- definition verbal
- definition (3 with proof)

Back: 
# Definition
Given a [[set]] $A$ with a [[cardinality]] $n$ "a [[permutations|permutation]] of $n$ taken $k$" is an **ordered selection without replacement** with a size of $k$.

## Number of [[permutations]] $P_{n,k}$
The selection of a [[permutations|permutation]] can be interpreted as a [[random experiment]] consisting of $k$ partial [[random experiment|experiments]]. The first part is the selection of the first element out of $n$ possible elements. The second part is the selection of the second element out of the $n-1$ remaining elements, and so on. 
$$
\begin{split}
P_{n, k} 
&= 

\overbrace{(n)}^\text{first pick} \cdot \overbrace{(n-1)}^\text{second pick}  \cdot...\cdot  \overbrace{\left(n-(k-1)\right)}^\text{kth pick} \\
&= \prod\limits_{i=0}^{k-1} (n-i) \\
&= \frac{n!}{(n-k)!} \\
\end{split}
$$
We can define it using the [[factorial]]. 
Proof:
$$
\begin{split}
\frac{n!}{(n-k)!}
&= \frac{\prod\limits_{i=1}^{n} i}{\prod\limits_{i=1}^{n-k} i}
= \frac{
\overbrace{
\left(\prod\limits_{i=1}^{n-k} i\right)
}^{1 \cdot 2 \cdot ... \cdot (n-k)}
\overbrace{
\left( \prod\limits_{i=0}^{k-1} (n-i)\right)
}^{(n-k+1)(n-k+2)...n}
}{\prod\limits_{i=1}^{n-k} i}
\\
&= \prod\limits_{i=0}^{k-1} (n-i) \\
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1667662694123-->
END