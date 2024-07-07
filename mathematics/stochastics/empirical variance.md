### empirical variance
- given $n$ [[stochastic independent]] samples from the same [[distribution]] the $V$ is appoximating the [[variance]] of the [[distribution]] (but has a [[bias]])

$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
V &= \frac{1}{n} \sum_{i=1}^n (X_i - M)^2 \\
\end{split}
$$

$$
\begin{split}
V(X) 
&= \frac{1}{n}\sum_{i\in [n]}  \left(X_i - M(X)\right)^2 \\
&= \frac{1}{n}\sum_{i\in [n]}  X_i^2 + M(X)^2 - 2X_i M(X) \\
&= \left(\frac{1}{n}\sum_{i\in [n]}  X_i^2 \right)+ \frac{n}{n}M(X)^2 - 2M(X) \frac{1}{n} \sum_{i\in [n]}X_i  \\
&= \left(\frac{1}{n}\sum_{i\in [n]}  X_i^2 \right)- M(X)^2  \\
\end{split}
$$


### corrected empirical variance
- given $n$ [[stochastic independent]] samples from the same [[distribution]] the $V^*$ is appoximating the [[variance]] of the [[distribution]] and is [[bias|unbiased]]
$$
\begin{split}
V^* &= \frac{1}{n-1} \sum_{i=1}^n (X_i - M)^2 \\
\end{split}
$$

# -----------------------------
START
Basic
show that the following approximated the [[variance]]
$$
\begin{split}
V(X) 
&= \left(\frac{1}{n}\sum_{i\in [n]}  X_i^2 \right)- M(X)^2  \\
\end{split}
$$
Back: 
### empirical variance
- given $n$ [[stochastic independent]] samples from the same [[distribution]] the $V$ is appoximating the [[variance]] of the [[distribution]] (but has a [[bias]])

$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
V &= \frac{1}{n} \sum_{i=1}^n (X_i - M)^2 \\
\end{split}
$$

$$
\begin{split}
V(X) 
&= \frac{1}{n}\sum_{i\in [n]}  \left(X_i - M(X)\right)^2 \\
&= \frac{1}{n}\sum_{i\in [n]}  X_i^2 + M(X)^2 - 2X_i M(X) \\
&= \left(\frac{1}{n}\sum_{i\in [n]}  X_i^2 \right)+ \frac{n}{n}M(X)^2 - 2M(X) \frac{1}{n} \sum_{i\in [n]}X_i  \\
&= \left(\frac{1}{n}\sum_{i\in [n]}  X_i^2 \right)- M(X)^2  \\
\end{split}
$$


Tags: mathematics statistics
<!--ID: 1720372857677-->
END
