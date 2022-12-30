# Definition
[[markov chains]] are [[stochastic process]] that are 
1) time discrete ([[countable]] index [[set|sets]])
2) every transition is only depending on the current state


![[stochastic process#stochastic process: definition]]

# Transition
Each transition can be described with the [[conditional probability]]
$$
 P(X_{n+1} \leq b \mid X_1=x_1,...X_n=x_n) = P(X_{n+1} \leq b \mid X_n=x_n)
$$
We can describe the [[joint distribution]] of the [[stochastic process]] with the [[multiplication rule]] as the product of [[conditional probability|conditional probability's]]
$$
 P(X_1=x_1,..,X_n=x_n) = P(X_{1})P(X_{2} \mid X_1=x_1)...P(X_{n} \mid X_{n-1}=x_{n-1})
$$
## Transition [[matrix]]
We can define a [[stochastic matrix]] containing the [[conditional probability|conditional probabilities]]
$$
a_{i,j} = P(X_{n+1} = x_j \mid X_n = x_i)
$$
![[stochastic matrix#definition stochastic matrix]]
It is easy to see that $A$ is a [[stochastic matrix]] because $\forall i \in T$
1) $\sum\limits_{j \in \{1,...S\}} a_{i,j} = \sum\limits_{j \in T} P(X_{n+1} = x_j \mid X_n = x_i) = 1$
2) $a_{i,j} = P(X_{n+1} = x_j \mid X_n = x_i)  \geq 0$
3) $A \in \mathbb{R}^{\left| S \right| \times \left| S\right|}$
## single transitions
Given a state $X_n= \left(P(X_n=s_1), P(X_n=s_2), .., P(X_n=s_k)\right)^{\top}$  
$$
X_n= \begin{pmatrix}   P(X_n=x_1) \\   ... \\ P(X_n=x_k)   \end{pmatrix} \in \mathbb{R}^{|S|}
$$
$$
\begin{split}
X_{n+1} &= X_{n}^\top A  \\
&= \sum\limits_{x_i \in S} P(X_n=x_i) a_{i,j}  \\
&= \sum\limits_{x_i \in S} P(X_n=x_i) P(X_{n+1} = x_j \mid X_n = x_i)  \\
&= \sum\limits_{x_i \in S} P(X_{n+1} = x_j ,X_n=x_i) \\
&= \begin{pmatrix}   P(X_{n+1}=x_1) \\   ... \\ P(X_{n+1}=x_k)   \end{pmatrix} \in \mathbb{R}^{|S|}
\end{split} 
$$

## multi transitions
$$
\begin{split}
A^2 = AA^\top 
&= \left(\sum\limits_{k \in \{1,... |S|\}} a_{i,k}a_{k,j}\right)_{i,j} \\
&= \left(\sum\limits_{k \in \{1,... |S|\}} P(X_{n+2} = x_j \mid X_{n+1} = x_k)P(X_{n+1} = x_k \mid X_n = x_i)\right)_{i,j} \\
&= \left(\sum\limits_{k \in \{1,... |S|\}} P(X_{n+2} = x_j , X_{n+1} = x_k \mid X_n = x_i)\right)_{i,j} \\
&= \left( P(X_{n+2} = x_j  \mid X_n = x_i)\right)_{i,j} \\
\end{split}
$$
$$
A^m = \left( P(X_{n+m} = x_j  \mid X_n = x_i)\right)_{i,j} \\
$$
$$
\begin{split}
X_{n+m} &= X_{n}^\top A^m  \\
&= \sum\limits_{x_i \in S} P(X_n=x_i)P(X_{n+m} = x_j  \mid X_n = x_i)  \\
&= \sum\limits_{x_i \in S} P(X_{n+m} = x_j ,X_n=x_i) \\
&= \begin{pmatrix}   P(X_{n+m}=x_1) \\   ... \\ P(X_{n+m}=x_k)   \end{pmatrix} \in \mathbb{R}^{|S|}
\end{split} 
$$
# anki

START
Basic
[[markov chains]]
- defintion
Back: 
[[markov chains]] are [[stochastic process]] that are 
1) time discrete ([[countable]] index [[set|sets]])
2) every transition is only depending on the current state

# stochastic process: definition
## index set $T$
- $T$ can be an arbitrary finite or infinit [[set]] 
- can be [[countable]] (discrete time) or non [[countable]] (continuous time)

## stochastic process
- a stochastic process is a collection of [[random variable|random variables]] from a common [[probability space]] 
$$
\{X_n \mid  n \in T\}
$$
## state space $S$
- every value the collection of [[random variable|random variables]] $\{X_n \mid  n \in T\}$ can take

## sample function (transition function) $X$
- $X$ is a [[function]] that is appearing as a result of a [[random experiment]]
- at state $n$ $X_n$ is a [[random variable]] that is depending on the previous states $X_1,...,X_{n-1}$ and is mapping the [[sample space]] to a measurable space
$$
\begin{split}
&X_n(X_1,...,X_{n-1}): \Omega \mapsto \mathbb{R} \\
&X( \omega, X_1=x_1,...X_n=x_n) = X_{n+1}
\end{split}
$$
- the transition from $X_n$ to $X_{n+1}$ can be described with the following [[conditional probability]] 
 $$
 P(X_{n+1} \leq b \mid X_1=x_1,...X_n=x_n)
 $$
- for a given outcome $\omega \in \Omega$ the sample function is mapping the index set $T$ to the state space $S$
$$
X(\cdot \:, \omega ): T \mapsto S 
$$
# examples
- a stochastic process with $|T| = 1$ is a [[random variable]]
- a stochastic process with a finite and [[countable]] index set $|T| < \infty$ is a [[random vector]]
<!--ID: 1672403411254-->
END

START
Basic
[[markov chains]]
- single transitions
Back: 
Each transition can be described with the [[conditional probability]]
$$
 P(X_{n+1} \leq b \mid X_1=x_1,...X_n=x_n) = P(X_{n+1} \leq b \mid X_n=x_n)
$$
We can describe the [[joint distribution]] of the [[stochastic process]] with the [[multiplication rule]] as the product of [[conditional probability|conditional probability's]]
$$
 P(X_1=x_1,..,X_n=x_n) = P(X_{1})P(X_{2} \mid X_1=x_1)...P(X_{n} \mid X_{n-1}=x_{n-1})
$$
## Transition [[matrix]]
We can define a [[stochastic matrix]] containing the [[conditional probability|conditional probabilities]]
$$
a_{i,j} = P(X_{n+1} = x_j \mid X_n = x_i)
$$
Tags: mathematics, statistics
<!--ID: 1672403411256-->
END


START
Basic
[[markov chains]]
- multiple transitions
Back: 
## multi transitions
$$
\begin{split}
A^2 = AA^\top 
&= \left(\sum\limits_{k \in \{1,... |S|\}} a_{i,k}a_{k,j}\right)_{i,j} \\
&= \left(\sum\limits_{k \in \{1,... |S|\}} P(X_{n+2} = x_j \mid X_{n+1} = x_k)P(X_{n+1} = x_k \mid X_n = x_i)\right)_{i,j} \\
&= \left(\sum\limits_{k \in \{1,... |S|\}} P(X_{n+2} = x_j , X_{n+1} = x_k \mid X_n = x_i)\right)_{i,j} \\
&= \left( P(X_{n+2} = x_j  \mid X_n = x_i)\right)_{i,j} \\
\end{split}
$$
$$
A^m = \left( P(X_{n+m} = x_j  \mid X_n = x_i)\right)_{i,j} \\
$$
$$
\begin{split}
X_{n+m} &= X_{n}^\top A^m  \\
&= \sum\limits_{x_i \in S} P(X_n=x_i)P(X_{n+m} = x_j  \mid X_n = x_i)  \\
&= \sum\limits_{x_i \in S} P(X_{n+m} = x_j ,X_n=x_i) \\
&= \begin{pmatrix}   P(X_{n+m}=x_1) \\   ... \\ P(X_{n+m}=x_k)   \end{pmatrix} \in \mathbb{R}^{|S|}
\end{split} 
$$
Tags: mathematics, statistics
<!--ID: 1672403411259-->
END