
## negative binomial distibution

### [[probability function]]
- $r =$ number of positive [[bernoulli distribution|bernoulli experiments]] 
- $x=$ number of positive fails before $r$ positive outcomes are achived
- $p=$ probability of positive outcome of the [[bernoulli distribution|bernoulli experiments]] 

$$
f_X(X = x | r, p)= 
\begin{cases}
{r + x - 1 \choose x}
p^{r}(1-p)^{x}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
$$
### [[expectation]]

$$
\mathbb{E}[X] = \frac{1-p}{p}
$$
### [[variance]]

$$
\mathbb{VAR}[X] = \frac{r(1-p)}{p^2}
$$
## geometric distribution
- [[negative binomial distibution]] with $r=1$ (number of failes untill first success)
### [[probability function]]
- $r =$ number of positive [[bernoulli distribution|bernoulli experiments]] 
- $x=$ number of positive fails before $r$ positive outcomes are achived
- $p=$ probability of positive outcome of the [[bernoulli distribution|bernoulli experiments]] 

$$
\begin{split}
f_X(X = x | r = 1, p)
&= 
\begin{cases}
{r + x - 1 \choose x}
p^{r}(1-p)^{x}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases} \\
&= 
\begin{cases}
p(1-p)^{x}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
\end{split}
$$
### memorylessness
$$
\begin{split}
& X \sim f_X(X = x | r = 1, p) \\
& P(X = k+t | X \geq k) = P(X = t)
\end{split}
$$

#### proof
$$
\begin{split}
P(X = k+t | X \geq k) 
&= P\left(\bigcup\limits_{i=1}^{k+t} X_i = 0 \cap X_{k+t+1} = 1 \mid \bigcup\limits_{i=1}^k X_i = 0 \right) \\
&= \frac{P\left(\bigcup\limits_{i=1}^k X_i = 0 \right)  P\left(X_{k+t+1} = 1 \cap\bigcup\limits_{i=k+t+1}^k X_i 
= 0\right)}{P\left(\bigcup\limits_{i=1}^k X_i = 0 \right)} \\
&=P\left(X_{t+1} = 1 \cap\bigcup\limits_{i=1}^t X_i = 0\right) \\
&=P(X = t )\\
\end{split}
$$


# anki

START
Basic
negative binomial distibution
- [[probability function]]
- [[expectation]]
- [[variance]]
Back: 
### [[probability function]]
- $r =$ number of positive [[bernoulli distribution|bernoulli experiments]] 
- $x=$ number of positive fails before $r$ positive outcomes are achived
- $p=$ probability of positive outcome of the [[bernoulli distribution|bernoulli experiments]] 

$$
f_X(X = x | r, p)= 
\begin{cases}
{r + x - 1 \choose x}
p^{r}(1-p)^{x}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
$$
### [[expectation]]

$$
\mathbb{E}[X] = \frac{1-p}{p}
$$
### [[variance]]

$$
\mathbb{VAR}[X] = \frac{r(1-p)}{p^2}
$$
Tags: mathematics statistics
<!--ID: 1678609876580-->
END


START
Basic
geometric distribution
- [[probability function]]
- memorylessness (with proof)
Back: 
## geometric distribution
- [[negative binomial distibution]] with $r=1$ (number of failes untill first success)
### [[probability function]]
- $r =$ number of positive [[bernoulli distribution|bernoulli experiments]] 
- $x=$ number of positive fails before $r$ positive outcomes are achived
- $p=$ probability of positive outcome of the [[bernoulli distribution|bernoulli experiments]] 

$$
\begin{split}
f_X(X = x | r = 1, p)
&= 
\begin{cases}
{r + x - 1 \choose x}
p^{r}(1-p)^{x}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases} \\
&= 
\begin{cases}
p(1-p)^{x}
 
,& \text{if } x \in \{0,1,2,..., n\}\\
0
,& \text{otherwise}
\end{cases}
\end{split}
$$
### memorylessness
$$
\begin{split}
& X \sim f_X(X = x | r = 1, p) \\
& P(X = k+t | X \geq k) = P(X = t)
\end{split}
$$

#### proof
$$
\begin{split}
P(X = k+t | X \geq k) 
&= P\left(\bigcup\limits_{i=1}^{k+t} X_i = 0 \cap X_{k+t+1} = 1 \mid \bigcup\limits_{i=1}^k X_i = 0 \right) \\
&= \frac{P\left(\bigcup\limits_{i=1}^k X_i = 0 \right)  P\left(X_{k+t+1} = 1 \cap\bigcup\limits_{i=k+t+1}^k X_i 
= 0\right)}{P\left(\bigcup\limits_{i=1}^k X_i = 0 \right)} \\
&=P\left(X_{t+1} = 1 \cap\bigcup\limits_{i=1}^t X_i = 0\right) \\
&=P(X = t )\\
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1678609876586-->
END