## Definition
- derived from 
- the [[conditional distribution]] can be interpreted as a [[joint distribution]] with one value fixed that is normalized to be a [[probability density function|PDF]] again
$$
f_{X\mid Y}(x \mid y)=\frac{f_{XY}(x,y)}{f_Y(y)}
$$

![[Screenshot from 2022-12-16 10-00-52.jpg]]


![[multiplication rule#multiplication rule for continuous PDF]]

![[law of total probability#law of total probability for a continuous random variable]]

![[stochastic independent#conditional distribution of independent random variable random variables]]

## $f_{X\mid Y}(x \mid y)$ is a [[probability density function|PDF]]
Proof:
$$
\int\limits^{\infty}_{-\infty} f_{X\mid Y}(x \mid y) dx
=\frac{\int\limits^{\infty}_{-\infty}f_{XY}(x,y) dx}{f_Y(y)}
=\frac{f_{Y}(y)}{f_Y(y)}
= 1
$$
# Anki
START
Basic
[[conditional distribution|conditional PDF]] $f_{X\mid Y=y}(x)$
- definition
- interpretation
Back: 
- the [[conditional distribution]] can be interpreted as a [[joint distribution]] with one value fixed that is normalized to be a [[probability density function|PDF]] again
$$
f_{X\mid Y}(x \mid y)=\frac{f_{XY}(x,y)}{f_Y(y)}
$$
$$
f_{X\mid Y}(x \mid y) \cdot f_Y(y)=f_{XY}(x,y)
$$

Tags: mathematics, statistics
<!--ID: 1664619948156-->
END





START
Basic
proof that $f_{X\mid Y}(x \mid y)$ is a [[probability density function|PDF]]
Back: 
$$
\int\limits^{\infty}_{-\infty} f_{X\mid Y}(x \mid y) dx
=\frac{\int\limits^{\infty}_{-\infty}f_{XY}(x,y) dx}{f_Y(y)}
=\frac{f_{Y}(y)}{f_Y(y)}
= 1
$$
Tags: mathematics, statistics
<!--ID: 1671186732891-->
END