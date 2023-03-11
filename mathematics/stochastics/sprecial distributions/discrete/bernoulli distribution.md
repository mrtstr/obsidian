# bernoulli random variable
- [[discrete random variable]] $Z$ that can only take $0$ and $1$
	→support of $X = \{0,1\}$ 
- parameter $p$ defines the probability of $Z$ being 0 or 1
	- $P(1) = p$
	- $P(0) = 1-p$
- the probability function is defined as follows

### [[probability function]]
- binary [[random experiment]] 
- $p=$ probability of positive outcome
$$
\begin{split}
f_X(x | p) &= 
\begin{cases}
    p,& \text{if } x= 1\\
    1-p,& \text{if } x= 0\\
    0,              & \text{otherwise}
\end{cases} \\
&= 
\begin{cases}
    p^x (1-p)^{1-x},& \text{if } x= 0,1\\
    0,              & \text{otherwise}
\end{cases}
\end{split}
$$
### [[expectation]]
$$
\mathbb{E}[B] = \sum_{\{0,1\}} b_i \cdot P(B=b_i) = 1 \cdot p + 0 \cdot (1-p) = p
$$
$$
\mathbb{E}\left[B^2\right] = \sum_{\{0,1\}} b_i^2 \cdot P(B=b_i) = 1^2 \cdot p + 0^2 \cdot (1-p) = p
$$
### [[variance]]
$$
\mathbb{VAR}\left[B\right] = \mathbb{E}\left[B^2\right] - \mathbb{E}\left[B\right]^2 = p - p^2 =p(1-p)
$$
# anki

START
Basic
[[bernoulli distribution]]
- definition
- probability function
- [[expectation]]
- [[variance]]
Back: 
- [[discrete random variable]] $Z$ that can only take $0$ and $1$
	→support of $Z = \{0,1\}$ 
- parameter $p$ defines the probability of $Z$ being 0 or 1
	- $P(1) = p$
	- $P(0) = 1-p$
- the probability function is defined as follows
$$
\begin{split}
f_X(x) &= 
\begin{cases}
    p,& \text{if } x= 1\\
    1-p,& \text{if } x= 0\\
    0,              & \text{otherwise}
\end{cases} \\
&= 
\begin{cases}
    p^x (1-p)^{1-x},& \text{if } x= 0,1\\
    0,              & \text{otherwise}
\end{cases}
\end{split}
$$
# [[expectation]]
$$
\mathbb{E}[B] = \sum_{\{0,1\}} b_i \cdot P(B=b_i) = 1 \cdot p + 0 \cdot (1-p) = p
$$
$$
\mathbb{E}\left[B^2\right] = \sum_{\{0,1\}} b_i^2 \cdot P(B=b_i) = 1^2 \cdot p + 0^2 \cdot (1-p) = p
$$
## [[variance]]
$$
\mathbb{VAR}\left[B\right] = \mathbb{E}\left[B^2\right] - \mathbb{E}\left[B\right]^2 = p - p^2 =p(1-p)
$$

Tags: mathematics, statistics
<!--ID: 1667211139246-->
END