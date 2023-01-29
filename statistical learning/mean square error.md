# [[mean square error]]
[[loss functions]]

## Definition
For a [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, \widehat{x})=\mathbb{E}\left[(X-\widehat{x})^2\right]
$$

For a [[statistical predictor|statistical prediction]] of the [[random variable]] $Y$ given a dependent [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, f(x))=\mathbb{E}\left[(X-f(x))^2\right]
$$
$L(Y, f(x))=E[(Y-f(x))^2] \rightarrow f(x)=E[Y|X=x]$  

## minimum 

### [[statistical estimator|statistical estimaton]] $\widehat{x}$
The [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ that is minimizing the [[mean square error]] is the [[expectation]] $\widehat{x}_{MSE}=\mathbb{E}[X]$.
Proof
$$
\begin{split}
\mathbb{E}\left[(X-\widehat{x})^2\right] &= \mathbb{E}\left[X^2\right] + \widehat{x}^2 + 2\widehat{x}\mathbb{E}\left[X\right] \\
\frac{d\mathbb{E}\left[X^2\right] + \widehat{x}^2 + 2\widehat{x}\mathbb{E}\left[X\right]}{d\widehat{x}} &= 2\widehat{x}-2\mathbb{E}\left[X\right] = 0 \\
\rightarrow argmin \: \mathbb{E}\left[(X-\widehat{x})^2\right] &= \widehat{x}_{MSE}=\mathbb{E}[X]
\end{split}
$$


The [[mean square error]] of $\widehat{x}_{MSE}$ the [[variance]] $L_{MSE}(X, \widehat{x}_{MSE})=\mathbb{VAR}\left[X\right]$.
$$
L_{MSE}(X, \widehat{x}_{MSE})=\mathbb{E}\left[(X-\widehat{x}_{MSE})^2\right] = \mathbb{E}\left[(X-\mathbb{E}[X])^2\right] = \mathbb{VAR}\left[X\right]
$$
### [[statistical predictor]] $f(x)$
The [[statistical predictor]] $f(x)$ that is minimizing the [[mean square error]] is the [[conditional expectation]] $f_{MSE}(x)=\mathbb{E}[Y\:|\:X=x]$

#### proof
- from the [[law of total probability]] we know that $\mathbb{E}[(Y-f(X))^2] =\mathbb{E}\left[\mathbb{E}\left[(Y-f(X))^2 | X \right] \right]$
![[conditional expectation#law of total probability for expectation expectations general case]]
- for an observed $x_0$ $\mathbb{E}\left[\mathbb{E}\left[(Y-f(x_0))^2 | X=x_0 \right] \right] = \mathbb{E}\left[(Y-f(x_0))^2 | X=x_0 \right]$ since its a constant
- if we can prove for every $x$ that $f(x)=argmin_c \:\mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]=\mathbb{E}[Y\:|\:X=x]$ its clear that $f(X)=\mathbb{E}[Y\:|\:X]$ is also true
$$
\begin{split}
\frac{d \mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]}{dc} &= 0 \\
&=\frac{d \mathbb{E}_{Y|X=x}[Y^2\:|\:X=x]+c^2-2\mathbb{E}_{Y|X=x}[Y\:|\:X=x]c}{dc}  \\
&= 2x-2\mathbb{E}_{Y|X=x}[Y\:|\:X=x] \\
\rightarrow c&=\mathbb{E}_{Y|X=x}[Y\:|\:X=x] = f(x) 
\end{split}
$$
- for every constant $X=x_0$ the [[mean square error]] for an optimal [[statistical predictor]] $f(x) = \mathbb{E}_{Y|X=x}[Y\:|\:X=x]$ is equal to the [[conditional variance]] of $Y$ given $X=x$
$$
\mathbb{E}\left[(Y-\mathbb{E}_{Y|X=x_0}[Y\:|\:X])^2 | X=x_0 \right] = \mathbb{VAR}_{Y|X=x_0}\left[Y\:|\:X=x_0 \right]
$$

# Anki
START
Basic
[[mean square error]] definition
- [[statistical estimator]]
- [[statistical predictor]]
Back: 
For a [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, \widehat{x})=\mathbb{E}\left[(X-\widehat{x})^2\right]
$$

For a [[statistical predictor|statistical prediction]] of the [[random variable]] $Y$ given a dependent [[random variable]] $X$ the [[mean square error]] is defined as the following
$$
L_{MSE}(X, f(x))=\mathbb{E}\left[(X-f(x))^2\right]
$$
$L(Y, f(x))=E[(Y-f(x))^2] \rightarrow f(x)=E[Y|X=x]$  

Tags: statistical estimator, statistical learning
<!--ID: 1661678999134-->
END


START
Basic
minumum of the [[mean square error]] with proof
- [[statistical estimator]]
Back: 
### [[statistical estimator|statistical estimaton]] $\widehat{x}$
The [[statistical estimator|statistical estimaton]] $\widehat{x}$ of the [[random variable]] $X$ that is minimizing the [[mean square error]] is the [[expectation]] $\widehat{x}_{MSE}=\mathbb{E}[X]$.
Proof
$$
\begin{split}
\mathbb{E}\left[(X-\widehat{x})^2\right] &= \mathbb{E}\left[X^2\right] + \widehat{x}^2 + 2\widehat{x}\mathbb{E}\left[X\right] \\
\frac{d\mathbb{E}\left[X^2\right] + \widehat{x}^2 + 2\widehat{x}\mathbb{E}\left[X\right]}{d\widehat{x}} &= 2\widehat{x}-2\mathbb{E}\left[X\right] = 0 \\
\rightarrow argmin \: \mathbb{E}\left[(X-\widehat{x})^2\right] &= \widehat{x}_{MSE}=\mathbb{E}[X]
\end{split}
$$


The [[mean square error]] of $\widehat{x}_{MSE}$ the [[variance]] $L_{MSE}(X, \widehat{x}_{MSE})=\mathbb{VAR}\left[X\right]$.
$$
L_{MSE}(X, \widehat{x}_{MSE})=\mathbb{E}\left[(X-\widehat{x}_{MSE})^2\right] = \mathbb{E}\left[(X-\mathbb{E}[X])^2\right] = \mathbb{VAR}\left[X\right]
$$

Tags: statistical estimator, statistical learning
<!--ID: 1674122984694-->
END



START
Basic
[[statistical predictor]] that minimizes the [[mean square error]] and its [[mean square error]] with proof

Back: 

### [[statistical predictor]] $f(x)$
The [[statistical predictor]] $f(x)$ that is minimizing the [[mean square error]] is the [[conditional expectation]] $f_{MSE}(x)=\mathbb{E}[Y\:|\:X=x]$

- from the [[law of total probability]] we know that $\mathbb{E}[(Y-f(X))^2] =\mathbb{E}\left[\mathbb{E}\left[(Y-f(X))^2 | X \right] \right]$

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


- for an observed $x_0$ $\mathbb{E}\left[\mathbb{E}\left[(Y-f(x_0))^2 | X=x_0 \right] \right] = \mathbb{E}\left[(Y-f(x_0))^2 | X=x_0 \right]$ since its a constant
- if we can prove for every $x$ that $f(x)=argmin_c \:\mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]=\mathbb{E}[Y\:|\:X=x]$ its clear that $f(X)=\mathbb{E}[Y\:|\:X]$ is also true

$$
\begin{split}
\frac{d \mathbb{E}_{Y|X=x}[(Y-c)^2\:|\:X=x]}{dc} &= 0 \\
&=\frac{d \mathbb{E}_{Y|X=x}[Y^2\:|\:X=x]+c^2-2\mathbb{E}_{Y|X=x}[Y\:|\:X=x]c}{dc}  \\
&= 2x-2\mathbb{E}_{Y|X=x}[Y\:|\:X=x] \\
\rightarrow c&=\mathbb{E}_{Y|X=x}[Y\:|\:X=x] = f(x) 
\end{split}
$$
- for every constant $X=x_0$ the [[mean square error]] for an optimal [[statistical predictor]] $f(x) = \mathbb{E}_{Y|X=x}[Y\:|\:X=x]$ is equal to the [[conditional variance]] of $Y$ given $X=x$
$$
\mathbb{E}\left[(Y-\mathbb{E}_{Y|X=x_0}[Y\:|\:X])^2 | X=x_0 \right] = \mathbb{VAR}_{Y|X=x_0}\left[Y\:|\:X=x_0 \right]
$$

Tags: statistical estimator, statistical learning
<!--ID: 1674988747232-->
END