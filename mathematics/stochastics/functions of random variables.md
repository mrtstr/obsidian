[[function|functions]] of [[random variable|random variables]]


# [[discrete random variable|discrete case]] with an arbitrary [[function]]
- $X$ is a [[discrete random variable]] with a [[probability function]] $f_X(x)$
- $Y=g(X)$ with an arbitrary [[function]] $g$
$$
f_{Y}(y)=P(Y=y)=P(g(X)=y)=\sum\limits_{x_i \in \{x \mid g(x)=y \}} f_X(x_i)
$$
$$
F_{Y}(y)=P(Y \leq y)=P(g(X) \leq y)=\sum\limits_{x_i \in \{x \mid g(x) \leq y \}} f_X(x_i)
$$

# [[continuous random variable]]
- $X$ is a [[continuous random variable]] with a [[probability density function]] $f_X(x)$
- $Y=g(X)$ with an arbitrary [[function]] $g$
## [[inverse function]] $g^{-1}(X)$ unknown
$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) \\
&=\int\limits_{\{x \mid g(x) \leq y \}} f_X(x) \: dx \\
f_{Y}(y) &= \frac{dF_{Y}(y)}{dy}
\end{split}
$$

## [[inverse function]] $g^{-1}(X)$ known
$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) \\
&=F_{X}\left(g^{-1}(y)\right) \\

f_{Y}(y) &= \frac{dF_{Y}(y)}{dy} \\
&= \frac{dF_{X}\left(g^{-1}(y)\right)}{dy} \\
&= \frac{dg^{-1}(y)}{dy} f_{X}\left(g^{-1}(y)\right) \\
\end{split}
$$
#### example
- $X \sim U(-1,1)$ is from a [[continous uniform distribution]] with a [[probability density function]] 
$$f_X(x)=\begin{cases}
    \frac{1}{2},& \text{if } x \in [-1,1] \\
    0,              & \text{otherwise}
\end{cases}
$$
- $Y=g(X)=X^2$
$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) \\
&=P(X^2 \leq y) 
=P(-y^{\frac{1}{2}} \leq X \leq y^{\frac{1}{2}}) \\
&=\int\limits_{\{x \mid g(x) \leq y \}} f_X(x) \: dx 
=\int\limits_{-y^{\frac{1}{2}}}^{y^{\frac{1}{2}}} \frac{1}{2} \: dx
= y^{\frac{1}{2}} \\
f_{Y}(y) &= \frac{dF_{Y}(y)}{y} = \frac{1}{2} y^{-\frac{1}{2}}
\end{split}
$$

## [[linear function]] of a [[probability density function]]
- $X$ is a [[continuous random variable]] with a [[probability density function]] $f_X(x)$
- $Y=g(X)=aX+b$ with an [[linear function]] $g$

$$
f_Y(y)=\underbrace{\frac{1}{|a|}}_{\frac{dg^{-1}(y)}{dy}} f_{X}
\underbrace{
\left(\frac{y-b}{a}\right)
}_{g^{-1}(y)}
$$
proof:

$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) = P(aX=b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P(aX+b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P\left( X \leq \frac{y-b}{a} \right) \\
&= F_X\left(g^{-1}(y)\right) = F_X\left(\frac{y-b}{a}\right) \\


f_{Y}(y) &= \frac{dF_{Y}(y)}{dy} = \frac{dF_X\left(\frac{y-b}{a}\right)}{dy} f_{X}\left(\frac{y-b}{a}\right) \\
&= \frac{dg^{-1}(y)}{dy} f_{X}\left(\frac{y-b}{a}\right)
= \frac{1}{|a|} f_{X}\left(\frac{y-b}{a}\right)
\end{split}
$$

## [[continuous random variable]] with $g(X)=F_X(X)$
- $X$ is a [[continuous random variable]] with a [[CDF]] $F_X(x)$
- $Y$ is a [[functions of random variables|function of]] $X$ with the function being the [[CDF]] of $X$ $Y=F_X(X)$
Then $Y \sim U(0,1)$ has [[continous uniform distribution|uniform distribution]] and its [[CDF]] is $F_Y(y) = y$.

#### Proof
$$
\begin{split}
F_{Y}(y)&=P(Y \leq y) \\
&=P(F_X(X) \leq y) \\
&=P(X \leq F_X^{-1}(y)) \\
&= F_{X}(F_X^{-1}(y)) = y \\
\end{split}
$$

# Anki

START
Basic
functions of random variables: [[discrete random variable|discrete case]] with an arbitrary [[function]]
- [[probability function]] $f_Y(y)$ of the transformed [[random variable]] $Y=g(X)$
- [[CDF]] $F_Y(y)$ of the transformed [[random variable]] $Y=g(X)$
Back: 
 $X$ is a [[discrete random variable]] with a [[probability function]] $f_X(x)$
- $Y=g(X)$ with an arbitrary [[function]] $g$

$$
f_{Y}(y)=P(Y=y)=P(g(X)=y)=\sum\limits_{x_i \in \{x \mid g(x)=y \}} f_X(x_i)
$$
$$
F_{Y}(y)=P(Y \leq y)=P(g(X) \leq y)=\sum\limits_{x_i \in \{x \mid g(x) \leq y \}} f_X(x_i)
$$

Tags: mathematics, statistics
<!--ID: 1671275212198-->
END

START
Basic
[[functions of random variables]]: 
- [[continuous random variable]] with a [[linear function]]
- $X$ is a [[continuous random variable]] with a [[probability density function]] $f_X(x)$
- $Y=g(X)=aX+b$ with an [[linear function]] $g$
- [[probability density function]] of the transformed [[random variable]] $f_Y(y)$ (with proof)
Back: 

$$
f_Y(y)=\underbrace{\frac{1}{|a|}}_{\frac{dg^{-1}(y)}{dy}} f_{X}
\underbrace{
\left(\frac{y-b}{a}\right)
}_{g^{-1}(y)}
$$
proof:
$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) = P(aX=b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P(aX+b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P\left( X \leq \frac{y-b}{a} \right) \\
&= F_X\left(g^{-1}(y)\right) = F_X\left(\frac{y-b}{a}\right) \\


f_{Y}(y) &= \frac{dF_{Y}(y)}{dy} = \frac{dF_X\left(\frac{y-b}{a}\right)}{dy} f_{X}\left(\frac{y-b}{a}\right) \\
&= \frac{dg^{-1}(y)}{dy} f_{X}\left(\frac{y-b}{a}\right)
= \frac{1}{|a|} f_{X}\left(\frac{y-b}{a}\right)
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1671275212205-->
END


START
Basic
[[functions of random variables]]: 
- [[continuous random variable]] with an arbitrary [[function]]
- $X$ is a [[continuous random variable]] with a [[probability density function]] $f_X(x)$
- $Y=g(X)$ with an arbitrary [[function]] $g$
- - general case: [[inverse function]] $g^{-1}(X)$ unknown


- [[CDF]] of the transformed [[random variable]] $F_Y(y)$
- [[probability density function]] of the transformed [[random variable]] $f_Y(y)$

Back: 
#### [[inverse function]] $g^{-1}(X)$ unknown
$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) \\
&=\int\limits_{\{x \mid g(x) \leq y \}} f_X(x) \: dx \\
f_{Y}(y) &= \frac{dF_{Y}(y)}{dy}
\end{split}
$$



Tags: mathematics, statistics
<!--ID: 1671360434130-->
END




START
Basic
[[functions of random variables]]: 
- [[continuous random variable]] with an arbitrary [[function]]
- $X$ is a [[continuous random variable]] with a [[probability density function]] $f_X(x)$
- $Y=g(X)$ with an arbitrary [[function]] $g$
- [[inverse function]] $g^{-1}(X)$ known

- [[CDF]] of the transformed [[random variable]] $F_Y(y)$
- [[probability density function]] of the transformed [[random variable]] $f_Y(y)$

Back: 

#### [[inverse function]] $g^{-1}(X)$ known
$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) \\
&=F_{X}\left(g^{-1}(y)\right) \\

f_{Y}(y) &= \frac{dF_{Y}(y)}{dy} \\
&= \frac{dF_{X}\left(g^{-1}(y)\right)}{dy} \\
&= \frac{dg^{-1}(y)}{dy} f_{X}\left(g^{-1}(y)\right) \\
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1671702302816-->
END


START
Basic
[[functions of random variables]] example:  
- $X \sim U(-1,1)$ is from a [[continous uniform distribution]] with a [[probability density function]] 
$$f_X(x)=\begin{cases}
    \frac{1}{2},& \text{if } x \in [-1,1] \\
    0,              & \text{otherwise}
\end{cases}
$$
- $Y=g(X)=X^2$


- [[CDF]] of the transformed [[random variable]] $F_Y(y)$
- [[probability density function]] of the transformed [[random variable]] $f_Y(y)$
Back: 
$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) \\
&=P(X^2 \leq y) 
=P(-y^{\frac{1}{2}} \leq X \leq y^{\frac{1}{2}}) \\
&=\int\limits_{\{x \mid g(x) \leq y \}} f_X(x) \: dx 
=\int\limits_{-y^{\frac{1}{2}}}^{y^{\frac{1}{2}}} \frac{1}{2} \: dx
= y^{\frac{1}{2}} \\
f_{Y}(y) &= \frac{dF_{Y}(y)}{y} = \frac{1}{2} y^{-\frac{1}{2}}
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1671360434136-->
END


START
Basic
[[functions of random variables|function]] of [[continuous random variable]] with $g(X)=F_X(X)$
- $X$ is a [[continuous random variable]] with a [[CDF]] $F_X(x)$
- $Y$ is a [[functions of random variables|function of]] $X$ with the function being the [[CDF]] of $X$ $Y=F_X(X)$
how is $Y$ distributed? (with proof)
Back: 
$Y \sim U(0,1)$ has [[continous uniform distribution|uniform distribution]] and its [[CDF]] is $F_Y(y) = y$.
Proof
$$
\begin{split}
F_{Y}(y)&=P(Y \leq y) \\
&=P(F_X(X) \leq y) \\
&=P(X \leq F_X^{-1}(y)) \\
&= F_{X}(F_X^{-1}(y)) = y \\
\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1671614666445-->
END