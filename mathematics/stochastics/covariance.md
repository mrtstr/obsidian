### covariance
$$
\mathbb{COV}\left[X,Y\right] = \mathbb{E}\left[(X-\mathbb{E}\left[X\right])(Y-\mathbb{E}\left[Y\right])\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]
$$

## Interpretation
### positive [[covariance]]
- $X$ and $Y$ move in the same direction at the same time thus there is a positive dependency between $X$ and $Y$
- $X$ and $Y$ are bigger/samler that their [[mean]] at the same time
- $\mathbb{E}\left[X\right] >> X$ and $\mathbb{E}\left[Y\right] >> Y$ is happening at the same time and $\mathbb{E}\left[X\right] << X$ and $\mathbb{E}\left[Y\right] << Y$ is happening at the same time
### negative [[covariance]]:
- the [[covariance]] is negative when $X$ or $Y$ is bigger that its [[mean]] while the other is smaller than its [[mean]] and vice versa

### properties [[covariance]]
#### dependency on the absolute size of the [[random variable|random variables]]
- the [[covariance]] is a measure for the linear dependency of [[random variable|random variables]] but it also depends on the absolute size of the [[random variable|random variables]] $X$ and $Y$
$$
\begin{split}
\mathbb{COV}\left[aX,bY\right] 
&= 
\mathbb{E}\left[aXbY\right]-\mathbb{E}\left[aX\right]\mathbb{E}\left[bY\right] \\
&= 
ab\left(\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]\right) \\
&= 
ab\left(\mathbb{COV}\left[X,Y\right]\right) \\
\end{split}
$$
#### relationship to the [[variance]]
$$
\mathbb{COVAR}[X_1,X_2] = \frac{\mathbb{VAR}[X_1 + X_2]-(\mathbb{VAR}[X_1]+\mathbb{VAR}[X_2])}{2}
$$
proof:
$$
\begin{split}
\mathbb{VAR}[X_1 + X_2]&=\mathbb{E}\left[\left(X_1 + X_2-\mathbb{E}[X_1 + X_2]\right)^2\right] \\
&=\mathbb{E}\left[\left(X_1 + X_2-\mathbb{E}[X_1] - \mathbb{E}[X_2]\right)^2\right]  \\
&=\mathbb{E}\left[\left(\left(X_1 -\mathbb{E}[X_1]) + (X_2 - \mathbb{E}[X_2]\right)\right)^2\right]  \\
&=\mathbb{E}\left[\left(X_1 -\mathbb{E}[X_1])^2 + (X_2 - \mathbb{E}[X_2]\right)^2 + 2 \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right]  \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{E}\left[ \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{E}\left[ X_1X_2 +\mathbb{E}[X_1]\mathbb{E}[X_2] - X_1\mathbb{E}[X_2] - X_2\mathbb{E}[X_1]\right] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\left(\mathbb{E}\left[ X_1X_2 \right] + \mathbb{E}[X_1]\mathbb{E}[X_2] - \mathbb{E}[X_1X_2] - \mathbb{E}[X_1X_2] \right) \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\left(\mathbb{E}\left[ X_1X_2 \right] - \mathbb{E}[X_1X_2]  \right) \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{COVAR}[X_1,X_2] \\
\end{split}
$$
#### [[covariance]] of [[stochastic independent]] [[random variable|random variables]]
- [[stochastic independent]] [[random variable|random variables]] have no dependency thus the [[covariance]] is $0$ 
$$
\mathbb{COV}\left[X,Y\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[XY\right]
= 0
$$
- from $\mathbb{COV}\left[X,Y\right] = 0$ does not follow [[stochastic independent|stochastic independence]] it just means that there is no linear relationship
proof: 
$$
\begin{split}
X &\in \{-1,0,1\} \\
Y&=X^2 \\
\mathbb{COV}\left[X,Y\right] 
&= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right] \\
&= 
\mathbb{E}\left[X^3\right]-\mathbb{E}\left[X^3\right] \\
&= 
0 \\
\end{split}
$$


# Anki


START
Basic
[[covariance]]
- definition
- positive [[covariance]]
- negative [[covariance]]
- dependency on the absolute size of the [[random variable|random variables]]
- [[covariance]] of [[stochastic independent]] [[random variable|random variables]]
- [[covariance]] of [[stochastic independent]] [[random variable|random variables]]
(proofs not needed but given)

Back: 
### covariance
$$
\mathbb{COV}\left[X,Y\right] = \mathbb{E}\left[(X-\mathbb{E}\left[X\right])(Y-\mathbb{E}\left[Y\right])\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]
$$

### positive [[covariance]]
- $X$ and $Y$ move in the same direction at the same time thus there is a positive dependency between $X$ and $Y$
- $X$ and $Y$ are bigger/samler that their [[mean]] at the same time
- $\mathbb{E}\left[X\right] >> X$ and $\mathbb{E}\left[Y\right] >> Y$ is happening at the same time and $\mathbb{E}\left[X\right] << X$ and $\mathbb{E}\left[Y\right] << Y$ is happening at the same time
### negative [[covariance]]:
- the [[covariance]] is negative when $X$ or $Y$ is bigger that its [[mean]] while the other is smaller than its [[mean]] and vice versa
### dependency on the absolute size of the [[random variable|random variables]]
- the [[covariance]] is a measure for the linear dependency of [[random variable|random variables]] but it also depends on the absolute size of the [[random variable|random variables]] $X$ and $Y$
$$
\begin{split}
\mathbb{COV}\left[aX,bY\right] 
&= 
\mathbb{E}\left[aXbY\right]-\mathbb{E}\left[aX\right]\mathbb{E}\left[bY\right] \\
&= 
ab\left(\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]\right) \\
&= 
ab\left(\mathbb{COV}\left[X,Y\right]\right) \\
\end{split}
$$
### [[covariance]] of [[stochastic independent]] [[random variable|random variables]]
- [[stochastic independent]] [[random variable|random variables]] have no dependency thus the [[covariance]] is $0$ 
$$
\mathbb{COV}\left[X,Y\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[XY\right]
= 0
$$
- from $\mathbb{COV}\left[X,Y\right] = 0$ does not follow [[stochastic independent|stochastic independence]] it just means that there is no linear relationship
proof: 
$$
\begin{split}
X &\in \{-1,0,1\} \\
Y&=X^2 \\
\mathbb{COV}\left[X,Y\right] 
&= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right] \\
&= 
\mathbb{E}\left[X^3\right]-\mathbb{E}\left[X^3\right] \\
&= 
0 \\
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1674378389867-->
END


START
Basic
dependency of the [[covariance]] on the absolute size of the [[random variable|random variables]] (with proof)

Back: 
the [[covariance]] is a measure for the linear dependency of [[random variable|random variables]] but it also depends on the absolute size of the [[random variable|random variables]] $X$ and $Y$
$$
\begin{split}
\mathbb{COV}\left[aX,bY\right] 
&= 
\mathbb{E}\left[aXbY\right]-\mathbb{E}\left[aX\right]\mathbb{E}\left[bY\right] \\
&= 
ab\left(\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]\right) \\
&= 
ab\left(\mathbb{COV}\left[X,Y\right]\right) \\
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1674378389870-->
END


START
Basic
relationship of the [[covariance]] to the [[variance]]
Back: 

$$
\mathbb{COVAR}[X_1,X_2] = \frac{\mathbb{VAR}[X_1 + X_2]-(\mathbb{VAR}[X_1]+\mathbb{VAR}[X_2])}{2}
$$
proof:
$$
\begin{split}
\mathbb{VAR}[X_1 + X_2]&=\mathbb{E}\left[\left(X_1 + X_2-\mathbb{E}[X_1 + X_2]\right)^2\right] \\
&=\mathbb{E}\left[\left(X_1 + X_2-\mathbb{E}[X_1] - \mathbb{E}[X_2]\right)^2\right]  \\
&=\mathbb{E}\left[\left(\left(X_1 -\mathbb{E}[X_1]) + (X_2 - \mathbb{E}[X_2]\right)\right)^2\right]  \\
&=\mathbb{E}\left[\left(X_1 -\mathbb{E}[X_1])^2 + (X_2 - \mathbb{E}[X_2]\right)^2 + 2 \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right]  \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{E}\left[ \left(X_1 -\mathbb{E}[X_1]\right)\left(X_2 -\mathbb{E}[X_2]\right)\right] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{E}\left[ X_1X_2 +\mathbb{E}[X_1]\mathbb{E}[X_2] - X_1\mathbb{E}[X_2] - X_2\mathbb{E}[X_1]\right] \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\left(\mathbb{E}\left[ X_1X_2 \right] + \mathbb{E}[X_1]\mathbb{E}[X_2] - \mathbb{E}[X_1X_2] - \mathbb{E}[X_1X_2] \right) \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\left(\mathbb{E}\left[ X_1X_2 \right] - \mathbb{E}[X_1X_2]  \right) \\
&= \mathbb{VAR}[X_1] + \mathbb{VAR}[X_2] + 
2\mathbb{COVAR}[X_1,X_2] \\
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1674378389872-->
END



START
Basic
- [[covariance]] of [[stochastic independent]] [[random variable|random variables]]
- meaning of zero [[covariance]]

Back: 
- [[stochastic independent]] [[random variable|random variables]] have no dependency thus the [[covariance]] is $0$ 
$$
\mathbb{COV}\left[X,Y\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[XY\right]
= 0
$$
- from $\mathbb{COV}\left[X,Y\right] = 0$ does not follow [[stochastic independent|stochastic independence]] it just means that there is no linear relationship
proof: 
$$
\begin{split}
X &\in \{-1,0,1\} \\
Y&=X^2 \\
\mathbb{COV}\left[X,Y\right] 
&= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right] \\
&= 
\mathbb{E}\left[X^3\right]-\mathbb{E}\left[X^3\right] \\
&= 
0 \\
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1674378389875-->
END


