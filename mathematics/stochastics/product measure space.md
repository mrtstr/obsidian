### product measure space
- given the [[measurable space]] $(\Omega_1, \mathcal{A}_1, \mu_1)$ and $(\Omega_2, \mathcal{A}_2, \mu_2)$
- we can construct a [[product measure space]] $(\Omega_1 \times \Omega_2, \mathcal{A}_1  \otimes \mathcal{A}_2 , \mu_1 \otimes \mu_2)$

$$
\mathcal{A}_1  \otimes \mathcal{A}_2 = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\}
$$

$$
\begin{split}
\mu_1 \otimes \mu_2=\mu(A_1 \times A_2) = \mu(A_1)\mu(A_2)
\end{split}
$$

- [[stochastic independent]] [[random variable]] form a [[product probability space]]
- the [[lebesgue measure]] $\lambda^n: \mathcal{B} ({\mathbb{R}^n}) \to [0, \infty)$ is a product measure over the dimensions if $\mathbb{R}$

# anki

START
Basic
[[product measure space]]
- definition
- 2 examples

Back: 
### product measure space
- given the [[measurable space]] $(\Omega_1, \mathcal{A}_1, \mu_1)$ and $(\Omega_2, \mathcal{A}_2, \mu_2)$
- we can construct a [[product measure space]] $(\Omega_1 \times \Omega_2, \mathcal{A}_1  \otimes \mathcal{A}_2 , \mu_1 \otimes \mu_2)$

$$
\mathcal{A}_1  \otimes \mathcal{A}_2 = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\}
$$

$$
\begin{split}
\mu_1 \otimes \mu_2=\mu(A_1 \times A_2) = \mu(A_1)\mu(A_2)
\end{split}
$$

- [[stochastic independent]] [[random variable]] form a [[product probability space]]
- the [[lebesgue measure]] $\lambda^n: \mathcal{B} ({\mathbb{R}^n}) \to [0, \infty)$ is a product measure over the dimensions if $\mathbb{R}$
__________________
### measure
- given a [[measurable space]] $(\Omega, \mathcal{A})$ of a [[set]] $\Omega$ equipped with a [[sigma algebra]] $\mathcal{A}$ a [[function]] $\lambda: \mathcal{A} \mapsto \mathbb{R}$ is a [[measure]] if the following holds true

- the probability of the [[empty set]] is zero and can't be negative

$$
\begin{split}
\lambda(\emptyset) = 0 \\
\lambda(A) \geq 0 \\
\end{split}
$$

- given a [[countable]] collection of [[mathematics/basics/disjoint]] events $(A_n)_{n \in \mathbb{N}}$ with $A_n \in \mathcal{A}$ 

$$
\begin{split}
\lambda\left(\bigcup_{i \in \mathbb{N}} A_i \right) = \sum_{i \in \mathbb{N}} \lambda(A_i) \\
\end{split}
$$

- $\lambda$ is normalized in a sense that  $\lambda(\Omega) = 1$ it's a [[probability measure]]
- one important example is the [[lebesgue measure]] which describes the column of sets

- the following notations are equivalent

$$
\lambda(A) = \int_A 1 \:d\lambda
$$

### lebesgue measure
- the [[lebesgue measure]] is a way to assign a "size" or "length" to subsets of the $\mathbb{R}^n$ 
- for intervals in the $\mathbb{R}^n$ it is defined as follows, but there also exists a definition for a general subset

$$
\begin{split}
\lambda([a,b]) &= b-a  &\text{(length of an interval)} \\
\lambda([a_1,b_1] \times [a_2,b_2]) &= (b_1-a_1)(b_2-a_2) &\text{(volumn of a box)} \\
\lambda\left( \bigtimes_{i \in [n]} [a_i,b_i] \right) &= \prod_{i \in [n]}(b_i-a_i) &\text{(volumn of a n-box)} \\
\end{split}
$$


- in a **discrete** setting (countable sets), a measure can be defined by a sum:

$$
\begin{split}
\mathbb{\lambda}(A) 
&= \sum_{\omega \in A}  \lambda(\{\omega\}) \\
\end{split}
$$

- in the continuous case thus, we **must use integration** instead of summation
$$
\begin{split}
\lambda(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\lambda(\omega) \\
&= \int_A  d\lambda(\omega) \\
\end{split}
$$

- in $\mathbb{R}^n$ the [[lebesgue measure]] and the [[riemann integral]] are the same because they agree on length


$$
\begin{split}
\mathbb{\lambda}([a,b]) 
&= \int_{[a, b]}  d\lambda(\omega) = b - a\\
\end{split}
$$


- for an interval $[a,b]$ and a regular function $g$:

$$
\begin{split}
\int_{[a, b]} g(\omega)  d\lambda(\omega) = \int_a^b g(\omega)  d\omega\\
\end{split}
$$
### lebesgue measures for probability
- on a [[measurable space]] $\left(\Omega,\mathcal{A} \right)$ the [[lebesgue measure]] $\lambda$ is a [[probability measure]] if $\lambda(\Omega)=1$
- on a finite $\Omega$ we can define a [[probability measure]] by rescaling
$$
\lambda_p(A) = \frac{\lambda(A)}{\lambda(\Omega)}
$$

- on infinite sets $\Omega$ we need a [[probability density function (PDF)]] $p: \Omega \to \mathbb{R}^n$ that decays fast enough such that

$$
\begin{split}
\mathbb{\lambda}(\Omega) 
&= \int_{\Omega} p(\omega)  d\lambda(\omega) =1\\

\end{split}
$$

$$
\begin{split}
\mathbb{\lambda}([a,b]) 
&= \int_{[a, b]} p(\omega) d\lambda(\omega) = b - a\\
\end{split}
$$


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
<!--ID: 1746006343530-->
END