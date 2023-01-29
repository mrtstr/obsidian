# Definition
(Extension of the concept of the [[variance]] for [[conditional probability]])
The [[conditional variance]] is a function of $x$
$$
 \mathbb{VAR}_{Y|x}\left[Y\:|\:x \right] = \mathbb{E}[(Y-\mathbb{E}[Y\:|\:x ])^2\:|\:x ]=\mathbb{E}[Y^2\:|\:x ]-\mathbb{E}[Y\:|\:x ]^2=g(x)
$$
($\mathbb{VAR}_{Y|x}\left[Y\:|\:x \right]$ is a short notation for $\mathbb{VAR}_{Y|X=x}\left[Y\:|\:X=x \right]$)
Similar to the [[conditional expectation]] the [[conditional variance]] can be used as a [[functions of random variables|function]] of [[random variable]] which is a [[random variable]] again
$$
g(X)=\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]  = \mathbb{E}[(Y-\mathbb{E}[Y\:|\:X ])^2\:|\:X ] = \mathbb{E}[Y^2\:|\:X ]-\mathbb{E}[Y\:|\:X ]^2
$$
# [[law of total probability]] for the [[variance]]
$$
\mathbb{VAR}\left[Y\right] = \mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
+ \mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right]
$$
## proof
$$
\begin{split}
\mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
+ \mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right] \

&=\mathbb{E}\left[ \mathbb{E}\left[ Y^2\:|\:X\right]\right] - \mathbb{E}\left[ \mathbb{E}\left[ Y\:|\:X\right]^2\right] \\
&\quad+\mathbb{E}\left[ \mathbb{E}\left[ Y\:|\:X\right]\right]^2 -
\mathbb{E}\left[ \mathbb{E}\left[ Y\:|\:X\right]\right]^2 \\
&=\mathbb{E}\left[ \mathbb{E}\left[ Y^2\:|\:X\right]\right] - 
\mathbb{E}\left[ \mathbb{E}\left[ Y\:|\:X\right]\right]^2  \\
&=\mathbb{E}\left[ Y^2\right] - \mathbb{E}\left[ Y\right]^2 \\
&=\mathbb{VAR}[Y]
\end{split}
$$


# anki

START
Basic
[[conditional variance]]: definition
Back: 
(Extension of the concept of the [[variance]] for [[conditional probability]])
The [[conditional variance]] is a function of $x$
$$
 \mathbb{VAR}_{Y|x}\left[Y\:|\:x \right] = \mathbb{E}[(Y-\mathbb{E}[Y\:|\:x ])^2\:|\:x ]=\mathbb{E}[Y^2\:|\:x ]-\mathbb{E}[Y\:|\:x ]^2=g(x)
$$
($\mathbb{VAR}_{Y|x}\left[Y\:|\:x \right]$ is a short notation for $\mathbb{VAR}_{Y|X=x}\left[Y\:|\:X=x \right]$)
Similar to the [[conditional expectation]] the [[conditional variance]] can be used as a [[functions of random variables|function]] of [[random variable]] which is a [[random variable]] again
$$
g(X)=\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]  = \mathbb{E}[(Y-\mathbb{E}[Y\:|\:X ])^2\:|\:X ] = \mathbb{E}[Y^2\:|\:X ]-\mathbb{E}[Y\:|\:X ]^2
$$
Tags: mathematics, statistics
<!--ID: 1674999785357-->
END

START
Basic
[[conditional variance]]: [[law of total probability]] with proof
Back: 
### Definition
(Extension of the concept of the [[variance]] for [[conditional probability]])
The [[conditional variance]] is a function of $x$
$$
 \mathbb{VAR}_{Y|x}\left[Y\:|\:x \right] = \mathbb{E}[(Y-\mathbb{E}[Y\:|\:x ])^2\:|\:x ]=\mathbb{E}[Y^2\:|\:x ]-\mathbb{E}[Y\:|\:x ]^2=g(x)
$$
($\mathbb{VAR}_{Y|x}\left[Y\:|\:x \right]$ is a short notation for $\mathbb{VAR}_{Y|X=x}\left[Y\:|\:X=x \right]$)
Similar to the [[conditional expectation]] the [[conditional variance]] can be used as a [[functions of random variables|function]] of [[random variable]] which is a [[random variable]] again
$$
g(X)=\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]  = \mathbb{E}[(Y-\mathbb{E}[Y\:|\:X ])^2\:|\:X ] = \mathbb{E}[Y^2\:|\:X ]-\mathbb{E}[Y\:|\:X ]^2
$$
### [[law of total probability]] for the [[variance]]
$$
\mathbb{VAR}\left[Y\right] = \mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
+ \mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right]
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
+ \mathbb{VAR}\left[\mathbb{E}_{Y|X}\left[Y\:|\:X \right]\right] \

&=\mathbb{E}\left[ \mathbb{E}\left[ Y^2\:|\:X\right]\right] - \mathbb{E}\left[ \mathbb{E}\left[ Y\:|\:X\right]^2\right] \\
&\quad+\mathbb{E}\left[ \mathbb{E}\left[ Y\:|\:X\right]\right]^2 -
\mathbb{E}\left[ \mathbb{E}\left[ Y\:|\:X\right]\right]^2 \\
&=\mathbb{E}\left[ \mathbb{E}\left[ Y^2\:|\:X\right]\right] - 
\mathbb{E}\left[ \mathbb{E}\left[ Y\:|\:X\right]\right]^2  \\
&=\mathbb{E}\left[ Y^2\right] - \mathbb{E}\left[ Y\right]^2 \\
&=\mathbb{VAR}[Y]
\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1674999785362-->
END