## [[probability density function]]

$$
f_X\left(x|\mu, \sigma^2\right) = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]}
$$
## [[moment generating function]]

![[moment generating function#definition]]

$$
\psi_X(t) = \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]}
$$
(no proof)
## [[expectation]] / mean

$$
\begin{split}
\mathbb{E}[X] &= \mu \\ 

 &= \left.\frac{d\psi_X(t)}{dt} \right|_{t=0} \\
 &= \left.\frac{d}{dt} \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} (\mu+t \sigma^2) \right|_{t=0} \\
\end{split}
$$
## [[variance]]

$$
\begin{split}
\mathbb{VAR}[X] 
&= \mathbb{E}\left[X^2\right] - \mathbb{E}[X]^2\\
&= \mu^2 + \sigma^2 - \mu^2\\
&=  \sigma^2 \\ \\

\mathbb{E}\left[X^2\right] 
 &= \left.\frac{d^2\psi_X(t)}{dt^2} \right|_{t=0} \\
 &= \left.\frac{d^2}{dt^2} \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \frac{d}{dt} \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \left(\mu+t \sigma^2\right) \right|_{t=0} \\
 &= \left. \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \left(\left(\mu+t \sigma^2\right)^2 + \sigma^2\right) \right|_{t=0} \\
 &= \mu^2 + \sigma^2 \\
 
\end{split}
$$

## properties
### [[symmetric distribution]] around its mean $\mu$
![[symmetric distribution#symmetric around its mean]]

### [[mode]] equal to [[expectation|mean]] and [[median]] at $\mu$
$$
\mu = \mathrm{argmax}_x \: f_X\left(x|\mu, \sigma^2\right)
$$
proof:
$$
\begin{split}
\frac{d}{dx}f_X\left(x|\mu, \sigma^2\right) &= 0 \\
&= \frac{d}{dx}\frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]} \\
&= \frac{-1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]} \frac{(x-\mu)}{\sigma^2} \\
&\Rightarrow x=\mu
\end{split}
$$
### maximum of the [[probability density function]]
$$
\begin{split}
\mathrm{max}_x \: f_X\left(x|\mu, \sigma^2\right) 
&= f_X\left(\mu|\mu, \sigma^2\right) \\
&= \frac{1}{\sqrt{2 \pi \sigma^2}} \\
\end{split}
$$
### [[linear function|Linear Transformation]]
$$
\begin{split}
x &\sim f_x\left(x|\mu, \sigma^2 \right) \\
Y &= aX+b \sim f_Y\left(y | a\mu + b, a^2 \sigma^2\right) \\ 
\end{split}

$$
proof
$$
\begin{split}
\psi_X(t) &= \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} = \mathbb{E}\left[e^{Xt}\right] \\
\psi_Y(t) &= \mathbb{E}\left[e^{\left(aX+b\right)t}\right] \\
\psi_Y(t) &= \mathbb{E}\left[e^{aXt}\right] \cdot e^{bt} \\
\psi_Y(t) &= \psi_X(at) \cdot e^{bt} \\
\psi_Y(t) &= \exp{\left[\mu at+\frac{1}{2}\sigma^2 a^2 t^2\right]} \cdot e^{bt} \\
\psi_Y(t) &= \exp{\left[(\mu a + b)t+\frac{1}{2}\sigma^2 a^2 t^2\right]}  \\
\end{split}
$$
# standard [[normal distribution]]
$$
\phi(x) = f_X\left(x|\mu = 1, \sigma^2 = 0\right) = \frac{1}{\sqrt{2 \pi }}\exp{\left[-\frac{x}{2}\right]}
$$
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
# anki


START
Basic
- [[linear function|Linear Transformation]] of a [[normal distribution]] (with proof)
Back: 
## [[moment generating function]]

$$
\psi_X(t) = \mathbb{E}\left[e^{tx}\right] = \int\limits_{-\infty}^\infty e^{tx} f_X(x) dx
$$
$$
\psi_X(t) = \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]}
$$
### [[linear function|Linear Transformation]]
$$
\begin{split}
x &\sim f_x\left(x|\mu, \sigma^2 \right) \\
Y &= aX+b \sim f_Y\left(y | a\mu + b, a^2 \sigma^2\right) \\ 
\end{split}

$$
proof
$$
\begin{split}
\psi_X(t) &= \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} = \mathbb{E}\left[e^{Xt}\right] \\
\psi_Y(t) &= \mathbb{E}\left[e^{\left(aX+b\right)t}\right] \\
\psi_Y(t) &= \mathbb{E}\left[e^{aXt}\right] \cdot e^{bt} \\
\psi_Y(t) &= \psi_X(at) \cdot e^{bt} \\
\psi_Y(t) &= \exp{\left[\mu at+\frac{1}{2}\sigma^2 a^2 t^2\right]} \cdot e^{bt} \\
\psi_Y(t) &= \exp{\left[(\mu a + b)t+\frac{1}{2}\sigma^2 a^2 t^2\right]}  \\
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1680425858043-->
END


START
Basic
[[normal distribution]]
- [[probability density function]]
- [[moment generating function]] (no proof)
Back: 
## [[probability density function]]

$$
f_X\left(x|\mu, \sigma^2\right) = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]}
$$
## [[moment generating function]]

$$
\psi_X(t) = \mathbb{E}\left[e^{tx}\right] = \int\limits_{-\infty}^\infty e^{tx} f_X(x) dx
$$
$$
\psi_X(t) = \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]}
$$
(no proof)
Tags: mathematics, statistics
<!--ID: 1680336763978-->
END


START
Basic
[[normal distribution]]
- [[expectation]] (with proof)
- [[variance]] (with proof)
Back: 
## [[probability density function]]

$$
f_X\left(x|\mu, \sigma^2\right) = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]}
$$
## [[moment generating function]]

$$
\psi_X(t) = \mathbb{E}\left[e^{tx}\right] = \int\limits_{-\infty}^\infty e^{tx} f_X(x) dx
$$
$$
\psi_X(t) = \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]}
$$
(no proof)
## [[expectation]] / mean

$$
\begin{split}
\mathbb{E}[X] &= \mu \\ 

 &= \left.\frac{d\psi_X(t)}{dt} \right|_{t=0} \\
 &= \left.\frac{d}{dt} \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} (\mu+t \sigma^2) \right|_{t=0} \\
\end{split}
$$
## [[variance]]

$$
\begin{split}
\mathbb{VAR}[X] 
&= \mathbb{E}\left[X^2\right] - \mathbb{E}[X]^2\\
&= \mu^2 + \sigma^2 - \mu^2\\
&=  \sigma^2 \\ \\

\mathbb{E}\left[X^2\right] 
 &= \left.\frac{d^2\psi_X(t)}{dt^2} \right|_{t=0} \\
 &= \left.\frac{d^2}{dt^2} \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \frac{d}{dt} \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \left(\mu+t \sigma^2\right) \right|_{t=0} \\
 &= \left. \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \left(\left(\mu+t \sigma^2\right)^2 + \sigma^2\right) \right|_{t=0} \\
 &= \mu^2 + \sigma^2 \\
 
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1680336763984-->
END


START
Basic
[[normal distribution]]
- symmetrie (with proof)
- [[mode]] (with proof)
- [[probability density function]] optimum (with proof)
Back: 
## [[probability density function]]

$$
f_X\left(x|\mu, \sigma^2\right) = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]}
$$
## [[moment generating function]]

$$
\psi_X(t) = \mathbb{E}\left[e^{tx}\right] = \int\limits_{-\infty}^\infty e^{tx} f_X(x) dx
$$
$$
\psi_X(t) = \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]}
$$
(no proof)
## properties
### [[symmetric distribution]] around its mean $\mu$

A [[distribution]] is symmetric around its mean iff $f_X(\mu + x) = f_X(\mu - x)$

$$
\begin{split}
f_X(\mu + x) = f_X(\mu - x) 
&\Rightarrow F_X(\mu + x) = 1- F_X(\mu - x) \\
&\Rightarrow F_X(\mu - x) = 1- F_X(\mu + x) \\
\end{split}
$$
proof
$$
\begin{split}
f_X(\mu + x) = f_X(\mu - x) 
&\Rightarrow P\left(X \leq \mu - x\right) = P\left(X \geq \mu + x\right) \\ 
&\Rightarrow P\left(X \leq \mu - x\right) = 1 - P\left(X \leq \mu + x\right) \\ 
&\Rightarrow F_X\left( \mu - x\right) = 1 - F_X\left( \mu + x\right) \\ 
&\Rightarrow F_X\left( \mu + x\right) = 1 - F_X\left( \mu - x\right) \\ 


\end{split}
$$
### [[mode]] equal to [[expectation|mean]] and [[median]] at $\mu$
$$
\mu = \mathrm{argmax}_x \: f_X\left(x|\mu, \sigma^2\right)
$$
proof:
$$
\begin{split}
\frac{d}{dx}f_X\left(x|\mu, \sigma^2\right) &= 0 \\
&= \frac{d}{dx}\frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]} \\
&= \frac{-1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]} \frac{(x-\mu)}{\sigma^2} \\
&\Rightarrow x=\mu
\end{split}
$$
### maximum of the [[probability density function]]
$$
\begin{split}
\mathrm{max}_x \: f_X\left(x|\mu, \sigma^2\right) 
&= f_X\left(\mu|\mu, \sigma^2\right) \\
&= \frac{1}{\sqrt{2 \pi \sigma^2}} \\
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1680336763988-->
END


START
Basic
[[normal distribution]]
- summary
Back: 
## [[probability density function]]

$$
f_X\left(x|\mu, \sigma^2\right) = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]}
$$
## [[moment generating function]]

$$
\psi_X(t) = \mathbb{E}\left[e^{tx}\right] = \int\limits_{-\infty}^\infty e^{tx} f_X(x) dx
$$
$$
\psi_X(t) = \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]}
$$
(no proof)
## [[expectation]] / mean

$$
\begin{split}
\mathbb{E}[X] &= \mu \\ 

 &= \left.\frac{d\psi_X(t)}{dt} \right|_{t=0} \\
 &= \left.\frac{d}{dt} \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} (\mu+t \sigma^2) \right|_{t=0} \\
\end{split}
$$
## [[variance]]

$$
\begin{split}
\mathbb{VAR}[X] 
&= \mathbb{E}\left[X^2\right] - \mathbb{E}[X]^2\\
&= \mu^2 + \sigma^2 - \mu^2\\
&=  \sigma^2 \\ \\

\mathbb{E}\left[X^2\right] 
 &= \left.\frac{d^2\psi_X(t)}{dt^2} \right|_{t=0} \\
 &= \left.\frac{d^2}{dt^2} \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \frac{d}{dt} \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \left(\mu+t \sigma^2\right) \right|_{t=0} \\
 &= \left. \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]} \left(\left(\mu+t \sigma^2\right)^2 + \sigma^2\right) \right|_{t=0} \\
 &= \mu^2 + \sigma^2 \\
 
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1680336763991-->
END