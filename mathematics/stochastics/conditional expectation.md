
# Definition
- the [[conditional expectation]] $\mathbb{E}[Y|x]$ of a [[random variable]] $Y$ given $X$ can is a [[function]] of $x$ 
- thus $\mathbb{E}[Y|c]$ with the constant $c$ is a constant itself
- [[expectation]] for [[conditional distribution|conditional distributions]]
$$
g(x) =\mathbb{E}[Y|x]=\int\limits_{-\infty}^\infty y f_{Y|X}(y|x)dy = \frac{1}{f_{X}(x)} \int\limits_{-\infty}^\infty y f_{YX}(y,x)dy 
$$
- $g(X)=\mathbb{E}[Y|X]$ is a [[functions of random variables]] and thus is a [[random variable]] itself

# Existance
- the [[conditional expectation]] is only defined for $f_{X}(x) \neq 0$ 

# [[conditional expectation]] and [[statistical predictor]]
- the [[function]] $g(x) =\mathbb{E}[Y|x]$ can be interpreted as a [[statistical predictor]] that predicts a [[random variable]] $Y$ given an observed depandent [[random variable]] $X$
- the [[conditional expectation]] $\mathbb{E}[Y|x]$ optimizes the [[mean square error]] loss 

# properties

$$
\mathbb{E}\left[g(X) | X\right]  = g(X)
$$

$$
\mathbb{E}\left[Y , g(X) | X\right]  = g(X) \mathbb{E}\left[Y | X\right]
$$

$$
\mathbb{E}\left[Y  | X , g(X) \right]  = \mathbb{E}\left[Y | X\right]
$$

## linearity
$$
\mathbb{E}\left[aY_1 + bY_2 + c \: | \: X\right] = a \mathbb{E}\left[Y_1 \: | \: X\right] + b \mathbb{E}\left[Y_2  \: | \: X\right] + c
$$

### [[stochastic independent]] [[random variable|random variables]]
$$
Y \perp X \Rightarrow  \mathbb{E}\left[Y|X\right] =\mathbb{E}\left[Y\right]
$$
## [[law of total probability]] for [[expectation|expectations]]
### simple case
$$
\mathbb{E}[Y]  = \mathbb{E}\left[\mathbb{E}[Y|X]\right]
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[\mathbb{E}[Y|X]\right] 
& =\int\limits_{-\infty}^\infty f_{X}(x) 
\underbrace{ \int\limits_{-\infty}^\infty y  f_{Y|X}(y \mid x)dy 
}_{\mathbb{E}[Y|X]}
\:dx \\
& = \int\limits_{-\infty}^\infty  y \int\limits_{-\infty}^\infty  \frac{f_{X}(x)}{f_{X}(x)}  f_{YX}(y, x)dx \:dy \\
& = \int\limits_{-\infty}^{\infty} y f_{Y}(y)dy  \\
& = \mathbb{E}\left[Y\right]
\end{split}
$$
### simple case with a third [[random variable]]
$$
\mathbb{E}[Y | X_1]  = \mathbb{E}\left[\mathbb{E}[Y|X_1,X_2] | X_1\right]
$$

### with a [[functions of random variables]]
$$
\mathbb{E}\left[g(X,Y)\right]  = \mathbb{E}\left[\mathbb{E}\left[g(X,Y)|X\right]\right]
$$
#### proof

$$
\begin{split}
\mathbb{E}\left[\mathbb{E}\left[g(X,Y)|X\right]\right] 
& = \int\limits_{-\infty}^\infty f_{X}(x)  \int\limits_{-\infty}^\infty 
 g(X,Y) \cdot f_{YX|X}(y,x \mid x)dy \:dx \\
& = \int\limits_{-\infty}^\infty f_{X}(x) \int\limits_{-\infty}^\infty 
g(X,Y) \cdot f_{Y|X}(y \mid x)dy \:dx \\
& = \int\limits_{-\infty}^\infty \int\limits_{-\infty}^\infty \frac{f_{X}(x)}{f_{X}(x)}  
g(X,Y) \cdot f_{YX}(y, x)dy \:dx \\
&=  \mathbb{E}\left[g(X,Y)\right]
\end{split}
$$


START
Basic
conditional expected values: 
- definition
- proof for $\mathbb{E}[Y]  = \mathbb{E}\left[\mathbb{E}[Y|X]\right]$ 
Back: 
$\mathbb{E}[Y|X=x]=\int\limits_\infty^\infty y f_{Y|X=x}(x)dy$

proof for $\mathbb{E}[Y]  = \mathbb{E}\left[\mathbb{E}[Y|X]\right]$:
$$
\begin{split}
\mathbb{E}\left[\mathbb{E}[X|Y]\right] 
& =\int\limits_{-\infty}^\infty f_{X}(x) 
\underbrace{ \int\limits_{-\infty}^\infty y  f_{Y|X}(y \mid x)dy 
}_\text{E[X|Y]}
\:dx \\
& = \int\limits_{-\infty}^\infty \int\limits_{-\infty}^\infty y f_{X}(x) f_{Y|X}(y \mid x)dy \:dx \\
& = \int\limits_{-\infty}^{\infty} y f_{Y}(y)dy  \\
& = \mathbb{E}\left[Y\right]
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1661928261922-->
END