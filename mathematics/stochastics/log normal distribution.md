### log normal distribution
- A [[random variable]] $X$ is [[log normal distribution|log normal distributed]] if the [[logarithm]] of $X$ $Y=log(X) \sim f_Y\left(y|\mu, \sigma^2\right)$ is [[normal distribution|normal distributed]]


```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-2, 4, 0, 0.7]
disableZoom: true
grid: true
---
f(x) = 1/x 1/sqrt(2*PI) exp(-log(x)^2 / 2)
g(x) = 1/sqrt(2*PI) exp(-x^2 / 2)
```

#### CDF
$$
F_X\left(x \: | \: \mu, \sigma^2\right) = 
F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$
proof
$$
\begin{split}
F_X\left(x\: | \: \mu, \sigma^2\right) 
&= P\left(X \leq x\right)  \\
&= P\left(log(X) \leq log(x)\right) \qquad \text{(since log is monotone increasing)}\\
&= F_Y\left(log(X)\right) \\
&= F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
\end{split}
$$

#### PDF
$$
f_X\left(x \: | \: \mu, \sigma^2\right) = 
\frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$



proof

$$
\begin{split}
f_X\left(x \: | \: \mu, \sigma^2\right) 
&= \frac{dF_X\left(x \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dF_Y\left(log(x) \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dlog(x)}{dy} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 
&= \frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 


\end{split}
$$

### moments of the log normal distribution

$$
\mathbb{E}\left[X^n\right] = e^{n\mu + \frac{n^2}{2} \sigma^2 }
$$

$$
\mathbb{E}\left[X\right] = e^{\mu + \frac{\sigma^2}{2}}
$$

$$
\begin{split}
\mathbb{VAR}\left[X\right] 
&= \mathbb{E}\left[X^2\right] - \mathbb{E}\left[X\right]^2 \\
&= e^{2\mu + 2 \sigma^2 } - e^{2 \cdot 1\mu + \frac{1^2}{2} 2 \sigma^2 } \\
&= e^{2\mu + 2 \sigma^2 } - e^{2 \mu +  \sigma^2 } \\
&= e^{2\mu+ \sigma^2} (e^{\sigma^2} - 1 ) \\
\end{split}
$$

# Anki

START
Basic
[[log normal distribution]]
- [[probability density function (PDF)]]
- [[expectation]]
- [[variance]]

Back: 
### moments of the log normal distribution

$$
\mathbb{E}\left[X^n\right] = e^{n\mu + \frac{n^2}{2} \sigma^2 }
$$

$$
\mathbb{E}\left[X\right] = e^{\mu + \frac{\sigma^2}{2}  }
$$

$$
\begin{split}
\mathbb{VAR}\left[X\right] 
&= \mathbb{E}\left[X^2\right] - \mathbb{E}\left[X\right]^2 \\
&= e^{2\mu + 2 \sigma^2 } - e^{2 \cdot 1\mu + \frac{1^2}{2} 2 \sigma^2 } \\
&= e^{2\mu + 2 \sigma^2 } - e^{2 \mu +  \sigma^2 } \\
&= e^{2\mu+ \sigma^2} (e^{\sigma^2} - 1 ) \\
\end{split}
$$


### log normal distribution
- A [[random variable]] $X$ is [[log normal distribution|log normal distributed]] if the [[logarithm]] of $X$ $Y=log(X) \sim f_Y\left(y|\mu, \sigma^2\right)$ is [[normal distribution|normal distributed]]


#### CDF
$$
F_X\left(x \: | \: \mu, \sigma^2\right) = 
F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$
proof
$$
\begin{split}
F_X\left(x\: | \: \mu, \sigma^2\right) 
&= P\left(X \leq x\right)  \\
&= P\left(log(X) \leq log(x)\right) \qquad \text{(since log is monotone increasing)}\\
&= F_Y\left(log(X)\right) \\
&= F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
\end{split}
$$

#### PDF
$$
f_X\left(x \: | \: \mu, \sigma^2\right) = 
\frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$



proof

$$
\begin{split}
f_X\left(x \: | \: \mu, \sigma^2\right) 
&= \frac{dF_X\left(x \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dF_Y\left(log(x) \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dlog(x)}{dy} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 
&= \frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 


\end{split}
$$

Tags: mathematics statistics WS2425
<!--ID: 1735301089895-->
END

START
Basic
[[log normal distribution]]
- [[cumulative distribution function (CDF)]] (with proof)
- [[probability density function (PDF)]] (with proof)
Back: 
- A [[random variable]] $X$ is [[log normal distribution|log normal distributed]] if $Y=log(X) \sim f_Y\left(y|\mu, \sigma^2\right)$ is [[normal distribution|normal distributed]]

## [[cumulative distribution function (CDF)]]
$$
F_X\left(x \: | \: \mu, \sigma^2\right) = 
F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$
proof
$$
\begin{split}
F_X\left(x\: | \: \mu, \sigma^2\right) 
&= P\left(X \leq x\right)  \\
&= P\left(log(X) \leq log(x)\right) \qquad \text{(since log is monotone increasing)}\\
&= F_Y\left(log(X)\right) \\
&= F_Y\left(log(x) \: | \: \mu, \sigma^2\right)
\end{split}
$$

## [[probability density function (PDF)]]
$$
f_X\left(x \: | \: \mu, \sigma^2\right) = 
\frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)
$$
proof

$$
\begin{split}
f_X\left(x \: | \: \mu, \sigma^2\right) 
&= \frac{dF_X\left(x \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dF_Y\left(log(x) \: | \: \mu, \sigma^2\right)}{dy} \\ 
&= \frac{dlog(x)}{dy} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 
&= \frac{1}{x} f_Y\left(log(x) \: | \: \mu, \sigma^2\right)  \\ 


\end{split}
$$

Tags: mathematics statistics
<!--ID: 1682926631764-->
END