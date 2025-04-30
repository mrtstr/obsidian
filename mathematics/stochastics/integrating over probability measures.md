### integrating over probability measures
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and with a [[probability measure]] $\mathbb{P}$ 
- the probability of an [[event]] $A \in \mathcal{A}$ defined by the [[integral]] over its [[probability measure]] 
$$
\begin{split}
\mathbb{P}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\mathbb{P}(\omega) \\
&= \int_A  d\mathbb{P}(\omega) \\
\end{split}
$$

- integrating over $\mathbb{P}$ means we are measuring the [[probability]] of $A$ with respect to $\mathbb{P}$ and not to the [[riemann integral]] in $\mathbb{R}^n$
- however if $\mathbb{P}$ is [[absolutely continuous]] to a [[lebesgue measure]] $\lambda$ that is defined on the same [[measurable space]] we can convert this to a [[riemann integral]]
- since $\mathbb{P}$ is total continues to $\lambda$ by the [[radon nikodym theorem]] there exists a [[probability density function (PDF)]] $p: \Omega \to [0, \infty)$ such that

$$
p(\omega) = \frac{d\mathbb{P}}{d\lambda}(\omega) \Rightarrow d\mathbb{P} = p(\omega) d\lambda
$$

- therefore $\mathbb{P}(A)$ of any $A \in \mathcal{A}$ can be expressed as an [[integral]] over $\lambda$ weighted by the [[probability density function (PDF)]] $p$
- and thus also as a [[riemann integral]] because the [[lebesgue measure]] which is equivalent to the [[riemann integral]] in $\mathbb{R}^n$

$$
\begin{split}
\mathbb{P}(A) = \int_A  d\mathbb{P}(\omega) 
&= \int_A  p(\omega) d\lambda(\omega) = \int_A  p(\omega) d\omega \\
\end{split}
$$

-  [[probability measure]] $\mathbb{P}$ and the [[lebesgue measure]] $\lambda$ generally live on different spaces (cannot be compared directly)
- But for a [[random variable]] $X: \Omega \to \mathbb{R}^n$ its pushforward measure $\mathcal{P}_X$ is a measure on $\mathbb{R}^n$, and now it makes sense to ask if $\mathcal{P}_X<< \lambda$ ([[absolutely continuous]])
- if yes $X$ as a [[probability density function (PDF)]] and [[riemann integral]] often matches [[lebesgue measure]] (if the PDF has nice properties)


#### random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ from a source space $\left(\Omega, \mathcal{A})\right)$ to $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$with a pushforward measure $\mathcal{P}_X(C)$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C)\right) 
= \mathbb{P}\left( \{\omega \in \Omega : X(\omega) \in C\}\right) \\
&= \mathbb{P}\left( X \in C\right) \quad \text{(in short)} \\
\end{split}
$$

- for every [[set]] $C \in \mathcal{B}(\mathbb{R})$ the probability $\mathcal{P}_X(C)$ can be calculated by integrating over $\mathcal{P}_X$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X 
&= \int_\mathbb{R} \mathbb{I}[x \in C] d\mathcal{P}_X  \\
\end{split}
$$

- however $\mathcal{P}_X(C)$ can also always be measured with the [[probability measure]] of the source space $\mathbb{P}$
- if $\mathbb{P}$ is absolutely continuous to a [[lebesgue measure]] $\lambda$ we can even convert this to a [[riemann integral]]

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X \\
&= \int_{X^{-1}(C)}  d\mathbb{P}(\omega) \\
&= \int_{X^{-1}(C)} p(\omega) d\lambda(\omega) 
&= \int_{X^{-1}(C)} p(\omega) d\omega \\
\end{split}
$$

- the [[probability density function (PDF)]] $p(\omega)$ is converting from the source [[probability measure]] $\mathbb{P}$ to the [[lebesgue measure]] $\lambda$

$$
\begin{split}
f_X(x) = \frac{d\mathcal{P}_X}{d\lambda}(x) \Rightarrow d\mathcal{P}_X = f_X(x) d\lambda
\end{split}
$$

- however if the [[random variable]] $X$ itself has a [[probability density function (PDF)]] $f_X: \mathbb{R} \to \mathbb{R}$ that is converting from $\mathcal{P}_X(C)$ to the [[lebesgue measure]] $\lambda$ then $\mathcal{P}_X(C)$ can also be expressed as an [[integral]] on $\mathbb{R}$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X 
&= \int_C f_X(x) d\lambda (x)
&= \int_C f_X(x) dx
\end{split}
$$
#### functions of random variables
- given a function $g: \mathbb{R} \to \mathbb{R}$ and [[random variable]] $X: \Omega \to \mathbb{R}$ from a source space $\left(\Omega, \mathcal{A})\right)$ to $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$with a pushforward measure $\mathcal{P}_X(C)$
- $g$ can be measured with respect to $\mathcal{P}_X$ or the source [[probability measure]] $\mathbb{P}$
- or the [[lebesgue measure]] if the [[probability density function (PDF)]] exists

$$
\begin{split}
\int_\mathbb{R} g(x) d\mathcal{P}_X(x)
&= \int_\Omega g\left(X(\omega)\right) d\mathbb{P}(\omega) \\
&= \int_\mathbb{R} g\left(x\right) f_X(x) d\lambda(x) \\
\end{split}
$$

# ----------

![[lebesgue measure#lebesgue measure]]

![[radon nikodym theorem#radon nikodym theorem]]

![[random variable#random variable]]

![[probability measure#probability measure]]


# anki

START
Basic
[[integrating over probability measures]]
- how to calculate the [[probability]] of a [[set]] using a [[probability measure]] (two version)
- what does it mean to integrate over a [[probability measure]] and how to translate it to a [[riemann integral]]
- in which situations is this practically used and when is not possible?

Back: 
### integrating over probability measures
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and with a [[probability measure]] $\mathbb{P}$ 
- the probability of an [[event]] $A \in \mathcal{A}$ defined by the [[integral]] over its [[probability measure]] 
$$
\begin{split}
\mathbb{P}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\mathbb{P}(\omega) \\
&= \int_A  d\mathbb{P}(\omega) \\
\end{split}
$$

- integrating over $\mathbb{P}$ means we are measuring the [[probability]] of $A$ with respect to $\mathbb{P}$ and not to the [[riemann integral]] in $\mathbb{R}^n$
- however if $\mathbb{P}$ is absolutely continuous to a [[lebesgue measure]] $\lambda$ we can convert this to a [[riemann integral]]
- since $\mathbb{P}$ is total continues to $\lambda$ by the [[radon nikodym theorem]] there exists a [[probability density function (PDF)]] $p: \Omega \to [0, \infty)$ such that

$$
p(\omega) = \frac{d\mathbb{P}}{d\lambda}(\omega) \Rightarrow d\mathbb{P} = p(\omega) d\lambda
$$

- therefore $\mathbb{P}(A)$ of any $A \in \mathcal{A}$ can be expressed as an [[integral]] over $\lambda$ weighted by the [[probability density function (PDF)]] $p$
- and thus also as a [[riemann integral]] because the [[lebesgue measure]] which is equivalent to the [[riemann integral]] in $\mathbb{R}^n$

$$
\begin{split}
\mathbb{P}(A) = \int_A  d\mathbb{P}(\omega) 
&= \int_A  p(\omega) d\lambda(\omega) = \int_A  p(\omega) d\omega \\
\end{split}
$$

-  [[probability measure]] $\mathbb{P}$ and the [[lebesgue measure]] $\lambda$ generally live on different spaces (cannot be compared directly)
- But for a [[random variable]] $X: \Omega \to \mathbb{R}^n$ its pushforward measure $\mathcal{P}_X$ is a measure on $\mathbb{R}^n$, and now it makes sense to ask if $\mathcal{P}_X<< \lambda$ ([[absolutely continuous]])
- if yes $X$ as a [[probability density function (PDF)]] and [[riemann integral]] often matches [[lebesgue measure]] (if the PDF has nice properties)

__________________
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
### radon nikodym theorem
- given two [[measure]] $\nu$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
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

Tags: mathematics statistics SS25
<!--ID: 1745690880068-->
END


START
Basic
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and with a [[probability measure]] $\mathbb{P}$ 
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ with a pushforward [[probability measure]] $\mathcal{P}_X(C)$ on $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$

[[integrating over probability measures]]
- how to measure of probability of an event $C \in \mathcal{B}(\mathbb{R})$ of an [[random variable]] $X$
	1) using the pushforward [[probability measure]] $\mathcal{P}_X$
	2) using the source [[probability measure]] $\mathbb{P}$ (when is it possible?)
	3) using a [[riemann integral]] (when is it possible?)

Back: 
### integrating over probability measures
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and with a [[probability measure]] $\mathbb{P}$ 
- the probability of an [[event]] $A \in \mathcal{A}$ defined by the [[integral]] over its [[probability measure]] 
$$
\begin{split}
\mathbb{P}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\mathbb{P}(\omega) \\
&= \int_A  d\mathbb{P}(\omega) \\
\end{split}
$$

- integrating over $\mathbb{P}$ means we are measuring the [[probability]] of $A$ with respect to $\mathbb{P}$ and not to the [[riemann integral]] in $\mathbb{R}^n$
- however if $\mathbb{P}$ is absolutely continuous to a [[lebesgue measure]] $\lambda$ we can convert this to a [[riemann integral]]
- since $\mathbb{P}$ is total continues to $\lambda$ by the [[radon nikodym theorem]] there exists a [[probability density function (PDF)]] $p: \Omega \to [0, \infty)$ such that

$$
p(\omega) = \frac{d\mathbb{P}}{d\lambda}(\omega) \Rightarrow d\mathbb{P} = p(\omega) d\lambda
$$

- therefore $\mathbb{P}(A)$ of any $A \in \mathcal{A}$ can be expressed as an [[integral]] over $\lambda$ weighted by the [[probability density function (PDF)]] $p$
- and thus also as a [[riemann integral]] because the [[lebesgue measure]] which is equivalent to the [[riemann integral]] in $\mathbb{R}^n$

$$
\begin{split}
\mathbb{P}(A) = \int_A  d\mathbb{P}(\omega) 
&= \int_A  p(\omega) d\lambda(\omega) = \int_A  p(\omega) d\omega \\
\end{split}
$$

-  [[probability measure]] $\mathbb{P}$ and the [[lebesgue measure]] $\lambda$ generally live on different spaces (cannot be compared directly)
- But for a [[random variable]] $X: \Omega \to \mathbb{R}^n$ its pushforward measure $\mathcal{P}_X$ is a measure on $\mathbb{R}^n$, and now it makes sense to ask if $\mathcal{P}_X<< \lambda$ ([[absolutely continuous]])
- if yes $X$ as a [[probability density function (PDF)]] and [[riemann integral]] often matches [[lebesgue measure]] (if the PDF has nice properties)

#### random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ from a source space $\left(\Omega, \mathcal{A})\right)$ to $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$with a pushforward measure $\mathcal{P}_X(C)$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C)\right) 
= \mathbb{P}\left( \{\omega \in \Omega : X(\omega) \in C\}\right) \\
&= \mathbb{P}\left( X \in C\right) \quad \text{(in short)} \\
\end{split}
$$

- for every [[set]] $C \in \mathcal{B}(\mathbb{R})$ the probability $\mathcal{P}_X(C)$ can be calculated by integrating over $\mathcal{P}_X$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X 
&= \int_\mathbb{R} \mathbb{I}[x \in C] d\mathcal{P}_X  \\
\end{split}
$$

- however $\mathcal{P}_X(C)$ can also always be measured with the [[probability measure]] of the source space $\mathbb{P}$
- if $\mathbb{P}$ is absolutely continuous to a [[lebesgue measure]] $\lambda$ we can even convert this to a [[riemann integral]]

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X \\
&= \int_{X^{-1}(C)}  d\mathbb{P}(\omega) \\
&= \int_{X^{-1}(C)} p(\omega) d\lambda(\omega) 
&= \int_{X^{-1}(C)} p(\omega) d\omega \\
\end{split}
$$

- the [[probability density function (PDF)]] $p(\omega)$ is converting from the source [[probability measure]] $\mathbb{P}$ to the [[lebesgue measure]] $\lambda$

$$
\begin{split}
f_X(x) = \frac{d\mathcal{P}_X}{d\lambda}(x) \Rightarrow d\mathcal{P}_X = f_X(x) d\lambda
\end{split}
$$

- however if the [[random variable]] $X$ itself has a [[probability density function (PDF)]] $f_X: \mathbb{R} \to \mathbb{R}$ that is converting from $\mathcal{P}_X(C)$ to the [[lebesgue measure]] $\lambda$ then $\mathcal{P}_X(C)$ can also be expressed as an [[integral]] on $\mathbb{R}$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X 
&= \int_C f_X(x) d\lambda (x)
&= \int_C f_X(x) dx
\end{split}
$$
__________________

### lebesgue measure
- the [[lebesgue measure]] is a [[measure]] that assigns size, length or volume to sets
- similar but more flexible than the [[riemann integral]] (in $\mathbb{R}^n$ they are interchangeable)
- for higher dimensions the [[lebesgue measure]] $\lambda^n: \mathcal{B} ({\mathbb{R}^n}) \to [0, \infty)$ is a [[catesian product]] product measure over $\mathbb{R}$ 

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
<!--ID: 1745690880070-->
END


START
Basic
how can $\mathbb{E}[g(X)]$ be calculated with 3 different [[probability measure]]?

Back: 
#### functions of random variables
- given a function $g: \mathbb{R} \to \mathbb{R}$ and [[random variable]] $X: \Omega \to \mathbb{R}$ from a source space $\left(\Omega, \mathcal{A})\right)$ to $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$with a pushforward measure $\mathcal{P}_X(C)$
- $g$ can be measured with respect to $\mathcal{P}_X$ or the source [[probability measure]] $\mathbb{P}$
- or the [[lebesgue measure]] if the [[probability density function (PDF)]] exists

$$
\begin{split}
\int_\mathbb{R} g(x) d\mathcal{P}_X(x)
&= \int_\Omega g\left(X(\omega)\right) d\mathbb{P}(\omega) \\
&= \int_\mathbb{R} g\left(x\right) f_X(x) d\lambda(x) \\
\end{split}
$$

__________________
### integrating over probability measures
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and with a [[probability measure]] $\mathbb{P}$ 
- the probability of an [[event]] $A \in \mathcal{A}$ defined by the [[integral]] over its [[probability measure]] 
$$
\begin{split}
\mathbb{P}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\mathbb{P}(\omega) \\
&= \int_A  d\mathbb{P}(\omega) \\
\end{split}
$$

- integrating over $\mathbb{P}$ means we are measuring the [[probability]] of $A$ with respect to $\mathbb{P}$ and not to the [[riemann integral]] in $\mathbb{R}^n$
- however if $\mathbb{P}$ is absolutely continuous to a [[lebesgue measure]] $\lambda$ we can convert this to a [[riemann integral]]
- since $\mathbb{P}$ is total continues to $\lambda$ by the [[radon nikodym theorem]] there exists a [[probability density function (PDF)]] $p: \Omega \to [0, \infty)$ such that

$$
p(\omega) = \frac{d\mathbb{P}}{d\lambda}(\omega) \Rightarrow d\mathbb{P} = p(\omega) d\lambda
$$

- therefore $\mathbb{P}(A)$ of any $A \in \mathcal{A}$ can be expressed as an [[integral]] over $\lambda$ weighted by the [[probability density function (PDF)]] $p$
- and thus also as a [[riemann integral]] because the [[lebesgue measure]] which is equivalent to the [[riemann integral]] in $\mathbb{R}^n$

$$
\begin{split}
\mathbb{P}(A) = \int_A  d\mathbb{P}(\omega) 
&= \int_A  p(\omega) d\lambda(\omega) = \int_A  p(\omega) d\omega \\
\end{split}
$$

-  [[probability measure]] $\mathbb{P}$ and the [[lebesgue measure]] $\lambda$ generally live on different spaces (cannot be compared directly)
- But for a [[random variable]] $X: \Omega \to \mathbb{R}^n$ its pushforward measure $\mathcal{P}_X$ is a measure on $\mathbb{R}^n$, and now it makes sense to ask if $\mathcal{P}_X<< \lambda$ ([[absolutely continuous]])
- if yes $X$ as a [[probability density function (PDF)]] and [[riemann integral]] often matches [[lebesgue measure]] (if the PDF has nice properties)

#### random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ from a source space $\left(\Omega, \mathcal{A})\right)$ to $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$with a pushforward measure $\mathcal{P}_X(C)$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C)\right) 
= \mathbb{P}\left( \{\omega \in \Omega : X(\omega) \in C\}\right) \\
&= \mathbb{P}\left( X \in C\right) \quad \text{(in short)} \\
\end{split}
$$

- for every [[set]] $C \in \mathcal{B}(\mathbb{R})$ the probability $\mathcal{P}_X(C)$ can be calculated by integrating over $\mathcal{P}_X$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X 
&= \int_\mathbb{R} \mathbb{I}[x \in C] d\mathcal{P}_X  \\
\end{split}
$$

- however $\mathcal{P}_X(C)$ can also always be measured with the [[probability measure]] of the source space $\mathbb{P}$
- if $\mathbb{P}$ is absolutely continuous to a [[lebesgue measure]] $\lambda$ we can even convert this to a [[riemann integral]]

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X \\
&= \int_{X^{-1}(C)}  d\mathbb{P}(\omega) \\
&= \int_{X^{-1}(C)} p(\omega) d\lambda(\omega) 
&= \int_{X^{-1}(C)} p(\omega) d\omega \\
\end{split}
$$

- the [[probability density function (PDF)]] $p(\omega)$ is converting from the source [[probability measure]] $\mathbb{P}$ to the [[lebesgue measure]] $\lambda$

$$
\begin{split}
f_X(x) = \frac{d\mathcal{P}_X}{d\lambda}(x) \Rightarrow d\mathcal{P}_X = f_X(x) d\lambda
\end{split}
$$

- however if the [[random variable]] $X$ itself has a [[probability density function (PDF)]] $f_X: \mathbb{R} \to \mathbb{R}$ that is converting from $\mathcal{P}_X(C)$ to the [[lebesgue measure]] $\lambda$ then $\mathcal{P}_X(C)$ can also be expressed as an [[integral]] on $\mathbb{R}$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X 
&= \int_C f_X(x) dx
\end{split}
$$


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
<!--ID: 1745771490773-->
END


START
Basic
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ from a source space $\left(\Omega, \mathcal{A}, \mathbb{P})\right)$ to $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$with a pushforward measure $\mathcal{P}_X(C)$
- what does $\mathbb{P}\left( X \in C\right)$ in this case mean?
Back: 

__________________

#### random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ from a source space $\left(\Omega, \mathcal{A})\right)$ to $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$with a pushforward measure $\mathcal{P}_X(C)$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \mathbb{P}\left(X^{-1}(C)\right) 
= \mathbb{P}\left( \{\omega \in \Omega : X(\omega) \in C\}\right) \\
&= \mathbb{P}\left( X \in C\right) \quad \text{(in short)} \\
\end{split}
$$

- for every [[set]] $C \in \mathcal{B}(\mathbb{R})$ the probability $\mathcal{P}_X(C)$ can be calculated by integrating over $\mathcal{P}_X$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X 
&= \int_\mathbb{R} \mathbb{I}[x \in C] d\mathcal{P}_X  \\
\end{split}
$$

- however $\mathcal{P}_X(C)$ can also always be measured with the [[probability measure]] of the source space $\mathbb{P}$
- if $\mathbb{P}$ is absolutely continuous to a [[lebesgue measure]] $\lambda$ we can even convert this to a [[riemann integral]]

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X \\
&= \int_{X^{-1}(C)}  d\mathbb{P}(\omega) \\
&= \int_{X^{-1}(C)} p(\omega) d\lambda(\omega) 
&= \int_{X^{-1}(C)} p(\omega) d\omega \\
\end{split}
$$

- the [[probability density function (PDF)]] $p(\omega)$ is converting from the source [[probability measure]] $\mathbb{P}$ to the [[lebesgue measure]] $\lambda$

$$
\begin{split}
f_X(x) = \frac{d\mathcal{P}_X}{d\lambda}(x) \Rightarrow d\mathcal{P}_X = f_X(x) d\lambda
\end{split}
$$

- however if the [[random variable]] $X$ itself has a [[probability density function (PDF)]] $f_X: \mathbb{R} \to \mathbb{R}$ that is converting from $\mathcal{P}_X(C)$ to the [[lebesgue measure]] $\lambda$ then $\mathcal{P}_X(C)$ can also be expressed as an [[integral]] on $\mathbb{R}$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X 
&= \int_C f_X(x) dx
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
<!--ID: 1745991645679-->
END


