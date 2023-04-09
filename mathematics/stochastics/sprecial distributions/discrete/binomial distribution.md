# definition
- [[discrete distribution]] of a [[discrete random variable]] that describes the number of positive  [[ random variable|bernoulli experiments]] with a parameter $p$ after $n$ 
- $X_1, ..., X_n \sim Ber(p)$
- $Y= g(\boldsymbol{X}) = X_1 + ... + X_n \sim Bin(n, p)$

![[bernoulli distribution#bernoulli random variable]]


![[Pasted image 20221120114927.png]]

### [[probability function]]
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

### interpretation 
- The can interpret the chain of [[ random variable|bernoulli experiments]] as a [[set]] $\{B_1,...,B_n\}$.
- The number of ways to split up the [[ random variable|bernoulli experiments]] in a positive group and a negative group with $x$ of them being in the positive group is $n \choose x$
- for each of the possible splits the probability of all [[ random variable|bernoulli experiments]] in the positive group being positive and all [[ random variable|bernoulli experiments]] in the negative group being negative is $p^{x}(1-p)^{n-x}$


### [[expectation]]
$Y= X_1 + ... + X_n$ with $X_1, ..., X_n \sim Ber(p)$ i.i.d.
$$
\mathbb{E}[Y] =\mathbb{E}[X_1 + ... + X_n] = n \mathbb{E}[X_i] = np
$$
### [[variance]]

$Y= X_1 + ... + X_n$ with $X_1, ..., X_n \sim Ber(p)$ i.i.d.
$$
\mathbb{VAR}[Y] =\mathbb{VAR}[X_1 + ... + X_n] = n \mathbb{VAR}[X_i] = np(1-p)
$$
## Sum of [[binomial distribution|binomial]] [[random variable|random variables]] with the same $p$ parameter
$$
Y= X_1 + ... + X_n \: with \: X_i \sim Bin(n_i, p) \Rightarrow X_n \sim Bin\left(\sum_{i=1}^n n_i, p\right)$
$$



# anki

START
Basic
[[binomial distribution]]
- definition
- probability function
- interpretation
- [[expectation]]
- [[variance]]
- Sum of [[binomial distribution|binomial]] [[random variable|random variables]] with the same $p$ parameter
Back: 
 [[discrete distribution]] of a [[discrete random variable]] that describes the number of positive  [[ random variable|bernoulli experiments]] with a parameter $p$ after $n$ 
- $X_1, ..., X_n \sim Ber(p)$
- $Y= g(\boldsymbol{X}) = X_1 + ... + X_n \sim Bin(n, p)$
## probability function
$$
f_X(X = x)= P(X = x)
\begin{cases}
\overbrace{{n \choose x}}^\text{number of valid splits }
\overbrace{p^{x}(1-p)^{n-x}}^\text{ probability per split}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
$$

## interpretation 
- The can interpret the chain of [[ random variable|bernoulli experiments]] as a [[set]] $\{B_1,...,B_n\}$.
- The number of ways to split up the [[ random variable|bernoulli experiments]] in a positive group and a negative group with $x$ of them being in the positive group is $n \choose x$
- for each of the possible splits the probability of all [[ random variable|bernoulli experiments]] in the positive group being positive and all [[ random variable|bernoulli experiments]] in the negative group being negative is $p^{x}(1-p)^{n-x}$

## [[expectation]]
$Y= X_1 + ... + X_n$ with $X_1, ..., X_n \sim Ber(p)$ i.i.d.
$$
\mathbb{E}[Y] =\mathbb{E}[X_1 + ... + X_n] = n \mathbb{E}[X_i] = np
$$
## [[variance]]

$Y= X_1 + ... + X_n$ with $X_1, ..., X_n \sim Ber(p)$ i.i.d.
$$
\mathbb{VAR}[Y] =\mathbb{VAR}[X_1 + ... + X_n] = n \mathbb{VAR}[X_i] = np(1-p)
$$
## Sum of [[binomial distribution|binomial]] [[random variable|random variables]] with the same $p$ parameter
$$
Y= X_1 + ... + X_n \: with \: X_i \sim Bin(n_i, p) \Rightarrow X_n \sim Bin\left(\sum_{i=1}^n n_i, p\right)$
$$


Tags: mathematics statistics
<!--ID: 1668943285990-->
END