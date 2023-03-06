# Definition
## examples
- [[discrete distribution]] that discribes occurence of [[event|events]] that 
	1) probability that two [[event|events]] occure in the same time interval is close to zero because the rate of occurence is very low enough of the time interval is short enough 
	2) the probability that a [[event]] occured in a timeinterval is proportional to its lengh
	3) homogen: the probability that a [[event]] occured in the timeinterval does not depend on the interval's location
	4) [[stochastic independent|independence]]: the probability of one [[event]] in a time interval is [[stochastic independent]] from the occurence of events in non overlapping time intervals
- e.g.
	- customers arriving in a store 
	- rice falling on a chess board
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


