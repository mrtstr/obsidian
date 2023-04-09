# Definition
### example
- we want to model the arrivel of customers with a [[binomial distribution]]
- on average 4.5 customer arrive per hour → $0.00125$ per second → $p=0.00125$ $n=3600$
- we assume that every second either 1 or 0 customers arrove because to probability of two arriving at the same time are negligible
- we assume [[stochastic independent|independence]] and homogeneity
- we assume $p \ll 1 \Leftrightarrow x \ll n$ and 

### general conditions
1) probability that two [[event|events]] occure in the same time interval is close to zero because the rate of occurence is very low enough of the time interval is short enough ( $p \ll 1 \Leftrightarrow x \ll n$)
2) the probability that a [[event]] occured in a timeinterval is proportional to its lengh
3) homogen: the probability that a [[event]] occured in the timeinterval does not depend on the interval's location
4) [[stochastic independent|independence]]: the probability of one [[event]] in a time interval is [[stochastic independent]] from the occurence of events in non overlapping time intervals

### [[probability function]] derivation
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

### [[probability function]]
- $\lambda = np$ with $n =$ number of [[bernoulli distribution|bernoulli experiments]] and $p=$ probability of positive outcome
- assumtions: $p \ll 1 \Leftrightarrow x \ll n$
- $x=$ number of positive outcomes
$$
f_X(x | \lambda) =
\begin{cases}
\frac{\lambda^xe^{-\lambda}}{x!}
& \text{if } x \in \{0,1,2,..., n\}\\
0
& \text{otherwise}
\end{cases}
$$
### [[expectation]]
$$
\begin{split}
\mathbb{E}[X] 
&= \sum_{i=0}^\infty x \frac{\lambda^xe^{-\lambda}}{x!} \\
&= \sum_{i=1}^\infty x \frac{\lambda^xe^{-\lambda}}{x!} \\
&= \lambda \sum_{i=1}^\infty \frac{\lambda^{x-1}e^{-\lambda}}{(x-1)!} \\
&= \lambda \sum_{i=1}^{\infty+1} \frac{\lambda^{x}e^{-\lambda}}{x!} \\
&= \lambda \sum_{i=1}^{\infty} \frac{\lambda^{x}e^{-\lambda}}{x!} \\
&= \lambda 
\end{split}
$$
### [[variance]]
$$
\begin{split}
\mathbb{E}[X(X-1)] 
&= \sum_{i=0}^\infty x (x-1) \frac{\lambda^xe^{-\lambda}}{x!} \\
&= \sum_{i=2}^\infty x (x-1) \frac{\lambda^xe^{-\lambda}}{x!} \\
&= \lambda^2 \sum_{i=2}^\infty \frac{\lambda^{x-2}e^{-\lambda}}{(x-2)!} \\
&= \lambda^2 \sum_{i=2}^{\infty+2} \frac{\lambda^{x}e^{-\lambda}}{x!} \\
&= \lambda^2 \sum_{i=1}^{\infty} \frac{\lambda^{x}e^{-\lambda}}{x!} \\
&= \lambda^2 \\ \\
\mathbb{E}[X(X-1)] 
&= \mathbb{E}[X^2]-\mathbb{E}[X] = \lambda^2 \\
\lambda^2 &= \mathbb{E}[X^2]- \lambda \\
\Rightarrow  \mathbb{E}[X^2] &= \lambda^2 +\lambda \\ \\
\mathbb{VAR}[X] 
&= \mathbb{E}[X^2] - \mathbb{E}[X]^2 \\
&= \lambda^2 +\lambda - \lambda^2 \\
&= \lambda \\
\end{split}
$$
### direct proof for $\mathbb{E}[Y] = \mathbb{VAR}[Y]$
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

### [[probability function]]
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
Tags: mathematics statistics
<!--ID: 1678167394158-->
END


START
Basic
[[poisson distribution]]
- [[expectation]]
- [[variance]]
- direct proof for $\mathbb{E}[Y] = \mathbb{VAR}[Y]$
Back: 
#### [[expectation]]
$$
\begin{split}
\mathbb{E}[X] 
&= \sum_{i=0}^\infty x \frac{\lambda^xe^{-\lambda}}{x!} \\
&= \sum_{i=1}^\infty x \frac{\lambda^xe^{-\lambda}}{x!} \\
&= \lambda \sum_{i=1}^\infty \frac{\lambda^{x-1}e^{-\lambda}}{(x-1)!} \\
&= \lambda \sum_{i=1}^{\infty+1} \frac{\lambda^{x}e^{-\lambda}}{x!} \\
&= \lambda \sum_{i=1}^{\infty} \frac{\lambda^{x}e^{-\lambda}}{x!} \\
&= \lambda 
\end{split}
$$
#### [[variance]]
$$
\begin{split}
\mathbb{E}[X(X-1)] 
&= \sum_{i=0}^\infty x (x-1) \frac{\lambda^xe^{-\lambda}}{x!} \\
&= \sum_{i=2}^\infty x (x-1) \frac{\lambda^xe^{-\lambda}}{x!} \\
&= \lambda^2 \sum_{i=2}^\infty \frac{\lambda^{x-2}e^{-\lambda}}{(x-2)!} \\
&= \lambda^2 \sum_{i=2}^{\infty+2} \frac{\lambda^{x}e^{-\lambda}}{x!} \\
&= \lambda^2 \sum_{i=1}^{\infty} \frac{\lambda^{x}e^{-\lambda}}{x!} \\
&= \lambda^2 \\ \\
\mathbb{E}[X(X-1)] 
&= \mathbb{E}[X^2]-\mathbb{E}[X] = \lambda^2 \\
\lambda^2 &= \mathbb{E}[X^2]- \lambda \\
\Rightarrow  \mathbb{E}[X^2] &= \lambda^2 +\lambda \\ \\
\mathbb{VAR}[X] 
&= \mathbb{E}[X^2] - \mathbb{E}[X]^2 \\
&= \lambda^2 +\lambda - \lambda^2 \\
&= \lambda \\
\end{split}
$$
#### direct proof for $\mathbb{E}[Y] = \mathbb{VAR}[Y]$
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

Tags: mathematics statistics
<!--ID: 1678520971197-->
END

START
Basic
[[poisson distribution]] example:
Approximating a Probability . Suppose that in a large population the proportion of people who have a certain disease is $0.01$. We shall determine the probability that in a random group of $200$ people at least four people will have the disease.
- Define [[poisson distribution]] and [[binomial distribution]]
- $P(X ≥ 4)$: result of [[binomial distribution]] vs [[poisson distribution]] approximation
Back: 
In this example, we can assume that the exact distribution of the number of people having the disease among the $200$ people in the random group is the binomial distribution with parameters $n = 200$ and $p = 0.01$. Therefore, this distribution can be approximated by the Poisson distribution for which the mean is $\lambda = np = 2$. If X denotes a random variable having this Poisson distribution, then it can be found from the table of the Poisson distribution at the end of this book that $P(X ≥ 4) = 0.1428$. Hence, the probability that at least four people will have the disease is approximately $0.1428$. The actual value is $0.1420$.

$$
\begin{split}
f_Y(y) &= \frac{\lambda^xe^{-\lambda}}{x!} = \frac{2^xe^{-2}}{x!} \\ 
f_X(x) &= {n \choose x}p^{x}(1-p)^{n-x} = {200 \choose x}0.01^{x}(1-0.01)^{200-x} \\ \\
P(X \geq 4) &= 1 - P(X \leq 3) \\
&= 1 - 
1 \cdot 1 \cdot 1 \cdot (0.99)^{200} \\ 

&\qquad - 200 \cdot 0.01 \cdot 0.99^{199}\\
&\qquad - {200 \choose 2}0.01^{2}(0.99)^{198}\\
&\qquad - {200 \choose 3}0.01^{3}(0.99)^{197}\\
&= 0.1420 \\ \\
P(Y \geq 4) &= 1 - P(Y \leq 3) = \\
 &= 1 - e^{-2} \left(\frac{2^0}{0!} + \frac{2^1}{1!} + \frac{2^2}{2!} + \frac{2^3}{3!} \right) \\
&= 0.1428 \\
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1678520971201-->
END


START
Basic
relationship of [[binomial distribution]], [[poisson distribution]] and [[hypergeometric distribution]]

Back: 

[[hypergeometric distribution]]
$$
f_X({x|a,b,n}) = \frac{
{a \choose x}{b \choose n-x}
}{{a+b \choose n}}
\quad for \: max\{0, n-b\}<x<min\{n, a\}
$$
- $p=\frac{a}{a+b}$, $a+b \gg n$ → [[binomial distribution]]

[[binomial distribution]]
$$
f_X(x | n, p)= 
\begin{cases}
{n \choose x}
p^{x}(1-p)^{n-x}

,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
$$
- $\lambda = np$, $p \ll 1$ →  [[poisson distribution]]

[[poisson distribution]]:
$$
f_X(x | \lambda) =
\begin{cases}
\frac{\lambda^xe^{-\lambda}}{x!}
& \text{if } x \in \{0,1,2,..., n\}\\
0
& \text{otherwise}
\end{cases}
$$

Tags: mathematics statistics
<!--ID: 1678520971204-->
END