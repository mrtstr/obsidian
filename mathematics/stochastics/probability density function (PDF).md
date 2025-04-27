### probability density function
- a [[probability density function (PDF)]] is a function converts a [[probability measure]] to a [[lebesgue measure]] 

$$
\begin{split}
&p(\omega) = \frac{d\mathbb{P}}{d\lambda} (\omega) \\
\Rightarrow &d\mathbb{P}(\omega) = p(\omega)d\lambda(\omega) \\
\end{split}
$$

#### for a random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ with the [[distribution]] $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$
- the [[probability mass function (PMF)]] would be undefined but the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,1]$ can be derived from the [[cumulative distribution function (CDF)]]

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$
- with the [[probability density function (PDF)]] we can calculate the [[probability]] that a [[continuous probability space|continuous]] [[random variable]] is in a [[set]] of values $C$ (of $C$ is countable the [[probability]] is zero)

$$
\begin{split}
\mathbb{P}(X \in C) &=\int\limits^{C}  f_X(x)\:dx \\
\mathbb{P}(X \in [a,b]) &=\int\limits_{b}^{a}  f_X(x)\:dx
\end{split}
$$

#### for a general probability measure
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ with a [[probability measure]] $\mathbb{P}: \mathcal{A} \to [0,1]$
- the [[probability density function (PDF)]] $p: \Omega \to \mathbb{R}$ of $\mathbb{P}$ exists if $\mathbb{P}$ is [[differentiable]] and is defined as follows
- the [[probability density function (PDF)]] $p: \Omega \to \mathbb{R}$ with respect to a reference measure (typically [[lebesgue measure]] $\lambda$ on $\mathbb{R}$) is defined as follows by the [[radon nikodym theorem]]
- **only works** if the probability measure P\mathbb{P}P is **absolutely continuous with respect to Lebesgue measure** λ\lambdaλ

$$
\begin{split}
&p(\omega) = \frac{d\mathbb{P}}{d\lambda} (\omega) \\
\Rightarrow &d\mathbb{P}(\omega) = p(\omega)d\lambda(\omega) \\
\end{split}
$$

# ----------------------
![[radon nikodym theorem#radon nikodym theorem]]

![[lebesgue measure#lebesgue measure]]

![[continuous probability space#continuous probability space]]

![[random variable#a random variable induces a probability measure]]


![[random variable#random variable]]

![[probability space#probability space]]

# anki

START
Basic
[[probability density function (PDF)]]
- definition
- probability that a [[random variable]] is in a [[set]]
Back: 
### probability density function
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ with the [[distribution]] $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$
- the [[probability mass function (PMF)]] would be undefined but the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,1]$ can be derived from the [[cumulative distribution function (CDF)]]

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$
- with the [[probability density function (PDF)]] we can calculate the [[probability]] that a [[continuous probability space|continuous]] [[random variable]] is in a [[set]] of values $C$ (of $C$ is countable the [[probability]] is zero)

$$
\begin{split}
\mathbb{P}(X \in C) &=\int\limits^{C}  f_X(x)\:dx \\
\mathbb{P}(X \in [a,b]) &=\int\limits_{b}^{a}  f_X(x)\:dx
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1664291691108-->
END


START
Basic
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ with a [[probability measure]] $\mathcal{P}_X(C)$ on $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$
- how can the [[probability density function (PDF)]] $f_X$ be derived from the [[probability density function (PDF)]] $p(\omega)$ of its source space?
- how is the [[probability density function (PDF)]] $p(\omega)$ of its source space defined, and when does it exist? (name a theorem)

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
- however if the [[random variable]] $X$ itself has a [[probability density function (PDF)]] $f_X: \mathbb{R} \to \mathbb{R}$ that is converting from $\mathcal{P}_X(C)$ to the [[lebesgue measure]] $\lambda$ then $\mathcal{P}_X(C)$ can also be expressed as an [[integral]] on $\mathbb{R}$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C f_X(x) dx\\
&= \int_C p\left(X^{-1}(x)\right) \left|\frac{dX^{-1}}{dx}\right| dx\\
\end{split}
$$

- if $X(\omega)$ is [[inverse function|invertable]] and the inverse is [[differentiable]] then $f_X(x)$ can be derived from the [[probability density function (PDF)]] of the source space
- this is done by pulling in the inverse random variable in the original [[probability density function (PDF)]] and rescaling by the Jacobian determinant (in higher dimensions), or in 1D, by the absolute value of the derivative.

$$
\begin{split}
f_X(x) = p\left(X^{-1}(x)\right) \left|\frac{dX^{-1}}{dx}\right|
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
### radon nikodym theorem
- given two [[probability measure]] $\nu$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
- $\nu$ is absolute continuous to $\lambda$ which means $\lambda(A) = 0 \Rightarrow \nu(A) = 0$
- this means that $\nu$ is just a scaled version of $\lambda$ and there exists a function $f=\frac{d\nu}{d\lambda}$ that compensates for that

$$
\begin{split}
\mathbb{\nu}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\nu \\
&= \int_A  d\nu \\

&= \int_A \frac{d\nu}{d\lambda} d\lambda \\
\end{split}
$$

- How much more (or less) weight does ν\nuν give to each point, compared to μ\muμ?

### measurable space
- a [[measurable space]] $\left(\Omega,\mathcal{A} )\right)$ is a [[set]] $\Omega$ equipped with a [[sigma algebra]] $\mathcal{A}$
- every [[probability space]] is by definition a [[measurable space]]

Tags: mathematics statistics SS25
<!--ID: 1745690880073-->
END