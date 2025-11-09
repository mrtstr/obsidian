## information content
- let $X$ be a discrete [[random variable]] = [[channel]] with a [[sample space]] $\Omega=\{p_1, ..., p_N\}$ with each possible outcome is called a [[signal]]
- each signal $\mathbb{P}(X=p_i)$ has a [[probability]] or relative frequency
- let $I(A)$ be a function that measures the [[information content]] of an [[event]] $A \in \mathcal{P}(\Omega)$ that satisfies the following conditions

1) **non-negativity and certainty**: $I(A) \geq 0$ with $I(A) = 0$ if and only if $\mathbb{P}(A) = 1$
2) **monotonicity**:  $\mathbb{P}(A) \geq \mathbb{P}(B) \Leftrightarrow I(A) \leq I(B)$
3) **additivity for independent events**if $A$ and $B$ are [[stochastic independent]] then $I(A \cup B) = I(A) + I(B)$

- only the following function satisfies all 3 conditions

$$
I(A) = \log\left(\frac{1}{\mathbb{P}(A)}\right)
$$

# anki

START
Basic
[[information content]]
- definition
- 3 base properties

Back: 

## information content
- let $X$ be a discrete [[random variable]] = [[channel]] with a [[sample space]] $\Omega=\{p_1, ..., p_N\}$ with each possible outcome is called a [[signal]]
- each signal $\mathbb{P}(X=p_i)$ has a [[probability]] or relative frequency
- let $I(A)$ be a function that measures the [[information content]] of an [[event]] $A \in \mathcal{P}(\Omega)$ that satisfies the following conditions

1) **non-negativity and certainty**: $I(A) \geq 0$ with $I(A) = 0$ if and only if $\mathbb{P}(A) = 1$
2) **monotonicity**:  $\mathbb{P}(A) \geq \mathbb{P}(B) \Leftrightarrow I(A) \leq I(B)$
3) **additivity for independent events**if $A$ and $B$ are [[stochastic independent]] then $I(A \cup B) = I(A) + I(B)$

- only the following function satisfies all 3 conditions

$$
I(A) = \log\left(\frac{1}{\mathbb{P}(A)}\right)
$$


Tags: mathematics WS2526 ml
END


START
Basic
[[information content]] and [[entropy]]
- how are they related
Back: 

## information content
- let $X$ be a discrete [[random variable]] = [[channel]] with a [[sample space]] $\Omega=\{p_1, ..., p_N\}$ with each possible outcome is called a [[signal]]
- each signal $\mathbb{P}(X=p_i)$ has a [[probability]] or relative frequency
- let $I(A)$ be a function that measures the [[information content]] of an [[event]] $A \in \mathcal{P}(\Omega)$ that satisfies the following conditions

1) **non-negativity and certainty**: $I(A) \geq 0$ with $I(A) = 0$ if and only if $\mathbb{P}(A) = 1$
2) **monotonicity**:  $\mathbb{P}(A) \geq \mathbb{P}(B) \Leftrightarrow I(A) \leq I(B)$
3) **additivity for independent events**if $A$ and $B$ are [[stochastic independent]] then $I(A \cup B) = I(A) + I(B)$

- only the following function satisfies all 3 conditions

$$
I(A) = \log\left(\frac{1}{\mathbb{P}(A)}\right)
$$

## entropy
- measure of the **average [[information content]]** $I$ contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
\begin{split}
H(X) 
&= \mathbb{E}\left[-\log\left(p_X(X)\right)\right]  \\
&= - \sum p_X(x_i) \log\left(p_X(x_i)\right) \\
&= \mathbb{E}\left[I(X)\right]
\end{split}
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$
##### example
- [[bernoulli distribution]] with $p=0.9$ and $p=0.5$
- We see that the entropy is **higher** when $p=0.5$, indicating that this outcome is **more uncertain** and thus contains **more information per observation**.

$$
\begin{split}
H(X) &= - 0.1 \cdot \log_2(0.1) - 0.9 \cdot \log_2(0.9) = 0.33 + 0.14 = 0.47 \\
H(X) &= - 0.5 \cdot \log_2(0.5) - 0.5 \cdot \log_2(0.5) = \frac{1}{2} + \frac{1}{2} = 1 \\
\end{split}
$$


Tags: mathematics WS2526 ml
END
