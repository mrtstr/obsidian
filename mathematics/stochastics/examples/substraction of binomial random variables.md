
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
$$
f_Y(y)= 
\begin{cases}
\sum\limits_{i=0}^{n_1} f(y + i | n_1, p_1)f(i | n_2, p_2)
,& \text{if } x \geq 0\\
\sum\limits_{i=0}^{n_2} f(i | n_1, p_1)f(i + y | n_2, p_2)
,& \text{otherwise}
\end{cases}
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
$$
f_Y(y)= 
\begin{cases}
\sum\limits_{i=0}^{n_1} f(y + i | n_1, p_1)f(i | n_2, p_2)
,& \text{if } x \geq 0\\
\sum\limits_{i=0}^{n_2} f(i | n_1, p_1)f(i + y | n_2, p_2)
,& \text{otherwise}
\end{cases}
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