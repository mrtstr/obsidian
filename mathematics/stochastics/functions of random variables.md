[[function|functions]] of [[random variable|random variables]]


## [[discrete random variable|discrete case]] with an arbitrary [[function]]
- $X$ is a [[discrete random variable]] with a [[probability function]] $f_X(x)$
- $Y=g(X)$ with an arbitrary [[function]] $g$
$$
f_{Y}(y)=P(Y=y)=P(r(X)=y)=\sum\limits_{x_i \in \{x \mid g(x)=y \}} f_X(x_i)
$$

## [[continuous random variable]]


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
- [[probability function]] of the transformed [[random variable]]
Back: 
 $X$ is a [[discrete random variable]] with a [[probability function]] $f_X(x)$
- $Y=g(X)$ with an arbitrary [[function]] $g$
$$
f_{Y}(y)=P(Y=y)=P(r(X)=y)=\sum\limits_{x_i \in \{x \mid g(x)=y \}} f_X(x_i)
$$

Tags: mathematics, statistics
<!--ID: 1671275212198-->
END

START
Basic
functions of random variables: [[continuous random variable]] with a [[linear function]]
- [[PDF]] of the transformed [[random variable]]
Back: 
- $X$ is a [[continuous random variable]] with a [[PDF]] $f_X(x)$
- $Y=g(X)=aX=b$ with an [[linear function]] $g$
$$
f_Y(y)=\underbrace{\frac{1}{|a|}}_\text{normalization} f_{X}
\underbrace{
\left(\frac{y-b}{a}\right)
}_{g^{-1}(y)}
$$
Tags: mathematics, statistics
<!--ID: 1671275212205-->
END