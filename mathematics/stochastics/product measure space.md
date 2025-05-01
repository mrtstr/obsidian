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

### lebesgue measure
- the [[lebesgue measure]] is a [[measure]] that assigns size, length or volume to sets
- similar but more flexible than the [[riemann integral]] (in $\mathbb{R}^n$ they are interchangeable)
- for higher dimensions the [[lebesgue measure]] $\lambda^n: \mathcal{B} ({\mathbb{R}^n}) \to [0, \infty)$ forms a [[product measure space]] using the [[catesian product]]  over the dimensions of $\mathbb{R}$ 

$$
\begin{split}
\lambda([a,b]) 
&= \int_a^b1 \: d\lambda(x)  &\text{(length of an interval)} \\
&= b-a   \\
\lambda^2 ([a_1,b_1] \times [a_2,b_2])
&= \int_{[a_1,b_1] \times [a_2,b_2]}1 \: d\lambda(x_1, x_2) &\text{(volumn of a box)} \\ 
&= \int_{a_1}^{b_1} \int_{a_2}^{b_2} 1 \, d\lambda^1(y) \, d\lambda^1(x) \\
&= \int_{a_1}^{b_1}\int_{a_2}^{b_2}1 \: dx_1dx_2  \\
&= (b_1-a_1)(b_2-a_2)  \\
&= \lambda([a_1,b_1])\lambda([a_2,b_2])  \\
\lambda^n\left( \bigtimes_{i=1}^n [a_i, b_i] \right)
&= \int_{\bigtimes_{i=1}^n [a_i, b_i]} 1 \, d\lambda^n(x_1, \dots, x_n) & \text{(volume of an $n$-box)} \\
&= \int_{a_1}^{b_1} \cdots \int_{a_n}^{b_n} 1 \, d\lambda^1(x_n) \cdots d\lambda^1(x_1) \\
&= \prod_{i=1}^n (b_i - a_i) \\
&= \prod_{i=1}^n \lambda([a_i,b_i]) 
\end{split}
$$
### product probability space
- given the [[probability space|probability spaces]] $(\Omega_1, \mathcal{A}_1, \mathbb{P}_1)$ and $(\Omega_2, \mathcal{A}_2, \mathbb{P}_2)$
- we can construct a [[product probability space]] $(\Omega_1 \times \Omega_2, \mathcal{A}_1  \otimes \mathcal{A}_2 , \mathbb{P}_1 \otimes \mathbb{P}_2)$

$$
\mathcal{A}_1  \otimes \mathcal{A}_2 = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\}
$$

$$
\begin{split}
\mathbb{P}_1 \otimes \mathbb{P}_2=\mathbb{P}(A_1 \times A_2) = \mathbb{P}(A_1)\mathbb{P}(A_2)
\end{split}
$$


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