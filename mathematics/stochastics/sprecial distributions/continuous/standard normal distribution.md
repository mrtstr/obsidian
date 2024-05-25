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
&= P\left(X \leq  y \sigma + \mu \right) = F_X\left(y \sigma + \mu\right) \\ \\
f_{Y}(y) &= \frac{dF_{Y}(y)}{dy} = \frac{dF_X\left(y \sigma + \mu \right)}{dy}  \\
&= \frac{d\left(y \sigma - \mu \right)}{dy} f_{X}\left(y \sigma + \mu \right)
= \sigma f_{X}\left(y \sigma + \mu \right) \\
&= \frac{\sigma}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(y \sigma - \mu +\mu)^2}{\sigma^2}\right]} \\
&= \frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{y^2}{2}\right]} \\
&= \phi(x) \\
\end{split}
$$

## [[probability integral transformation|transformation]] from [[standard normal distribution]] to a [[normal distribution]]

### [[probability density function]] and [[cumulative distribution function (CDF)]]
$$
\begin{split}
X &\sim \phi(x) = f_X(x | \mu = 0, \sigma^2 =1)  \\
Y &= aX + b  \\


\Rightarrow Y & \sim f_Y\left(y |  b, a^2 \right) 
 = \frac{1}{\sqrt{2 \pi a^2 }}\exp{\left[-\frac{1}{2}\frac{(x- b)^2}{a^2 }\right]} \\
 \Rightarrow F_Y(y) &=   \Phi\left(\frac{y-b}{a}\right) \\
\end{split}
$$
proof 
![[normal distribution#proof1: functions of random variables]]


### [[quantile function]]

$$
F^{-1}_Y(q) =  a \Phi^{-1}\left(q\right) + b
$$
proof
$$
\begin{split}
1) \: F_Y(y) &=   \Phi\left(\frac{y-b}{a}\right) \\
2) \: F_Y(y)  &= q \Leftrightarrow F^{-1}_Y(q) = y \\ 
\Rightarrow q &= \Phi\left(\frac{y-b}{a}\right) \\
\Rightarrow \Phi^{-1}\left(q\right) 
&=   \Phi^{-1}\left(\Phi\left(\frac{y-b}{a}\right)\right)  =   \frac{y-b}{a}  \\
\Rightarrow y &=  a \Phi^{-1}\left(q\right) + b  \\
\Rightarrow F^{-1}_Y(q) &=  a \Phi^{-1}\left(q\right) + b  \\

\end{split}
$$

# anki


START
Basic
[[standard normal distribution]]
- definition
- [[probability density function]]
- [[moment generating function]]
Back: 
#### Definition
[[normal distribution]] with [[expectation|mean]] $\mu = 1$ and [[variance]] $\sigma^2 = 0$ is called [[standard normal distribution]]
#### [[probability density function]]
$$
\phi(x) = f_X\left(x|\mu = 1, \sigma^2 = 0\right) = \frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x}{2}\right]}
$$
#### [[moment generating function]]

$$
\psi_X(t) = \exp{\left[\frac{t^2}{2}\right]}
$$
Tags: mathematics statistics
<!--ID: 1680933861852-->
END


START
Basic
[[probability integral transformation|transformation]] of a [[normal distribution]] to a [[standard normal distribution]]
- [[probability density function]]
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


Tags: mathematics statistics
<!--ID: 1680933861858-->
END


START
Basic
[[probability integral transformation|transformation]] from [[standard normal distribution]] to a [[normal distribution]]
- [[probability density function]]
- [[cumulative distribution function (CDF)]]
Back: 

### [[probability density function]] and [[cumulative distribution function (CDF)]]
$$
\begin{split}
X &\sim \phi(x) = f_X(x | \mu = 0, \sigma^2 =1)  \\
Y &= aX + b  \\


\Rightarrow Y & \sim f_Y\left(y |  b, a^2 \right) 
 = \frac{1}{\sqrt{2 \pi a^2 }}\exp{\left[-\frac{1}{2}\frac{(x- b)^2}{a^2 }\right]} \\
 \Rightarrow F_Y(y) &=   \Phi\left(\frac{y-b}{a}\right) \\
\end{split}
$$

proof
$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) = P(aX+b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P(aX+b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P\left( X \leq \frac{y-b}{a} \right) \\
&= F_X\left(g^{-1}(y)\right) = F_X\left(\frac{y-b}{a}\right) \\

f_{Y}(y) &= \frac{dF_{Y}(y)}{dy} = \frac{dF_{Y}(y)}{dy} f_{X}\left(\frac{y-b}{a}\right) \\
&= \frac{dg^{-1}(y)}{dy} f_{X}\left(\frac{y-b}{a}\right) \\
&=\underbrace{\frac{1}{|a|}}_{\frac{dg^{-1}(y)}{dy}} f_{X}
\underbrace{
\left(\frac{y-b}{a}\right)
}_{g^{-1}(y)} \\
&=\frac{1}{|a|} \frac{1}{\sqrt{2 \pi \sigma^2 }} \exp{\left(-\frac{1}{2}\frac{\left(\mu - \frac{y-b}{a}\right)^2}{\sigma^2}\right)} \\
&=\frac{1}{|a|} \frac{1}{\sqrt{2 \pi \sigma^2 }} \exp{\left(-\frac{1}{2}\frac{\left(\frac{a\mu - y-b}{a}\right)^2}{\sigma^2}\right)} \\
&=\frac{1}{\sqrt{2 \pi a^2 \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(y-a\mu + b)^2}{a^2 \sigma^2}\right]} \\ 
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1680933861861-->
END


START
Basic
- [[quantile function]] of a linear [[probability integral transformation|transformed]] [[standard normal distribution]] depending on the quantile of the [[standard normal distribution]] with proof

Back: 

### [[quantile function]]

$$
F^{-1}_Y(q) =  a \Phi^{-1}\left(q\right) + b
$$
proof
$$
\begin{split}
1) \: F_Y(y) &=   \Phi\left(\frac{y-b}{a}\right) \\
2) \: F_Y(y)  &= q \Leftrightarrow F^{-1}_Y(q) = y \\ 
\Rightarrow q &= \Phi\left(\frac{y-b}{a}\right) \\
\Rightarrow \Phi^{-1}\left(q\right) 
&=   \Phi^{-1}\left(\Phi\left(\frac{y-b}{a}\right)\right)  =   \frac{y-b}{a}  \\
\Rightarrow y &=  a \Phi^{-1}\left(q\right) + b  \\
\Rightarrow F^{-1}_Y(q) &=  a \Phi^{-1}\left(q\right) + b  \\

\end{split}
$$

### given the [[cumulative distribution function (CDF)]]
$$
\begin{split}
X &\sim \phi(x) = f_X(x | \mu = 0, \sigma^2 =1)  \\
Y &= aX + b  \\

 \Rightarrow F_Y(y) &=   \Phi\left(\frac{y-b}{a}\right) \\
\end{split}
$$

proof
$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) = P(aX+b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P(aX+b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P\left( X \leq \frac{y-b}{a} \right) \\
&= F_X\left(g^{-1}(y)\right) = F_X\left(\frac{y-b}{a}\right) \\
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1698471532949-->
END