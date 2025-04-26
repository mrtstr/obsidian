### integrating over probability measures
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and with a [[probability measure]] $\mathbb{P}$ that is total continues to a [[lebesgue measure]] $\lambda$
- the probability of an [[event]] $A \in \mathcal{A}$ defined by the [[integral]] over its [[probability measure]] 

$$
\begin{split}
\mathbb{P}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\mathbb{P}(\omega) \\
&= \int_A  d\mathbb{P}(\omega) \\
\end{split}
$$

- since $\mathbb{P}$ is total continues to $\lambda$ by the [[radon nikodym theorem]] there exists a [[probability density function (PDF)]] $p: \Omega \to [0, \infty)$ such that

$$
p(\omega) = \frac{d\mathbb{P}}{d\lambda}(\omega) \Rightarrow d\mathbb{P} = p(\omega) d\lambda
$$

- therefore $\mathbb{P}(A)$ of any $A \in \mathcal{A}$ can be expressed as an [[integral]] over $\lambda$ weighted by the [[probability density function (PDF)]] $p$

$$
\begin{split}
\mathbb{P}(A) = \int_A  d\mathbb{P}(\omega) 
&= \int_A  p(\omega) d\lambda = \int_a^b  p(\omega) d\omega \\
\end{split}
$$

#### random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ with a [[probability measure]] $\mathcal{P}_X(C)$ on $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$

$$
\mathcal{P}_X(C) = \mathbb{P}\left(X^{-1}(C)\right) = \mathbb{P}\left( \{\omega \in \Omega : X(\omega) \in C\}\right)
$$

- for every [[set]] $C \in \mathcal{B}(\mathbb{R})$ the probability $\mathcal{P}_X(C)$ can be expressed as an [[integral]] over $\mathbb{P}$ or over the [[lebesgue measure]] $\lambda$ on the source space $(\Omega, \mathcal{A})$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X \\
&= \int_{X^{-1}(C)}  d\mathbb{P}(\omega) \\
&= \int_{X^{-1}(C)} p(\omega) d\lambda(\omega) \\
\end{split}
$$

- if the [[random variable]] $X$ itself has a [[probability density function (PDF)]] $f_X: \mathbb{R} \to \mathbb{R}$ then $\mathcal{P}_X(C)$ can also be expressed as an [[integral]] on $\mathbb{R}$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_\mathbb{R} f_X(x) dx\\
&= \int_C p\left(X^{-1}(x)\right) \left|\frac{dX^{-1}}{dx}\right| dx\\
\end{split}
$$

- if $X(\omega)$ is [[inverse function|invertable]] and the inverse is [[differentiable]] then $f_X(x)$ can be derived from the [[probability density function (PDF)]] of the source space
- this is done by pulling in the inverse random variable in the original [[probability density function (PDF)]] and re-scaling it by the ratio of which is stretched or compressed 

$$
\begin{split}
f_X(x) = p\left(X^{-1}(x)\right) \left|\frac{dX^{-1}}{dx}\right|
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
- how to calculate the same [[probability]] using a [[lebesgue measure]] $\lambda$?
- which condition has to be satisfied?

Back: 
### integrating over probability measures
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and with a [[probability measure]] $\mathbb{P}$ that is total continues to a [[lebesgue measure]] $\lambda$
- the probability of an [[event]] $A \in \mathcal{A}$ defined by the [[integral]] over its [[probability measure]] 

$$
\begin{split}
\mathbb{P}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\mathbb{P}(\omega) \\
&= \int_A  d\mathbb{P}(\omega) \\
\end{split}
$$

- since $\mathbb{P}$ is total continues to $\lambda$ by the [[radon nikodym theorem]] there exists a [[probability density function (PDF)]] $p: \Omega \to [0, \infty)$ such that

$$
p(\omega) = \frac{d\mathbb{P}}{d\lambda}(\omega) \Rightarrow d\mathbb{P} = p(\omega) d\lambda
$$

- therefore $\mathbb{P}(A)$ of any $A \in \mathcal{A}$ can be expressed as an [[integral]] over $\lambda$ weighted by the [[probability density function (PDF)]] $p$

$$
\begin{split}
\mathbb{P}(A) = \int_A  d\mathbb{P}(\omega) 
&= \int_A  p(\omega) d\lambda = \int_A  p(\omega) d\omega \\
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
<!--ID: 1745690880068-->
END


START
Basic
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ with a [[probability measure]] $\mathcal{P}_X(C)$ on $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$

[[integrating over probability measures]]
- how is the [[probability measure]] of a [[random variable]] defined
- how to calculate the [[probability]] of a [[set]]?
	- using the [[probability measure]] $\mathcal{P}_X(C)$ of the [[random variable]]
	- using the source [[probability measure]] $\mathbb{P}$ 
	- using a [[lebesgue measure]] $\lambda$
	-  using an [[integral]] on $\mathbb{R}$ (conditions?)



Back: 


#### random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ with a [[probability measure]] $\mathcal{P}_X(C)$ on $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$

$$
\mathcal{P}_X(C) = \mathbb{P}\left(X^{-1}(C)\right) = \mathbb{P}\left( \{\omega \in \Omega : X(\omega) \in C\}\right)
$$

- for every [[set]] $C \in \mathcal{B}(\mathbb{R})$ the probability $\mathcal{P}_X(C)$ can be expressed as an [[integral]] over $\mathbb{P}$ or over the [[lebesgue measure]] $\lambda$ on the source space $(\Omega, \mathcal{A})$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X \\
&= \int_{X^{-1}(C)}  d\mathbb{P}(\omega) \\
&= \int_{X^{-1}(C)} p(\omega) d\lambda(\omega) \\
\end{split}
$$

- if the [[random variable]] $X$ itself has a [[probability density function (PDF)]] $f_X: \mathbb{R} \to \mathbb{R}$ then $\mathcal{P}_X(C)$ can also be expressed as an [[integral]] on $\mathbb{R}$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_\mathbb{R} f_X(x) dx\\
&= \int_C p\left(X^{-1}(x)\right) \left|\frac{dX^{-1}}{dx}\right| dx\\
\end{split}
$$

- if $X(\omega)$ is [[inverse function|invertable]] and the inverse is [[differentiable]] then $f_X(x)$ can be derived from the [[probability density function (PDF)]] of the source space
- this is done by pulling in the inverse random variable in the original [[probability density function (PDF)]] and re-scaling it by the ratio of which is stretched or compressed 

$$
\begin{split}
f_X(x) = p\left(X^{-1}(x)\right) \left|\frac{dX^{-1}}{dx}\right|
\end{split}
$$

### integrating over probability measures
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and with a [[probability measure]] $\mathbb{P}$ that is total continues to a [[lebesgue measure]] $\lambda$
- the probability of an [[event]] $A \in \mathcal{A}$ defined by the [[integral]] over its [[probability measure]] 

$$
\begin{split}
\mathbb{P}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\mathbb{P}(\omega) \\
&= \int_A  d\mathbb{P}(\omega) \\
\end{split}
$$

- since $\mathbb{P}$ is total continues to $\lambda$ by the [[radon nikodym theorem]] there exists a [[probability density function (PDF)]] $p: \Omega \to [0, \infty)$ such that

$$
p(\omega) = \frac{d\mathbb{P}}{d\lambda}(\omega) \Rightarrow d\mathbb{P} = p(\omega) d\lambda
$$

- therefore $\mathbb{P}(A)$ of any $A \in \mathcal{A}$ can be expressed as an [[integral]] over $\lambda$ weighted by the [[probability density function (PDF)]] $p$

$$
\begin{split}
\mathbb{P}(A) = \int_A  d\mathbb{P}(\omega) 
&= \int_A  p(\omega) d\lambda = \int_A  p(\omega) d\omega \\
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
<!--ID: 1745690880070-->
END



START
Basic
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ with a [[probability measure]] $\mathcal{P}_X(C)$ on $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$
- how can the [[probability density function (PDF)]] $f_X$ be derived from the [[probability density function (PDF)]] $p(\omega)$ of its source space?
- how is the [[probability density function (PDF)]] $p(\omega)$ of its source space defined, and when does it exist? (name a theorem)

Back: 

### integrating over probability measures
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and with a [[probability measure]] $\mathbb{P}$ that is total continues to a [[lebesgue measure]] $\lambda$
- the probability of an [[event]] $A \in \mathcal{A}$ defined by the [[integral]] over its [[probability measure]] 

$$
\begin{split}
\mathbb{P}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\mathbb{P}(\omega) \\
&= \int_A  d\mathbb{P}(\omega) \\
\end{split}
$$

- since $\mathbb{P}$ is total continues to $\lambda$ by the [[radon nikodym theorem]] there exists a [[probability density function (PDF)]] $p: \Omega \to [0, \infty)$ such that

$$
p(\omega) = \frac{d\mathbb{P}}{d\lambda}(\omega) \Rightarrow d\mathbb{P} = p(\omega) d\lambda
$$

- therefore $\mathbb{P}(A)$ of any $A \in \mathcal{A}$ can be expressed as an [[integral]] over $\lambda$ weighted by the [[probability density function (PDF)]] $p$

$$
\begin{split}
\mathbb{P}(A) = \int_A  d\mathbb{P}(\omega) 
&= \int_A  p(\omega) d\lambda = \int_A  p(\omega) d\omega \\
\end{split}
$$

#### random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ with a [[probability measure]] $\mathcal{P}_X(C)$ on $\left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$

$$
\mathcal{P}_X(C) = \mathbb{P}\left(X^{-1}(C)\right) = \mathbb{P}\left( \{\omega \in \Omega : X(\omega) \in C\}\right)
$$

- for every [[set]] $C \in \mathcal{B}(\mathbb{R})$ the probability $\mathcal{P}_X(C)$ can be expressed as an [[integral]] over $\mathbb{P}$ or over the [[lebesgue measure]] $\lambda$ on the source space $(\Omega, \mathcal{A})$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_C d\mathcal{P}_X \\
&= \int_{X^{-1}(C)}  d\mathbb{P}(\omega) \\
&= \int_{X^{-1}(C)} p(\omega) d\lambda(\omega) \\
\end{split}
$$

- if the [[random variable]] $X$ itself has a [[probability density function (PDF)]] $f_X: \mathbb{R} \to \mathbb{R}$ then $\mathcal{P}_X(C)$ can also be expressed as an [[integral]] on $\mathbb{R}$

$$
\begin{split}
\mathcal{P}_X(C) 
&= \int_\mathbb{R} f_X(x) dx\\
&= \int_C p\left(X^{-1}(x)\right) \left|\frac{dX^{-1}}{dx}\right| dx\\
\end{split}
$$

- if $X(\omega)$ is [[inverse function|invertable]] and the inverse is [[differentiable]] then $f_X(x)$ can be derived from the [[probability density function (PDF)]] of the source space
- this is done by pulling in the inverse random variable in the original [[probability density function (PDF)]] and re-scaling it by the ratio of which is stretched or compressed 

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