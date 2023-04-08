# standard [[normal distribution]]
[[normal distribution]] with [[expectation|mean]] $\mu = 1$ and [[variance]] $\sigma^2 = 0$ is called [[standard normal distribution]]
## [[probability density function]]
$$
\phi(x) = f_X\left(x|\mu = 1, \sigma^2 = 0\right) = \frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x}{2}\right]}
$$
## [[moment generating function]]

![[moment generating function#definition]]

$$
\psi_X(t) = \exp{\left[\frac{t^2}{2}\right]}
$$
## [[symmetric distribution|symmetrie]]
Sice the [[normal distribution]] is symmetric around its mean and the mean of the standard [[normal distribution]] is zero
![[symmetric distribution#symmetric around zero]]

## [[probability integral transformation|transformation]] of a [[normal distribution]] to a [[standard normal distribution]]
$$
\begin{split}
X &\sim f_X(x | \mu, \sigma^2)  \\
 \Rightarrow Y &= \frac{X-\mu}{\sigma}\sim \phi(y)
\end{split}
$$
proof
$$
\begin{split}
F_Y(y) &= P\left(Y \leq  y\right) = P\left(\frac{X-\mu}{\sigma}  \leq  y\right) \\
&= P\left(X \leq  y \sigma - \mu \right) = F_X\left(y \sigma - \mu\right) \\ \\
f_{Y}(y) &= \frac{dF_{Y}(y)}{dy} = \frac{dF_X\left(y \sigma - \mu \right)}{dy}  \\
&= \frac{d\left(y \sigma - \mu \right)}{dy} f_{X}\left(y \sigma - \mu \right)
= \sigma f_{X}\left(y \sigma - \mu \right) \\
&= \frac{\sigma}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(y \sigma - \mu -\mu)^2}{\sigma^2}\right]} \\
&= \frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{y^2}{2}\right]} \\
&= \phi(x) \\
\end{split}
$$

## [[probability integral transformation|transformation]] from [[standard normal distribution]] to a [[normal distribution]]

$$
\begin{split}
X &\sim \phi(y) = f_X(x | \mu = 0, \sigma^2 =1)  \\
 \Rightarrow Y &= aX + b \sim f_Y\left(y |  b, a^2 \right) 
 = \frac{1}{\sqrt{2 \pi a^2 }}\exp{\left[-\frac{1}{2}\frac{(x- b)^2}{a^2 }\right]}
\end{split}
$$

proof 
![[normal distribution#proof1: functions of random variables]]



# anki


START
Basic
[[standard normal distribution]]
- [[probability density function]]
- [[moment generating function]]
Back: 
## [[probability density function]]
$$
\phi(x) = f_X\left(x|\mu = 1, \sigma^2 = 0\right) = \frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x}{2}\right]}
$$
## [[moment generating function]]

$$
\psi_X(t) = \exp{\left[\frac{t^2}{2}\right]}
$$
Tags: mathematics, statistics
<!--ID: 1680933861852-->
END


START
Basic
[[probability integral transformation|transformation]] of a [[normal distribution]] to a [[standard normal distribution]]
Back: 
## [[probability density function]]
$$
\phi(x) = f_X\left(x|\mu = 1, \sigma^2 = 0\right) = \frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x}{2}\right]}
$$
## [[moment generating function]]

$$
\psi_X(t) = \exp{\left[\frac{t^2}{2}\right]}
$$
## [[probability integral transformation|transformation]] of a [[normal distribution]] to a [[standard normal distribution]]
$$
\begin{split}
X &\sim f_X(x | \mu, \sigma^2)  \\
 \Rightarrow Y &= \frac{X-\mu}{\sigma}\sim \phi(y)
\end{split}
$$
proof
$$
\begin{split}
F_Y(y) &= P\left(Y \leq  y\right) = P\left(\frac{X-\mu}{\sigma}  \leq  y\right) \\
&= P\left(X \leq  y \sigma - \mu \right) = F_X\left(y \sigma - \mu\right) \\ \\
f_{Y}(y) &= \frac{dF_{Y}(y)}{dy} = \frac{dF_X\left(y \sigma - \mu \right)}{dy}  \\
&= \frac{d\left(y \sigma - \mu \right)}{dy} f_{X}\left(y \sigma - \mu \right)
= \sigma f_{X}\left(y \sigma - \mu \right) \\
&= \frac{\sigma}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(y \sigma - \mu -\mu)^2}{\sigma^2}\right]} \\
&= \frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{y^2}{2}\right]} \\
&= \phi(x) \\
\end{split}
$$


Tags: mathematics, statistics
<!--ID: 1680933861858-->
END


START
Basic
[[probability integral transformation|transformation]] from [[standard normal distribution]] to a [[normal distribution]]
Back: 
## [[probability density function]]
$$
\phi(x) = f_X\left(x|\mu = 1, \sigma^2 = 0\right) = \frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x}{2}\right]}
$$
## [[moment generating function]]

$$
\psi_X(t) = \exp{\left[\frac{t^2}{2}\right]}
$$
## [[probability integral transformation|transformation]] from [[standard normal distribution]] to a [[normal distribution]]

$$
\begin{split}
X &\sim \phi(y) = f_X(x | \mu = 0, \sigma^2 =1)  \\
 \Rightarrow Y &= aX + b \sim f_Y\left(y |  b, a^2 \right) 
 = \frac{1}{\sqrt{2 \pi a^2 }}\exp{\left[-\frac{1}{2}\frac{(x- b)^2}{a^2 }\right]}
\end{split}
$$

proof
$$
\begin{split}
X &\sim f_x\left(x|\mu, \sigma^2 \right) \\
\Rightarrow Y &= aX+b \\
&\sim f_Y\left(y | a\mu + b, a^2 \sigma^2\right) =\frac{1}{\sqrt{2 \pi a^2 \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-a\mu + b)^2}{a^2 \sigma^2}\right]} \\ 
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1680933861861-->
END