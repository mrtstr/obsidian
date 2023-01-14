## Concept
- Defined for [[random variable]]
- Generalization of the weighted mean: mean of possible outcomes weighted by its probability
- defined for [[conditional distribution|conditional distributions]]: [[conditional expectation]] 

## definition
### [[expectation]] of a [[continuous random variable]] $X$ with a [[probability density function|PDF]] $f_X(x)$:
$\mathbb{E}[X]=\int\limits_\infty^\infty x f_X(x)dx$  

### [[expectation]] of a [[discrete random variable]] $X$:
$\mathbb{E}[X]=\sum\limits_{i=0}^\infty x_i p(x_i)$  

## Existance
The reason that the [[expectation]] fails to exist if both of the sums/integrals are
infinite is that, in such cases, the sums/integrals in are not well-defined. The sum of an infinite series whose positive and negative terms both add to infinity either fails to converge or can be made to converge to many different values by rearranging the terms in different orders.

### [[discrete random variable]]
The [[expectation]] of a [[discrete random variable]] $\mathbb{E}[X]$ exists if $\sum\limits_0^\infty x f_X(x) < \infty$ or $\sum\limits_\infty^0 x f_X(x) < \infty$. 
### [[continuous random variable]]
The [[expectation]] of a [[continuous random variable]] $\mathbb{E}[X]$ exists if $\int\limits_0^\infty x f_X(x)dx < \infty$ or $\int\limits_\infty^0 x f_X(x)dx < \infty$. 

## [[expectation]] of [[functions of random variables]]
### definition
$$
\mathbb{E}[g(X)]=\int\limits_{-\infty}^\infty g(x) \cdot f_X(x)dx
$$
$$
\mathbb{E}[g(X, Y)]=\int\limits_\infty^\infty \int\limits_\infty^\infty g(x,y) \cdot f_{XY}(x,y)dx dY
$$
### linear functions $g(X)$
If $g(X)$ is a [[linear function]] $\mathbb{E}\left[g(X)\right] = g\left(\mathbb{E}[X]\right)$
proof: see linearity of the [[expectation]]

## Properties
### linearity
$$\mathbb{E}[aX+b]=a\mathbb{E}[X]+b$$
$$
\begin{split}
\mathbb{E}[aX+b] &=\int\limits_{-\infty}^\infty (aX+b) \cdot f_X(x)dx \\
&=a\int\limits_{-\infty}^\infty X \cdot f_X(x)  + b \int\limits_{-\infty}^\infty f_X(x) dx \\
&= a\mathbb{E}[X] + b \\
\end{split}
$$
- 
- $X\geq Y \Leftrightarrow \mathbb{E}[X] \geq \mathbb{E}[Y]$ (monoton)
- $\mathbb{E}[\mathbb{E}[X]]=\mathbb{E}[X]$ because $\mathbb{E}[a]=a$

## examples
#### expected value of the product of two random variables $X$ and $Y$ with a [[joint distribution]] $f_{XY}(x,y)$
$\mathbb{E}[XY]=\int\limits_\infty^\infty \int\limits_\infty^\infty xyf_{XY}(x,y)dx dy = \mathbb{E}[X] \cdot\mathbb{E}[Y]-\mathbb{COV}[X,Y]$  
(with $\mathbb{COV}[X,Y]=0$ when $X$ and $Y$ [[independence|independent]])

### [[expectation]] of a [[random variable]] with a [[continous uniform distribution]]
$$
\begin{split}
X &\sim U(a,b) \\ \\
\mathbb{E}[X] &= \int\limits_\infty^\infty x \cdot f_X(x)dx \\ 
&= \int\limits_\infty^\infty x \cdot \frac{1}{b-a}dx \\
&= \frac{1}{b-a} \frac{1}{2} (b^2-a^2) \\
&= \frac{1}{b-a} \frac{1}{2} (b+a)(b-a) \\
&= \frac{(b+a)}{2} 
\end{split} 
$$
### [[expectation]] of the maximum and minumum of [[random variable]]
#### example
Suppose that a point is chosen at random on a stick of unit length and that the stick is broken into two pieces at that point. Find the expected value of the length of the longer piece.
$$
\begin{split}
X &\sim U(0,1) \\ \\
\mathbb{E}[max(X, 1-x)] &= \int\limits_0^\frac{1}{2} (1-x) dx + \int\limits_\frac{1}{2}^1 x dx \\ 
&= 2 \int\limits_0^\frac{1}{2} (1-x) dx \\
&= \frac{3}{4} 
\end{split} 
$$
# anki

START
Basic
[[linearity]] of the [[expectation]] with proof
Back: 
$$\mathbb{E}[aX+b]=a\mathbb{E}[X]+b$$
$$
\begin{split}
\mathbb{E}[aX+b] &=\int\limits_{-\infty}^\infty (aX+b) \cdot f_X(x)dx \\
&=a\int\limits_{-\infty}^\infty X \cdot f_X(x)  + b \int\limits_{-\infty}^\infty f_X(x) dx \\
&= a\mathbb{E}[X] + b \\
\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1673686885277-->
END



START
Basic
definition: [[expectation]]
- [[continuous random variable]]
- [[discrete random variable]]
Back: 
continuous:
$\mathbb{E}[X]=\int\limits_\infty^\infty x f_X(x)dx$ 
discrete:
$\mathbb{E}[X]=\sum\limits_{i=0}^\infty x_i p(x_i)$  
Tags: mathematics, statistics
<!--ID: 1661882015629-->
END

START
Basic
expected value of the product of two random variables $X$ and $Y$ with a joint distribution $f_{XY}(x,y)$
Back: 
$\mathbb{E}[XY]=\int\limits_\infty^\infty \int\limits_\infty^\infty xyf_{XY}(x,y)dx dy = \mathbb{E}[X] \cdot\mathbb{E}[Y]-\mathbb{COV}[X,Y]$  
(with $\mathbb{COV}[X,Y]=0$ when $X$ and $Y$ independent)
Tags: mathematics, statistics
<!--ID: 1661882015633-->
END

START
Basic
[[expectation]] of [[functions of random variables]] $\mathbb{E}[g(X)]$
- of a single [[random variable]]
- of a multiple [[random variable]]
- spectial case: linear function $g(.)$
Back: 
## [[expectation]] of [[functions of random variables]]
### definition
$$
\mathbb{E}[g(X)]=\int\limits_\infty^\infty g(x) \cdot f_X(x)dx
$$
$$
\mathbb{E}[g(X, Y)]=\int\limits_\infty^\infty \int\limits_\infty^\infty g(x,y) \cdot f_{XY}(x,y)dx dY
$$
### linear functions $g(X)$
If $g(X)$ is a [[linear function]] $\mathbb{E}[g(X)] = g(\mathbb{E}[X])$

proof:
$$
\begin{split}
g(X) &= aX+b \\ \\

\mathbb{E}[aX+b] &=\int\limits_{-\infty}^\infty (aX+b) \cdot f_X(x)dx \\
&=a\int\limits_{-\infty}^\infty X \cdot f_X(x)  + b \int\limits_{-\infty}^\infty f_X(x) dx \\
&= a\mathbb{E}[X] + b \\

\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1661882015635-->
END

START
Basic
expected value of the sum of two random variables
Back: 
$\mathbb{E}[aX+bY]=a\mathbb{E}[X]+b\mathbb{E}[Y]$  
Tags: mathematics, statistics
<!--ID: 1661882015637-->
END

START
Basic
existance of the [[expectation]]
-  [[discrete random variable]]
- [[continuous random variable]]
Back: 
## existance
The reason that the [[expectation]] fails to exist if both of the sums/integrals are
infinite is that, in such cases, the sums/integrals in are not well-defined. The sum of an infinite series whose positive and negative terms both add to infinity either fails to converge or can be made to converge to many different values by rearranging the terms in different orders.

### [[discrete random variable]]
The [[expectation]] of a [[discrete random variable]] $\mathbb{E}[X]$ exists if $\sum\limits_0^\infty x f_X(x) < \infty$ or $\sum\limits_\infty^0 x f_X(x) < \infty$. 
### [[continuous random variable]]
The [[expectation]] of a [[continuous random variable]] $\mathbb{E}[X]$ exists if $\int\limits_0^\infty x f_X(x)dx < \infty$ or $\int\limits_\infty^0 x f_X(x)dx < \infty$. 

Tags: mathematics, statistics
<!--ID: 1673686885283-->
END


START
Basic
### [[expectation]] of a [[random variable]] with a [[continous uniform distribution]]
Back: 

$$
\begin{split}
X &\sim U(a,b) \\ \\
\mathbb{E}[X] &= \int\limits_\infty^\infty x \cdot f_X(x)dx \\ 
&= \int\limits_\infty^\infty x \cdot \frac{1}{b-a}dx \\
&= \frac{1}{b-a} \frac{1}{2} (b^2-a^2) \\
&= \frac{1}{b-a} \frac{1}{2} (b+a)(b-a) \\
&= \frac{(b+a)}{2} 
\end{split} 
$$
Tags: mathematics, statistics
<!--ID: 1673686885286-->
END

START
Basic
Suppose that a point is chosen at random on a stick of unit length and that the stick is broken into two pieces at that point. Find the [[expectation]] of the length of the longer piece.
Back: 

$$
\begin{split}
X &\sim U(0,1) \\ \\
\mathbb{E}[max(X, 1-x)] &= \int\limits_0^\frac{1}{2} x dx + \int\limits_\frac{1}{2}^1 (1-x) dx \\ 
&= 2 \int\limits_0^\frac{1}{2} (1-x) dx \\
&= \frac{3}{4} 
\end{split} 
$$

Tags: mathematics, statistics
<!--ID: 1673686885291-->
END

