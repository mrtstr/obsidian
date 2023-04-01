## [[probability density function]]

$$
f_X\left(x|\mu, \sigma^2\right) = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]}
$$
## [[moment generating function]]

![[moment generating function#definition]]

$$
\psi_X(t) = \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]}
$$
(no proof)
## [[expectation]] / mean

$$
\begin{split}
\mathbb{E}[X] &= \mu \\ 

 &= \left.\frac{d\psi_X(t)}{dt} \right|_{t=0} \\
 &= \left.\frac{d}{dt} \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} (\mu+t \sigma^2) \right|_{t=0} \\
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
 &= \left.\frac{d^2}{dt^2} \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \frac{d}{dt} \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \left(\mu+t \sigma^2\right) \right|_{t=0} \\
 &= \left. \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \left(\left(\mu+t \sigma^2\right)^2 + \sigma^2\right) \right|_{t=0} \\
 &= \mu^2 + \sigma^2 \\
 
\end{split}
$$

## properties
### [[symmetric distribution]] around its mean $\mu$

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


# anki

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
\psi_X(t) = \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]}
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
\psi_X(t) = \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]}
$$
(no proof)
## [[expectation]] / mean

$$
\begin{split}
\mathbb{E}[X] &= \mu \\ 

 &= \left.\frac{d\psi_X(t)}{dt} \right|_{t=0} \\
 &= \left.\frac{d}{dt} \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} (\mu+t \sigma^2) \right|_{t=0} \\
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
 &= \left.\frac{d^2}{dt^2} \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \frac{d}{dt} \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \left(\mu+t \sigma^2\right) \right|_{t=0} \\
 &= \left. \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \left(\left(\mu+t \sigma^2\right)^2 + \sigma^2\right) \right|_{t=0} \\
 &= \mu^2 + \sigma^2 \\
 
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1680336763984-->
END


START
Basic
[[normal distribution]]
- symmetrie
- [[mode]]
- [[probability density function]] optimum
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
\psi_X(t) = \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]}
$$
(no proof)
## properties
### [[symmetric distribution]] around its mean $\mu$

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
\psi_X(t) = \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]}
$$
(no proof)
## [[expectation]] / mean

$$
\begin{split}
\mathbb{E}[X] &= \mu \\ 

 &= \left.\frac{d\psi_X(t)}{dt} \right|_{t=0} \\
 &= \left.\frac{d}{dt} \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} (\mu+t \sigma^2) \right|_{t=0} \\
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
 &= \left.\frac{d^2}{dt^2} \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \right|_{t=0} \\
 &= \left. \frac{d}{dt} \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \left(\mu+t \sigma^2\right) \right|_{t=0} \\
 &= \left. \exp{\left[\mu t-\frac{1}{2}\sigma^2 t^2\right]} \left(\left(\mu+t \sigma^2\right)^2 + \sigma^2\right) \right|_{t=0} \\
 &= \mu^2 + \sigma^2 \\
 
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1680336763991-->
END