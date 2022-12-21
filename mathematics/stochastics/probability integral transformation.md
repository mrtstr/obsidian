With the [[probability integral transformation]] it is possible to [[sampling|sample]] from every distribution as long as its [[CDF]] $F_X(x)$ is known

## theory

![[functions of random variables#continuous random variable with $g(X)=F_X(X)$]]

Therefore, we can [[sampling|sample]] from the distribution of $X$ when $F_X(x)$ is known by generating random samples from $U(0,1)$ and transforming them with $F^{-1}_X(u)$.
# Anki

START
Basic
probability integral transformation
method to [[sampling|sample]] from an arbitrary distribution with a known [[CDF]] $F_X(x)$
Back: 
- for every [[continuous random variable]] $X$ with a [[CDF]] $F_X(x)$, $Y=F_X(X) \sim U(0,1)$
- Therefore we can [[sampling|sample]] from the distribution of $X$ by generating random samples from the [[continous uniform distribution]] $U(0,1)$ and transforming them with $F^{-1}_X(u)$
Tags: mathematics, statistics
<!--ID: 1671614666438-->
END