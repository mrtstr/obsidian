# Definition
- The [[correlation]] is a measure for the linear dependency of [[random variable|random variables]] 
- in contrast to the [[covariance]] the [[correlation]] is not depending on the absolut size of the [[random variable|random variables]]
$$
\rho[X,Y] = \frac{\mathbb{COVAR}[X,Y]}{\sigma_X\sigma_Y}=\frac{\mathbb{COVAR}[X,Y]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[Y]}}
$$
# Properties
## the [[correlation]] is independent of [[random variable]] size
$$
\begin{split}
\rho\left[aX,bY\right] 
&= 
\frac{\mathbb{COVAR}[aX,bY]}{\sqrt{\mathbb{VAR}[aX]\mathbb{VAR}[bY]}} \\
&= 
\frac{ab \cdot\mathbb{COVAR}[X,Y]}{\sqrt{a^2b^2\mathbb{VAR}[X]\mathbb{VAR}[Y]}} \\
&= \frac{ab}{\sqrt{a^2b^2}} \cdot \frac{\mathbb{COVAR}[X,Y]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[Y]}} \\
&= sign(ab) \cdot \rho\left[X,Y\right]
\end{split}
$$
## boundarys
$$
-1 \leq \rho[X,Y] \leq 1
$$
proof: [[cauchy schwarz inequality]]

## [[correlation]] of [[stochastic independent]] [[random variable|random variables]]
From [[stochastic independent|stochastic independence]] follows zero [[correlation]] and [[covariance]] but not the other way.
$$
\begin{split}
X \perp Y &\Rightarrow \rho[X,Y] = \mathbb{COVAR}[X,y] = 0 \\
\rho[X,Y] = 0 &\nRightarrow X \perp Y    
\end{split}
$$
proof:
$$
\rho[X,Y] = \frac{\mathbb{COVAR}[X,Y]}{\sigma_X\sigma_Y}=\frac{0}{\sigma_X\sigma_Y} = 0
$$
![[covariance#covariance of stochastic independent random variable random variables]]

## [[correlation]] of linear dependent [[random variable|random variables]]
from $\left|\rho\left[X,Y\right]\right|= 1$ that the [[random variable|random variables]] $X$ and $Y$  are linearly related thus $X=g(Y)$ and $Y=g(X)$ with $g(.)$ being a [[linear function]] and vice versa
$$
\left|\rho\left[X,Y\right]\right|= 1 \Leftrightarrow X=g(Y)
$$
- if $Y$ is a [[linear function]] of $X$ $\rho\left[X,Y\right]$ is either $1$ or $-1$ depending on the sign of $a$
proof
$$
\begin{split}
\rho\left[X,aX+b\right] 
&= 
\frac{\mathbb{COVAR}[X,aX+b]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[aX+b]}} \\
&= 
\frac{\mathbb{E}\left[X(aX+b)\right]\mathbb{E}\left[X\right]\mathbb{E}\left[aX+b\right]}{\sqrt{a^2\mathbb{VAR}[X]\mathbb{VAR}[X]}} \\
&= 
\frac{a\mathbb{E}\left[X^2\right]+b\mathbb{E}\left[X\right]-a\mathbb{E}\left[X\right]^2-b\mathbb{E}\left[X\right]}{\sqrt{a^2\mathbb{VAR}[X]\mathbb{VAR}[X]}} \\
&= 
\frac{a\left(\mathbb{E}\left[X^2\right]-\mathbb{E}\left[X\right]^2\right)}{\sqrt{a^2}\mathbb{VAR}[X]} \\
&= 
\frac{a}{\sqrt{a^2}}
\frac{\mathbb{VAR}[X]}{\mathbb{VAR}[X]}\\
&= 
sign(a)\\
\end{split}
$$
## interpretation of a small [[correlation]]
- a small $\left|\rho\left[X,Y\right]\right|$ does not mean that $X$ and $Y$ are not related - it only says that there is no linear relationship between them

# Anki
START
Basic
[[correlation]]
- definition
- interpretation
- properties
(proofs given but not needed)

Back: 
# Definition
- The [[correlation]] is a measure for the linear dependency of [[random variable|random variables]] 
- in contrast to the [[covariance]] the [[correlation]] is not depending on the absolut size of the [[random variable|random variables]]
$$
\rho[X,Y] = \frac{\mathbb{COVAR}[X,Y]}{\sigma_X\sigma_Y}=\frac{\mathbb{COVAR}[X,Y]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[Y]}}
$$
# Properties
## the [[correlation]] is independent of [[random variable]] size
$$
\begin{split}
\rho\left[aX,bY\right] 
&= 
\frac{\mathbb{COVAR}[aX,bY]}{\sqrt{\mathbb{VAR}[aX]\mathbb{VAR}[bY]}} \\
&= 
\frac{ab \cdot\mathbb{COVAR}[X,Y]}{\sqrt{a^2b^2\mathbb{VAR}[X]\mathbb{VAR}[Y]}} \\
&= \frac{ab}{\sqrt{a^2b^2}} \cdot \frac{\mathbb{COVAR}[X,Y]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[Y]}} \\
&= sign(ab) \cdot \rho\left[X,Y\right]
\end{split}
$$
## boundarys
$$
-1 \leq \rho[X,Y] \leq 1
$$
proof: [[cauchy schwarz inequality]]


## [[correlation]] of [[stochastic independent]] [[random variable|random variables]]
From [[stochastic independent|stochastic independence]] follows zero [[correlation]] and [[covariance]] but not the other way.
$$
\begin{split}
X \perp Y &\Rightarrow \rho[X,Y] = \mathbb{COVAR}[X,y] = 0 \\
\rho[X,Y] = 0 &\nRightarrow X \perp Y    
\end{split}
$$
proof:
$$
\rho[X,Y] = \frac{\mathbb{COVAR}[X,Y]}{\sigma_X\sigma_Y}=\frac{0}{\sigma_X\sigma_Y} = 0
$$
####  [[covariance]] of [[stochastic independent]] [[random variable|random variables]]
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

## [[correlation]] of linear dependent [[random variable|random variables]]
from $\left|\rho\left[X,Y\right]\right|= 1$ that the [[random variable|random variables]] $X$ and $Y$  are linearly related thus $X=g(Y)$ and $Y=g(X)$ with $g(.)$ being a [[linear function]] and vice versa
$$
\left|\rho\left[X,Y\right]\right|= 1 \Leftrightarrow X=g(Y)
$$
- if $Y$ is a [[linear function]] of $X$ $\rho\left[X,Y\right]$ is either $1$ or $-1$ depending on the sign of $a$
proof
$$
\begin{split}
\rho\left[X,aX+b\right] 
&= 
\frac{\mathbb{COVAR}[X,aX+b]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[aX+b]}} \\
&= 
\frac{\mathbb{E}\left[X(aX+b)\right]\mathbb{E}\left[X\right]\mathbb{E}\left[aX+b\right]}{\sqrt{a^2\mathbb{VAR}[X]\mathbb{VAR}[X]}} \\
&= 
\frac{a\mathbb{E}\left[X^2\right]+b\mathbb{E}\left[X\right]-a\mathbb{E}\left[X\right]^2-b\mathbb{E}\left[X\right]}{\sqrt{a^2\mathbb{VAR}[X]\mathbb{VAR}[X]}} \\
&= 
\frac{a\left(\mathbb{E}\left[X^2\right]-\mathbb{E}\left[X\right]^2\right)}{\sqrt{a^2}\mathbb{VAR}[X]} \\
&= 
\frac{a}{\sqrt{a^2}}
\frac{\mathbb{VAR}[X]}{\mathbb{VAR}[X]}\\
&= 
sign(a)\\
\end{split}
$$
## interpretation of a small [[correlation]]
- a small $\left|\rho\left[X,Y\right]\right|$ does not mean that $X$ and $Y$ are not related - it only says that there is no linear relationship between them

Tags: mathematics, statistics
<!--ID: 1674378389849-->
END



START
Basic
impact of the size of [[random variable]] on the [[correlation]] with proof

Back: 
- the [[correlation]] is independent of [[random variable]] size
$$
\begin{split}
\rho\left[aX,bY\right] 
&= 
\frac{\mathbb{COVAR}[aX,bY]}{\sqrt{\mathbb{VAR}[aX]\mathbb{VAR}[bY]}} \\
&= 
\frac{ab \cdot\mathbb{COVAR}[X,Y]}{\sqrt{a^2b^2\mathbb{VAR}[X]\mathbb{VAR}[Y]}} \\
&= \frac{ab}{\sqrt{a^2b^2}} \cdot \frac{\mathbb{COVAR}[X,Y]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[Y]}} \\
&= sign(ab) \cdot \rho\left[X,Y\right]
\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1674378389855-->
END



START
Basic
properties of the [[correlation]]
- [[correlation]] of [[stochastic independent]] [[random variable|random variables]] (with proof)
- [[correlation]] of linear dependent [[random variable|random variables]] (with proof)
- what does a zero/small absolut [[correlation]] say about the [[stochastic independent|stochastic dependent]] of [[random variable|random variables]]

Back: 
# Definition
- The [[correlation]] is a measure for the linear dependency of [[random variable|random variables]] 
- in contrast to the [[covariance]] the [[correlation]] is not depending on the absolut size of the [[random variable|random variables]]
$$
\rho[X,Y] = \frac{\mathbb{COVAR}[X,Y]}{\sigma_X\sigma_Y}=\frac{\mathbb{COVAR}[X,Y]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[Y]}}
$$
## [[correlation]] of [[stochastic independent]] [[random variable|random variables]]
From [[stochastic independent|stochastic independence]] follows zero [[correlation]] and [[covariance]] but not the other way.
$$
\begin{split}
X \perp Y &\Rightarrow \rho[X,Y] = \mathbb{COVAR}[X,y] = 0 \\
\rho[X,Y] = 0 &\nRightarrow X \perp Y    
\end{split}
$$
proof:
$$
\rho[X,Y] = \frac{\mathbb{COVAR}[X,Y]}{\sigma_X\sigma_Y}=\frac{0}{\sigma_X\sigma_Y} = 0
$$
####  [[covariance]] of [[stochastic independent]] [[random variable|random variables]]
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

## [[correlation]] of linear dependent [[random variable|random variables]]
from $\left|\rho\left[X,Y\right]\right|= 1$ that the [[random variable|random variables]] $X$ and $Y$  are linearly related thus $X=g(Y)$ and $Y=g(X)$ with $g(.)$ being a [[linear function]] and vice versa
$$
\left|\rho\left[X,Y\right]\right|= 1 \Leftrightarrow X=g(Y)
$$
- if $Y$ is a [[linear function]] of $X$ $\rho\left[X,Y\right]$ is either $1$ or $-1$ depending on the sign of $a$
proof
$$
\begin{split}
\rho\left[X,aX+b\right] 
&= 
\frac{\mathbb{COVAR}[X,aX+b]}{\sqrt{\mathbb{VAR}[X]\mathbb{VAR}[aX+b]}} \\
&= 
\frac{\mathbb{E}\left[X(aX+b)\right]\mathbb{E}\left[X\right]\mathbb{E}\left[aX+b\right]}{\sqrt{a^2\mathbb{VAR}[X]\mathbb{VAR}[X]}} \\
&= 
\frac{a\mathbb{E}\left[X^2\right]+b\mathbb{E}\left[X\right]-a\mathbb{E}\left[X\right]^2-b\mathbb{E}\left[X\right]}{\sqrt{a^2\mathbb{VAR}[X]\mathbb{VAR}[X]}} \\
&= 
\frac{a\left(\mathbb{E}\left[X^2\right]-\mathbb{E}\left[X\right]^2\right)}{\sqrt{a^2}\mathbb{VAR}[X]} \\
&= 
\frac{a}{\sqrt{a^2}}
\frac{\mathbb{VAR}[X]}{\mathbb{VAR}[X]}\\
&= 
sign(a)\\
\end{split}
$$
## interpretation of a small [[correlation]]
- a small $\left|\rho\left[X,Y\right]\right|$ does not mean that $X$ and $Y$ are not related - it only says that there is no linear relationship between them

Tags: mathematics, statistics
<!--ID: 1674378389859-->
END