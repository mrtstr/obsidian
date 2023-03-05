# Definition
- [[distribution]] of the sum of $n$ [[stochastic independent|non independent]] [[bernoulli distribution|bernoulli]] [[random variable|random variables]]
- given a [[set]] with $a$ ones and $b$ zeros each is a random [[sampling|random sample]] is a [[bernoulli distribution| bernoulli experiment]]
- the sum of $n$ [[unordered sampling without replacement|unordered samples without replacement]] has a [[hypergeometric distribution]]
- let $p=\frac{a}{a+b}$ be the proportion of ones
The [[probability function]] of x is given by the following:
$$
f_X({x|a,b,n}) = \frac{
{a \choose x}{b \choose n-x}
}{{a+b \choose n}}
\quad for \: max\{0, n-b\}<x<min\{n, a\}
$$
# [[expectation]]
![[unordered sampling without replacement#expectation of unordered sampling without replacement]]
# [[variance]]
$$
\begin{split}
\mathbb{VAR}[X_i] &= \mathbb{E}[X_i^2] - \mathbb{E}[X_i]^2 = p - p^2 = p(1-p) \\
\mathbb{E}[X_2X_1] &= \mathbb{E}\left[\mathbb{E}\left[X_1X_2|X_1\right]\right]  \\
&= p \cdot \mathbb{E}\left[1 \cdot X_2|X_1=1\right] + (1-p) \cdot \mathbb{E}\left[0 \cdot X_2|X_1=0\right] \\
&= p \cdot \mathbb{E}\left[1 \cdot X_2|X_1=1\right]  \\
&= p \cdot \left(\frac{a-1}{a+b-1} \cdot 1 + \frac{b}{a+b-1} \cdot 0\right)  \\
&= \frac{a}{a+b} \cdot \frac{a-1}{a+b-1}   \\
&= \frac{a\left(a-1\right)}{(a+b)(a+b-1)}   \\
\mathbb{COVAR}[X_2,X_1] &= \mathbb{E}[X_2X_1] - \mathbb{E}[X_1]\mathbb{E}[X_2]  \\
&= \frac{a\left(a-1\right)}{(a+b)(a+b-1)} - p^2  \\
&= \frac{a\left(a-1\right)}{(a+b)(a+b-1)} - \frac{a^2}{(a+b)^2}  \\
&= \frac{ab}{(a+b)^2(a+b-1)}   \\
\mathbb{VAR}[X] &= \mathbb{VAR}\left[\sum_{i=1}^nX_i\right]  \\
&= \sum_{i=1}^n \mathbb{VAR}[X_i] + \sum_{i=1}^n \sum_{i=1, i\neq j}^n \mathbb{COVAR}[X_i,X_i] \\
&= n \mathbb{VAR}[X_1] + n(n-1) \mathbb{COVAR}[X_2,X_1] \\
&= n p(1-p) + n(n-1) \frac{ab}{(a+b)^2(a+b-1)} \\

\end{split}
$$


# Anki

START
Basic
hypergeometric distribution
- interpretation
- [[probability function]]
- [[expectation]]
- [[variance]]
Back: 
## interpretation
- [[distribution]] of the sum of $n$ [[stochastic independent|non independent]] [[bernoulli distribution|bernoulli]] [[random variable|random variables]]
- given a [[set]] with $a$ ones and $b$ zeros each is a random [[sampling|random sample]] is a [[bernoulli distribution| bernoulli experiment]]
- the sum of $n$ [[unordered sampling without replacement|unordered samples without replacement]] has a [[hypergeometric distribution]]
- let $p=\frac{a}{a+b}$ be the proportion of ones
## [[probability function]]
$$
f_X({x|a,b,n}) = \frac{
{a \choose x}{b \choose n-x}
}{{a+b \choose n}}
\quad for \: max\{0, n-b\}<x<min\{n, a\}
$$
## [[expectation]]
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
## [[variance]]
$$
\begin{split}
\mathbb{VAR}[X_i] &= \mathbb{E}[X_i^2] - \mathbb{E}[X_i]^2 = p - p^2 = p(1-p) \\
\mathbb{E}[X_2X_1] &= \mathbb{E}\left[\mathbb{E}\left[X_1X_2|X_1\right]\right]  \\
&= p \cdot \mathbb{E}\left[1 \cdot X_2|X_1=1\right] + (1-p) \cdot \mathbb{E}\left[0 \cdot X_2|X_1=0\right] \\
&= p \cdot \mathbb{E}\left[1 \cdot X_2|X_1=1\right]  \\
&= p \cdot \left(\frac{a-1}{a+b-1} \cdot 1 + \frac{b}{a+b-1} \cdot 0\right)  \\
&= \frac{a}{a+b} \cdot \frac{a-1}{a+b-1}   \\
&= \frac{a\left(a-1\right)}{(a+b)(a+b-1)}   \\
\mathbb{COVAR}[X_2,X_1] &= \mathbb{E}[X_2X_1] - \mathbb{E}[X_1]\mathbb{E}[X_2]  \\
&= \frac{a\left(a-1\right)}{(a+b)(a+b-1)} - p^2  \\
&= \frac{a\left(a-1\right)}{(a+b)(a+b-1)} - \frac{a^2}{(a+b)^2}  \\
&= \frac{ab}{(a+b)^2(a+b-1)}   \\
\mathbb{VAR}[X] &= \mathbb{VAR}\left[\sum_{i=1}^nX_i\right]  \\
&= \sum_{i=1}^n \mathbb{VAR}[X_i] + \sum_{i=1}^n \sum_{i=1, i\neq j}^n \mathbb{COVAR}[X_i,X_i] \\
&= n \mathbb{VAR}[X_1] + n(n-1) \mathbb{COVAR}[X_2,X_1] \\
&= n p(1-p) + n(n-1) \frac{ab}{(a+b)^2(a+b-1)} \\

\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1678001380982-->
END