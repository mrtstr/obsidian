### estimator convergence
- give a [[statistical estimator]] $X_n$ and with en [[expectation]] that [[convergence in probability|converges in probability]] against $\mu$ and a [[variance]] that converges against zero i.e. $\mathbb{E}[X_n] \xrightarrow{\mathbb{P}} \mu$ and $\mathbb{VAR}[X_n] \xrightarrow{\mathbb{P}} 0$ 
- then $X_n \xrightarrow{\mathbb{P}} \mu$ also converges against $\mu$

#### proof
$$
\begin{split}
\mathbb{P}\left(|X_n-\mu| > \epsilon\right) 
&\leq \frac{\mathbb{E}\left[(X_n-\mu)^2\right]}{\epsilon^2}  \\
&\leq \frac{\mathbb{VAR}[X_n]}{\epsilon^2} \xrightarrow{n \to \infty} 0 \\
\end{split}
$$

# --------------------

![[chebyshev markov inequality#markov inequality]]


![[convergence in probability#convergence in probability]]
# Anki

START
Basic
how to show that a [[statistical estimator]] converges against a certain value

Back: 
1) show that the [[expectation]] of the [[statistical estimator]] [[convergence in probability|converges in probability]]  against the value
2) show that the [[variance]] [[convergence in probability|converges in probability]]  against zero

### estimator convergence
- give a [[statistical estimator]] $X_n$ and with en [[expectation]] that [[convergence in probability|converges in probability]] against $\mu$ and a [[variance]] that converges against zero i.e. $\mathbb{E}[X_n] \xrightarrow{\mathbb{P}} \mu$ and $\mathbb{VAR}[X_n] \xrightarrow{\mathbb{P}} 0$ 
- then $X_n \xrightarrow{\mathbb{P}} \mu$ also converges against $\mu$

#### proof
$$
\begin{split}
\mathbb{P}\left(|X_n-\mu| > \epsilon\right) 
&\leq \frac{\mathbb{E}\left[(X_n-\mu)^2\right]}{\epsilon^2}  \\
&\leq \frac{\mathbb{VAR}[X_n]}{\epsilon^2} \xrightarrow{n \to \infty} 0 \\
\end{split}
$$

_________________

### markov inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{E}\left[|X|^r\right] \geq \epsilon^r \cdot \mathbb{P}\left(|X| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[|X|^r\right] 
&= \int_{-\infty}^{0} (-x)^r f_X(x) \mathrm{d} x^r + \int_{0}^{\infty} x f_X(x) \mathrm{d} x \\
&= \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{-\epsilon}^{0} (-x)^r f_X(x) \mathrm{d} x 
+ \int_{0}^{\epsilon} x^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} \epsilon^r f_X(x) \mathrm{d} x + \int_{\epsilon}^{\infty} \epsilon^r f_X(x) \mathrm{d} x \\
&\geq \epsilon^r \cdot \mathbb{P}(|X| \geq \epsilon)\\
\end{split}
$$

### convergence in probability
- given a sequence of [[random variable]] $\{X_n\}$
- $X_n$ is converging against a [[random variable]] $X$ if there difference in probability get arbitrary small

$$
\forall \epsilon > 0: \lim_{n \to \infty}\mathbb{P}\left(|X_n - X | \geq \epsilon\right) = 0
$$

#### equivalent statements

$$
\mathbb{P}(X_n \leq x) \to \mathbb{P}(X \leq x)
$$

$$
\mathbb{E}[X_n] \to \mathbb{E}[X_n]
$$



Tags: mathematics time_series WS2425
<!--ID: 1737718507729-->
END