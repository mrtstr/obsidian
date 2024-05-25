### binomial distribution
- [[discrete distribution]] of a [[probability mass function (PMF)]] that describes the number of positive [[stochastic independent]] [[ random variable|bernoulli experiments]] with a parameter $p$ after $n$ 
- $X_1, ..., X_n \sim Ber(p)$
- $Y= g(\boldsymbol{X}) = X_1 + ... + X_n \sim Bin(n, p)$


![[Pasted image 20221120114927.png]]

#### [[probability function]]
- $n =$ number of [[bernoulli distribution|bernoulli experiments]] 
- $p=$ probability of positive outcome
- $x=$ number of positive outcomes

$$
f_X(X = x | n, p)= 
\begin{cases}
\overbrace{{n \choose x}}^\text{number of valid splits }
\overbrace{p^{x}(1-p)^{n-x}}^\text{ probability per split}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
$$


#### [[expectation]]
- $Y= X_1 + ... + X_n$ with $X_1, ..., X_n \sim Ber(p)$ 
- (because of the [[linear map|linearity]] of the [[expectation]])

$$
\mathbb{E}[Y] =\mathbb{E}[X_1 + ... + X_n] = n \mathbb{E}[X_i] = np
$$
#### [[variance]]
- $Y= X_1 + ... + X_n$ with $X_1, ..., X_n \sim Ber(p)$
- (because of the [[stochastic independent|stochastic independence]] of the [[bernoulli distribution|bernoulli random valiables]])

$$
\mathbb{VAR}[Y] =\mathbb{VAR}[X_1 + ... + X_n] = n \mathbb{VAR}[X_i] = np(1-p)
$$

### interpretation [[binomial distribution]]
- The can interpret the chain of [[ random variable|bernoulli experiments]] as a [[set]] $\{B_1,...,B_n\}$.
- The number of ways to split up the [[ random variable|bernoulli experiments]] in a positive group and a negative group with $x$ of them being in the positive group is $n \choose x$
- for each of the possible splits the probability of all [[ random variable|bernoulli experiments]] in the positive group being positive and all [[ random variable|bernoulli experiments]] in the negative group being negative is $p^{x}(1-p)^{n-x}$


### Sum of [[binomial distribution|binomial]] [[random variable|random variables]] with the same $p$ parameter
$$
Y= X_1 + ... + X_n \: with \: X_i \sim Bin(n_i, p) \Rightarrow X_n \sim Bin\left(\sum_{i=1}^n n_i, p\right)$
$$

# ---------------------
![[stochastic independent#stochastic independent]]

![[bernoulli distribution#bernoulli random variable]]

![[expectation#expectation]]

![[variance#variance]]

# anki

START
Basic
[[binomial distribution]]
- definition
- probability function
- interpretation

Back: 
### binomial distribution
- [[discrete distribution]] of a [[probability mass function (PMF)]] that describes the number of positive  [[ random variable|bernoulli experiments]] with a parameter $p$ after $n$ 
- $X_1, ..., X_n \sim Ber(p)$
- $Y= g(\boldsymbol{X}) = X_1 + ... + X_n \sim Bin(n, p)$


#### [[probability function]]
- $n =$ number of [[bernoulli distribution|bernoulli experiments]] 
- $p=$ probability of positive outcome
- $x=$ number of positive outcomes

$$
f_X(X = x | n, p)= 
\begin{cases}
\overbrace{{n \choose x}}^\text{number of valid splits }
\overbrace{p^{x}(1-p)^{n-x}}^\text{ probability per split}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
$$
### interpretation [[binomial distribution]]
- The can interpret the chain of [[ random variable|bernoulli experiments]] as a [[set]] $\{B_1,...,B_n\}$.
- The number of ways to split up the [[ random variable|bernoulli experiments]] in a positive group and a negative group with $x$ of them being in the positive group is $n \choose x$
- for each of the possible splits the probability of all [[ random variable|bernoulli experiments]] in the positive group being positive and all [[ random variable|bernoulli experiments]] in the negative group being negative is $p^{x}(1-p)^{n-x}$

#### [[expectation]]
- $Y= X_1 + ... + X_n$ with $X_1, ..., X_n \sim Ber(p)$ 
- (because of the [[linear map|linearity]] of the [[expectation]])

$$
\mathbb{E}[Y] =\mathbb{E}[X_1 + ... + X_n] = n \mathbb{E}[X_i] = np
$$
#### [[variance]]
- $Y= X_1 + ... + X_n$ with $X_1, ..., X_n \sim Ber(p)$
- (because of the [[stochastic independent|stochastic independence]] of the [[bernoulli distribution|bernoulli random valiables]])

$$
\mathbb{VAR}[Y] =\mathbb{VAR}[X_1 + ... + X_n] = n \mathbb{VAR}[X_i] = np(1-p)
$$

__________________
### stochastic independent
- a collection of [[event|events]] is [[stochastic independent]] if the occurrence of [[event space|event]] $B$ does not change the [[probability]] that [[event space|event]] also happened

$$
P\left(\bigcap\limits_{i=1}^{k} A_i \right) = \prod\limits_{i=1}^{k} P(A_i) 
$$
### bernoulli random variable
- [[probability mass function (PMF)]] $Z$ that can only take $0$ and $1$
	→support of $X = \{0,1\}$ 
- parameter $p$ defines the probability of $Z$ being 0 or 1
	- $P(1) = p$
	- $P(0) = 1-p$
- the probability function is defined as follows

#### [[probability function]]
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
#### [[expectation]]
$$
\mathbb{E}[B] = \sum_{\{0,1\}} b_i \cdot P(B=b_i) = 1 \cdot p + 0 \cdot (1-p) = p
$$
$$
\mathbb{E}\left[B^2\right] = \sum_{\{0,1\}} b_i^2 \cdot P(B=b_i) = 1^2 \cdot p + 0^2 \cdot (1-p) = p
$$
#### [[variance]]
$$
\mathbb{VAR}\left[B\right] = \mathbb{E}\left[B^2\right] - \mathbb{E}\left[B\right]^2 = p - p^2 =p(1-p)
$$


Tags: mathematics statistics
<!--ID: 1668943285990-->
END


START
Basic
[[binomial distribution]]
- [[expectation]]
- [[variance]]
Back: 

#### [[expectation]]
- $Y= X_1 + ... + X_n$ with $X_1, ..., X_n \sim Ber(p)$ 
- (because of the [[linear map|linearity]] of the [[expectation]])

$$
\mathbb{E}[Y] =\mathbb{E}[X_1 + ... + X_n] = n \mathbb{E}[X_i] = np
$$
#### [[variance]]
- $Y= X_1 + ... + X_n$ with $X_1, ..., X_n \sim Ber(p)$
- (because of the [[stochastic independent|stochastic independence]] of the [[bernoulli distribution|bernoulli random valiables]])

$$
\mathbb{VAR}[Y] =\mathbb{VAR}[X_1 + ... + X_n] = n \mathbb{VAR}[X_i] = np(1-p)
$$


__________________
### binomial distribution
- [[discrete distribution]] of a [[probability mass function (PMF)]] that describes the number of positive  [[ random variable|bernoulli experiments]] with a parameter $p$ after $n$ 
- $X_1, ..., X_n \sim Ber(p)$
- $Y= g(\boldsymbol{X}) = X_1 + ... + X_n \sim Bin(n, p)$


#### [[probability function]]
- $n =$ number of [[bernoulli distribution|bernoulli experiments]] 
- $p=$ probability of positive outcome
- $x=$ number of positive outcomes

$$
f_X(X = x | n, p)= 
\begin{cases}
\overbrace{{n \choose x}}^\text{number of valid splits }
\overbrace{p^{x}(1-p)^{n-x}}^\text{ probability per split}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
$$


### stochastic independent
- a collection of [[event|events]] is [[stochastic independent]] if the occurrence of [[event space|event]] $B$ does not change the [[probability]] that [[event space|event]] also happened

$$
P\left(\bigcap\limits_{i=1}^{k} A_i \right) = \prod\limits_{i=1}^{k} P(A_i) 
$$
### bernoulli random variable
- [[probability mass function (PMF)]] $Z$ that can only take $0$ and $1$
	→support of $X = \{0,1\}$ 
- parameter $p$ defines the probability of $Z$ being 0 or 1
	- $P(1) = p$
	- $P(0) = 1-p$
- the probability function is defined as follows

#### [[probability function]]
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
#### [[expectation]]
$$
\mathbb{E}[B] = \sum_{\{0,1\}} b_i \cdot P(B=b_i) = 1 \cdot p + 0 \cdot (1-p) = p
$$
$$
\mathbb{E}\left[B^2\right] = \sum_{\{0,1\}} b_i^2 \cdot P(B=b_i) = 1^2 \cdot p + 0^2 \cdot (1-p) = p
$$
#### [[variance]]
$$
\mathbb{VAR}\left[B\right] = \mathbb{E}\left[B^2\right] - \mathbb{E}\left[B\right]^2 = p - p^2 =p(1-p)
$$


Tags: mathematics statistics
<!--ID: 1716652417636-->
END