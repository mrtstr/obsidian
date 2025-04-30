### probability density function
- a [[probability density function (PDF)]] is a [[measurable function]] $p: \mathbb{R} \to [0, \infty)$ that describes how a [[probability measure]] $\mathcal{P}$ on $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n)\right)$ is [[absolutely continuous]] with respect to the [[lebesgue measure]] $\lambda$ (see [[radon nikodym theorem]])

$$
\begin{split}
&p(\omega) = \frac{d\mathcal{P}}{d\lambda} (\omega) \\
\Rightarrow &d\mathcal{P}(\omega) = p(\omega)d\lambda(\omega) \\
\end{split}
$$
- thus for all $A \subseteq \mathbb{R}$

$$
\begin{split}
\mathcal{P}(A) = \int_A  d\mathcal{P}(\omega) 
&= \int_A  p(\omega) d\lambda(\omega) = \int_A  p(\omega) d\omega \\
\end{split}
$$

- intuitively, the [[probability density function (PDF)]] weights the [[lebesgue measure]] to build the [[probability measure]] $\mathcal{P}$
- instead of describing the [[probability density function (PDF)]] as a differential equation often it makes sense to describe the ratio of the measurement of an infinitesimal small [[ball]] around the point $\omega$

$$
\begin{split}
&p(\omega) \approx \frac{\mathcal{P}\left(B_\epsilon (\omega)\right)}{\lambda \left(B_\epsilon (\omega)\right)} \quad \text{as } \epsilon \to 0  \\
&p\left(g(\omega)\right) \approx \frac{\mathcal{P}\left(B_\epsilon \left(g(\omega)\right)\right)}{\lambda \left(B_\epsilon \left(g(\omega)\right)\right)} \quad \text{as } \epsilon \to 0  \\
\end{split}
$$

#### for a random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in that maps a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ into $(\mathbb{R}, \mathcal{B}(\mathbb{R})\mathcal{P}_X)$
- where $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ is the pushforward [[probability measure]] 
- and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$

$$
F_X =\mathcal{P}_X\left([-\infty, x)\right)
$$

- if $F_X$ is [[differentiable]] the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,\infty)$ exists and is given by

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

- With the PDF, we can compute probabilities of events involving $X$ by integrating over sets $C$

$$
\begin{split}
\mathbb{P}(X \in C) &=\int\limits^{C}  f_X(x)\:dx \\
\mathbb{P}(X \in [a,b]) &=\int\limits_{a}^{b}  f_X(x)\:dx
\end{split}
$$


# ----------------------
![[radon nikodym theorem#radon nikodym theorem]]


![[absolutely continuous#absolutely continuous]]

![[lebesgue measure#lebesgue measure]]

![[continuous probability space#continuous probability space]]

![[random variable#a random variable induces a probability measure]]


![[random variable#random variable]]

![[probability space#probability space]]

# anki

START
Basic
[[probability density function (PDF)]]
- general definition and intuition
- relationship to the [[radon nikodym theorem]]
- how to calculate the [[probability density function (PDF)]] of a [[random variable]]
Back: 
### probability density function
- a [[probability density function (PDF)]] is a [[measurable function]] $p: \mathbb{R} \to [0, \infty)$ that describes how a [[probability measure]] $\mathcal{P}$ on $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n)\right)$ is [[absolutely continuous]] with respect to the [[lebesgue measure]] $\lambda$ (see [[radon nikodym theorem]])

$$
\begin{split}
&p(\omega) = \frac{d\mathcal{P}}{d\lambda} (\omega) \\
\Rightarrow &d\mathcal{P}(\omega) = p(\omega)d\lambda(\omega) \\
\end{split}
$$
- thus for all $A \subseteq \mathbb{R}$

$$
\begin{split}
\mathcal{P}(A) = \int_A  d\mathcal{P}(\omega) 
&= \int_A  p(\omega) d\lambda(\omega) = \int_A  p(\omega) d\omega \\
\end{split}
$$

- intuitively, the [[probability density function (PDF)]] weights the [[lebesgue measure]] to build the [[probability measure]] $\mathcal{P}$
- instead of describing the [[probability density function (PDF)]] as a differential equation often it makes sense to describe the ratio of the measurement of an infinitesimal small [[ball]] around the point $\omega$

$$
\begin{split}
&p(\omega) \approx \frac{\mathcal{P}\left(B_\epsilon (\omega)\right)}{\lambda \left(B_\epsilon (\omega)\right)} \quad \text{as } \epsilon \to 0  \\
&p\left(g(\omega)\right) \approx \frac{\mathcal{P}\left(B_\epsilon \left(g(\omega)\right)\right)}{\lambda \left(B_\epsilon \left(g(\omega)\right)\right)} \quad \text{as } \epsilon \to 0  \\
\end{split}
$$

#### for a random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in that maps a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ into $(\mathbb{R}, \mathcal{B}(\mathbb{R})\mathcal{P}_X)$
- where $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ is the pushforward [[probability measure]] 
- and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$

$$
F_X =\mathcal{P}_X\left([-\infty, x)\right)
$$

- if $F_X$ is [[differentiable]] the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,\infty)$ exists and is given by

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

- With the PDF, we can compute probabilities of events involving $X$ by integrating over sets $C$

$$
\begin{split}
\mathbb{P}(X \in C) &=\int\limits^{C}  f_X(x)\:dx \\
\mathbb{P}(X \in [a,b]) &=\int\limits_{a}^{b}  f_X(x)\:dx
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

Tags: mathematics statistics SS25
<!--ID: 1664291691108-->
END


START
Basic
[[probability density function (PDF)]]
- definition (general and for a [[random variable]] $X$)
- when does it exist (general and for a [[random variable]] $X$)

Back: 
### probability density function
- a [[probability density function (PDF)]] is a [[measurable function]] $p: \mathbb{R} \to [0, \infty)$ that describes how a [[probability measure]] $\mathcal{P}$ on $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n)\right)$ is [[absolutely continuous]] with respect to the [[lebesgue measure]] $\lambda$ (see [[radon nikodym theorem]])

$$
\begin{split}
&p(\omega) = \frac{d\mathcal{P}}{d\lambda} (\omega) \\
\Rightarrow &d\mathcal{P}(\omega) = p(\omega)d\lambda(\omega) \\
\end{split}
$$
- thus for all $A \subseteq \mathbb{R}$

$$
\begin{split}
\mathcal{P}(A) = \int_A  d\mathcal{P}(\omega) 
&= \int_A  p(\omega) d\lambda(\omega) = \int_A  p(\omega) d\omega \\
\end{split}
$$

- intuitively, the [[probability density function (PDF)]] weights the [[lebesgue measure]] to build the [[probability measure]] $\mathcal{P}$
- instead of describing the [[probability density function (PDF)]] as a differential equation often it makes sense to describe the ratio of the measurement of an infinitesimal small [[ball]] around the point $\omega$

$$
\begin{split}
&p(\omega) \approx \frac{\mathcal{P}\left(B_\epsilon (\omega)\right)}{\lambda \left(B_\epsilon (\omega)\right)} \quad \text{as } \epsilon \to 0  \\
&p\left(g(\omega)\right) \approx \frac{\mathcal{P}\left(B_\epsilon \left(g(\omega)\right)\right)}{\lambda \left(B_\epsilon \left(g(\omega)\right)\right)} \quad \text{as } \epsilon \to 0  \\
\end{split}
$$

#### for a random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in that maps a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ into $(\mathbb{R}, \mathcal{B}(\mathbb{R})\mathcal{P}_X)$
- where $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ is the pushforward [[probability measure]] 
- and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$

$$
F_X =\mathcal{P}_X\left([-\infty, x)\right)
$$

- if $F_X$ is [[differentiable]] the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,\infty)$ exists and is given by

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

- With the PDF, we can compute probabilities of events involving $X$ by integrating over sets $C$

$$
\begin{split}
\mathbb{P}(X \in C) &=\int\limits^{C}  f_X(x)\:dx \\
\mathbb{P}(X \in [a,b]) &=\int\limits_{a}^{b}  f_X(x)\:dx
\end{split}
$$

### absolutely continuous
- given two [[probability measure]] $\mathcal{P}$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
- $\mathcal{P}$ is [[absolutely continuous]] to $\lambda$ written as $\mathcal{P} \ll \lambda$ if the following is hold for all $A \in \mathcal{A}$

$$
\lambda(A) = 0 \quad \Rightarrow \quad \mathcal{P}(A) = 0
$$

- in other words: $\mathcal{P}$ does not assign probabilities to sets that $\lambda$ considers zero
- in this case $\mathcal{P}$ can be described as a scaled version of $\lambda$ see ([[radon nikodym theorem]])

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
<!--ID: 1745690880073-->
END


START
Basic
[[probability density function (PDF)]]
- how to approximate the differential equation?
- how to approximate $p(g(\omega))$

Back: 
### probability density function
- a [[probability density function (PDF)]] is a [[measurable function]] $p: \mathbb{R} \to [0, \infty)$ that describes how a [[probability measure]] $\mathcal{P}$ on $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n)\right)$ is [[absolutely continuous]] with respect to the [[lebesgue measure]] $\lambda$ (see [[radon nikodym theorem]])

$$
\begin{split}
&p(\omega) = \frac{d\mathcal{P}}{d\lambda} (\omega) \\
\Rightarrow &d\mathcal{P}(\omega) = p(\omega)d\lambda(\omega) \\
\end{split}
$$
- thus for all $A \subseteq \mathbb{R}$

$$
\begin{split}
\mathcal{P}(A) = \int_A  d\mathcal{P}(\omega) 
&= \int_A  p(\omega) d\lambda(\omega) = \int_A  p(\omega) d\omega \\
\end{split}
$$

- intuitively, the [[probability density function (PDF)]] weights the [[lebesgue measure]] to build the [[probability measure]] $\mathcal{P}$
- instead of describing the [[probability density function (PDF)]] as a differential equation often it makes sense to describe the ratio of the measurement of an infinitesimal small [[ball]] around the point $\omega$

$$
\begin{split}
&p(\omega) \approx \frac{\mathcal{P}\left(B_\epsilon (\omega)\right)}{\lambda \left(B_\epsilon (\omega)\right)} \quad \text{as } \epsilon \to 0  \\
&p\left(g(\omega)\right) \approx \frac{\mathcal{P}\left(B_\epsilon \left(g(\omega)\right)\right)}{\lambda \left(B_\epsilon \left(g(\omega)\right)\right)} \quad \text{as } \epsilon \to 0  \\
\end{split}
$$

#### for a random variable
- given a [[random variable]] $X: \Omega \to \mathbb{R}$ in that maps a [[continuous probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ into $(\mathbb{R}, \mathcal{B}(\mathbb{R})\mathcal{P}_X)$
- where $\mathcal{P}_X:\mathcal{B}(\mathbb{R}) \to [0,1]$ is the pushforward [[probability measure]] 
- and its [[cumulative distribution function (CDF)]] $F_X: \mathbb{R} \to [0,1]$

$$
F_X =\mathcal{P}_X\left([-\infty, x)\right)
$$

- if $F_X$ is [[differentiable]] the [[probability density function (PDF)]] $f_X: \mathbb{R} \to [0,\infty)$ exists and is given by

$$
f_X(x) = \frac{dF_X(x)}{dx}
$$

- With the PDF, we can compute probabilities of events involving $X$ by integrating over sets $C$

$$
\begin{split}
\mathbb{P}(X \in C) &=\int\limits^{C}  f_X(x)\:dx \\
\mathbb{P}(X \in [a,b]) &=\int\limits_{a}^{b}  f_X(x)\:dx
\end{split}
$$

### absolutely continuous
- given two [[probability measure]] $\mathcal{P}$ and $\lambda$ on the same [[measurable space]] $(\Omega, \mathcal{A})$ 
- $\mathcal{P}$ is [[absolutely continuous]] to $\lambda$ written as $\mathcal{P} \ll \lambda$ if the following is hold for all $A \in \mathcal{A}$

$$
\lambda(A) = 0 \quad \Rightarrow \quad \mathcal{P}(A) = 0
$$

- in other words: $\mathcal{P}$ does not assign probabilities to sets that $\lambda$ considers zero
- in this case $\mathcal{P}$ can be described as a scaled version of $\lambda$ see ([[radon nikodym theorem]])

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
<!--ID: 1745991645677-->
END