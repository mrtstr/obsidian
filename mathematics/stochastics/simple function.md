### simple function
- given a [[measurable space]] $(\Omega, \mathcal{A})$ and $k$ pairwise [[disjoint]] sets $A_1, ..., A_k \in \mathcal{A}$ and $k$ values $c_1, ..., c_k \in \mathbb{R}$ 
- a [[simple function]] is a function $f: \Omega \to \mathbb{R}$ with the following form

$$
f(\omega) = \sum_{i=1}^k c_i \mathbb{I}[\omega \in A_i]
$$

- all $\omega \in \Omega$ outside $A_1, ..., A_k$ take the value $0$

### measuring simple functions
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and a [[simple function]] $f: \Omega \to \mathbb{R}$ 
- then $f$ can be measured with respect to $\mathbb{P}$ like the following

$$
\int_\Omega f(\omega) d\mathbb{P}(\omega) = \sum_{i=1}^k c_i \mathbb{P}(A_i)
$$

### approximating measurable functions with simple functions
- given a non-negative [[measurable function]] $g:\Omega \to [0, \infty]$ like a [[probability density function (PDF)]] or a [[loss functions]]
- $g$ can be approximated by a sequence of [[simple function]]

TODO add details
# -------------

![[measurable function#measurable function]]

# anki

START
Basic
[[simple function]]
- definition
- how to measure them
- common application

Back: 
### simple function
- given a [[measurable space]] $(\Omega, \mathcal{A})$ and $k$ pairwise [[disjoint]] sets $A_1, ..., A_k \in \mathcal{A}$ and $k$ values $c_1, ..., c_k \in \mathbb{R}$ 
- a [[simple function]] is a function $f: \Omega \to \mathbb{R}$ with the following form

$$
f(\omega) = \sum_{i=1}^k c_i \mathbb{I}[\omega \in A_i]
$$

- all $\omega \in \Omega$ outside $A_1, ..., A_k$ take the value $0$

### measuring simple functions
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and a [[simple function]] $f: \Omega \to \mathbb{R}$ 
- then $f$ can be measured with respect to $\mathbb{P}$ like the following

$$
\int_\Omega f(\omega) d\mathbb{P}(\omega) = \sum_{i=1}^k c_i \mathbb{P}(A_i)
$$

### approximating measurable functions with simple functions
- given a non-negative [[measurable function]] $g:\Omega \to [0, \infty]$ like a [[probability density function (PDF)]] or a [[loss functions]]
- $g$ can be approximated by a sequence of [[simple function]]


__________________
### probability measure
- given a [[measurable space]] $(\Omega, \mathcal{A})$ of a [[set]] $\Omega$ equiped with a [[sigma algebra]] $\mathcal{A}$ a [[function]] $P: \mathcal{A} \mapsto [0,1]$ is a [[probability measure]]
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

### measurable space
- a [[measurable space]] $\left(\Omega,\mathcal{A} )\right)$ is a [[set]] $\Omega$ equipped with a [[sigma algebra]] $\mathcal{A}$
- every [[probability space]] is by definition a [[measurable space]]

Tags: mathematics statistics SS25
<!--ID: 1745771490761-->
END