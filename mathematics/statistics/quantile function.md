## Quantile or percentile function
- $Q_X:[0,1] \mapsto \mathbb{R}$ 
- For a given probability $q$: $Q_X(q)$ gives the value that a [[random variable]] $X$ will not exceed with a probability of $q$.
- $Q_X(q)$ is the smallest values with a [[CDF]] less or equal than $q$  
$$Q_X(q) = \inf\left\{x \mid q \leq F_X(x)\right\}$$
- $Q_X(q)$ is the inverse of the [[CDF]]
$$Q_X(q)=F_X^{-1}(q)\quad with \: q = F_X(x)=P(X \leq x)$$
## estimation
- can be [[statistical predictor|estimated]] using [[quantile regression]]
- taking the $q$ smallest value of a [[statistical sample|sample]] $\widehat{Q}_X(q)=\inf\left\{x \mid \frac{1}{n} \sum\limits_{i=1}^n\mathbb{I}[x_i \leq x] \geq q\right\}$


START
Basic
quantile function
- definitions (verbal + 2 equations)
Back: 
- $Q_X:[0,1] \mapsto \mathbb{R}$ 
- For a given probability $q$: $Q_X(q)$ gives the value that a [[random variable]] $X$ will not exceed with a probability of $q$.
- $Q_X(q)$ is the smallest values with a [[CDF]] greater or equal than $q$  
$$Q_X(q) = \inf\left\{x \mid q \leq F_X(x)\right\}$$
- $Q_X(q)$ is the inverse of the [[CDF]]
$$Q_X(q)=F_X^{-1}(q)\quad with \: q = F_X(x)=P(X \leq x)$$

Tags: mathematics, statistics
<!--ID: 1664619948145-->
END


START
Basic
quantile function
- how to estimate it
Back: 
- can be [[statistical predictor|estimated]] using [[quantile regression]]
- taking the $q$ smallest value of a [[statistical sample|sample]] $\widehat{Q}_X(q)=\inf\left\{x \mid \frac{1}{n} \sum\limits_{i=1}^n\mathbb{I}[x_i \leq x] \geq q\right\}$
Tags: mathematics, statistics
<!--ID: 1664619948153-->
END