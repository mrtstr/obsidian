### empirical distribution of a dataset
- given a dataset $\mathcal{D} \subset \mathbb{R}^d=\{x_1, ..., x_n\}$
- the [[empirical distribution of a dataset]] $\mathbb{\hat P}_n$ is a [[probability measure]] that puts equal weight on each data point and can be formalized with the [[dirac measure]]  

$$
\mathbb{\hat P}_n = \frac{1}{n} \sum_{i=1}^n \delta_{x_i}
$$
- thus any $A \subset \mathbb{R}^d$ can be measured with respect to $\mathbb{\hat P}_n$

$$
\mathbb{\hat P}_n(A) = \frac{1}{n} \sum_{i=1}^n \delta_{x_i}(A) = \frac{|A \cap \mathcal{D}|}{n}
$$

# -----------------------

![[dirac measure#dirac measure]]


# anki

START
Basic
- mathematical formulation of the [[empirical distribution of a dataset]]
- how to measure the probability of a set

Back: 
### empirical distribution of a dataset
- given a dataset $\mathcal{D} \subset \mathbb{R}^d=\{x_1, ..., x_n\}$
- the [[empirical distribution of a dataset]] $\mathbb{\hat P}_n$ is a [[probability measure]] that puts equal weight on each data point and can be formalized with the [[dirac measure]]  

$$
\mathbb{\hat P}_n = \frac{1}{n} \sum_{i=1}^n \delta_{x_i}
$$
- thus any $A \subset \mathbb{R}^d$ can be measured with respect to $\mathbb{\hat P}_n$

$$
\mathbb{\hat P}_n(A) = \frac{1}{n} \sum_{i=1}^n \delta_{x_i}(A) = \frac{|A \cap \mathcal{D}|}{n}
$$

__________________

### dirac measure
- given a point $x$ in a [[measurable space]] $(\Omega, \mathcal{A})$ the [[dirac measure]] $\delta_x(A): \mathcal{A} \to \{0,1\}$ is defined as follows

$$
\delta_x(A)=\left\{
\begin{matrix} 
1& \text{if } x \in A  \\
0& \text{if } x \notin A  \\
\end{matrix}\right.
$$

- is a [[probability measure]] because $\delta_x(\Omega)=\int_\Omega d\delta_x = 1$
- is not [[absolutely continuous]] to the [[lebesgue measure]] because $\lambda(\{x\})=0$ but $\delta_x(\{x\})=1$
- if $f$ is a [[measurable function]] on $(\Omega, \mathcal{A})$ then integrating $f$ against $\delta_x$ is equivalent to evaluating $f$ at $x$

$$
\int_\Omega f(\omega) d\delta_x = f(x)
$$

- similar to the indicator function $\mathbb{I}[x \in A]=\delta_x(A)$ 


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
<!--ID: 1745771490765-->
END