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
\mathcal{P}_X(C) = \mathbb{P}\left(X^{-1}(C)\right) = \mathbb{P}\left( \{\omega \in \Omega : X(\omega) \in C\}\right)
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

$$
\begin{split}
\int_\mathbb{R} g(x) d\mathcal{P}_X(x)
&= \int_\Omega g\left(X(\omega)\right) d\mathbb{P}(\omega) \\
\end{split}
$$

see [[change of variables formula for pushforward measures]]
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
\mathcal{P}_X(C) = \mathbb{P}\left(X^{-1}(C)\right) = \mathbb{P}\left( \{\omega \in \Omega : X(\omega) \in C\}\right)
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
<!--ID: 1745690880070-->
END


START
Basic
how can $\mathbb{E}[g(X)]$ be calculated with two different [[probability measure]]?

Back: 
#### functions of random variables
- given a function $g: \mathbb{R} \to \mathbb{R}$ and [[random variable]] $X: \Omega \to \mathbb{R}$ from a source space $\left(\Omega, \mathcal{A})\right)$ to $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$with a pushforward measure $\mathcal{P}_X(C)$
- $g$ can be measured with respect to $\mathcal{P}_X$ or the source [[probability measure]] $\mathbb{P}$

$$
\begin{split}
\mathbb{E}[g(X)]
&= \int_\mathbb{R} g(x) d\mathcal{P}_X(x)
&= \int_\Omega g\left(X(\omega)\right) d\mathbb{P}(\omega) \\
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
\mathcal{P}_X(C) = \mathbb{P}\left(X^{-1}(C)\right) = \mathbb{P}\left( \{\omega \in \Omega : X(\omega) \in C\}\right)
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
<!--ID: 1745771490773-->
END


