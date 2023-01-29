
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
\mathbb{E}\left[Y g(X) | X\right]  = g(X) \mathbb{E}\left[Y | X\right]
$$
#### proof
- concider the [[function]] $r(x) = \mathbb{E}\left[Y g(X) | X = x\right] = \mathbb{E}\left[Y g(x) | X = x\right]  = g(x) \mathbb{E}\left[Y | X = x\right]$
- given $X=x$ $g(x)$ is a constant and thus can be taken out of the [[expectation]]
- now lets concider the function $r(.)$ of a [[random variable]] $X$ 
- $r(X)= \mathbb{E}\left[Y g(X) | X\right] = g(X) \mathbb{E}\left[Y | X\right]$

### simplified case
$$
\mathbb{E}\left[g(X) | X\right]  = g(X)
$$
#### proof
- concider the function $r(x)=\mathbb{E}\left[g(X) | X=x\right] = \mathbb{E}\left[g(x)\right]=g(x)$
- given $X=x$ $g(x)$ is a constant
- now lets concider the function $r(.)$ of a [[random variable]] $X$ 
- $r(X)=g(X)=\mathbb{E}\left[g(X) | X\right]$

## [[conditional expectation]] given a [[random variable]] and a [[function]] of the [[random variable]] 
$$
\mathbb{E}\left[Y  | X , g(X) \right]  = \mathbb{E}\left[Y | X\right]
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

# anki

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

Tags: mathematics, statistics
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
Tags: mathematics, statistics
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
Tags: mathematics, statistics
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
Tags: mathematics, statistics
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
Tags: mathematics, statistics
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
Tags: mathematics, statistics
<!--ID: 1674983478647-->
END