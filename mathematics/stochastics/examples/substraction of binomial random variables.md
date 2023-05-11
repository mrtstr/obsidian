
[[substraction]] of two [[binomial distribution|binomial distributed]] [[random variable|random variables]]
$$
\begin{split}
Y = X_1 - X_2 \\
X_1 \sim Ber(n_1, p_1) \\ 
X_2 \sim Ber(n_2, p_2) \\ \\
\end{split}
$$

$$
f(x | n, p)= 
\begin{cases}
{n \choose x}
p^{x}(1-p)^{n-x}
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
$$
## [[probability function]]
[[convolution of distributions]]
$$
\begin{split}
F_Y(y)
=& P(Y \leq y) \\
=& \sum\limits_{X_2 \in \Omega_{X_2}} P(m + X_1  - x_2 \leq y \cap X_2 = x_2) \\
=& \sum\limits_{x_2 \in \Omega_{X_2}} P(m + X_1 - x_2 \leq y) P(X_2 = x_2) \\
=& \sum\limits_{x_2 \in \Omega_{X_2}} P(m + X_1 \leq y + x_2) P(X_2 = x_2) \\
=& \sum\limits_{x_2 \in \Omega_{X_2}} F_{X_1}(m + y + x_2 ) f_{X_2}(x_2) \\
f_Y(y)
&= \frac{dF_Y(y)}{dy} \\
=& \sum\limits_{x_2 \in \Omega_{X_2}} f_{X_2}(X_2) f_{X_1}(m + y +x_2) \\
\end{split}
$$

## [[expectation]]
$$
\begin{split}
\mathbb{E}\left[Y\right] 
&= \mathbb{E}\left[\sum_{i =0}^{n_1} X_i - \sum_{i =0}^{n_2} X_i\right] \\
&= \sum_{i =0}^{n_1} \mathbb{E}\left[ X_i\right] - \sum_{i =0}^{n_2} \mathbb{E}\left[ X_i\right] \\
&= n_1 p_1 - n_2 p_2
\end{split}
$$

## [[variance]]
- since the [[random variable|random variables]] are [[stochastic independent]] the
$$
\begin{split}
\mathbb{VAR}\left[Y\right] 
&= \mathbb{VAR}\left[\sum_{i =0}^{n_1} X_i - \sum_{i =0}^{n_2} X_i\right] \\
&= \mathbb{VAR}\left[\sum_{i =0}^{n_1} X_i + \sum_{i =0}^{n_2} (-1)X_i\right] \\
&= \sum_{i =0}^{n_1} \mathbb{VAR}\left[ X_i\right] + \sum_{i =0}^{n_2} (-1)^2 \mathbb{VAR}\left[ X_i\right] \\
&= n_1 p_1(1-p_1) - n_2 p_2(1-p_2)
\end{split}
$$

# anki

START
Basic
[[substraction]] of two [[binomial distribution|binomial distributed]] [[random variable|random variables]]
$$
\begin{split}
Y = X_1 - X_2 \\
X_1 \sim Ber(n_1, p_1) \\ 
X_2 \sim Ber(n_2, p_2) \\ \\
\end{split}
$$
- [[probability function]]
- [[expectation]]
- [[variance]]

Back: 
## [[probability function]]
[[convolution of distributions]]
$$
\begin{split}
F_Y(y)
=& P(Y \leq y) \\
=& \sum\limits_{X_2 \in \Omega_{X_2}} P(m + X_1  - x_2 \leq y \cap X_2 = x_2) \\
=& \sum\limits_{x_2 \in \Omega_{X_2}} P(m + X_1 - x_2 \leq y) P(X_2 = x_2) \\
=& \sum\limits_{x_2 \in \Omega_{X_2}} P(m + X_1 \leq y + x_2) P(X_2 = x_2) \\
=& \sum\limits_{x_2 \in \Omega_{X_2}} F_{X_1}(m + y + x_2 ) f_{X_2}(x_2) \\
f_Y(y)
&= \frac{dF_Y(y)}{dy} \\
=& \sum\limits_{x_2 \in \Omega_{X_2}} f_{X_2}(X_2) f_{X_1}(m + y +x_2) \\
\end{split}
$$


## [[expectation]]
$$
\begin{split}
\mathbb{E}\left[Y\right] 
&= \mathbb{E}\left[\sum_{i =0}^{n_1} X_i - \sum_{i =0}^{n_2} X_i\right] \\
&= \sum_{i =0}^{n_1} \mathbb{E}\left[ X_i\right] - \sum_{i =0}^{n_2} \mathbb{E}\left[ X_i\right] \\
&= n_1 p_1 - n_2 p_2
\end{split}
$$

## [[variance]]
- since the [[random variable|random variables]] are [[stochastic independent]] the
$$
\begin{split}
\mathbb{VAR}\left[Y\right] 
&= \mathbb{VAR}\left[\sum_{i =0}^{n_1} X_i - \sum_{i =0}^{n_2} X_i\right] \\
&= \mathbb{VAR}\left[\sum_{i =0}^{n_1} X_i + \sum_{i =0}^{n_2} (-1)X_i\right] \\
&= \sum_{i =0}^{n_1} \mathbb{VAR}\left[ X_i\right] + \sum_{i =0}^{n_2} (-1)^2 \mathbb{VAR}\left[ X_i\right] \\
&= n_1 p_1(1-p_1) - n_2 p_2(1-p_2)
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1683480987854-->
END