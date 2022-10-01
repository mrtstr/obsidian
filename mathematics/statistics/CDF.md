## Cumulative distribution function
Probability that a [[random variable]] will take a greater or equal value to the given value.
## Properties 
1) $F_X:\Omega \mapsto [0,1]$
2) $F_X(x)=P(X \leq x)$
3) $\lim\limits_{x \rightarrow \infty} F_X(x)=1$
4) $\lim\limits_{x \rightarrow -\infty} F_X(x)=0$
5) is [[monotonic function|monotonic increasing]] $x_1 \leq x_2 \Leftrightarrow F_X(x_1) \leq F_X(x_2)$
6) $P(X \in [a,b]) = F_X(b)-F_X(a) = \int\limits_{b}^{a}  f_X(x)\:dx$  

## Relationship to [[PDF]]
- $F_X(x)=P(X \leq x) =\int\limits_{-\infty}^{x}  f_X(x)\:dx$
- $f_X(x)=\frac{dF_X(x)}{dx}$ 

## empirical CDF 
Approximated CDF from [[statistical sample|samples]] 
$\widehat{F}_X(x)=\frac{1}{n} \sum\limits_{i=1}^n\mathbb{I}[x_i \leq x]$ 

## relationship to the [[quantile function]] $Q_X(q)$
- $Q_X(q)$ is the smallest values with a [[CDF]] less or equal than $q$  
$$Q_X(q) = \inf\left\{x \mid q \leq F_X(x)\right\}$$
- $Q_X(q)$ is the inverse of the [[CDF]]
$$Q_X(q)=F_X^{-1}(q)\quad with \: q = F_X(x)=P(X \leq x)$$



START
Basic
Cumulative Distribution Function (CDF)
- definition
Back: 
Probability that a [[random variable]] will take a greater or equal value to the given value.
- $F_X:\Omega \mapsto [0,1]$
- $F_X(x)=P(X \leq x)$
Tags: mathematics, statistics
<!--ID: 1664619948160-->
END

START
Basic
Cumulative Distribution Function (CDF)
- properties (6)
Back: 
1) $F_X:\Omega \mapsto [0,1]$
2) $F_X(x)=P(X \leq x)$
3) $\lim\limits_{x \rightarrow \infty} F_X(x)=1$
4) $\lim\limits_{x \rightarrow -\infty} F_X(x)=0$
5) is [[monotonic function|monotonic increasing]] $x_1 \leq x_2 \Leftrightarrow F_X(x_1) \leq F_X(x_2)$
6) $P(X \in [a,b]) = F_X(b)-F_X(a) = \int\limits_{b}^{a}  f_X(x)\:dx$  
Tags: mathematics, statistics
<!--ID: 1664619948163-->
END

START
Basic
Cumulative Distribution Function (CDF)
- how to estimate if from a sample
Back: 
empirical CDF: approximated CDF from [[statistical sample|samples]] 
$\widehat{F}_X(x)=\frac{1}{n} \sum\limits_{i=1}^n\mathbb{I}[x_i \leq x]$ 
Tags: mathematics, statistics
<!--ID: 1664619948167-->
END

START
Basic
 Relationship CDF $F_X(q)$ and [[quantile function]] $Q_X(q)$
Back: 

- $Q_X(q)$ is the smallest values with a [[CDF]] less or equal than $q$  
$$Q_X(q) = \inf\left\{x \mid q \leq F_X(x)\right\}$$
- $Q_X(q)$ is the inverse of the [[CDF]]
$$Q_X(q)=F_X^{-1}(q)\quad with \: q = F_X(x)=P(X \leq x)$$

Tags: mathematics, statistics
<!--ID: 1664619948170-->
ENDSTART
​￼Basic
 Relationship CDF ￼FX(q)￼ and ￼￼quantile function￼￼ ￼QX(q)￼
Back: 

 ￼QX(q)￼ is the smallest values with a ￼￼CDF￼￼ less or equal than ￼q￼  
QX(q)=inf{x∣q≤FX(x)}
 ￼QX(q)￼ is the inverse of the ￼￼CDF￼￼
QX(q)=FX−1(q)withq=FX(x)=P(X≤x)

Tags: mathematics, statistics
END