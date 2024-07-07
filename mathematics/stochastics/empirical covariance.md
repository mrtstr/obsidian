### empirical covariance
- given $n$ [[stochastic independent]] samples from the two [[distribution]] of the [[random variable]] $X$ and $V$
- the [[function]] $C$ is appoximating the [[covariance]] of the [[distribution]] (but has a [[bias]])

$$
\begin{split}
M(X) &= \frac{1}{n} \sum_{i=1}^n X_i \\
C(X, Y) &= \frac{1}{n} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\
\end{split}
$$

$$
\begin{split}
C(X, Y) 
&= \frac{1}{n} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) + M(X)M(Y) - M(X)\frac{1}{n} \sum_{i=1}^n Y_i - M(Y)\frac{1}{n} \sum_{i=1}^n X_i \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) + M(X)M(Y) - M(X)M(Y) - M(Y)M(X) \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) - M(X)M(Y)\\
\end{split}
$$


### corrected empirical covariance
- given $n$ [[stochastic independent]] samples from the same [[distribution]] the $V^*$ is appoximating the [[variance]] of the [[distribution]] and is [[bias|unbiased]]
$$
\begin{split}
C^*(X, Y) &= \frac{1}{n-1} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\ \\
\end{split}
$$


# ----------------------
# anki
START
Basic
definitions for
- [[empirical variance]] (2 versions)
- [[empirical covariance]] (2 version)
- corrected empirical covariance
- corrected empirical variance
Back: 
### empirical covariance
- given $n$ [[stochastic independent]] samples from the two [[distribution]] of the [[random variable]] $X$ and $V$
- the [[function]] $C$ is appoximating the [[covariance]] of the [[distribution]] (but has a [[bias]])

$$
\begin{split}
M(X) &= \frac{1}{n} \sum_{i=1}^n X_i \\
C(X, Y) &= \frac{1}{n} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\
\end{split}
$$


$$
\begin{split}
C(X, Y) 
&= \frac{1}{n} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) + M(X)M(Y) - M(X)\frac{1}{n} \sum_{i=1}^n Y_i - M(Y)\frac{1}{n} \sum_{i=1}^n X_i \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) + M(X)M(Y) - M(X)M(Y) - M(Y)M(X) \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) - M(X)M(Y)\\
\end{split}
$$

### corrected empirical covariance
- given $n$ [[stochastic independent]] samples from the same [[distribution]] the $V^*$ is appoximating the [[variance]] of the [[distribution]] and is [[bias|unbiased]]
$$
\begin{split}
C^*(X, Y) &= \frac{1}{n-1} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\ \\
\end{split}
$$

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

Tags: mathematics statistics
<!--ID: 1720372857670-->
END



START
Basic
show that the following approximated the [[covariance]]
$$
\begin{split}
C(X, Y) 
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) - M(X)M(Y)\\
\end{split}
$$
Back: 
### empirical covariance
- given $n$ [[stochastic independent]] samples from the two [[distribution]] of the [[random variable]] $X$ and $V$
- the [[function]] $C$ is appoximating the [[covariance]] of the [[distribution]] (but has a [[bias]])

$$
\begin{split}
M(X) &= \frac{1}{n} \sum_{i=1}^n X_i \\
C(X, Y) &= \frac{1}{n} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\
\end{split}
$$


$$
\begin{split}
C(X, Y) 
&= \frac{1}{n} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) + M(X)M(Y) - M(X)\frac{1}{n} \sum_{i=1}^n Y_i - M(Y)\frac{1}{n} \sum_{i=1}^n X_i \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) + M(X)M(Y) - M(X)M(Y) - M(Y)M(X) \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) - M(X)M(Y)\\
\end{split}
$$



Tags: mathematics statistics
<!--ID: 1720372857675-->
END
