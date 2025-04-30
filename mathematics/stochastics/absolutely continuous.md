### absolutely continuous
- given two [[measure]] $\mathcal{P}$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
- $\mathcal{P}$ is [[absolutely continuous]] to $\lambda$ written as $\mathcal{P} \ll \lambda$ if the following is hold for all $A \in \mathcal{A}$

$$
\lambda(A) = 0 \quad \Rightarrow \quad \mathcal{P}(A) = 0
$$

- in other words: $\mathcal{P}$ does not assign probabilities to sets that $\lambda$ considers zero
- in this case $\mathcal{P}$ can be described as a scaled version of $\lambda$ see ([[radon nikodym theorem]])

# ----------
![[radon nikodym theorem#radon nikodym theorem]]


# anki

# anki

START
Basic
[[absolutely continuous]]
- definition
- intuition
- common application

Back: 
### absolutely continuous
- given two [[measure]] $\mathcal{P}$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
- $\mathcal{P}$ is [[absolutely continuous]] to $\lambda$ written as $\mathcal{P} \ll \lambda$ if the following is hold for all $A \in \mathcal{A}$

$$
\lambda(A) = 0 \quad \Rightarrow \quad \mathcal{P}(A) = 0
$$

- in other words: $\mathcal{P}$ does not assign probabilities to sets that $\lambda$ considers zero
- in this case $\mathcal{P}$ can be described as a scaled version of $\lambda$ see ([[radon nikodym theorem]])

__________________

### radon nikodym theorem
- given two [[measure]]  $\nu$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
- $\nu$ is [[absolutely continuous]] to $\lambda$ which means $\lambda(A) = 0 \Rightarrow \nu(A) = 0$
- this means that $\nu$ is just a scaled version of $\lambda$ and there exists a function $f=\frac{d\nu}{d\lambda}$ that compensates for that

$$
\begin{split}
\mathbb{\nu}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\nu \\
&= \int_A  d\nu \\

&= \int_A \frac{d\nu}{d\lambda} d\lambda \\
\end{split}
$$

#### intuition
- intuitively f answers how dense $\nu$ is to $\lambda$ at each point $\omega$ 

#### common application
- when $\lambda$ is a [[lebesgue measure]] on $\mathbb{R}^n$ $\nu$ is a [[probability measure]] of a [[random variable]]
- then $f$ is the [[probability density function (PDF)]] of $X$
- In this setting, computing probabilities becomes an [[riemann integral]]

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

### measurable space
- a [[measurable space]] $\left(\Omega,\mathcal{A} )\right)$ is a [[set]] $\Omega$ equipped with a [[sigma algebra]] $\mathcal{A}$
- every [[probability space]] is by definition a [[measurable space]]

Tags: mathematics statistics SS25
<!--ID: 1745742964856-->
END
