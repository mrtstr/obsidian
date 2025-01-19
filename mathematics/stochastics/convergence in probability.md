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



# -------------
![[random variable#random variable]]




# anki


START
Basic
[[convergence in probability]]
- definition
- verbal explanation
- two equivalent statements
Back: 

### convergence in probability
- given a sequence of [[random variable]] $\{X_n\}$
- $X_n$ is converging against a [[random variable]] $X$ if there difference in probabiulity get arbitrary small

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

__________________

### random variable
- given a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$
- a [[function]] $X: \Omega \to \mathbb{R}$ from the [[sample space]] $\Omega$ to the [[real numbers]] $\mathbb{R}$ is a [[random variable]] if it's a [[measurable function]] $X: (\Omega, \mathcal{A}) \to \left(\mathbb{R}, \mathcal{B}(\mathbb{R})\right)$ 

$$
\forall C \in \mathcal{B}(\mathbb{R}): X^{-1}(C) = \{\omega \in \Omega : X(\omega) \in C\} \in \mathcal{A}
$$

- this is the case exactly when the following is true (given the [[inverse function]] $X^{-1}: \mathbb{R} \to \Omega$)

$$
\forall x \in \mathbb{R}: X^{-1}\left((-\infty, x]\right) = \{\omega \in \Omega: X(\omega) \in (-\infty, x]\} \in \mathcal{A}
$$

Tags: mathematics statistics WS2425
<!--ID: 1729346313380-->
END