- [[discrete distribution]] of a [[discrete random variable]] that describes the number of positive  [[ random variable|bernoulli experiments]] with a parameter $p$ after $n$ 

![[bernoulli random variable#bernoulli random variable]]


![[Pasted image 20221120114927.png]]

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


# anki

START
Basic
[[binomial distribution]]
- verbal definition
- probability function
- interpretation
Back: 
- [[discrete distribution]] of a [[discrete random variable]] that describes the number of positive  [[ random variable|bernoulli experiments]] with a parameter $p$ after $n$ 

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

Tags: mathematics, statistics
<!--ID: 1668943285990-->
END