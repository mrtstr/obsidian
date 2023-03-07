# Definition
## example
- we want to model the arrivel of customers with a [[binomial distribution]]
- on average 4.5 customer arrive per hour → $0.00125$ per second → $p=0.00125$ $n=3600$
- we assume that every second either 1 or 0 customers arrove because to probability of two arriving at the same time are negligible
- we assume [[stochastic independent|independence]] and homogeneity
- we assume $p \ll 1 \Leftrightarrow x \ll n$ and 

## general conditions
1) probability that two [[event|events]] occure in the same time interval is close to zero because the rate of occurence is very low enough of the time interval is short enough ( $p \ll 1 \Leftrightarrow x \ll n$)
2) the probability that a [[event]] occured in a timeinterval is proportional to its lengh
3) homogen: the probability that a [[event]] occured in the timeinterval does not depend on the interval's location
4) [[stochastic independent|independence]]: the probability of one [[event]] in a time interval is [[stochastic independent]] from the occurence of events in non overlapping time intervals

## [[probability function]]
Eventhough the exact calculation is inconvenient, the change from $x$ to $x+1$ can be claulated easily
$$
\begin{split}
\frac{f_x(x+1)}{f_x(x)} 
&= \frac{{n \choose x+1}p^{x+1}(1-p)^{n-x-1}}{{n \choose x}p^{x} (1-p)^{n-x}} \\ 
&= \frac{(n-x)p}{(x+1)(1-p)} \\ 
&\approx \frac{np}{x+1} \quad \: because \: p \ll 1 \Leftrightarrow x \ll n \\
&= \frac{\lambda}{x+1}\quad \: with \: \lambda=np
\end{split}
$$
With this result we can define the [[probability function]] of the [[hypergeometric distribution]] iterative with the following
$$
\begin{split}
%%%%f_x(0) &={n \choose 0}p^{0} (1-p)^{n} = (1-p)^{n} \\
f_x(1) &= f_x(0) \frac{\lambda}{x} = f_x(0) \lambda \\
f_x(2) &= f_x(0) \frac{\lambda}{2}    \\
f_x(3) &= f_x(0) \frac{\lambda}{2} \frac{\lambda}{3} = f_x(0) \frac{\lambda^2}{6}  \\
... \\
f_x(x) &= f_x(0) \frac{\lambda^x}{x!}  \\
\end{split}
$$
We know from the definition of [[eulers number]] that the following is true.
$$
e^\lambda = \sum\limits_{k=0}^\infty \frac{\lambda^k}{k!}
$$
We know that the [[distribution]] has to be normailzed and therefore $f_x(0) = e^{-\lambda}$ has to be true.
$$
\begin{split}
 &\sum_{x=0}^\infty \frac{\lambda^xf_x(0)}{x!} = 1 = \sum\limits_{k=0}^\infty \frac{\lambda^k e^{-\lambda}}{k!} \\
 &\Rightarrow f_x(0) = e^{-\lambda}
\end{split}
$$

Now, we can define the [[probability function]] of the [[poisson distribution]].
$$
f_X(x) =
\begin{cases}
\frac{\lambda^xe^{-\lambda}}{x!}
& \text{if } x \in \{0,1,2,..., n\}\\
0
& \text{otherwise}
\end{cases}
$$
## approimation of the [[binomial distribution]]
- the [[poisson distribution]] approximates a [[binomial distribution]] with a very small $p \ll 1$
- it follows $\mathbb{E}[Y] = \mathbb{VAR}[Y]$
$$
\begin{split}
Y &= X_1 + ... + X_n \:\: with \:\: X_1, ..., X_n \sim Ber(p) \:\: i.i.d. \\
\mathbb{E}[Y] &=\mathbb{E}[X_1 + ... + X_n] = n \mathbb{E}[X_i] = np \\
\mathbb{VAR}[Y] &=\mathbb{VAR}[X_1 + ... + X_n] = n \mathbb{VAR}[X_i] = np(1-p) \\ \\
p \ll 1 & \Rightarrow \mathbb{VAR}[Y] = np(1-p) \approx np \cdot 1 = \mathbb{E}[Y]
\end{split}
$$


# anki

START
Basic
[[poisson distribution]]
- definition
- conditions
- [[probability function]] (with derivation)
Back: 
## examples
- we want to model the arrivel of customers with a [[binomial distribution]]
- on average 4.5 customer arrive per hour → $0.00125$ per second → $p=0.00125$ $n=3600$
- we assume that every second either 1 or 0 customers arrove because to probability of two arriving at the same time are negligible
- we assume [[stochastic independent|independence]] and homogeneity
- we assume $p \ll 1 \Leftrightarrow x \ll n$ and 

## general conditions
1) probability that two [[event|events]] occure in the same time interval is close to zero because the rate of occurence is very low enough of the time interval is short enough ( $p \ll 1 \Leftrightarrow x \ll n$)
2) the probability that a [[event]] occured in a timeinterval is proportional to its lengh
3) homogen: the probability that a [[event]] occured in the timeinterval does not depend on the interval's location
4) [[stochastic independent|independence]]: the probability of one [[event]] in a time interval is [[stochastic independent]] from the occurence of events in non overlapping time intervals

## [[probability function]]
Eventhough the exact calculation is inconvenient, the change from $x$ to $x+1$ can be claulated easily
$$
\begin{split}
\frac{f_x(x+1)}{f_x(x)} 
&= \frac{{n \choose x+1}p^{x+1}(1-p)^{n-x-1}}{{n \choose x}p^{x} (1-p)^{n-x}} \\ 
&= \frac{(n-x)p}{(x+1)(1-p)} \\ 
&\approx \frac{np}{x+1} \quad \: because \: p \ll 1 \Leftrightarrow x \ll n \\
&= \frac{\lambda}{x+1}\quad \: with \: \lambda=np
\end{split}
$$
With this result we can define the [[probability function]] of the [[hypergeometric distribution]] iterative with the following
$$
\begin{split}
%%%%f_x(0) &={n \choose 0}p^{0} (1-p)^{n} = (1-p)^{n} \\
f_x(1) &= f_x(0) \frac{\lambda}{x} = f_x(0) \lambda \\
f_x(2) &= f_x(0) \frac{\lambda}{2}    \\
f_x(3) &= f_x(0) \frac{\lambda}{2} \frac{\lambda}{3} = f_x(0) \frac{\lambda^2}{6}  \\
... \\
f_x(x) &= f_x(0) \frac{\lambda^x}{x!}  \\
\end{split}
$$
We know from the definition of [[eulers number]] that the following is true.
$$
e^\lambda = \sum\limits_{k=0}^\infty \frac{\lambda^k}{k!}
$$
We know that the [[distribution]] has to be normailzed and therefore $f_x(0) = e^{-\lambda}$ has to be true.
$$
\begin{split}
 &\sum_{x=0}^\infty \frac{\lambda^xf_x(0)}{x!} = 1 = \sum\limits_{k=0}^\infty \frac{\lambda^k e^{-\lambda}}{k!} \\
 &\Rightarrow f_x(0) = e^{-\lambda}
\end{split}
$$

Now, we can define the [[probability function]] of the [[poisson distribution]].
$$
f_X(x) =
\begin{cases}
\frac{\lambda^xe^{-\lambda}}{x!}
& \text{if } x \in \{0,1,2,..., n\}\\
0
& \text{otherwise}
\end{cases}
$$
Tags: mathematics, statistics
<!--ID: 1678167394158-->
END