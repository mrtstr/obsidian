### integrating over probability measures
- given a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$ and a [[random variable]] $X: \Omega \to \mathbb{R}$ with a [[probability measure]] $\mathcal{P}_X(C): \mathcal{B}(\mathbb{R}) \to [0,1] = \mathbb{P}\left(X^{-1}(C)\right)$
- the probability of an [[event]] $A \in \mathcal{A}$ is calculated by the [[integral]] over its [[probability measure]]


$$
\begin{split}
\mathbb{P}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\mathbb{P}(\omega) \\
&= \int_A  d\mathbb{P}(\omega) \\
&= \int_\Omega \mathbb{I}[\omega \in A] d\mathbb{P}(\omega) \\
\end{split}
$$

- if $\mathbb{P}$ has a [[probability density function (PDF)]] $p:\Omega \to \mathbb{R}$ then $d\mathbb{P}(\omega) = p(\omega)d\omega$ 

$$
\begin{split}
\mathbb{P}(A) 
&= \int_\Omega \mathbb{I}[\omega \in A] d\mathbb{P}(\omega) \\
&= \int_\Omega \mathbb{I}[\omega \in A] p(\omega) d\omega  \\
\end{split}
$$


# ----------
![[random variable#random variable]]

![[probability measure#probability measure]]