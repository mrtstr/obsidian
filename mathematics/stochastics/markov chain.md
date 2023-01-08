# Definition
[[markov chain]] are [[stochastic process]] that are 
1) time discrete ([[countable]] index [[set|sets]])
2) every transition is only depending on the current state


![[stochastic process##stochastic process: definition]]



# Transition
Each possible path $\boldsymbol{s} = (s_1,...s_n) \in S$ is from the [[joint distribution]] of the [[stochastic process]] $f_\boldsymbol{X}(s_1,...,s_n)=P(X_1=s_1,..,X_n=s_n)$
With the [[multiplication rule]] we can decompose the [[joint distribution]] of the [[stochastic process]] in the [[conditional probability|conditional probability's]] of each transition.
$$
 P(X_1=s_1,..,X_n=s_n) = P(X_{1})P(X_{2} \mid X_1=s_1)...P(X_{n} \mid X_{n-1}=s_{n-1})
$$

Now each transition can be described with its [[conditional probability]]
$$
 P(X_{n+1} = s_{n+1} \mid X_1=s_1,...X_n=s_n) = P(X_{n+1} = s_{n+1} \mid X_n=s_n)
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
Given the [[probability vector]] of the state $n$ $X_n= \left(P(X_n=s_1), P(X_n=s_2), .., P(X_n=s_k)\right)^{\top}$  
$$
X_n= \begin{pmatrix}   P(X_n=s_1) \\   ... \\ P(X_n=s_k)   \end{pmatrix}^\top \in \mathbb{R}^{1 \times |S|}
$$
We can calculate the [[probability vector]] of the following state $X_{n+1}$.
$$
\begin{split}
X_{n+1} &= X_{n} A  \\
&= \sum\limits_{s_i \in S} P(X_n=s_i) a_{i,j}  \\
&= \sum\limits_{s_i \in S} P(X_n=s_i) P(X_{n+1} = s_j \mid X_n = s_i)  \\
&= \sum\limits_{s_i \in S} P(X_{n+1} = x_j ,X_n=s_i) \\
&= \begin{pmatrix}   P(X_{n+1}=s_1) \\   ... \\ P(X_{n+1}=s_k)   \end{pmatrix} \in \mathbb{R}^{1 \times |S|}
\end{split} 
$$

## multi transitions
$$
\begin{split}
A^2 = AA^\top 
&= \left(\sum\limits_{k \in \{1,... |S|\}} a_{i,k}a_{k,j}\right)_{i,j} \\
&= \left(\sum\limits_{k \in \{1,... |S|\}} P(X_{n+2} = s_j \mid X_{n+1} = s_k)P(X_{n+1} = s_k \mid X_n = s_i)\right)_{i,j} \\
&= \left(\sum\limits_{k \in \{1,... |S|\}} P(X_{n+2} = s_j , X_{n+1} = s_k \mid X_n = s_i)\right)_{i,j} \\
&= \left( P(X_{n+2} = s_j  \mid X_n = s_i)\right)_{i,j} \\
\end{split}
$$
$$
A^m = \left( P(X_{n+m} = s_j  \mid X_n = s_i)\right)_{i,j} \\
$$
$$
\begin{split}
X_{n+m} &= X_{n} A^m  \\
&= \sum\limits_{x_i \in S} P(X_n=s_i)P(X_{n+m} = s_j  \mid X_n = s_i)  \\
&= \sum\limits_{s_i \in S} P(X_{n+m} = s_j ,X_n=s_i) \\
&= \begin{pmatrix}   P(X_{n+m}=s_1) \\   ... \\ P(X_{n+m}=s_k)   \end{pmatrix} \in \mathbb{R}^{1 \times |S|}
\end{split} 
$$

## Stationary Distribution
Given with a transition martix $A$ and a [[random vector]] $\boldsymbol{s}$ as initial state. $\boldsymbol{s}$ is a stationary distribution of the [[markov chain]] of the following is true.
$$
\boldsymbol{s}=A\boldsymbol{s}
$$
if the [[markov chain]] has only one stationary distribution, it can be found with the following equation.
$$
\boldsymbol{s} = (0,...,0,1) (A-I)^{-1}
$$
(no proof)
### existence
If there exists $m$ such that every element of $A^m$ is strictly positive, then
1) the Markov chain has a unique stationary distribution $\boldsymbol{s}$
2) 
$$\boldsymbol{s} = \sum\limits_{i \in \mathcal{I}}\left(\lim\limits_{n \rightarrow \infty} A_n \right)_{i,j} = \sum\limits_{i \in \mathcal{I}} P(X_{n+1} = x_j \mid X_n = x_i)$$
3) for every initial state the [[markov chain]] will allways converge to the stationary distribution $\boldsymbol{s}$
# anki

START
Basic
[[markov chain]]: statonary processes
- definition
- existence
- converging
Back: 
## Stationary Distribution
Given with a transition martix $A$ and a [[random vector]] $\boldsymbol{s}$ as initial state. $\boldsymbol{s}$ is a stationary distribution of the [[markov chain]] of the following is true.
$$
\boldsymbol{s}=A\boldsymbol{s}
$$
if the [[markov chain]] has only one stationary distribution it can be found with the following equation.
$$
\boldsymbol{s} = (0,...,0,1) (A-I)^{-1}
$$
(no proof)
### existence
If there exists $m$ such that every element of $A^m$ is strictly positive, then
1) the Markov chain has a unique stationary distribution $\boldsymbol{s}$
2) 
$$\boldsymbol{s} = \sum\limits_{i \in \mathcal{I}}\left(\lim\limits_{n \rightarrow \infty} A_n \right)_{i,j} = \sum\limits_{i \in \mathcal{I}} P(X_{n+1} = x_j \mid X_n = x_i)$$
3) for every initial state the [[markov chain]] will allways converge to the stationary distribution $\boldsymbol{s}$
Tags: mathematics, statistics
<!--ID: 1673172329093-->
END





START
Basic
[[markov chain]]
- defintion
Back: 
[[markov chain]] are [[stochastic process]] that are 
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
e.g. 
$$
\begin{split}
\boldsymbol{s} &= (s_1,...s_n) \in S \\
& \sim f_\boldsymbol{X}(s_1,...s_n)
\end{split}
$$

## sample function (transition function) $X$
- $X$ is a [[function]] that is appearing as a result of a [[random experiment]]
- at state $n$ $X_n$ is a [[random variable]] that is depending on the previous states $X_1,...,X_{n-1}$ and is mapping the [[sample space]] to a measurable space
$$
\begin{split}
&X_n(X_1,...,X_{n-1}): \Omega \mapsto \mathbb{R} \\
&X( \omega, X_1=s_1,...X_n=s_n) = X_{n+1}
\end{split}
$$
- the transition from $X_n$ to $X_{n+1}$ can be described with the following [[conditional probability]] 
 $$
 P(X_{n+1} \leq b \mid X_1=s_1,...X_n=s_n)
 $$
- for a given outcome $\omega \in \Omega$ the sample function is mapping the index set $T$ to the state space $S$
$$
X(\cdot \:, \omega ): T \mapsto S 
$$
# examples
- a stochastic process with $|T| = 1$ is a [[random variable]]
- a stochastic process with a finite and [[countable]] index set $|T| < \infty$ is a [[random vector]]
Tags: mathematics, statistics
<!--ID: 1672403411254-->
END

START
Basic
[[markov chain]]
- single transitions
Back: 
Each possipble path $\boldsymbol{s} = (s_1,...s_n) \in S$ is from the [[joint distribution]] of the [[stochastic process]] $f_\boldsymbol{X}(s_1,...,s_n)=P(X_1=s_1,..,X_n=s_n)$
With the [[multiplication rule]] we can decompose the [[joint distribution]] of the [[stochastic process]] in the [[conditional probability|conditional probability's]] of each transition.
$$
 P(X_1=s_1,..,X_n=s_n) = P(X_{1})P(X_{2} \mid X_1=s_1)...P(X_{n} \mid X_{n-1}=s_{n-1})
$$

Now each transition can be described with its [[conditional probability]]
$$
 P(X_{n+1} = s_{n+1} \mid X_1=s_1,...X_n=s_n) = P(X_{n+1} = s_{n+1} \mid X_n=s_n)
$$

## Transition [[matrix]]
We can define a [[stochastic matrix]] containing the [[conditional probability|conditional probabilities]]
$$
a_{i,j} = P(X_{n+1} = s_j \mid X_n = s_i)
$$
## single transitions
Given the [[probability vector]] of the state $n$ $X_n= \left(P(X_n=s_1), P(X_n=s_2), .., P(X_n=s_k)\right)^{\top}$  
$$
X_n= \begin{pmatrix}   P(X_n=s_1) \\   ... \\ P(X_n=s_k)   \end{pmatrix}^\top \in \mathbb{R}^{1 \times |S|}
$$
We can calculate the [[probability vector]] of the following state $X_{n+1}$.
$$
\begin{split}
X_{n+1} &= X_{n} A  \\
&= \sum\limits_{s_i \in S} P(X_n=s_i) a_{i,j}  \\
&= \sum\limits_{s_i \in S} P(X_n=s_i) P(X_{n+1} = s_j \mid X_n = s_i)  \\
&= \sum\limits_{s_i \in S} P(X_{n+1} = x_j ,X_n=s_i) \\
&= \begin{pmatrix}   P(X_{n+1}=s_1) \\   ... \\ P(X_{n+1}=s_k)   \end{pmatrix} \in \mathbb{R}^{1 \times |S|}
\end{split} 
$$
Tags: mathematics, statistics
<!--ID: 1672403411256-->
END


START
Basic
[[markov chain]]
- multiple transitions
Back: 
## multi transitions
$$
\begin{split}
A^2 = AA^\top 
&= \left(\sum\limits_{k \in \{1,... |S|\}} a_{i,k}a_{k,j}\right)_{i,j} \\
&= \left(\sum\limits_{k \in \{1,... |S|\}} P(X_{n+2} = s_j \mid X_{n+1} = s_k)P(X_{n+1} = s_k \mid X_n = s_i)\right)_{i,j} \\
&= \left(\sum\limits_{k \in \{1,... |S|\}} P(X_{n+2} = s_j , X_{n+1} = s_k \mid X_n = s_i)\right)_{i,j} \\
&= \left( P(X_{n+2} = s_j  \mid X_n = s_i)\right)_{i,j} \\
\end{split}
$$
$$
A^m = \left( P(X_{n+m} = s_j  \mid X_n = s_i)\right)_{i,j} \\
$$
$$
\begin{split}
X_{n+m} &= X_{n} A^m  \\
&= \sum\limits_{x_i \in S} P(X_n=s_i)P(X_{n+m} = s_j  \mid X_n = s_i)  \\
&= \sum\limits_{s_i \in S} P(X_{n+m} = s_j ,X_n=s_i) \\
&= \begin{pmatrix}   P(X_{n+m}=s_1) \\   ... \\ P(X_{n+m}=s_k)   \end{pmatrix} \in \mathbb{R}^{1 \times |S|}
\end{split} 
$$
Tags: mathematics, statistics
<!--ID: 1672403411259-->
END