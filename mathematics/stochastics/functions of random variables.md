[[function|functions]] of [[random variable|random variables]]


## [[discrete random variable|discrete case]] with an arbitrary [[function]]
- $X$ is a [[discrete random variable]] with a [[probability function]] $f_X(x)$
- $Y=g(X)$ with an arbitrary [[function]] $g$
$$
f_{Y}(y)=P(Y=y)=P(g(X)=y)=\sum\limits_{x_i \in \{x \mid g(x)=y \}} f_X(x_i)
$$
$$
F_{Y}(y)=P(Y \leq y)=P(g(X) \leq y)=\sum\limits_{x_i \in \{x \mid g(x) \leq y \}} f_X(x_i)
$$

## [[continuous random variable]]
- $X$ is a [[continuous random variable]] with a [[PDF]] $f_X(x)$
- $Y=g(X)$ with an arbitrary [[function]] $g$
$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) \\
&=\int\limits_{\{x \mid g(x) \leq y \}} f_X(x) \: dx \\
f_{Y}(y) &= \frac{dF_{Y}(y)}{y}
\end{split}
$$
#### example
- $X \sim U(-1,1)$ is from a [[continous uniform distribution]] with a [[PDF]] 
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
### [[continuous random variable]] with a [[linear function]]
- $X$ is a [[continuous random variable]] with a [[PDF]] $f_X(x)$
- $Y=g(X)=aX=b$ with an [[linear function]] $g$
$$
f_Y(y)=\underbrace{\frac{1}{|a|}}_\text{normalization} f_{X}
\underbrace{
\left(\frac{y-b}{a}\right)
}_{g^{-1}(y)}
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
- $X$ is a [[continuous random variable]] with a [[PDF]] $f_X(x)$
- $Y=g(X)=aX=b$ with an [[linear function]] $g$
- [[PDF]] of the transformed [[random variable]] $f_Y(y)$
Back: 

$$
f_Y(y)=\underbrace{\frac{1}{|a|}}_\text{normalization} f_{X}
\underbrace{
\left(\frac{y-b}{a}\right)
}_{g^{-1}(y)}
$$
Tags: mathematics, statistics
<!--ID: 1671275212205-->
END


START
Basic
[[functions of random variables]]: 
- [[continuous random variable]] with an arbitrary [[function]]
- $X$ is a [[continuous random variable]] with a [[PDF]] $f_X(x)$
- $Y=g(X)$ with an arbitrary [[function]] $g$

general equations:
- [[CDF]] of the transformed [[random variable]] $F_Y(y)$
- [[PDF]] of the transformed [[random variable]] $f_Y(y)$
Back: 
$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) \\
&=\int\limits_{\{x \mid g(x) \leq y \}} f_X(x) \: dx \\
f_{Y}(y) &= \frac{dF_{Y}(y)}{y}
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1671360434130-->
END


START
Basic
[[functions of random variables]] example:  
- $X \sim U(-1,1)$ is from a [[continous uniform distribution]] with a [[PDF]] 
$$f_X(x)=\begin{cases}
    \frac{1}{2},& \text{if } x \in [-1,1] \\
    0,              & \text{otherwise}
\end{cases}
$$
- $Y=g(X)=X^2$


- [[CDF]] of the transformed [[random variable]] $F_Y(y)$
- [[PDF]] of the transformed [[random variable]] $f_Y(y)$
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