
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
## linearity
$$
\mathbb{E}\left[aY_1 + bY_2 + c \: | \: X\right] = a \mathbb{E}\left[Y_1 \: | \: X\right] + b \mathbb{E}\left[Y_2  \: | \: X\right] + c
$$
### proof
$$
\begin{split}
\mathbb{E}\left[aY_1 + bY_2 + c \: | \: X\right]
& =  
\int\limits_{-\infty}^\infty \int\limits_{-\infty}^\infty \left(ay_2+by_2+c\right)  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_1dy_2 \\
& =  
a\int\limits_{-\infty}^\infty  y_1 \int\limits_{-\infty}^\infty  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_2dy_1 \\
& \quad +  
b\int\limits_{-\infty}^\infty  y_2 \int\limits_{-\infty}^\infty  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_1dy_2 \\
& \quad +  
c\int\limits_{-\infty}^\infty  \int\limits_{-\infty}^\infty  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_1dy_2 \\
& =  
a\int\limits_{-\infty}^\infty  y_1  f_{Y_1|X}(y_1 \mid x)dy_1 \\
& \quad + 
b\int\limits_{-\infty}^\infty  y_2  f_{Y_2|X}(y_2 \mid x)dy_2 \\
& \quad + 
c \\
&= a \mathbb{E}\left[Y_1 \: | \: X\right] + b \mathbb{E}\left[Y_2  \: | \: X\right] + c
\end{split}
$$
## [[stochastic independent]] [[random variable|random variables]]
$$
Y \perp X \Rightarrow  \mathbb{E}\left[Y|X\right] =\mathbb{E}\left[Y\right]
$$
### proof
$$
\begin{split}
\mathbb{E}\left[Y|X\right]  
& = \int\limits_{-\infty}^\infty y  f_{Y|X}(y \mid x)dy  \\
& = \int\limits_{-\infty}^\infty y \frac{f_{Y}(y)f_{X}(x)}{f_{X}(x)} f_{Y|X}(y \mid x)dy  \\
& = \int\limits_{-\infty}^\infty y  f_{Y}(y)dy  \\
& = \mathbb{E}\left[Y\right]
\end{split}
$$
## [[conditional expectation]] of a [[function]] of a given [[random variable]] 
$$
\mathbb{E}\left[g(X, Y) | X = x\right]  = \mathbb{E}\left[g(x, Y) | X = x\right] = \int\limits_{-\infty}^{\infty} g(x,y) f_{Y|x}(y|x)dy = r(x)
$$

### implications
#### $\mathbb{E}\left[Y g(X) | X\right]  = g(X) \mathbb{E}\left[Y | X\right]$

- concider the [[function]] $r(x) = \mathbb{E}\left[Y g(X) | X = x\right] = \mathbb{E}\left[Y g(x) | X = x\right]  = g(x) \mathbb{E}\left[Y | X = x\right]$
- given $X=x$ $g(x)$ is a constant and thus can be taken out of the [[expectation]]
- now lets concider the function $r(.)$ of a [[random variable]] $X$ 
- $r(X)= \mathbb{E}\left[Y g(X) | X\right] = g(X) \mathbb{E}\left[Y | X\right]$

#### $\mathbb{E}\left[g(X) | X\right]  = g(X)$
- concider the function $r(x)=\mathbb{E}\left[g(X) | X=x\right] = \mathbb{E}\left[g(x)\right]=g(x)$
- given $X=x$ $g(x)$ is a constant
- now lets concider the function $r(.)$ of a [[random variable]] $X$ 
- $r(X)=g(X)=\mathbb{E}\left[g(X) | X\right]$

## [[conditional expectation]] given a [[random variable]] and a [[function]] of the [[random variable]] 
$$
\mathbb{E}\left[Y  | X , g(X) \right]  = \mathbb{E}\left[Y | X\right]
$$

## [[law of total probability]] for [[expectation|expectations]]
### [[law of total probability]] for [[expectation|expectations]] general case
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


### example
$$
\mathbb{E}[XY]  = \mathbb{E}\left[X\mathbb{E}[Y|X]\right]
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[X\mathbb{E}[Y|X]\right] 
& =\int\limits_{-\infty}^\infty x f_{X}(x) 
\int\limits_{-\infty}^\infty  f_{Y|X}(y|x)dy 
\:dx \\
& = \int\limits_{-\infty}^\infty   \int\limits_{-\infty}^\infty    xyf_{YX}(y, x)dx \:dy \\
& = \mathbb{E}\left[XY\right]
\end{split}
$$


# Examples
## proof for $\mathbb{E}\left[Y|X\right]=c \Rightarrow \mathbb{COV}\left[X,Y\right]=0$
$$
\begin{split}
\mathbb{E}\left[YX\right] 
& = \mathbb{E}\left[\mathbb{E}[XY|X]\right] \\
& = \mathbb{E}\left[X\mathbb{E}[Y|X]\right] \\
& = \mathbb{E}\left[X\right]\mathbb{E}\left[Y\right] \\
 \\
\mathbb{COV}\left[X,Y\right]
& = \mathbb{E}\left[YX\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right] \\
& = \mathbb{E}\left[YX\right]-\mathbb{E}\left[YX\right] =0 \\
\end{split}
$$
## [[joint distribution]] to [[conditional expectation]] and [[conditional variance]]
$$
f_{XY}(x,y)=
\begin{cases}
x+y
,& \text{if } x, y \in [a,b]\\
0
,& \text{otherwise}
\end{cases}
$$
$$
f_{X}(x)=
\begin{cases}
x+\frac{1}{2}
,& \text{if } x \in [0,1]\\
0
,& \text{otherwise}
\end{cases}
$$
$$ f_{Y|X=x}(y,x)=\frac{f_{XY}(x,y)}{f_{X}(x)}  $$
$$
\begin{split}
\mathbb{E}\left[Y|X=x\right] 
& = \frac{3x+2}{3(2x+1)} \\
 \\
\mathbb{E}\left[Y^2|X=x\right] 
& = \frac{4x+3}{6(2x+1)} \\
 \\
\mathbb{VAR}\left[Y^2|X=x\right] 
& = \frac{4x+3}{6(2x+1)} - \frac{3x+2}{3(2x+1)}^2 \\
\end{split}
$$

### [[mean square error]] optimization given $X=\frac{1}{2}$
$$
\begin{split}
\mathbb{E}\left[Y|X=\frac{1}{2}\right] 
& = \frac{3x+2}{3(2x+1)} = \frac{7}{12} \\
 \\
\mathbb{VAR}\left[Y|X=\frac{1}{2}\right] 
& = \frac{4x+3}{6(2x+1)} - \frac{3x+2}{3(2x+1)}^2 = \frac{11}{144} \\
\end{split}
$$
### general [[mean square error]] if $X$ is observed
$$
\begin{split}
\mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
&= \int\limits_0^1 f_{X}(x) \mathbb{VAR}\left[Y|X=x\right] dx \\
&= \int\limits_0^1 \left(x+\frac{1}{2}\right) \left(\frac{4x+3}{6(2x+1)} - \frac{3x+2}{3(2x+1)}^2 \right) dx
\end{split}
$$
## simple [[generalized linear models]]
$$\mathbb{E}\left[Y|X\right] = aX+b$$

$$
\begin{split}
\mathbb{E}\left[Y\right] 
& = \mathbb{E}\left[\mathbb{E}[Y|X]\right] \\
& = \mathbb{E}\left[\mathbb{E}[aX+b|X]\right] \\
& = \mathbb{E}\left[aX + b\right] \\
& = a\mathbb{E}\left[X\right] + b \\
\rightarrow b &= \mathbb{E}\left[Y\right] - a\mathbb{E}\left[X\right] \\
 \\
\mathbb{E}\left[XY\right] 
& = \mathbb{E}\left[X(aX+b)\right] \\
& = a\mathbb{E}\left[X^2\right] + b \mathbb{E}\left[X\right] \\
& = a\mathbb{E}\left[X^2\right] + \left(\mathbb{E}\left[Y\right] - a\mathbb{E}\left[X\right]\right) \mathbb{E}\left[X\right] \\
& = a\mathbb{E}\left[X^2\right] - a\mathbb{E}\left[X\right]^2  + \mathbb{E}\left[Y\right]\mathbb{E}\left[X\right]  \\
& = a\mathbb{VAR}\left[X\right]   + \mathbb{E}\left[Y\right]\mathbb{E}\left[X\right]  \\
\rightarrow a &= \frac{\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]}{\mathbb{VAR}\left[X\right]} \\
&= \frac{\mathbb{COV}\left[X,Y\right]}{\mathbb{VAR}\left[X\right]} \\
\rightarrow b &= \mathbb{E}\left[Y\right] - \frac{\mathbb{COV}\left[X,Y\right]}{\mathbb{VAR}\left[X\right]}\mathbb{E}\left[X\right] \\
\end{split}
$$
# anki

START
Basic
describe $a$ and $b$ depending on $\mathbb{E}\left[X\right]$, $\mathbb{E}\left[Y\right]$,  $\mathbb{VAR}\left[X\right]$, $\mathbb{VAR}\left[Y\right]$ and $\mathbb{COVAR}\left[X, Y\right]$
$$\mathbb{E}\left[Y|X\right] = aX+b$$
Back: 
$$
\begin{split}
\mathbb{E}\left[Y\right] 
& = \mathbb{E}\left[\mathbb{E}[Y|X]\right] \\
& = \mathbb{E}\left[\mathbb{E}[aX+b|X]\right] \\
& = \mathbb{E}\left[aX + b\right] \\
& = a\mathbb{E}\left[X\right] + b \\
\rightarrow b &= \mathbb{E}\left[Y\right] - a\mathbb{E}\left[X\right] \\
 \\
\mathbb{E}\left[XY\right] 
& = \mathbb{E}\left[X(aX+b)\right] \\
& = a\mathbb{E}\left[X^2\right] + b \mathbb{E}\left[X\right] \\
& = a\mathbb{E}\left[X^2\right] + \left(\mathbb{E}\left[Y\right] - a\mathbb{E}\left[X\right]\right) \mathbb{E}\left[X\right] \\
& = a\mathbb{E}\left[X^2\right] - a\mathbb{E}\left[X\right]^2  + \mathbb{E}\left[Y\right]\mathbb{E}\left[X\right]  \\
& = a\mathbb{VAR}\left[X\right]   + \mathbb{E}\left[Y\right]\mathbb{E}\left[X\right]  \\
\rightarrow a &= \frac{\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]}{\mathbb{VAR}\left[X\right]} \\
&= \frac{\mathbb{COV}\left[X,Y\right]}{\mathbb{VAR}\left[X\right]} \\
\rightarrow b &= \mathbb{E}\left[Y\right] - \frac{\mathbb{COV}\left[X,Y\right]}{\mathbb{VAR}\left[X\right]}\mathbb{E}\left[X\right] \\
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1675329130225-->
END


START
Basic
[[joint distribution]] to [[conditional expectation]] and [[conditional variance]]

$$
f_{XY}(x,y)=
\begin{cases}
x+y
,& \text{if } x, y \in [0,1]\\
0
,& \text{otherwise}
\end{cases}
$$

- $\mathbb{E}\left[Y|X=x\right]$
- $\mathbb{VAR}\left[Y|X=x\right]$
If it is observed that $X = \frac{1}{2}$
- what predicted value of Y will have the smallest [[mean square error]]?
- What will be the value of this [[mean square error]]?
- General [[mean square error]] if $X$ is observed (integral only)
- how much is the observation of $X$ worth for predicting $Y$ (equation only)
Back: 
$$
f_{X}(x)=
\begin{cases}
x+\frac{1}{2}
,& \text{if } x \in [0,1]\\
0
,& \text{otherwise}
\end{cases}
$$
$$ f_{Y|X=x}(y,x)=\frac{f_{XY}(x,y)}{f_{X}(x)}  $$
$$
\begin{split}
\mathbb{E}\left[Y|X=x\right] 
& = \frac{3x+2}{3(2x+1)} \\
 \\
\mathbb{E}\left[Y^2|X=x\right] 
& = \frac{4x+3}{6(2x+1)} \\
 \\
\mathbb{VAR}\left[Y^2|X=x\right] 
& = \frac{4x+3}{6(2x+1)} - \frac{3x+2}{3(2x+1)}^2 \\
\end{split}
$$
### [[mean square error]] optimization given $X=\frac{1}{2}$
$$
\begin{split}
\mathbb{E}\left[Y|X=\frac{1}{2}\right] 
& = \frac{3x+2}{3(2x+1)} = \frac{7}{12} \\
 \\
\mathbb{VAR}\left[Y|X=\frac{1}{2}\right] 
& = \frac{4x+3}{6(2x+1)} - \frac{3x+2}{3(2x+1)}^2 = \frac{11}{144} \\
\end{split}
$$
### general [[mean square error]] if $X$ is observed
$$
\begin{split}
\mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]
&= \int\limits_0^1 f_{X}(x) \mathbb{VAR}\left[Y|X=x\right] dx \\
&= \int\limits_0^1 \left(x+\frac{1}{2}\right) \left(\frac{4x+3}{6(2x+1)} - \frac{3x+2}{3(2x+1)}^2 \right) dx
\end{split}
$$
### [[mean square error]] improvement because of the obseration of $X$
$$

\mathbb{VAR}_{Y}\left[Y \right] - \mathbb{E}\left[\mathbb{VAR}_{Y|X}\left[Y\:|\:X \right]\right]

$$
Tags: mathematics statistics
<!--ID: 1675329130228-->
END

START
Basic
proof for $\mathbb{E}\left[Y|X\right]=c \Rightarrow \mathbb{COV}\left[X,Y\right]=0$
Back: 
$$
\begin{split}
\mathbb{E}\left[YX\right] 
& = \mathbb{E}\left[\mathbb{E}[XY|X]\right] \\
& = \mathbb{E}\left[X\mathbb{E}[Y|X]\right] \\
& = \mathbb{E}\left[X\right]\mathbb{E}\left[Y\right] \\
 \\
\mathbb{COV}\left[X,Y\right]
& = \mathbb{E}\left[YX\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right] \\
& = \mathbb{E}\left[YX\right]-\mathbb{E}\left[YX\right] =0 \\
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1675329130232-->
END



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

Tags: mathematics statistics
<!--ID: 1661928261922-->
END


START
Basic
[[conditional expectation]]
- Definition
- Existance
- [[conditional expectation]] and [[statistical predictor]]
Back: 
### Definition
- the [[conditional expectation]] $\mathbb{E}[Y|x]$ of a [[random variable]] $Y$ given $X$ can is a [[function]] of $x$ 
- thus $\mathbb{E}[Y|c]$ with the constant $c$ is a constant itself
- [[expectation]] for [[conditional distribution|conditional distributions]]
$$
g(x) =\mathbb{E}[Y|x]=\int\limits_{-\infty}^\infty y f_{Y|X}(y|x)dy = \frac{1}{f_{X}(x)} \int\limits_{-\infty}^\infty y f_{YX}(y,x)dy 
$$
- $g(X)=\mathbb{E}[Y|X]$ is a [[functions of random variables]] and thus is a [[random variable]] itself

### Existance
- the [[conditional expectation]] is only defined for $f_{X}(x) \neq 0$ 

### [[conditional expectation]] and [[statistical predictor]]
- the [[function]] $g(x) =\mathbb{E}[Y|x]$ can be interpreted as a [[statistical predictor]] that predicts a [[random variable]] $Y$ given an observed depandent [[random variable]] $X$
- the [[conditional expectation]] $\mathbb{E}[Y|x]$ optimizes the [[mean square error]] loss 

Tags: mathematics statistics
<!--ID: 1674983478630-->
END


START
Basic
[[conditional expectation]]: properties (no proof)
- linearity
- of [[stochastic independent]] [[random variable]]
- [[conditional expectation]] of a [[function]] of a given [[random variable]] 
- [[law of total probability]] for [[expectation|expectations]]
Back: 
# properties
## linearity
$$
\mathbb{E}\left[aY_1 + bY_2 + c \: | \: X\right] = a \mathbb{E}\left[Y_1 \: | \: X\right] + b \mathbb{E}\left[Y_2  \: | \: X\right] + c
$$
### proof
$$
\begin{split}
\mathbb{E}\left[aY_1 + bY_2 + c \: | \: X\right]
& =  
\int\limits_{-\infty}^\infty \int\limits_{-\infty}^\infty \left(ay_2+by_2+c\right)  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_1dy_2 \\
& =  
a\int\limits_{-\infty}^\infty  y_1 \int\limits_{-\infty}^\infty  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_2dy_1 \\
& \quad +  
b\int\limits_{-\infty}^\infty  y_2 \int\limits_{-\infty}^\infty  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_1dy_2 \\
& \quad +  
c\int\limits_{-\infty}^\infty  \int\limits_{-\infty}^\infty  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_1dy_2 \\
& =  
a\int\limits_{-\infty}^\infty  y_1  f_{Y_1|X}(y_1 \mid x)dy_1 \\
& \quad + 
b\int\limits_{-\infty}^\infty  y_2  f_{Y_2|X}(y_2 \mid x)dy_2 \\
& \quad + 
c \\
&= a \mathbb{E}\left[Y_1 \: | \: X\right] + b \mathbb{E}\left[Y_2  \: | \: X\right] + c
\end{split}
$$
## [[stochastic independent]] [[random variable|random variables]]
$$
Y \perp X \Rightarrow  \mathbb{E}\left[Y|X\right] =\mathbb{E}\left[Y\right]
$$
### proof
$$
\begin{split}
\mathbb{E}\left[Y|X\right]  
& = \int\limits_{-\infty}^\infty y  f_{Y|X}(y \mid x)dy  \\
& = \int\limits_{-\infty}^\infty y \frac{f_{Y}(y)f_{X}(x)}{f_{X}(x)} f_{Y|X}(y \mid x)dy  \\
& = \int\limits_{-\infty}^\infty y  f_{Y}(y)dy  \\
& = \mathbb{E}\left[Y\right]
\end{split}
$$
## [[conditional expectation]] of a [[function]] of a given [[random variable]] 
$$
\mathbb{E}\left[g(X, Y) | X = x\right]  = \mathbb{E}\left[g(x, Y) | X = x\right] = \int\limits_{-\infty}^{\infty} g(x,y) f_{Y|x}(y|x)dy = r(x)
$$
### implications

$$
\mathbb{E}\left[Y g(X) | X\right]  = g(X) \mathbb{E}\left[Y | X\right]
$$
#### proof
- concider the [[function]] $r(x) = \mathbb{E}\left[Y g(X) | X = x\right] = \mathbb{E}\left[Y g(x) | X = x\right]  = g(x) \mathbb{E}\left[Y | X = x\right]$
- given $X=x$ $g(x)$ is a constant and thus can be taken out of the [[expectation]]
- now lets concider the function $r(.)$ of a [[random variable]] $X$ 
- $r(X)= \mathbb{E}\left[Y g(X) | X\right] = g(X) \mathbb{E}\left[Y | X\right]$

(simplified case: $\mathbb{E}\left[g(X) | X\right]  = g(X)$)


## [[law of total probability]] for [[expectation|expectations]]

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
(simple calse: $\mathbb{E}[Y]  = \mathbb{E}\left[\mathbb{E}[Y|X]\right]$)
Tags: mathematics statistics
<!--ID: 1674983478636-->
END


START
Basic
[[conditional expectation]]: proof for [[law of total probability]] for [[expectation|expectations]]
$$
\mathbb{E}\left[g(X,Y)\right]  = \mathbb{E}\left[\mathbb{E}\left[g(X,Y)|X\right]\right]
$$
Back: 

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
(simple calse: $\mathbb{E}[Y]  = \mathbb{E}\left[\mathbb{E}[Y|X]\right]$)
Tags: mathematics statistics
<!--ID: 1674983478639-->
END


START
Basic
[[conditional expectation]] of a [[function]] of a given [[random variable]] (proof): 
$$
\mathbb{E}\left[Y g(X) | X\right]  = g(X) \mathbb{E}\left[Y | X\right]
$$

Back: 
- concider the [[function]] $r(x) = \mathbb{E}\left[Y g(X) | X = x\right] = \mathbb{E}\left[Y g(x) | X = x\right]  = g(x) \mathbb{E}\left[Y | X = x\right]$
- given $X=x$ $g(x)$ is a constant and thus can be taken out of the [[expectation]]
- now lets concider the function $r(.)$ of a [[random variable]] $X$ 
- $r(X)= \mathbb{E}\left[Y g(X) | X\right] = g(X) \mathbb{E}\left[Y | X\right]$

(simplified case: $\mathbb{E}\left[g(X) | X\right]  = g(X)$)
Tags: mathematics statistics
<!--ID: 1674983478641-->
END


START
Basic
[[conditional expectation]]: [[stochastic independent]] [[random variable|random variables]] (proof)
$$
Y \perp X \Rightarrow  \mathbb{E}\left[Y|X\right] =\mathbb{E}\left[Y\right]
$$
Back: 
$$
\begin{split}
\mathbb{E}\left[Y|X\right]  
& = \int\limits_{-\infty}^\infty y  f_{Y|X}(y \mid x)dy  \\
& = \int\limits_{-\infty}^\infty y \frac{f_{Y}(y)f_{X}(x)}{f_{X}(x)} f_{Y|X}(y \mid x)dy  \\
& = \int\limits_{-\infty}^\infty y  f_{Y}(y)dy  \\
& = \mathbb{E}\left[Y\right]
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1674983478644-->
END


START
Basic
linearity of the [[conditional expectation]] (proof)
$$
\mathbb{E}\left[aY_1 + bY_2 + c \: | \: X\right] = a \mathbb{E}\left[Y_1 \: | \: X\right] + b \mathbb{E}\left[Y_2  \: | \: X\right] + c
$$
Back: 
$$
\begin{split}
\mathbb{E}\left[aY_1 + bY_2 + c \: | \: X\right]
& =  
\int\limits_{-\infty}^\infty \int\limits_{-\infty}^\infty \left(ay_2+by_2+c\right)  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_1dy_2 \\
& =  
a\int\limits_{-\infty}^\infty  y_1 \int\limits_{-\infty}^\infty  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_2dy_1 \\
& \quad +  
b\int\limits_{-\infty}^\infty  y_2 \int\limits_{-\infty}^\infty  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_1dy_2 \\
& \quad +  
c\int\limits_{-\infty}^\infty  \int\limits_{-\infty}^\infty  f_{Y_1Y_2|X}(y_1, y_2 \mid x)dy_1dy_2 \\
& =  
a\int\limits_{-\infty}^\infty  y_1  f_{Y_1|X}(y_1 \mid x)dy_1 \\
& \quad + 
b\int\limits_{-\infty}^\infty  y_2  f_{Y_2|X}(y_2 \mid x)dy_2 \\
& \quad + 
c \\
&= a \mathbb{E}\left[Y_1 \: | \: X\right] + b \mathbb{E}\left[Y_2  \: | \: X\right] + c
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1674983478647-->
END



START
Basic
[[conditional expectation]] of a [[function]] of a given [[random variable]] (proof): 
$$
\mathbb{E}\left[g(X, Y) | X = x\right]
$$

Back: 
$$
\mathbb{E}\left[g(X, Y) | X = x\right]  = \mathbb{E}\left[g(x, Y) | X = x\right] = \int\limits_{-\infty}^{\infty} g(x,y) f_{Y|x}(y|x)dy = r(x)
$$

### implications
#### $\mathbb{E}\left[Y g(X) | X\right]  = g(X) \mathbb{E}\left[Y | X\right]$

- concider the [[function]] $r(x) = \mathbb{E}\left[Y g(X) | X = x\right] = \mathbb{E}\left[Y g(x) | X = x\right]  = g(x) \mathbb{E}\left[Y | X = x\right]$
- given $X=x$ $g(x)$ is a constant and thus can be taken out of the [[expectation]]
- now lets concider the function $r(.)$ of a [[random variable]] $X$ 
- $r(X)= \mathbb{E}\left[Y g(X) | X\right] = g(X) \mathbb{E}\left[Y | X\right]$

#### $\mathbb{E}\left[g(X) | X\right]  = g(X)$
- concider the function $r(x)=\mathbb{E}\left[g(X) | X=x\right] = \mathbb{E}\left[g(x)\right]=g(x)$
- given $X=x$ $g(x)$ is a constant
- now lets concider the function $r(.)$ of a [[random variable]] $X$ 
- $r(X)=g(X)=\mathbb{E}\left[g(X) | X\right]$

Tags: mathematics statistics
<!--ID: 1674984828829-->
END


START
Basic
proof for:
$$
\mathbb{E}[XY]  = \mathbb{E}\left[X\mathbb{E}[Y|X]\right]
$$
Back: 
$$
\begin{split}
\mathbb{E}\left[X\mathbb{E}[Y|X]\right] 
& =\int\limits_{-\infty}^\infty x f_{X}(x) 
\int\limits_{-\infty}^\infty  f_{Y|X}(y|x)dy 
\:dx \\
& = \int\limits_{-\infty}^\infty   \int\limits_{-\infty}^\infty    xyf_{YX}(y, x)dx \:dy \\
& = \mathbb{E}\left[XY\right]
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1677320005316-->
END