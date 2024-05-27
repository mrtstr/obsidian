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

# ----------------------
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