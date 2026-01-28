## information theory
- Information theory provides a **different perspective on probability**:  instead of describing _how likely_ events are, it describes _how much information_ their occurrence conveys.
- given a [[channel]] $X$ which is equivalent to a [[random variable]] 
- $X$ can take one value of the [[set]] $\Omega = \{p_1, ..., p_n\}$ with $\Omega$ being equivalent to the [[sample space]] of $X$
- each possible outcome $p_i$ is called a [[signal]] and has a certain [[information content]]


### example: letters in a text channel
- Suppose a message is transmitted through a text [[channel]] where each **letter** is a [[signal]] emitted by the source $X$.
- You already know from experience (or statistics) that some letters occur much more often than others — e.g. the letter **“e”** is very frequent in English.
- When you observe a **rare** letter such as **“q”** or **“z”**, that outcome was _less probable_ under your prior knowledge.  
    →therefore it has a **higher [[information content]]** — it tells you something unexpected about the message source.
- Conversely, observing a very **common** letter (like “e”) hardly changes your belief — it confirms what you already expected, and thus carries **low [[information content]]**.
# ----------

![[information content#information content]]

![[random variable#random variable]]

![[probability measure#probability measure]]




# anki

START
Basic
[[information theory]]
- general concept and comparison to the statistical perceptive
- what is a [[channel]] and a [[signal]]
- example: letters in a text channel

Back: 
## information theory
- Information theory provides a **different perspective on probability**:  instead of describing _how likely_ events are, it describes _how much information_ their occurrence conveys.
- given a [[channel]] $X$ which is equivalent to a [[random variable]] 
- $X$ can take one value of the [[set]] $\Omega = \{p_1, ..., p_n\}$ with $\Omega$ being equivalent to the [[sample space]] of $X$
- each possible outcome $p_i$ is called a [[signal]] and has a certain [[information content]]


### example: letters in a text channel
- Suppose a message is transmitted through a text [[channel]] where each **letter** is a [[signal]] emitted by the source $X$.
- You already know from experience (or statistics) that some letters occur much more often than others — e.g. the letter **“e”** is very frequent in English.
- When you observe a **rare** letter such as **“q”** or **“z”**, that outcome was _less probable_ under your prior knowledge.  
    →therefore it has a **higher [[information content]]** — it tells you something unexpected about the message source.
- Conversely, observing a very **common** letter (like “e”) hardly changes your belief — it confirms what you already expected, and thus carries **low [[information content]]**.
### information content
- let $X$ be a discrete [[random variable]] = [[channel]] with a [[sample space]] $\Omega=\{p_1, ..., p_N\}$ with each possible outcome is called a [[signal]]
- each signal $\mathbb{P}(X=p_i)$ has a [[probability]] or relative frequency
- let $I(A)$ be a function that measures the [[information content]] of an [[event]] $A \in \mathcal{P}(\Omega)$ that satisfies the following conditions

1) **non-negativity and certainty**: $I(A) \geq 0$ with $I(A) = 0$ if and only if $\mathbb{P}(A) = 1$
2) **monotonicity**:  $\mathbb{P}(A) \geq \mathbb{P}(B) \Leftrightarrow I(A) \leq I(B)$
3) **additivity for independent events**if $A$ and $B$ are [[stochastic independent]] then $I(A \cap B) = I(A) + I(B)$

- only the following function satisfies all 3 conditions

$$
I(A) = \log\left(\frac{1}{\mathbb{P}(A)}\right)
$$

### random variable
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ 

$$
\forall C \in \mathcal{B}(\mathbb{R}): X^{-1}(C) = \{\omega \in \Omega : X(\omega) \in C\} \in \mathcal{A}
$$

- this is the case exactly when the following is true (given the [[inverse function]] $X^{-1}: \mathbb{R} \to \Omega$)

$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
$$



### probability measure
- given a [[measurable space]] $(\Omega, \mathcal{A})$ of a [[set]] $\Omega$ equipped with a [[sigma algebra]] $\mathcal{A}$ a [[function]] $P: \mathcal{A} \mapsto [0,1]$ is a [[probability measure]]
$$
P: \mathcal{A} \mapsto [0,1]
$$
- the probability of the [[empty set]] is zero

$$
\begin{split}
P(\emptyset) = 0 \\
\end{split}
$$
- the [[probability]] of the [[sample space]] is one
$$
\begin{split}
P(\Omega) = 1 \\
\end{split}
$$
- given a [[countable]] collection of [[mathematics/basics/disjoint]] events $(A_n)_{n \in \mathbb{N}}$ 
$$
\begin{split}
P\left(\bigcup_{i \in \mathbb{N}} A_i \right) = \sum_{i \in \mathbb{N}} P(A_i) \\
\end{split}
$$


Tags: mathematics WS2526 ml
<!--ID: 1762701434630-->
END
