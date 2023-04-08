# normal distribution
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
### proof

$$
\begin{split}
f_X\left(x =\mu -x|\mu, \sigma^2\right) 
& = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{\left((\mu -x)- \mu \right)^2}{\sigma^2}\right]} \\
& = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(-x)^2}{\sigma^2}\right]} \\
& = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{x^2}{\sigma^2}\right]} \\
& = f_X\left(x =\mu +x|\mu, \sigma^2\right) \\
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
## [[linear transformation of random variables|linear transformation]] of a [[normal distribution|normal distributed]] [[random variable]]

$$
\begin{split}
X &\sim f_x\left(x|\mu, \sigma^2 \right) \\
\Rightarrow Y &= aX+b \\
&\sim f_Y\left(y | a\mu + b, a^2 \sigma^2\right) =\frac{1}{\sqrt{2 \pi a^2 \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-a\mu + b)^2}{a^2 \sigma^2}\right]} \\ 
\end{split}
$$
### proof1: [[moment generating function]]
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
### proof1: [[functions of random variables]]
![[functions of random variables#linear function of a probability density function]]

$$
\begin{split}
f_Y(y)
&=\underbrace{\frac{1}{|a|}}_{\frac{dg^{-1}(y)}{dy}} f_{X}
\underbrace{
\left(\frac{y-b}{a}\right)
}_{g^{-1}(y)} \\
&=\frac{1}{|a|} \frac{1}{\sqrt{2 \pi \sigma^2 }} \exp{\left(-\frac{1}{2}\frac{\left(\mu - \frac{y-b}{a}\right)^2}{\sigma^2}\right)} \\
&=\frac{1}{|a|} \frac{1}{\sqrt{2 \pi \sigma^2 }} \exp{\left(-\frac{1}{2}\frac{\left(\frac{a\mu - y-b}{a}\right)^2}{\sigma^2}\right)} \\
&=\frac{1}{\sqrt{2 \pi a^2 \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(y-a\mu + b)^2}{a^2 \sigma^2}\right]} \\ 
\end{split}
$$
## Linear Combinations of [[normal distribution|normal distributed]] [[random variable|random variables]]
Linear Combinations of [[normal distribution|normal distributed]] [[random variable|random variables]] are again normal distributed.
### Sum of [[normal distribution|normal distributed]] [[random variable|random variables]]
$$
\begin{split}
X_i &\sim f_{X_i}\left(x_i | \mu_i, \sigma_i^2\right) \\
\Rightarrow Y&=\sum_{i=1}^nX_i \sim f_{Y}\left(y \mid \sum_{i=1}^n \mu_i, \sum_{i=1}^n \sigma_i^2\right) \\ \\

\psi_Y(t)&=\mathbb{E}\left[e^{tY}\right] = \mathbb{E}\left[\exp{\left(t\sum_{i=1}^nX_i\right)}\right] \\
&=\prod_{i=1}^n \mathbb{E}\left[\exp{\left(tX_i\right)}\right] = \prod_{i=1}^n \psi_{X_i}(t) \\
&=\prod_{i=1}^n \exp{\left[\mu_i t+\frac{1}{2}\sigma_i^2 t^2\right]} \\
&= \exp{\left[t\sum_{i=1}^n\mu_i +\frac{t^2}{2}\sum_{i=1}^n\sigma_i^2 \right]} \\

\end{split}
$$
### [[linear function|Linear Functions]] of [[normal distribution|normal distributed]] [[random variable|random variables]]

$$
\begin{split}
X_i &\sim f_{X_i}\left(x_i | \mu_i, \sigma_i^2\right) \\
\Rightarrow Y&=\sum_{i=1}^n a_i +b \sim f_{Y}\left(y \mid \sum_{i=1}^n a_i \mu_i + b, \sum_{i=1}^n a_i^2 \sigma_i^2\right) \\ \\

\psi_Y(t)&=\mathbb{E}\left[e^{tY}\right] = \mathbb{E}\left[\exp{\left(t\left(\sum_{i=1}^n a_i X_i + b\right)\right)}\right] \\
&= \mathbb{E}\left[e^{tb}\right] \cdot \prod_{i=1}^n \mathbb{E}\left[\exp{\left(t a_i X_i\right)}\right] = \mathbb{E}\left[e^{tb}\right] \cdot  \prod_{i=1}^n \psi_{X_i}(a_it) \\
&=\mathbb{E}\left[e^{tb}\right] \cdot \prod_{i=1}^n \exp{\left[\mu_i a_i t+\frac{1}{2}\sigma_i^2 a_i^2 t^2\right]} \\
&= \exp{\left[t\left(\sum_{i=1}^n\mu_i + b\right) +\frac{t^2}{2}\sum_{i=1}^n\sigma_i^2 \right]} \\

\end{split}
$$
## [[random sample]] from a [[normal distribution]]

The mean from a [[random sample]] of the sixe $n$ from a [[normal distribution]] is again [[normal distribution|normal distributed]] with a mean $\mu$ and a [[variance]] $\frac{\sigma^2}{n}$. 
$$
\begin{split}
X_i &\sim f_{X}\left(x | \mu, \sigma^2\right) \: i.i.d \\
\Rightarrow \bar{X_n}&=\frac{1}{n}\sum_{i=1}^nX_i \sim f_{\bar{X_n}}\left(\bar{x} \mid  \mu, \frac{\sigma^2}{n} \right) 
\end{split}
$$
proof
Since the folowing is true
$$
\begin{split}
X_i &\sim f_{X_i}\left(x_i | \mu_i, \sigma_i^2\right) \\
\Rightarrow Y&=\sum_{i=1}^n a_i +b \sim f_{Y}\left(y \mid \sum_{i=1}^n a_i \mu_i + b, \sum_{i=1}^n a_i^2 \sigma_i^2\right) 
\end{split}
$$
$$
\begin{split}
\bar{X_n}&=\frac{1}{n}\sum_{i=1}^nX_i  \\
&=\sum_{i=1}^n \frac{1}{n} X_i  \\
&\sim f_{\bar{X_n}}\left(\bar{x} \mid \sum_{i=1}^n \frac{\mu_i}{n} , \sum_{i=1}^n  \frac{\sigma_i^2}{n^2}\right) \\
&\sim f_{\bar{X_n}}\left(\bar{x} \mid  \mu, \frac{\sigma^2}{n} \right) \\ \\
\end{split}
$$
# anki

START
Basic
[[distribution]] of a [[random sample]] from a [[normal distribution]] (with proof)
Back: 
The mean from a [[random sample]] of the sixe $n$ from a [[normal distribution]] is again [[normal distribution|normal distributed]] with a mean $\mu$ and a [[variance]] $\frac{\sigma^2}{n}$. 
$$
\begin{split}
X_i &\sim f_{X}\left(x | \mu, \sigma^2\right) \: i.i.d \\
\Rightarrow \bar{X_n}&=\frac{1}{n}\sum_{i=1}^nX_i \sim f_{\bar{X_n}}\left(\bar{x} \mid  \mu, \frac{\sigma^2}{n} \right) 
\end{split}
$$
proof
Since the folowing is true
$$
\begin{split}
X_i &\sim f_{X_i}\left(x_i | \mu_i, \sigma_i^2\right) \\
\Rightarrow Y&=\sum_{i=1}^n a_i +b \sim f_{Y}\left(y \mid \sum_{i=1}^n a_i \mu_i + b, \sum_{i=1}^n a_i^2 \sigma_i^2\right) \\ \\

\psi_Y(t)&=\mathbb{E}\left[e^{tY}\right] = \mathbb{E}\left[\exp{\left(t\left(\sum_{i=1}^n a_i X_i + b\right)\right)}\right] \\
&= \mathbb{E}\left[e^{tb}\right] \cdot \prod_{i=1}^n \mathbb{E}\left[\exp{\left(t a_i X_i\right)}\right] = \mathbb{E}\left[e^{tb}\right] \cdot  \prod_{i=1}^n \psi_{X_i}(a_it) \\
&=\mathbb{E}\left[e^{tb}\right] \cdot \prod_{i=1}^n \exp{\left[\mu_i a_i t+\frac{1}{2}\sigma_i^2 a_i^2 t^2\right]} \\
&= \exp{\left[t\left(\sum_{i=1}^n\mu_i + b\right) +\frac{t^2}{2}\sum_{i=1}^n\sigma_i^2 \right]} \\

\end{split}
$$
$$
\begin{split}
\bar{X_n}&=\frac{1}{n}\sum_{i=1}^nX_i  \\
&=\sum_{i=1}^n \frac{1}{n} X_i  \\
&\sim f_{\bar{X_n}}\left(\bar{x} \mid \sum_{i=1}^n \frac{\mu_i}{n} , \sum_{i=1}^n  \frac{\sigma_i^2}{n^2}\right) \\
&\sim f_{\bar{X_n}}\left(\bar{x} \mid  \mu, \frac{\sigma^2}{n} \right) \\ \\
\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1680958035453-->
END


START
Basic
Linear Combinations of [[normal distribution|normal distributed]] [[random variable|random variables]]
- distribution of $Y$ with proof

$$
\begin{split}
X_i &\sim f_{X_i}\left(x_i | \mu_i, \sigma_i^2\right) \\
Y&=\sum_{i=1}^n a_i +b 
\end{split}
$$

Back: 
### [[probability density function]]
$$
f_X\left(x|\mu, \sigma^2\right) = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]}
$$
### [[moment generating function]]
$$
\psi_X(t) = \mathbb{E}\left[e^{tx}\right] = \int\limits_{-\infty}^\infty e^{tx} f_X(x) dx
$$
$$
\psi_X(t) = \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]}
$$
### Linear Combinations of [[normal distribution|normal distributed]] [[random variable|random variables]]
Linear Combinations of [[normal distribution|normal distributed]] [[random variable|random variables]] are again normal distributed.
$$
\begin{split}
X_i &\sim f_{X_i}\left(x_i | \mu_i, \sigma_i^2\right) \\
\Rightarrow Y&=\sum_{i=1}^n a_i +b \sim f_{Y}\left(y \mid \sum_{i=1}^n a_i \mu_i + b, \sum_{i=1}^n a_i^2 \sigma_i^2\right) \\ \\

\psi_Y(t)&=\mathbb{E}\left[e^{tY}\right] = \mathbb{E}\left[\exp{\left(t\left(\sum_{i=1}^n a_i X_i + b\right)\right)}\right] \\
&= \mathbb{E}\left[e^{tb}\right] \cdot \prod_{i=1}^n \mathbb{E}\left[\exp{\left(t a_i X_i\right)}\right] = \mathbb{E}\left[e^{tb}\right] \cdot  \prod_{i=1}^n \psi_{X_i}(a_it) \\
&=\mathbb{E}\left[e^{tb}\right] \cdot \prod_{i=1}^n \exp{\left[\mu_i a_i t+\frac{1}{2}\sigma_i^2 a_i^2 t^2\right]} \\
&= \exp{\left[t\left(\sum_{i=1}^n\mu_i + b\right) +\frac{t^2}{2}\sum_{i=1}^n\sigma_i^2 \right]} \\

\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1680958035459-->
END


START
Basic
- [[linear function|Linear Transformation]] of a [[normal distribution]]
- proof with the [[moment generating function]]
Back: 
### [[probability density function]]
$$
f_X\left(x|\mu, \sigma^2\right) = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]}
$$
### [[moment generating function]]
$$
\psi_X(t) = \mathbb{E}\left[e^{tx}\right] = \int\limits_{-\infty}^\infty e^{tx} f_X(x) dx
$$
$$
\psi_X(t) = \exp{\left[\mu t+\frac{1}{2}\sigma^2 t^2\right]}
$$
### [[linear function|Linear Transformation]] of a [[normal distribution]] 
$$
\begin{split}
X &\sim f_x\left(x|\mu, \sigma^2 \right) \\
\Rightarrow Y &= aX+b \\
&\sim f_Y\left(y | a\mu + b, a^2 \sigma^2\right) =\frac{1}{\sqrt{2 \pi a^2 \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-a\mu + b)^2}{a^2 \sigma^2}\right]} \\ 
\end{split}
$$
### proof1: [[moment generating function]]
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
- [[linear function|Linear Transformation]] of a [[normal distribution]]
- proof with the [[moment generating function]]
Back: 
### [[probability density function]]
$$
f_X\left(x|\mu, \sigma^2\right) = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-\mu)^2}{\sigma^2}\right]}
$$

### [[linear function]] of a [[probability density function]]
- $X$ is a [[continuous random variable]] with a [[probability density function]] $f_X(x)$
- $Y=g(X)=aX+b$ with an [[linear function]] $g$

$$
f_Y(y)=\underbrace{\frac{1}{|a|}}_{\frac{dg^{-1}(y)}{dy}} f_{X}
\underbrace{
\left(\frac{y-b}{a}\right)
}_{g^{-1}(y)}
$$
#### proof

$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) = P(aX=b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P(aX+b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P\left( X \leq \frac{y-b}{a} \right) \\
&= F_X\left(g^{-1}(y)\right) = F_X\left(\frac{y-b}{a}\right) \\


f_{Y}(y) &= \frac{dF_{Y}(y)}{dy} = \frac{dF_{Y}(y)}{dy} f_{X}\left(\frac{y-b}{a}\right) \\
&= \frac{dg^{-1}(y)}{dy} f_{X}\left(\frac{y-b}{a}\right)
= \frac{1}{|a|} f_{X}\left(\frac{y-b}{a}\right)
\end{split}
$$

### [[linear function|Linear Transformation]] of a [[normal distribution]] 
$$
\begin{split}
X &\sim f_x\left(x|\mu, \sigma^2 \right) \\
\Rightarrow Y &= aX+b \\
&\sim f_Y\left(y | a\mu + b, a^2 \sigma^2\right) =\frac{1}{\sqrt{2 \pi a^2 \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(x-a\mu + b)^2}{a^2 \sigma^2}\right]} \\ 
\end{split}
$$
#### proof
$$
\begin{split}
f_Y(y)
&=\underbrace{\frac{1}{|a|}}_{\frac{dg^{-1}(y)}{dy}} f_{X}
\underbrace{
\left(\frac{y-b}{a}\right)
}_{g^{-1}(y)} \\
&=\frac{1}{|a|} \frac{1}{\sqrt{2 \pi \sigma^2 }} \exp{\left(-\frac{1}{2}\frac{\left(\mu - \frac{y-b}{a}\right)^2}{\sigma^2}\right)} \\
&=\frac{1}{|a|} \frac{1}{\sqrt{2 \pi \sigma^2 }} \exp{\left(-\frac{1}{2}\frac{\left(\frac{a\mu - y-b}{a}\right)^2}{\sigma^2}\right)} \\
&=\frac{1}{\sqrt{2 \pi a^2 \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(y-a\mu + b)^2}{a^2 \sigma^2}\right]} \\ 
\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1680849735939-->
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
proof
$$
\begin{split}
f_X\left(x =\mu -x|\mu, \sigma^2\right) 
& = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{\left((\mu -x)- \mu \right)^2}{\sigma^2}\right]} \\
& = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{(-x)^2}{\sigma^2}\right]} \\
& = \frac{1}{\sqrt{2 \pi \sigma^2}}\exp{\left[-\frac{1}{2}\frac{x^2}{\sigma^2}\right]} \\
& = f_X\left(x =\mu +x|\mu, \sigma^2\right) \\
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