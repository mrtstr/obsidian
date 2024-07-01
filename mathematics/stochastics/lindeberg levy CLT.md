### lindeberg levy CLT
- given a sequence of [[random variable]] $X_1, ..., X_n$ i.i.d with $\mathbb{E}[X_i] = \mu$ and $\mathbb{VAR}[X_i] = \sigma^2$
- $\sqrt{n} \left(\bar{X}_n - \mu\right)$ converges in [[distribution]] to a [[normal distribution]] $\mathcal{N}(0, \sigma^2)$

$$
\begin{split}
&\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i \\
&\lim_{n \to \infty} \sqrt{n} \left(\bar{X}_n - \mu\right) \sim \mathcal{N}(0, \sigma^2)
\end{split}
$$
TODO add proof
# anki


START
Basic
[[lindeberg levy CLT]] (without proof)

Back: 
### lindeberg levy CLT
- given a sequence of [[random variable]] $X_1, ..., X_n$ i.i.d with $\mathbb{E}[X_i] = \mu$ and $\mathbb{VAR}[X_i] = \sigma^2$
- $\sqrt{n} \left(\bar{X}_n - \mu\right)$ converges in [[distribution]] to a [[normal distribution]] $\mathcal{N}(0, \sigma^2)$

$$
\begin{split}
&\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i \\
&\lim_{n \to \infty} \sqrt{n} \left(\bar{X}_n - \mu\right) \sim \mathcal{N}(0, \sigma^2)
\end{split}
$$


Tags: mathematics statistics
<!--ID: 1719737555992-->
END



START
Basic
- given a sequence of [[random variable]] $X_1, ..., X_n$ i.i.d with $\mathbb{E}[X_i] = \mu$ and $\mathbb{VAR}[X_i] = \sigma^2$
- how to transform $\bar X_n$ in to a [[random variable]] $Y \sim \mathcal{N}$ for $n \to \infty$
$$
\begin{split}
&\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i \\
\end{split}
$$

Back: 

$$
\begin{split}
Y = \frac{\sqrt{n}}{\sigma} \left(\bar{X}_n - \mu\right) \sim \mathcal{N}(0, 1)
\end{split}
$$

### lindeberg levy CLT
- given a sequence of [[random variable]] $X_1, ..., X_n$ i.i.d with $\mathbb{E}[X_i] = \mu$ and $\mathbb{VAR}[X_i] = \sigma^2$
- $\sqrt{n} \left(\bar{X}_n - \mu\right)$ converges in [[distribution]] to a [[normal distribution]] $\mathcal{N}(0, \sigma^2)$

$$
\begin{split}
&\bar{X}_n = \frac{1}{n} \sum_{i=1}^n X_i \\
&\lim_{n \to \infty} \sqrt{n} \left(\bar{X}_n - \mu\right) \sim \mathcal{N}(0, \sigma^2)
\end{split}
$$


Tags: mathematics statistics
<!--ID: 1719861660036-->
END