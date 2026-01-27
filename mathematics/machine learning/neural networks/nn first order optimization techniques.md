## optimization techniques
- optimization techniques for [[neural network]]

### dynamic learning rate
- it can be shown that the [[nn optimization algorithms#stochastic gradient descent]] converges under the following conditions to a local minimum

$$
\sum_{t=1}^\infty \alpha_t = \infty \qquad \sum_{t=1}^\infty \alpha_t^2 < \infty
$$

- both conditions are given for example for $\alpha_t = \frac{1}{t}$
- if the problem is furthermore strongly [[convex]] it converges with $\mathcal{O}\left(\frac{1}{t}\right)$ 

- in practice the following dynamic learning rate is often used with an initial learning rate $\alpha_0$ and a final learning rate $\alpha_\tau$ that is reached after $\tau$ steps

$$
\alpha_t = \begin{cases}
(1-\frac{t}{\tau}) \alpha_0 + \frac{t}{\tau} \alpha_\tau & \text{if } t < \tau \\
\alpha_\tau & \text{else}
\end{cases}
$$

### momentum
- fixed parameter $\rho \in [0,1)$

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
s &= \rho_1 s - \alpha g \\
\theta &=\theta + s \\
\end{split}
$$

- we can see that the momentum acts as an **accumulated weighted sum**
- note: its not exponential weighed average and the step size is scaled by $\frac{1}{1-\rho}$ which means the learning rate has to be adapted if $\rho_1$ becomes small
- the [[gradient]] can be seen as a force while $s$ is the momentum and each new force adjusts the trajectory of the momentum

$$
\begin{split}
s_0 &= -\alpha g_0 \\
s_1 &= \rho_1 s_0 - \alpha g_1 = -\rho_1 \alpha g_0 - \alpha g_1 \\
s_2 &= \rho_1 s_1 - \alpha g_2 = -\rho_1^2  \alpha g_0 - \rho_1 \alpha g_1  - \alpha g_2 \\
s_k &= -\sum_{i=0}^k\rho_1^i \alpha g_{k-i} \\
\end{split}
$$


- if we assume that the [[gradient]] is constant we have

$$
\lim_{k \to \infty} s_k = - \frac{\alpha g}{1-\rho_1} 
$$

- this means the parameters move with a speed of $\alpha ||g|| \frac{1}{1-\rho}$ → the steps will be much larger for small $\rho_1$


![[geometric series#geometric series]]

### nesterov momentum
- similar approach but we evaluate the gradient at an extrapolated point $\theta + \rho_1 s$
- since we already have a good idea how the step will look like this makes the gradient a better representation of the step

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta + \rho_1 s) \\
s &= \rho_1 s - \alpha g \\
\theta &=\theta + s \\
\end{split}
$$

### AdaGrad
- **Goal:** Customize the learning rate for all components individually.
- **Mechanism:** r is the accumulated sum of the **squared** gradients.
- **Behavior:** Over time r grows, which forces the effective learning rate to decay. Dimensions with large gradients (steep slopes) decay faster.
- effectively normalizes away the magnitude of the [[gradient]] resulting in something similar to $\mathrm{sign}(\nabla\mathcal{R}(\theta))$ to make the convergence more stable

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
r &= r +  g \odot g \\
\theta &=\theta - \frac{1}{\sqrt{r}+\epsilon} \odot \alpha g \\
\end{split}
$$

### RMSProp
- **Goal:** Fix the aggressive decay of **AdaGrad** to prevent the step size from converging to zero too fast
- **Mechanism:** Use an **exponential moving average** of squared gradients instead of sums
- **Behavior:** The step size adapts to local topography but does not shrink to zero effectively allowing training to continue indefinitely.

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
r &= r \rho_2+ (1-\rho_2) g \odot g \\
\theta &=\theta - \frac{1}{\sqrt{r}+\epsilon} \odot \alpha g \\
\end{split}
$$

- problem: oscillates around the optimum because step size does not vanish
### Adam
- combines the ideas of **momentum** and **RMSProp**
- combines exponential weighted average of the gradients (momentum) with an element wise normalization term that is based of exponential weighted average of the squared gradients
- $r$ is initialized with zero and to prevent the update step from exploding there is an additional normalization resulting in something like a warm start

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
s &= s \rho_1+ (1-\rho_1) g \\
\widehat{s} &= \frac{s}{1-\rho_1^k} \\
r &= r \rho_2+ (1-\rho_2) g \odot g \\
\widehat{r} &=  \frac{r}{1-\rho_2^k} \\
\theta &=\theta - \frac{\alpha}{\sqrt{\widehat{r}}+\epsilon} \odot  \widehat{s} \\
\end{split}
$$

- the first step of **Adam** is equivalent to **AdaGrad**

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
s &=  (1-\rho_1) g \\
\widehat{s} &= \frac{s}{1-\rho_1^k} = \frac{(1-\rho_1) g}{1-\rho_1} = g \\
r &=  (1-\rho_2) g \odot g \\
\widehat{r} &=  \frac{r}{1-\rho_2^k} = \frac{(1-\rho_2) g \odot g }{1-\rho_2^1} = g \odot g \\
\theta &=\theta - \frac{\alpha}{\sqrt{\widehat{r}}+\epsilon} \odot  \widehat{s}   \\
&=\theta - \frac{\alpha}{\sqrt{\widehat{r}}+\epsilon} \odot  g 
\end{split}
$$

# anki
START
Basic
momentum for [[neural network]] training:
- equations
- how do we have to adapt the learning rate to keep the step size the same when introducing momentum?

Back: 
### momentum
- fixed parameter $\rho \in [0,1)$

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
s &= \rho_1 s - \alpha g \\
\theta &=\theta + s \\
\end{split}
$$

- we can see that the momentum acts as an **accumulated weighted sum**
- note: its not exponential weighed average and the step size is scaled by $\frac{1}{1-\rho}$ which means the learning rate has to be adapted if $\rho_1$ becomes small
- the [[gradient]] can be seen as a force while $s$ is the momentum and each new force adjusts the trajectory of the momentum

$$
\begin{split}
s_0 &= -\alpha g_0 \\
s_1 &= \rho_1 s_0 - \alpha g_1 = -\rho_1 \alpha g_0 - \alpha g_1 \\
s_2 &= \rho_1 s_1 - \alpha g_2 = -\rho_1^2  \alpha g_0 - \rho_1 \alpha g_1  - \alpha g_2 \\
s_k &= -\sum_{i=0}^k\rho_1^i \alpha g_{k-i} \\
\end{split}
$$


- if we assume that the [[gradient]] is constant we have

$$
\lim_{k \to \infty} s_k = - \frac{\alpha g}{1-\rho_1} 
$$

- this means the parameters move with a speed of $\alpha ||g|| \frac{1}{1-\rho}$ → the steps will be much larger for small $\rho_1$

_________
### geometric series
geometric [[series]] is converging for $0< q < 1$

$$
\sum_{k=0}^\infty q^k = \frac{1}{1-q}
$$

- [[geometric series]] for [[matrix|matrices]]
$$
\sum_{i=0}^{n-1} A^k = (I-A)^{-1}(I-A^n)
$$

## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[nn activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
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

- note: if none of the [[nn activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers


Tags: mathematics WS2526 ml
<!--ID: 1769357465558-->
END


START
Basic
nesterov momentum for [[neural network]] training:
- equations
- what does it improve compared to normal momentum?

Back: 
### nesterov momentum
- similar approach but we evaluate the gradient at an extrapolated point $\theta + \rho_1 s$
- since we already have a good idea how the step will look like this makes the gradient a better representation of the step

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta + \rho_1 s) \\
s &= \rho_1 s - \alpha g \\
\theta &=\theta + s \\
\end{split}
$$


_________
### momentum
- fixed parameter $\rho \in [0,1)$

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
s &= \rho_1 s - \alpha g \\
\theta &=\theta + s \\
\end{split}
$$

- we can see that the momentum acts as an **accumulated weighted sum**
- note: its not exponential weighed average and the step size is scaled by $\frac{1}{1-\rho}$ which means the learning rate has to be adapted if $\rho_1$ becomes small
- the [[gradient]] can be seen as a force while $s$ is the momentum and each new force adjusts the trajectory of the momentum

$$
\begin{split}
s_0 &= -\alpha g_0 \\
s_1 &= \rho_1 s_0 - \alpha g_1 = -\rho_1 \alpha g_0 - \alpha g_1 \\
s_2 &= \rho_1 s_1 - \alpha g_2 = -\rho_1^2  \alpha g_0 - \rho_1 \alpha g_1  - \alpha g_2 \\
s_k &= -\sum_{i=0}^k\rho_1^i \alpha g_{k-i} \\
\end{split}
$$


- if we assume that the [[gradient]] is constant we have

$$
\lim_{k \to \infty} s_k = - \frac{\alpha g}{1-\rho_1} 
$$

- this means the parameters move with a speed of $\alpha ||g|| \frac{1}{1-\rho}$ → the steps will be much larger for small $\rho_1$

## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[nn activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
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

- note: if none of the [[nn activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers


Tags: mathematics WS2526 ml
<!--ID: 1769357465562-->
END

START
Basic
**AdaGrad** and **RMSProp** for [[neural network]] training:
- equations
- intuition
- problems

Back: 

### AdaGrad
- **Goal:** Customize the learning rate for all components individually.
- **Mechanism:** r is the accumulated sum of the **squared** gradients.
- **Behavior:** Over time r grows, which forces the effective learning rate to decay. Dimensions with large gradients (steep slopes) decay faster.
- effectively normalizes away the magnitude of the [[gradient]] resulting in something similar to $\mathrm{sign}(\nabla\mathcal{R}(\theta))$

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
r &= r +  g \odot g \\
\theta &=\theta - \frac{1}{\sqrt{r}+\epsilon} \odot \alpha g \\
\end{split}
$$

### RMSProp
- **Goal:** Fix the aggressive decay of **AdaGrad** to prevent the step size from converging to zero too fast
- **Mechanism:** Use an **exponential moving average** of squared gradients instead of sums
- **Behavior:** The step size adapts to local topography but does not shrink to zero effectively allowing training to continue indefinitely.

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
r &= r \rho_2+ (1-\rho_2) g \odot g \\
\theta &=\theta - \frac{1}{\sqrt{r}+\epsilon} \odot \alpha g \\
\end{split}
$$

- problem: oscillates around the optimum because step size does not vanish
_________


## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[nn activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
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

- note: if none of the [[nn activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers


Tags: mathematics WS2526 ml
<!--ID: 1769357465565-->
END


START
Basic
[[nn first order optimization techniques#Adam]]
- equations with explanation why each step is needed
- intuition

Back: 
### Adam
- combines the ideas of **momentum** and **RMSProp**
- combines exponential weighted average of the gradients (momentum) with an element wise normalization term that is based of exponential weighted average of the squared gradients
- $r$ is initialized with zero and to prevent the update step from exploding there is an additional normalization resulting in something like a warm start

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
s &= s \rho_1+ (1-\rho_1) g \\
\widehat{s} &= \frac{s}{1-\rho_1^k} \\
r &= r \rho_2+ (1-\rho_2) g \odot g \\
\widehat{r} &=  \frac{r}{1-\rho_2^k} \\
\theta &=\theta - \frac{\alpha}{\sqrt{\widehat{r}}+\epsilon} \odot  \widehat{s} \\
\end{split}
$$


_________

### AdaGrad
- **Goal:** Customize the learning rate for all components individually.
- **Mechanism:** r is the accumulated sum of the **squared** gradients.
- **Behavior:** Over time r grows, which forces the effective learning rate to decay. Dimensions with large gradients (steep slopes) decay faster.
- effectively normalizes away the magnitude of the [[gradient]] resulting in something similar to $\mathrm{sign}(\nabla\mathcal{R}(\theta))$ to make the convergence more stable
### RMSProp
- **Goal:** Fix the aggressive decay of **AdaGrad** to prevent the step size from converging to zero too fast
- **Mechanism:** Use an **exponential moving average** of squared gradients instead of sums
- **Behavior:** The step size adapts to local topography but does not shrink to zero effectively allowing training to continue indefinitely.

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
r &= r \rho_2+ (1-\rho_2) g \odot g \\
\theta &=\theta - \frac{1}{\sqrt{r}+\epsilon} \odot \alpha g \\
\end{split}
$$

- problem: oscillates around the optimum because step size does not vanish

### momentum
- fixed parameter $\rho \in [0,1)$

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
s &= \rho_1 s - \alpha g \\
\theta &=\theta + s \\
\end{split}
$$

- we can see that the momentum acts as an **accumulated weighted sum**
- note: its not exponential weighed average and the step size is scaled by $\frac{1}{1-\rho}$ which means the learning rate has to be adapted if $\rho_1$ becomes small
- the [[gradient]] can be seen as a force while $s$ is the momentum and each new force adjusts the trajectory of the momentum

$$
\begin{split}
s_0 &= -\alpha g_0 \\
s_1 &= \rho_1 s_0 - \alpha g_1 = -\rho_1 \alpha g_0 - \alpha g_1 \\
s_2 &= \rho_1 s_1 - \alpha g_2 = -\rho_1^2  \alpha g_0 - \rho_1 \alpha g_1  - \alpha g_2 \\
s_k &= -\sum_{i=0}^k\rho_1^i \alpha g_{k-i} \\
\end{split}
$$


- if we assume that the [[gradient]] is constant we have

$$
\lim_{k \to \infty} s_k = - \frac{\alpha g}{1-\rho_1} 
$$

- this means the parameters move with a speed of $\alpha ||g|| \frac{1}{1-\rho}$ → the steps will be much larger for small $\rho_1$

## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[nn activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
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

- note: if none of the [[nn activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers


Tags: mathematics WS2526 ml
<!--ID: 1769529258448-->
END


START
Basic
- which conditions the learning rate has to satisfy to grantee convergence with [[nn optimization algorithms#stochastic gradient descent]]
- example that satisfies this
- how fast does it converge then for strongly [[convex]] problems
- example that is often used in practice?

Back: 
### dynamic learning rate
- it can be shown that the [[nn optimization algorithms#stochastic gradient descent]] converges under the following conditions to a local minimum

$$
\sum_{t=1}^\infty \alpha_t = \infty \qquad \sum_{t=1}^\infty \alpha_t^2 < \infty
$$

- both conditions are given for example for $\alpha_t = \frac{1}{t}$
- if the problem is furthermore strongly [[convex]] it converges with $\mathcal{O}\left(\frac{1}{t}\right)$ 

- in practice the following dynamic learning rate is often used with an initial learning rate $\alpha_0$ and a final learning rate $\alpha_\tau$ that is reached after $\tau$ steps

$$
\alpha_t = \begin{cases}
(1-\frac{t}{\tau}) \alpha_0 + \frac{t}{\tau} \alpha_\tau & \text{if } t < \tau \\
\alpha_\tau & \text{else}
\end{cases}
$$


_________

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


## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[nn activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
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

- note: if none of the [[nn activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers


Tags: mathematics WS2526 ml
<!--ID: 1769529258452-->
END


START
Basic
relationship of [[nn first order optimization techniques#Adam]] and [[nn first order optimization techniques#AdaGrad]]

Back: 
### Adam
- combines the ideas of **momentum** and **RMSProp**
- combines exponential weighted average of the gradients (momentum) with an element wise normalization term that is based of exponential weighted average of the squared gradients
- $r$ is initialized with zero and to prevent the update step from exploding there is an additional normalization resulting in something like a warm start

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
s &= s \rho_1+ (1-\rho_1) g \\
\widehat{s} &= \frac{s}{1-\rho_1^k} \\
r &= r \rho_2+ (1-\rho_2) g \odot g \\
\widehat{r} &=  \frac{r}{1-\rho_2^k} \\
\theta &=\theta - \frac{\alpha}{\sqrt{\widehat{r}}+\epsilon} \odot  \widehat{s} \\
\end{split}
$$

- the first step of **Adam** is equivalent to **AdaGrad**

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
s &=  (1-\rho_1) g \\
\widehat{s} &= \frac{s}{1-\rho_1^k} = \frac{(1-\rho_1) g}{1-\rho_1} = g \\
r &=  (1-\rho_2) g \odot g \\
\widehat{r} &=  \frac{r}{1-\rho_2^k} = \frac{(1-\rho_2) g \odot g }{1-\rho_2^1} = g \odot g \\
\theta &=\theta - \frac{\alpha}{\sqrt{\widehat{r}}+\epsilon} \odot  \widehat{s}   \\
&=\theta - \frac{\alpha}{\sqrt{\widehat{r}}+\epsilon} \odot  g 
\end{split}
$$


_________

### AdaGrad
- **Goal:** Customize the learning rate for all components individually.
- **Mechanism:** r is the accumulated sum of the **squared** gradients.
- **Behavior:** Over time r grows, which forces the effective learning rate to decay. Dimensions with large gradients (steep slopes) decay faster.
- effectively normalizes away the magnitude of the [[gradient]] resulting in something similar to $\mathrm{sign}(\nabla\mathcal{R}(\theta))$ to make the convergence more stable
### RMSProp
- **Goal:** Fix the aggressive decay of **AdaGrad** to prevent the step size from converging to zero too fast
- **Mechanism:** Use an **exponential moving average** of squared gradients instead of sums
- **Behavior:** The step size adapts to local topography but does not shrink to zero effectively allowing training to continue indefinitely.

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
r &= r \rho_2+ (1-\rho_2) g \odot g \\
\theta &=\theta - \frac{1}{\sqrt{r}+\epsilon} \odot \alpha g \\
\end{split}
$$

- problem: oscillates around the optimum because step size does not vanish

### momentum
- fixed parameter $\rho \in [0,1)$

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
s &= \rho_1 s - \alpha g \\
\theta &=\theta + s \\
\end{split}
$$

- we can see that the momentum acts as an **accumulated weighted sum**
- note: its not exponential weighed average and the step size is scaled by $\frac{1}{1-\rho}$ which means the learning rate has to be adapted if $\rho_1$ becomes small
- the [[gradient]] can be seen as a force while $s$ is the momentum and each new force adjusts the trajectory of the momentum

$$
\begin{split}
s_0 &= -\alpha g_0 \\
s_1 &= \rho_1 s_0 - \alpha g_1 = -\rho_1 \alpha g_0 - \alpha g_1 \\
s_2 &= \rho_1 s_1 - \alpha g_2 = -\rho_1^2  \alpha g_0 - \rho_1 \alpha g_1  - \alpha g_2 \\
s_k &= -\sum_{i=0}^k\rho_1^i \alpha g_{k-i} \\
\end{split}
$$


- if we assume that the [[gradient]] is constant we have

$$
\lim_{k \to \infty} s_k = - \frac{\alpha g}{1-\rho_1} 
$$

- this means the parameters move with a speed of $\alpha ||g|| \frac{1}{1-\rho}$ → the steps will be much larger for small $\rho_1$

## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[nn activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
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

- note: if none of the [[nn activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers


Tags: mathematics WS2526 ml
<!--ID: 1769529258454-->
END