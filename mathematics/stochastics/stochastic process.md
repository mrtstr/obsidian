# stochastic process: definition
## index set $T$
- $T$ can be an arbitrary finite or infinit [[set]] 
- can be [[countable]] (discrete time) or non [[countable]] (continuous time)
e.g. $$T=\{1,2,3....,n\}$$
## stochastic process
- a stochastic process is a collection of [[random variable|random variables]] from a common [[probability space]] 
e.g.
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


# Anki
START
Basic
stochastic process 
- definition
- examples
Back: 
## index set $T$
- $T$ can be an arbitrary finite or infinit [[set]] 
- can be [[countable]] (discrete time) or non [[countable]] (continuous time)
e.g. $T=\{1,2,3....,n\}$

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
&X( \omega, X_1=x_1,...X_n=x_n) = X_{n+1}
\end{split}
$$
- the transition from $X_n$ to $X_{n+1}$ can be described with the following [[conditional probability]] 
 $$
 P(X_{n=1} \leq b \mid X_1=x_1,...X_n=x_n)
 $$ 
- for a given outcome $\omega \in \Omega$ the sample function is mapping the index set $T$ to the state space $S$
$$
X(\cdot \:, \omega ): T \mapsto S 
$$
## examples
- a stochastic process with $|T| = 1$ is a [[random variable]]
- a stochastic process with a finite and [[countable]] index set $|T| < \infty$ is a [[random vector]]


Tags: mathematics statistics
<!--ID: 1672328634263-->
END