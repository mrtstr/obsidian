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

# anki

START
Basic
[[dirac measure]]
- definition
- is it a [[probability measure]]? (with proof)
- is it a [[absolutely continuous]]? (with proof)
Back: 

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

__________________

### absolutely continuous
- given two [[probability measure]] $\mathcal{P}$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
- $\mathcal{P}$ is [[absolutely continuous]] to $\lambda$ written as $\mathcal{P} \ll \lambda$ if the following is hold for all $A \in \mathcal{A}$

$$
\lambda(A) = 0 \quad \Rightarrow \quad \mathcal{P}(A) = 0
$$

- in other words: $\mathcal{P}$ does not assign probabilities to sets that $\lambda$ considers zero
- in this case $\mathcal{P}$ can be described as a scaled version of $\lambda$ see ([[radon nikodym theorem]])


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
### radon nikodym theorem
- given two [[probability measure]] $\nu$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
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


### measurable space
- a [[measurable space]] $\left(\Omega,\mathcal{A} )\right)$ is a [[set]] $\Omega$ equipped with a [[sigma algebra]] $\mathcal{A}$
- every [[probability space]] is by definition a [[measurable space]]

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
\lambda^n\left( \bigtimes_{i=1}^n [a_i, b_i] \right)
&= \int_{\bigtimes_{i=1}^n [a_i, b_i]} 1 \, d\lambda^n(x_1, \dots, x_n) & \text{(volume of an $n$-box)} \\
&= \int_{a_1}^{b_1} \cdots \int_{a_n}^{b_n} 1 \, d\lambda^1(x_n) \cdots d\lambda^1(x_1) \\
&= \prod_{i=1}^n (b_i - a_i)
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


Tags: mathematics statistics SS25
<!--ID: 1745771490768-->
END


START
Basic
how to build a [[probability measure]] with the indicator function?

Back: 

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

__________________

### absolutely continuous
- given two [[probability measure]] $\mathcal{P}$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
- $\mathcal{P}$ is [[absolutely continuous]] to $\lambda$ written as $\mathcal{P} \ll \lambda$ if the following is hold for all $A \in \mathcal{A}$

$$
\lambda(A) = 0 \quad \Rightarrow \quad \mathcal{P}(A) = 0
$$

- in other words: $\mathcal{P}$ does not assign probabilities to sets that $\lambda$ considers zero
- in this case $\mathcal{P}$ can be described as a scaled version of $\lambda$ see ([[radon nikodym theorem]])


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
### radon nikodym theorem
- given two [[probability measure]] $\nu$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
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


### measurable space
- a [[measurable space]] $\left(\Omega,\mathcal{A} )\right)$ is a [[set]] $\Omega$ equipped with a [[sigma algebra]] $\mathcal{A}$
- every [[probability space]] is by definition a [[measurable space]]

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
\lambda^n\left( \bigtimes_{i=1}^n [a_i, b_i] \right)
&= \int_{\bigtimes_{i=1}^n [a_i, b_i]} 1 \, d\lambda^n(x_1, \dots, x_n) & \text{(volume of an $n$-box)} \\
&= \int_{a_1}^{b_1} \cdots \int_{a_n}^{b_n} 1 \, d\lambda^1(x_n) \cdots d\lambda^1(x_1) \\
&= \prod_{i=1}^n (b_i - a_i)
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

Tags: mathematics statistics SS25
<!--ID: 1745771490770-->
END

