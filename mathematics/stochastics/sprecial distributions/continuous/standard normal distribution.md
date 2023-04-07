# standard [[normal distribution]]
[[normal distribution]] with [[expectation|mean]] $\mu = 1$ and [[variance]] $\sigma^2 = 0$ is called [[standard normal distribution]]
## [[probability density function]]
$$
\phi(x) = f_X\left(x|\mu = 1, \sigma^2 = 0\right) = \frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x}{2}\right]}
$$
## [[moment generating function]]

![[moment generating function#definition]]

$$
\psi_X(t) = \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]}
$$
## [[symmetric distribution|symmetrie]]
Sice the [[normal distribution]] is symmetric around its mean and the mean of the standard [[normal distribution]] is zero
![[symmetric distribution#symmetric around zero]]

## [[probability integral transformation|transformation]] of a [[normal distribution]] to a standard [[normal distribution]]
$$
\begin{split}
&X \sim f_X(x | \mu, \sigma^2) \: with \: F_X(x | \mu, \sigma^2) \\
& \Rightarrow F_X(x | \mu, \sigma^2) = \Phi\left( \frac{x - \mu}{\sigma}\right) \\
& \Rightarrow F^{-1}_X(q | \mu, \sigma^2) = \mu + \sigma \Phi^{-1}\left(q\right) \\
\end{split}
$$
