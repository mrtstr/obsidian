### inversion method
- Given a [[cumulative distribution function (CDF)]] $F$ with a [[quantile function]] $F^{-1}$
- a [[random variable]] $X$ can be constructed like the following
- using a [[continous uniform distribution]] and the fact that the [[cumulative distribution function (CDF)]] of the standard [[continous uniform distribution]] is the identity function

$$
\begin{split}
&U \sim \mathcal{U}(1,0) \Leftrightarrow F_U(u) = u \\
&X = F^{-1}(U)
\end{split}
$$

#### proof
- let $X = T(U)$ be a tranformation of the standard [[continous uniform distribution]]

$$
\begin{split}
F(x) 
&= P(X \leq x) \\
&= P(T(U) \leq x) \\
&= P(U \leq T^{-1}(x)) \\
&= F_U\left(T^{-1}(x)\right) \\
&= T^{-1}(x) \\
\Rightarrow T(u) &= F^{-1}(u)
\end{split}
$$

Thus, the transformation $T$ is equal to the [[quantile function]] $F^{-1}(u)$

# ---------------------

![[continous uniform distribution#continous uniform distribution]]


# anki

START
Basic
- create a [[random variable]] from its [[cumulative distribution function (CDF)]]
- with proof

Back: 

### inversion method
- Given a [[cumulative distribution function (CDF)]] $F$ with a [[quantile function]] $F^{-1}$
- a [[random variable]] $X$ can be constructed like the following
- using a [[continous uniform distribution]] and the fact that the [[cumulative distribution function (CDF)]] of the standard [[continous uniform distribution]] is the identity function

$$
\begin{split}
&U \sim \mathcal{U}(1,0) \Leftrightarrow F_U(u) = u \\
&X = F^{-1}(U)
\end{split}
$$

#### proof
- let $X = T(U)$ be a tranformation of the standard [[continous uniform distribution]]

$$
\begin{split}
F(x) 
&= P(X \leq x) \\
&= P(T(U) \leq x) \\
&= P(U \leq T^{-1}(x)) \\
&= F_U\left(T^{-1}(x)\right) \\
&= T^{-1}(x) \\
\Rightarrow T(u) &= F^{-1}(u)
\end{split}
$$

Thus, the transformation $T$ is equal to the [[quantile function]] $F^{-1}(u)$


____________


### continous uniform distribution
[[probability density function (PDF)]] of a [[probability mass function (PMF)]] with the same probability of taking all values inside an interval $[a,b]$ and 0 for all other values.
#### [[probability density function (PDF)]]
$$
f_X(X = x)=
\begin{cases}
\frac{1}{b-a}
,& \text{if } x \in [a,b]\\
0
,& \text{otherwise}
\end{cases}
$$
#### [[cumulative distribution function (CDF)]]

$$
\begin{split}
F_X(x)&=
\begin{cases}
0 
,& \text{if } x<a \\
\int\limits_a^x\frac{1}{b-a}du
,& \text{if } x \in [a,b]\\
1
,& \text{if } x>b
\end{cases} \\
&= \begin{cases}
0 
,& \text{if } x<a \\
\frac{x-a}{b-a}
,& \text{if } x \in [a,b]\\
1
,& \text{if } x>b
\end{cases}
\end{split}
$$

Tags: mathematics statistics WS2425
<!--ID: 1729443087548-->
END