### rao blackwell theorem
- given a [[random variable]] $X$ with a [[sufficient statistics]] $T$
- given a part of the parameter represented by the function $\gamma:\Theta \to \mathbb{R}$
- for every unbiased [[statistical estimator]] $S$ for $\gamma(\vartheta)$ there is a further [[statistical estimator]] $S^* \circ T = S^*(T)$ that only depends on the [[sufficient statistics]] $T$ and is unbiased and has [[variance]] that is smaller or equal

$$
\begin{split}
\mathbb{E}_\vartheta\left[S^*(T)\right] &= \gamma(\vartheta) \qquad &\text{(unbiased)} \\
\mathbb{VAR}_\vartheta\left[S^*(T)\right] &\leq \mathbb{VAR}_\vartheta\left[S\right]
\end{split}
$$

- further if $S$ is not already a function if the [[sufficient statistics]] $T$ then the [[variance]] is even really smaller

$$
\mathbb{VAR}_\vartheta\left[S^*(T)\right] \le \mathbb{VAR}_\vartheta\left[S\right]
$$

#### interpretation
- if a [[sufficient statistics]] exists the [[best estimator]] is only dependent on the [[sufficient statistics]]
# ---------------
![[sufficient statistics#sufficient statistics]]


# anki


START
Basic
[[rao blackwell theorem]]
- definition
- interpretation

Back: 
### rao blackwell theorem
- given a [[random variable]] $X$ with a [[sufficient statistics]] $T$
- given a part of the parameter represented by the function $\gamma:\Theta \to \mathbb{R}$
- for every unbiased [[statistical estimator]] $S$ for $\gamma(\vartheta)$ there is a further [[statistical estimator]] $S^* \circ T = S^*(T)$ that only depends on the [[sufficient statistics]] $T$ and is unbiased and has [[variance]] that is smaller or equal

$$
\begin{split}
\mathbb{E}_\vartheta\left[S^*(T)\right] &= \gamma(\vartheta) \qquad &\text{(unbiased)} \\
\mathbb{VAR}_\vartheta\left[S^*(T)\right] &\leq \mathbb{VAR}_\vartheta\left[S\right]
\end{split}
$$

- further if $S$ is not already a function if the [[sufficient statistics]] $T$ then the [[variance]] is even really smaller

$$
\mathbb{VAR}_\vartheta\left[S^*(T)\right] \le \mathbb{VAR}_\vartheta\left[S\right]
$$

#### interpretation
- if a [[sufficient statistics]] exists the [[best estimator]] is only dependent on the [[sufficient statistics]]

________________


### sufficient statistics
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- a [[statistics]] $T: \mathfrak{X} \to \mathfrak{Y}$ is a [[sufficient statistics]] if there exists the [[measurable function|measurable functions]] $g_\vartheta: \mathfrak{Y} \to \mathbb{R}$ and $h: \mathfrak{X} \to \mathbb{R}$ such that the following being true $\forall x \in \mathfrak{X}$

$$
f_\vartheta(x) = g_\vartheta(T(x)) h(x) 
$$

- without loss of generality wen can assume that  $g_\vartheta, h \geq 0$ 

#### interpretation
- in this case $T$ contains all the nesseary information for $\vartheta$ that is contained in $X$  

Tags: mathematics statistics WS2425
<!--ID: 1731257650579-->
END