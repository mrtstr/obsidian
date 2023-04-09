[[sampling]]
## number of [[unordered sampling without replacement]]
number of [[unordered sampling without replacement]] is equal to number of [[combinations]]
![[combinations#Definition number of combinations]]

## [[expectation]] of [[unordered sampling without replacement]]
Suppose that a box contains $a$ red balls and $b$ blue balls so that the proportion of red balls in the box is $p = \frac{a}{a+b}$ with $0 ≤ p ≤ 1$. Suppose that $n$ balls are selected from the box at random without replacement, and let $X$ denote the number of red balls that are selected.

Since the order is arbitrary, we can assume that $P(X_i=1)=p$ and $P(X_i=0)=1-p$.
$$
\begin{split}
\mathbb{E}[X_i] &= P(X_i=1) \cdot 1 + P(X_i=0) \cdot 0 = p \\
\mathbb{E}[X] &= \mathbb{E}\left[\sum_{i=1}^nX_i\right]  = n \mathbb{E}\left[X_i\right] = n p 

\end{split}
$$
$$
\begin{split}
\mathbb{E}[X_i] &= P(X_i=1) \cdot 1 + P(X_i=0) \cdot 0 = p \\
\mathbb{E}[X] &= \mathbb{E}\left[\sum_{i=1}^nX_i\right]  = n \mathbb{E}\left[X_i\right] = n p 

\end{split}
$$
#### proof
We want to prove that the [[expectation]] of the second sample is equal to the [[expectation]] of the first sample. 
$$
\begin{split}
\mathbb{E}[X_2] &= \mathbb{E}\left[\mathbb{E}\left[X_2 | X_1\right]\right] \\
&= p \mathbb{E}\left[X_2 | X_1 = 1\right] + (1-p) \mathbb{E}\left[X_2 | X_1 = 0\right] \\
&= p \cdot \frac{a-1}{a+b-1} +  (1-p) \cdot \frac{a}{a+b-1}  \\
&= \frac{a}{a+b} \cdot \frac{a-1}{a+b-1} +  \frac{b}{a+b} \cdot \frac{a}{a+b-1}  \\
&=  \frac{a(a+b-1)}{(a+b)(a+b-1)} \\
&=  \frac{a}{a+b} \\
&=  p \\
\end{split}
$$
# Anki

START
Basic
number unordered samples without replacement
Back: 
- equal to the number of [[combinations]] $C_{n,k}$ 
$$
C_{n,k} = {n \choose k} = \frac{n!}{k!(n-k)!}
$$
Tags: mathematics statistics
<!--ID: 1667724693419-->
END


START
Basic
### [[expectation]] of [[unordered sampling without replacement]]
Suppose that a box contains red balls and blue balls and that the proportion of red balls in the box is $p$ with $0 ≤ p ≤ 1$. Suppose that $n$ balls are selected from the box at random without replacement, and let $X$ denote the number of red balls that are selected.
- [[expectation]] of $X$ $\mathbb{E}[X]$ ?
- with proof
Back: 
Since the order is arbitrary, we can assume that $P(X_i=1)=p$ and $P(X_i=0)=1-p$.

$$
\begin{split}
\mathbb{E}[X_i] &= P(X_i=1) \cdot 1 + P(X_i=0) \cdot 0 = p \\
\mathbb{E}[X] &= \mathbb{E}\left[\sum_{i=1}^nX_i\right]  = n \mathbb{E}\left[X_i\right] = n p 

\end{split}
$$
#### proof
We want to prove that the [[expectation]] of the second sample is equal to the [[expectation]] of the first sample. 
$$
\begin{split}
\mathbb{E}[X_2] &= \mathbb{E}\left[\mathbb{E}\left[X_2 | X_1\right]\right] \\
&= p \mathbb{E}\left[X_2 | X_1 = 1\right] + (1-p) \mathbb{E}\left[X_2 | X_1 = 0\right] \\
&= p \cdot \frac{a-1}{a+b-1} +  (1-p) \cdot \frac{a}{a+b-1}  \\
&= \frac{a}{a+b} \cdot \frac{a-1}{a+b-1} +  \frac{b}{a+b} \cdot \frac{a}{a+b-1}  \\
&=  \frac{a(a+b-1)}{(a+b)(a+b-1)} \\
&=  \frac{a}{a+b} \\
&=  p \\
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1678001380988-->
END