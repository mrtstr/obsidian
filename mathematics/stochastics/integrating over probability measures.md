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

____________

$$
\begin{split}
\mathbb{P}([a,b]) = \int_{[a,b]}  d\mathbb{P}(\omega) 
&= \int_{[a,b]}  p(\omega) d\lambda(\omega) \\
&= \int_a^b  p(\omega) d\omega \\
\end{split}
$$

$$
\begin{split}
\mathbb{\lambda}([a,b]) 
&= \int_{[a, b]}  d\lambda(\omega) = b - a\\
\end{split}
$$

# ----------

![[lebesgue measure#lebesgue measure]]

![[radon nikodym theorem#radon nikodym theorem]]

![[random variable#random variable]]

![[probability measure#probability measure]]