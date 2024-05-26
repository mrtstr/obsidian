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


# Anki

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