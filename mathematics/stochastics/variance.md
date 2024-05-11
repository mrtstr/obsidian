## definition [[variance]]
- [[expectation|expectation]] of the squared deviation of a [[discrete random variable]] from its mean
- measure of how for a [[random variable]] spreads out
- the square root of the [[variance]] is the [[standard deviation]] $\sigma$

$$
\mathbb{VAR}[X]=\mathbb{E}[(X-\mathbb{E}[X])^2]=\mathbb{E}[X^2]-\mathbb{E}[X]^2 = \sigma_X^2
$$

(variance of a set of [[observations]] see [[sample variance]])

## properties
### Non negativity 
$$
\mathbb{VAR}[X] \geq 0
$$

### [[variance]] of a constant
$\mathbb{VAR}[X] = 0$ $\Leftrightarrow$ $X$ is a constant with $P(X=c)=1$

### [[variance]] of a [[linear map]] of a single [[random variable]]

$$
\mathbb{VAR}[aX + b]=a^2\mathbb{VAR}[X]
$$
proof
$$
\begin{split}
\mathbb{VAR}[aX + b]&=\mathbb{E}\left[\left(aX + b-\mathbb{E}[aX + b]\right)^2\right] \\
&=\mathbb{E}\left[\left(aX + b -b -a\mathbb{E}[X ]\right)^2\right] \\
&=a^2\mathbb{E}\left[\left(X  -\mathbb{E}[X ]\right)^2\right] \\
&= a^2\mathbb{VAR}[X]
\end{split}
$$

it follows that $\mathbb{VAR}[-X]=(-1)^2\mathbb{VAR}[X] = \mathbb{VAR}[X]$

### [[variance]] of the sum of [[stochastic independent]] [[random variable|random variables]]

$$
\mathbb{VAR}\left[\sum_{i=1}^n X_i\right]=\sum_{i=1}^n  \mathbb{VAR}\left[ X_i\right]
$$
proof for $n=2$
$$
\begin{split}
\mathbb{VAR}[X_1 + X_2]&=\mathbb{E}\left[\left(X_1 + X_2-\mathbb{E}[X_1 + X_2]\right)^2\right] \\
&=\mathbb{E}\left[\left(X_1 + X_2-\mathbb{E}[X_1] - \mathbb{E}[X_2]\right)^2\right]  \\
&=\mathbb{E}\left[\left(\left(X_1 -\mathbb{E}[X_1]) + (X_2 - \mathbb{E}[X_2]\right)\right)^2\right]  \\
&=\mathbb{E}\left[\left(X_1 -\mathbb{E}[X_1])^2 + (X_2 - \mathbb{E}[X_2]\right)^2 + 2 \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right]  \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{E}\left[ \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{E}\left[ X_1X_2 +\mathbb{E}[X_1]\mathbb{E}[X_2] - X_1\mathbb{E}[X_2] - X_2\mathbb{E}[X_1]\right] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\left(\mathbb{E}\left[ X_1X_2 \right] + \mathbb{E}[X_1]\mathbb{E}[X_2] - \mathbb{E}[X_1X_2] - \mathbb{E}[X_1X_2] \right) \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\left(\mathbb{E}\left[ X_1X_2 \right] - \mathbb{E}[X_1X_2]  \right) \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{COVAR}[X_1,X_2] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] \\
\end{split}
$$
### [[variance]] of a [[linear map]] of a multiple [[linear independent]] [[random variable|random variables]]
With $\mathbb{VAR}[aX + b]=a^2\mathbb{VAR}[X]$ and $\mathbb{VAR}\left[\sum_{i=1}^n X_i\right]=\sum_{i=1}^n  \mathbb{VAR}\left[ X_i\right]$ it follows:
$$
\mathbb{VAR}\left[b +\sum_{i=1}^n a_iX_i\right]=\sum_{i=1}^n a_i^2 \mathbb{VAR}\left[ X_i\right]
$$
(no proof)
### [[variance]] of a [[linear map]] of a two [[random variable|random variables]]
$$
\begin{split}
\mathbb{VAR}[aX_1 + bX_2 + c]&=\mathbb{E}\left[\left(aX_1 + bX_2-\mathbb{E}[aX_1 + bX_2]\right)^2\right] \\
&=\mathbb{E}\left[a\left(\left(X_1 -\mathbb{E}[X_1]) + b(X_2 - \mathbb{E}[X_2]\right)\right)^2\right]  \\
&=\mathbb{E}\left[a^2\left(X_1 -\mathbb{E}[X_1])^2 + b^2(X_2 - \mathbb{E}[X_2]\right)^2 + 2ab \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right]  \\
&= a^2\mathbb{VAR}[X_1] + b^2\mathbb{VAR}[X_2] + 
2ab\mathbb{COVAR}[X_1,X_2] \\

\end{split}
$$
### [[variance]] of the sum of multiple [[random variable|random variables]]
$$
\begin{split}
\mathbb{VAR}\left[\sum_{i=1}^n X_i\right]
&=\mathbb{COVAR}\left[ \sum_{i=1}^nX_i, \sum_{i=1}^n X_i\right] \\
&=\sum_{i=1}^n\sum_{j=1}^n  \mathbb{COVAR}\left[ X_i, X_j\right] \\
&=\sum_{i=1}^n \mathbb{VAR}\left[\sum_{i=1}^n X_i\right] + \sum_{i=1}^n\sum_{j=1, i\neq j}^n  \mathbb{COVAR}\left[ X_i, X_j\right] \\
&=\sum_{i=1}^n \mathbb{VAR}\left[\sum_{i=1}^n X_i\right] + 2\sum_{i=1}^n\sum_{j=i + 1}^n  \mathbb{COVAR}\left[ X_i, X_j\right] \\
\end{split}
$$
# anki

START
Basic
definition of variance 
Back: 
- [[expectation|expectation]] of the squared deviation of a [[discrete random variable]] from its mean
- measure of how for a [[random variable]] spreads out
- the square root of the [[variance]] is the [[standard deviation]] $\sigma$

$$
\mathbb{VAR}[X]=\mathbb{E}[(X-\mathbb{E}[X])^2]=\mathbb{E}[X^2]-\mathbb{E}[X]^2 = \sigma_X^2
$$

(variance of a set of [[observations]] see [[sample variance]])
Tags: mathematics statistics
<!--ID: 1661928261918-->
END

START
Basic
properties of the variance (6)
Back: 
## Definition
- [[expectation|expectation]] of the squared deviation of a [[discrete random variable]] from its mean
- measure of how for a [[random variable]] spreads out
- the square root of the [[variance]] is the [[standard deviation]] $\sigma$

$$
\mathbb{VAR}[X]=\mathbb{E}[(X-\mathbb{E}[X])^2]=\mathbb{E}[X^2]-\mathbb{E}[X]^2 = \sigma_X^2
$$

(variance of a set of [[observations]] see [[sample variance]])

## properties
### Non negativity 
$$
\mathbb{VAR}[X] \geq 0
$$

### [[variance]] of a constant
$\mathbb{VAR}[X] = 0$ $\Leftrightarrow$ $X$ is a constant with $P(X=c)=1$

### [[variance]] of a [[linear map]] of a single [[random variable]]

$$
\mathbb{VAR}[aX + b]=a^2\mathbb{VAR}[X]
$$
proof
$$
\begin{split}
\mathbb{VAR}[aX + b]&=\mathbb{E}\left[\left(aX + b-\mathbb{E}[aX + b]\right)^2\right] \\
&=\mathbb{E}\left[\left(aX + b -b -a\mathbb{E}[X ]\right)^2\right] \\
&=a^2\mathbb{E}\left[\left(X  -\mathbb{E}[X ]\right)^2\right] \\
&= a^2\mathbb{VAR}[X]
\end{split}
$$

it follows that $\mathbb{VAR}[-X]=(-1)^2\mathbb{VAR}[X] = \mathbb{VAR}[X]$

### [[variance]] of the sum of [[stochastic independent]] [[random variable|random variables]]

$$
\mathbb{VAR}\left[\sum_{i=1}^n X_i\right]=\sum_{i=1}^n  \mathbb{VAR}\left[ X_i\right]
$$
proof for $n=2$
$$
\begin{split}
\mathbb{VAR}[X_1 + X_2]&=\mathbb{E}\left[\left(X_1 + X_2-\mathbb{E}[X_1 + X_2]\right)^2\right] \\
&=\mathbb{E}\left[\left(X_1 + X_2-\mathbb{E}[X_1] - \mathbb{E}[X_2]\right)^2\right]  \\
&=\mathbb{E}\left[\left(\left(X_1 -\mathbb{E}[X_1]) + (X_2 - \mathbb{E}[X_2]\right)\right)^2\right]  \\
&=\mathbb{E}\left[\left(X_1 -\mathbb{E}[X_1])^2 + (X_2 - \mathbb{E}[X_2]\right)^2 + 2 \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right]  \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{E}\left[ \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{E}\left[ X_1X_2 +\mathbb{E}[X_1]\mathbb{E}[X_2] - X_1\mathbb{E}[X_2] - X_2\mathbb{E}[X_1]\right] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\left(\mathbb{E}\left[ X_1X_2 \right] + \mathbb{E}[X_1]\mathbb{E}[X_2] - \mathbb{E}[X_1X_2] - \mathbb{E}[X_1X_2] \right) \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\left(\mathbb{E}\left[ X_1X_2 \right] - \mathbb{E}[X_1X_2]  \right) \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{COVAR}[X_1,X_2] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] \\
\end{split}
$$
### [[variance]] of a [[linear map]] of a multiple [[linear independent]] [[random variable|random variables]]
With $\mathbb{VAR}[aX + b]=a^2\mathbb{VAR}[X]$ and $\mathbb{VAR}\left[\sum_{i=1}^n X_i\right]=\sum_{i=1}^n  \mathbb{VAR}\left[ X_i\right]$ it follows:
$$
\mathbb{VAR}\left[b +\sum_{i=1}^n a_iX_i\right]=\sum_{i=1}^n a_i^2 \mathbb{VAR}\left[ X_i\right]
$$
(no proof)
### [[variance]] of a [[linear map]] of a two[[random variable|random variables]]
$$
\begin{split}
\mathbb{VAR}[aX_1 + bX_2 + c]&=\mathbb{E}\left[\left(aX_1 + bX_2-\mathbb{E}[aX_1 + bX_2]\right)^2\right] \\
&=\mathbb{E}\left[a\left(\left(X_1 -\mathbb{E}[X_1]) + b(X_2 - \mathbb{E}[X_2]\right)\right)^2\right]  \\
&=\mathbb{E}\left[a^2\left(X_1 -\mathbb{E}[X_1])^2 + b^2(X_2 - \mathbb{E}[X_2]\right)^2 + 2ab \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right]  \\
&= a^2\mathbb{VAR}[X_1] + b^2\mathbb{VAR}[X_2] + 
2ab\mathbb{COVAR}[X_1,X_2] \\

\end{split}
$$

Tags: mathematics statistics
<!--ID: 1661928261919-->
END


START
Basic
[[variance]]
- Non negativity 
- [[variance]] of a constant
Back: 
### Non negativity 
$$
\mathbb{VAR}[X] \geq 0
$$

### [[variance]] of a constant
$\mathbb{VAR}[X] = 0$ $\Leftrightarrow$ $X$ is a constant with $P(X=c)=1$
Tags: mathematics statistics
<!--ID: 1673776307106-->
END


START
Basic
[[variance]] of a [[linear map]] of a single [[random variable]] (with proof)
Back: 

$$
\mathbb{VAR}[aX + b]=a^2\mathbb{VAR}[X]
$$
proof
$$
\begin{split}
\mathbb{VAR}[aX + b]&=\mathbb{E}\left[\left(aX + b-\mathbb{E}[aX + b]\right)^2\right] \\
&=\mathbb{E}\left[\left(aX + b -b -a\mathbb{E}[X ]\right)^2\right] \\
&=a^2\mathbb{E}\left[\left(X  -\mathbb{E}[X ]\right)^2\right] \\
&= a^2\mathbb{VAR}[X]
\end{split}
$$

it follows that $\mathbb{VAR}[-X]=(-1)^2\mathbb{VAR}[X] = \mathbb{VAR}[X]$
Tags: mathematics statistics
<!--ID: 1673776307109-->
END



START
Basic
[[variance]] of the sum of [[stochastic independent]] [[random variable|random variables]] (with proof)
Back: 


$$
\mathbb{VAR}\left[\sum_{i=1}^n X_i\right]=\sum_{i=1}^n  \mathbb{VAR}\left[ X_i\right]
$$
proof for $n=2$
$$
\begin{split}
\mathbb{VAR}[X_1 + X_2]&=\mathbb{E}\left[\left(X_1 + X_2-\mathbb{E}[X_1 + X_2]\right)^2\right] \\
&=\mathbb{E}\left[\left(X_1 + X_2-\mathbb{E}[X_1] - \mathbb{E}[X_2]\right)^2\right]  \\
&=\mathbb{E}\left[\left(\left(X_1 -\mathbb{E}[X_1]) + (X_2 - \mathbb{E}[X_2]\right)\right)^2\right]  \\
&=\mathbb{E}\left[\left(X_1 -\mathbb{E}[X_1])^2 + (X_2 - \mathbb{E}[X_2]\right)^2 + 2 \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right]  \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{E}\left[ \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{E}\left[ X_1X_2 +\mathbb{E}[X_1]\mathbb{E}[X_2] - X_1\mathbb{E}[X_2] - X_2\mathbb{E}[X_1]\right] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\left(\mathbb{E}\left[ X_1X_2 \right] + \mathbb{E}[X_1]\mathbb{E}[X_2] - \mathbb{E}[X_1X_2] - \mathbb{E}[X_1X_2] \right) \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\left(\mathbb{E}\left[ X_1X_2 \right] - \mathbb{E}[X_1X_2]  \right) \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{COVAR}[X_1,X_2] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] \\
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1673776307111-->
END


START
Basic
[[variance]] of a [[linear map]] of a multiple [[linear independent]] [[random variable|random variables]]
- no proof but 
Back: 
With $\mathbb{VAR}[aX + b]=a^2\mathbb{VAR}[X]$ and $\mathbb{VAR}\left[\sum_{i=1}^n X_i\right]=\sum_{i=1}^n  \mathbb{VAR}\left[ X_i\right]$ it follows:
$$
\mathbb{VAR}\left[b +\sum_{i=1}^n a_iX_i\right]=\sum_{i=1}^n a_i^2 \mathbb{VAR}\left[ X_i\right]
$$
(no proof but proof idea)
Tags: mathematics statistics
<!--ID: 1673776307114-->
END

START
Basic
[[variance]] of a [[linear map]] of a two [[random variable|random variables]] (with proof)
Back: 
$$
\begin{split}
\mathbb{VAR}[aX_1 + bX_2 + c]&=\mathbb{E}\left[\left(aX_1 + bX_2-\mathbb{E}[aX_1 + bX_2]\right)^2\right] \\
&=\mathbb{E}\left[a\left(\left(X_1 -\mathbb{E}[X_1]) + b(X_2 - \mathbb{E}[X_2]\right)\right)^2\right]  \\
&=\mathbb{E}\left[a^2\left(X_1 -\mathbb{E}[X_1])^2 + b^2(X_2 - \mathbb{E}[X_2]\right)^2 + 2ab \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right]  \\
&= a^2\mathbb{VAR}[X_1] + b^2\mathbb{VAR}[X_2] + 
2ab\mathbb{COVAR}[X_1,X_2] \\

\end{split}
$$

Tags: mathematics statistics
<!--ID: 1674378389862-->
END


START
Basic
[[variance]] of the sum of multiple [[random variable|random variables]] (general case)
Back: 

$$
\begin{split}
\mathbb{VAR}\left[\sum_{i=1}^n X_i\right]
&=\mathbb{COVAR}\left[ \sum_{i=1}^nX_i, \sum_{i=1}^n X_i\right] \\
&=\sum_{i=1}^n\sum_{j=1}^n  \mathbb{COVAR}\left[ X_i, X_j\right] \\
&=\sum_{i=1}^n \mathbb{VAR}\left[\sum_{i=1}^n X_i\right] + \sum_{i=1}^n\sum_{j=1, i\neq j}^n  \mathbb{COVAR}\left[ X_i, X_j\right] \\
&=\sum_{i=1}^n \mathbb{VAR}\left[\sum_{i=1}^n X_i\right] + 2\sum_{i=1}^n\sum_{j=i + 1}^n  \mathbb{COVAR}\left[ X_i, X_j\right] \\
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1674378389865-->
END