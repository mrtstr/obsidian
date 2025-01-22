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


### example
- given $n$ [[random variable]] $X_1, ..., X_n$ i.i.d. with $\mathbb{VAR}[X_1] = \sigma^2$ and $\mathbb{E}[X_1] = 0$
- how is the limit [[distribution]] of $Y_n$?

$$
\begin{split}
Y_n = \frac{\sqrt{n}}{\sigma}  \sum_{k \in [n]} X_k
\end{split}
$$

$$
\begin{split}
\lim_{n \to \infty} F_Y(y) 
&= F\left(Y \leq y \right) \\
&= F\left(\frac{\sqrt{n}}{\sigma}  \sum_{k \in [n]} X_k \leq y \right) \\

&= F\left(\frac{\sqrt{n}}{\sigma}   (\hat X_n - \mu) \leq y  \right) \\
&\sim \mathcal{N}(0,1)\\
\end{split}
$$

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


START
Basic
- given $n$ [[random variable]] $X_1, ..., X_n$ i.i.d. with $\mathbb{VAR}[X_1] = \sigma^2$ and $\mathbb{E}[X_1] = 0$
- how is the limit [[distribution]] of $Y_n$?

$$
\begin{split}
Y_n = \frac{\sqrt{n}}{\sigma}  \sum_{k \in [n]} X_k
\end{split}
$$

Back: 

$$
\begin{split}
\lim_{n \to \infty} F_Y(y) 
&= F\left(Y \leq y \right) \\
&= F\left(\frac{\sqrt{n}}{\sigma}  \sum_{k \in [n]} X_k \leq y \right) \\

&= F\left(\frac{\sqrt{n}}{\sigma}   (\hat X_n - \mu) \leq y  \right) \\
&\sim \mathcal{N}(0,1)\\
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


Tags: mathematics statistics WS2425
<!--ID: 1729443087555-->
END
