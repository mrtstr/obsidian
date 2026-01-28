### first order optimization algorithms
- based on [[gradient descent]] using [[backpropagation]] for the [[gradient]] calculation

[[full gradient descent]]
[[mini batch gradient descent]]
[[stochastic gradient descent]]
[[adam optimizer]]
# anki
START
Basic
3 [[nn optimization algorithms]] for [[neural network]]
- overview
- pros and cons which to choose

Back: 

## optimization algorithms

- given a [[neural network]] $f_\theta$ and a [[loss function]] $\ell$
- with the [[backpropagation]] algorithm we can calculate the [[gradient]] of the [[risk]] $\mathcal{R}(\theta)$ with respect to the parameters $\theta$
- this works because the [[risk]] is just a linear function of the [[loss function]] of the samples

$$
\nabla_\theta\mathcal{R}(\theta) = \frac{1}{n} \sum_{i=1}^n \nabla_\theta \ell\left(y_i, f_\theta(x_i)\right)
$$
### full gradient descent
1) calculate $\nabla_\theta\mathcal{R}(\theta)$ for the complete [[training dataset]]
2) update the parameters

$$
\theta_{t+1} = \theta_{t} - \alpha \nabla_\theta\mathcal{R}(\theta_t)
$$

3) repeat iteratively until stopping criterion satisfied


### stochastic gradient descent
1) pick a single random sample
2) calculate $\nabla_\theta\mathcal{R}(\theta)$ for that sample
3) update the parameters $\theta_{t+1} = \theta_{t} - \alpha \nabla_\theta\mathcal{R}(\theta_t)$
4) repeat iteratively until stopping criterion satisfied

- let $\mathcal{R}^*$ be the [[risk|true risk]] defined as follows

$$
\begin{split}
\mathcal{R}^*(\theta) 
&= \mathbb{E}_{(x,y) \sim \mathcal{P}_{XY}}\left[\ell\left( y, f_\theta(x)\right)\right] \\
\end{split}
$$

- when calculating the [[gradient]] of a random sample, we are basically calculating the [[expectation|expected]] gradient
- because if the linearity of the [[risk]] (assuming i.i.d. training samples) we can pull in the [[expectation]]
- this shows that the gradient of a random sample is an unbiased estimator of the true risk

$$
\begin{split}
\mathbb{E} \left[\nabla_\theta \ell\left(y, f_\theta(x)\right)\right]
&=  \nabla_\theta  \mathbb{E}\left[\ell\left(y, f_\theta(x)\right)\right] \\
&=\nabla_\theta\mathcal{R}^*(\theta) \\
\end{split}
$$

### mini batch gradient descent
1) pick and random subset of $\{1, ..., m\}$ $B_t$ with $|B_t|=s$
2) calculate the gradient on the batch

$$\nabla_\theta\mathcal{R}^{B_t}(\theta) = \frac{1}{n} \sum_{i\in B_t}^s \nabla_\theta \ell\left(y_i, f_\theta(x_i)\right)$$

3) update the parameters $\theta_{t+1} = \theta_{t} - \alpha \nabla_\theta\mathcal{R}(\theta_t)$
4) repeat iteratively until stopping criterion satisfied

- for $s=1$ we have **stochastic gradient descent** and for $s=m$ we have **full gradient descent**
- high batch size:
	- faster calculation because it can be parallelized
	- leads to [[regularization]]
	- but increases the memory requirements


____________
## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
- the output of each layer is called the activation vector $\mathrm{a}^{(i)}$ with the first being the input of the model $\mathrm{a}^{(0)}=x \in \mathbb{R}^{n_0}$ 

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

- the complete model can be represented by a function $f_\theta$

$$
\begin{split}
f_\theta &= \mathrm{a}^{(L)} \\
\theta &= \left(W^{(1)}, b^{(1)}, ..., W^{(L)}, b^{(L)}\right) \\
\end{split}
$$

- note: if none of the [[activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers

## backpropagation
- let $f_\theta$ be [[neural network]] with $L$ layers and element wise [[activation function]] $g^{(i)}$ and let $l$ be a [[loss function]]
- the goal is to solve the following [[unconstraint optimization problem]] with [[gradient descent]]

$$
\hat\theta = \arg\min_{\theta} \frac{1}{m} \sum_{i=1}^m l\left(y^{(i)}, f_\theta \left(x^{(i)}\right)\right)
$$
- in the following we will just work with a single $(x, y)$ tuple but since the [[derivative]] is linear this can easily be extended to a sum


### algorithm
0) $\mathrm{a}^{(0)}=x$
1) forward pass: for $i \in 1, ..., L$

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

2) calculate

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\nabla_ {W^{(L)}} l &= \left( \underbrace {a^{(L-1)}}_{\mathbb{R}^{n_{L-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_L \times n_{L-1}} \\
 \nabla_ {b^{(L)}} l 
&= \delta^{(L)\top} \in \mathbb{R}^{n_{L}} \\
\end{split}
$$

3) backwards pass for $k \in L-1, ..., 1$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\delta^{(k+1)\top}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
W^{(k+1)}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}  \in \mathbb{R}^{1\times n_{k}}\\
\nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_k \times n_{k-1}} \\
 \nabla_ {b^{(k)}} l 
&= \delta^{(k)\top} \in \mathbb{R}^{n_{k}} \\
\end{split}
$$


4) return $\nabla_\theta l=\left(\nabla_W^{(1)}, \nabla_b^{(1)}, ..., \nabla_W^{(L)}, \nabla_b^{(L)}\right)$ 

### gradient descent
- iterative algorithm for solving continious optimization problems using the first order [[derivative]]
- [[gradient descent]] is a [[general descent method]] where we use the negative [[gradient]] $\nabla f\left(x^{(k)}\right)$ as direction which is the direction of the steepest descent in point $x^{(k)}$
- we choose a step size $\alpha^{(k)} \in (0,1]$

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)} \nabla f\left(x^{(k)}\right)
$$

- this can be interpreted as searching the [[minimum]] of the [[linear approximation]] of $f$ in each point


Tags: mathematics WS2526 ml
<!--ID: 1766137007809-->
END



START
Basic
proof that [[nn optimization algorithms#stochastic gradient descent]] is unbiased

Back: 
### stochastic gradient descent
1) pick a single random sample
2) calculate $\nabla_\theta\mathcal{R}(\theta)$ for that sample
3) update the parameters $\theta_{t+1} = \theta_{t} - \alpha \nabla_\theta\mathcal{R}(\theta_t)$
4) repeat iteratively until stopping criterion satisfied

- let $\mathcal{R}^*$ be the [[risk|true risk]] defined as follows

$$
\begin{split}
\mathcal{R}^*(\theta) 
&= \mathbb{E}_{(x,y) \sim \mathcal{P}_{XY}}\left[\ell\left( y, f_\theta(x)\right)\right] \\
\end{split}
$$

- when calculating the [[gradient]] of a random sample, we are basically calculating the [[expectation|expected]] gradient
- because if the linearity of the [[risk]] (assuming i.i.d. training samples) we can pull in the [[expectation]]
- this shows that the gradient of a random sample is an unbiased estimator of the true risk

$$
\begin{split}
\mathbb{E} \left[\nabla_\theta \ell\left(y, f_\theta(x)\right)\right]
&=  \nabla_\theta  \mathbb{E}\left[\ell\left(y, f_\theta(x)\right)\right] \\
&=\nabla_\theta\mathcal{R}^*(\theta) \\
\end{split}
$$

## optimization algorithms

- given a [[neural network]] $f_\theta$ and a [[loss function]] $\ell$
- with the [[backpropagation]] algorithm we can calculate the [[gradient]] of the [[risk]] $\mathcal{R}(\theta)$ with respect to the parameters $\theta$
- this works because the [[risk]] is just a linear function of the [[loss function]] of the samples

$$
\nabla_\theta\mathcal{R}(\theta) = \frac{1}{n} \sum_{i=1}^n \nabla_\theta \ell\left(y_i, f_\theta(x_i)\right)
$$
### full gradient descent
1) calculate $\nabla_\theta\mathcal{R}(\theta)$ for the complete [[training dataset]]
2) update the parameters

$$
\theta_{t+1} = \theta_{t} - \alpha \nabla_\theta\mathcal{R}(\theta_t)
$$

3) repeat iteratively until stopping criterion satisfied


### stochastic gradient descent
1) pick a single random sample
2) calculate $\nabla_\theta\mathcal{R}(\theta)$ for that sample
3) update the parameters $\theta_{t+1} = \theta_{t} - \alpha \nabla_\theta\mathcal{R}(\theta_t)$
4) repeat iteratively until stopping criterion satisfied

- let $\mathcal{R}^*$ be the [[risk|true risk]] defined as follows

$$
\begin{split}
\mathcal{R}^*(\theta) 
&= \mathbb{E}_{(x,y) \sim \mathcal{P}_{XY}}\left[\ell\left( y, f_\theta(x)\right)\right] \\
\end{split}
$$

- when calculating the [[gradient]] of a random sample, we are basically calculating the [[expectation|expected]] gradient
- because if the linearity of the [[risk]] (assuming i.i.d. training samples) we can pull in the [[expectation]]
- this shows that the gradient of a random sample is an unbiased estimator of the true risk

$$
\begin{split}
\mathbb{E} \left[\nabla_\theta \ell\left(y, f_\theta(x)\right)\right]
&=  \nabla_\theta  \mathbb{E}\left[\ell\left(y, f_\theta(x)\right)\right] \\
&=\nabla_\theta\mathcal{R}^*(\theta) \\
\end{split}
$$

### mini batch gradient descent
1) pick and random subset of $\{1, ..., m\}$ $B_t$ with $|B_t|=s$
2) calculate the gradient on the batch

$$\nabla_\theta\mathcal{R}^{B_t}(\theta) = \frac{1}{n} \sum_{i\in B_t}^s \nabla_\theta \ell\left(y_i, f_\theta(x_i)\right)$$

3) update the parameters $\theta_{t+1} = \theta_{t} - \alpha \nabla_\theta\mathcal{R}(\theta_t)$
4) repeat iteratively until stopping criterion satisfied

- for $s=1$ we have **stochastic gradient descent** and for $s=m$ we have **full gradient descent**
- high batch size:
	- faster calculation because it can be parallelized
	- leads to [[regularization]]
	- but increases the memory requirements


____________
## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
- the output of each layer is called the activation vector $\mathrm{a}^{(i)}$ with the first being the input of the model $\mathrm{a}^{(0)}=x \in \mathbb{R}^{n_0}$ 

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

- the complete model can be represented by a function $f_\theta$

$$
\begin{split}
f_\theta &= \mathrm{a}^{(L)} \\
\theta &= \left(W^{(1)}, b^{(1)}, ..., W^{(L)}, b^{(L)}\right) \\
\end{split}
$$

- note: if none of the [[activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers

## backpropagation
- let $f_\theta$ be [[neural network]] with $L$ layers and element wise [[activation function]] $g^{(i)}$ and let $l$ be a [[loss function]]
- the goal is to solve the following [[unconstraint optimization problem]] with [[gradient descent]]

$$
\hat\theta = \arg\min_{\theta} \frac{1}{m} \sum_{i=1}^m l\left(y^{(i)}, f_\theta \left(x^{(i)}\right)\right)
$$
- in the following we will just work with a single $(x, y)$ tuple but since the [[derivative]] is linear this can easily be extended to a sum


### algorithm
0) $\mathrm{a}^{(0)}=x$
1) forward pass: for $i \in 1, ..., L$

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

2) calculate

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\nabla_ {W^{(L)}} l &= \left( \underbrace {a^{(L-1)}}_{\mathbb{R}^{n_{L-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_L \times n_{L-1}} \\
 \nabla_ {b^{(L)}} l 
&= \delta^{(L)\top} \in \mathbb{R}^{n_{L}} \\
\end{split}
$$

3) backwards pass for $k \in L-1, ..., 1$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\delta^{(k+1)\top}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
W^{(k+1)}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}  \in \mathbb{R}^{1\times n_{k}}\\
\nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_k \times n_{k-1}} \\
 \nabla_ {b^{(k)}} l 
&= \delta^{(k)\top} \in \mathbb{R}^{n_{k}} \\
\end{split}
$$


4) return $\nabla_\theta l=\left(\nabla_W^{(1)}, \nabla_b^{(1)}, ..., \nabla_W^{(L)}, \nabla_b^{(L)}\right)$ 

### gradient descent
- iterative algorithm for solving continious optimization problems using the first order [[derivative]]
- [[gradient descent]] is a [[general descent method]] where we use the negative [[gradient]] $\nabla f\left(x^{(k)}\right)$ as direction which is the direction of the steepest descent in point $x^{(k)}$
- we choose a step size $\alpha^{(k)} \in (0,1]$

$$
x^{(k+1)} = x^{(k)} - \alpha^{(k)} \nabla f\left(x^{(k)}\right)
$$

- this can be interpreted as searching the [[minimum]] of the [[linear approximation]] of $f$ in each point


Tags: mathematics WS2526 ml
<!--ID: 1766137007814-->
END