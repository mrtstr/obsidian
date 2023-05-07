## Definition
- sum of $n$ [[stochastic independent]] [[bernoulli distribution|bernoulli random valiabels]] with different probabilities $p_1, ..., p_n$ with the indexset $I = \{1,...,n\}$
- generalization of the [[binomial distribution]] where $p$ is the same for all [[bernoulli distribution|bernoulli random valiabels]]
## [[probability function]]
- $M_x$ contains all subsets of the index set $I$ with the [[cardinality]] of $x$
- the [[cardinality]] of $M_x$ is equal to the number of [[combinations]] $|M_x| = {n \choose x}$ and thus is infeasible to calculate
$$
\begin{split}
f_x\left(x | n, \{p_1,...,p_n\}\right) &=\sum_{A \in 
M_x}\prod_{i \in A} p_i \prod_{i \in \bar{A}} 1-p_i \\ \\
M_x &=\left\{A | A \subseteq \{1,...,n\} \cap |A| = x\right\} \\
\bar{A} &= \{1, ..., n\} \setminus A
\end{split}
$$
## [[expectation]]
$$
\mathbb{E}\left[X\right] = \mathbb{E}\left[\sum_{i \in I} X_i\right] = \sum_{i \in I} \mathbb{E}\left[ X_i\right] = \sum_{i \in I} p_i
$$

## [[variance]]
- since the [[random variable|random variables]] are [[stochastic independent]] the
$$
\mathbb{VAR}\left[X\right] = \mathbb{VAR}\left[\sum_{i \in I} X_i\right] = \sum_{i \in I} \mathbb{VAR}\left[ X_i\right] = \sum_{i \in I} p_i (1-p_i)
$$


# anki

START
Basic
[[poission binomial distribution]]
- definition
- [[probability function]]
- [[expectation]]
- [[variance]]
Back: 
## Definition
- sum of $n$ [[stochastic independent]] [[bernoulli distribution|bernoulli random valiabels]] with different probabilities $p_1, ..., p_n$ with the indexset $I = \{1,...,n\}$
- generalization of the [[binomial distribution]] where $p$ is the same for all [[bernoulli distribution|bernoulli random valiabels]]
## [[probability function]]
- $M_x$ contains all subsets of the index set $I$ with the [[cardinality]] of $x$
- the [[cardinality]] of $M_x$ is equal to the number of [[combinations]] $|M_x| = {n \choose x}$ and thus is infeasible to calculate
$$
\begin{split}
f_x\left(x | n, \{p_1,...,p_n\}\right) &=\sum_{A \in 
M_x}\prod_{i \in A} p_i \prod_{i \in \bar{A}} 1-p_i \\ \\
M_x &=\left\{A | A \subseteq \{1,...,n\} \cap |A| = x\right\} \\
\bar{A} &= \{1, ..., n\} \setminus A
\end{split}
$$
## [[expectation]]
$$
\mathbb{E}\left[X\right] = \mathbb{E}\left[\sum_{i \in I} X_i\right] = \sum_{i \in I} \mathbb{E}\left[ X_i\right] = \sum_{i \in I} p_i
$$

## [[variance]]
- since the [[random variable|random variables]] are [[stochastic independent]] the
$$
\mathbb{VAR}\left[X\right] = \mathbb{VAR}\left[\sum_{i \in I} X_i\right] = \sum_{i \in I} \mathbb{VAR}\left[ X_i\right] = \sum_{i \in I} p_i (1-p_i)
$$

Tags: mathematics statistics
<!--ID: 1683480987859-->
END