
### adam optimizer
- combines the ideas of [[momentum]] and **RMSProp**
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
#### geometric obstetrical
- the [[adam optimizer]] can deal with most geometric obstetrical
- canyons / [[ill conditioned hessians with gradient descent]] → normalization with the second moments helps
- flat areas → [[momentum]] helps to escape
- saddle points → [[momentum]] helps to escape
- only local minima that are much worse than the global minimum are problematic
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


# anki

START
Basic
[[adam optimizer]]
- update rule and intuition

Back: 
### adam optimizer
- adaptive moment estimation optimizer ([[adam optimizer]]) has the following update rule
- $\hat  m_t$ is the exponential moving average (first moment estimate) of past gradients (bias corrected)
- $\hat  v_t$ is the exponential moving average (second moment estimate) of past squared gradients (bias corrected)
- $\eta(t)$ is the (possibly time-dependent) learning rate.

$$
\theta_{t+1} = \theta_t - \eta(t) \frac{\hat  m_t}{\sqrt{\hat v_t}+\epsilon}
$$

#### intuition
- taking the average $\hat  m_t$ of the past [[gradient|gradients]] instead of taking the [[gradient|gradients]] itself makes the updates more stable and less noisy 
- the second moment $\hat  v_t$ approximates the [[variance]] of the [[gradient|gradients]] scales down the updates then the gradients are changing a lot

Tags: ml WS2526
<!--ID: 1763995026497-->
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


Tags: mathematics WS2526 ml
<!--ID: 1769529258448-->
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


Tags: mathematics WS2526 ml
<!--ID: 1769529258454-->
END

START
Basic
how does the [[adam optimizer]] deal with geometric obstetrical in the energy surface?
when does it still fail?

Back: 
#### geometric obstetrical
- the [[adam optimizer]] can deal with most geometric obstetrical
- canyons / [[ill conditioned hessians with gradient descent]] → normalization with the second moments helps
- flat areas → [[momentum]] helps to escape
- saddle points → [[momentum]] helps to escape
- only local minima that are much worse than the global minimum are problematic
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

### ill conditioned hessians with gradient descent
- using the [[quadratic loss model]] we have the following approximation for a point $\theta$ while the approximation is centered around the current parameter location $\theta_t$

$$
\begin{split}
\mathcal{R}(\theta) \approx \mathcal{R}(\theta_t) + g^\top (\theta - \theta_t) + \frac{1}{2} (\theta - \theta_t)^\top H (\theta - \theta_t) \\
\end{split}
$$

- with $\theta_{t+1} = \theta_t - \alpha g$ we have the following

$$
\begin{split}
\mathcal{R}(\theta - \alpha g) 
&\approx \mathcal{R}(\theta_t) + g^\top (\theta - \alpha g - \theta_t) + \frac{1}{2} (\theta - \alpha g - \theta_t)^\top H (\theta - \alpha g - \theta_t) \\
&\approx \mathcal{R}(\theta_t) - g^\top \alpha g + \frac{1}{2}  \alpha^2 g^\top H g  \\
\end{split}
$$

- in order to decrease the [[risk]] we want the following which means that its problematic if $g^\top H g$ is very large

$$
 \frac{1}{2}  \alpha g^\top H g <  g^\top  g  
$$

$$
\begin{split}
g^\top H g 
&= g^\top Q\Lambda Q^\top g \\
&= \sum_i \lambda_i g^\top Q_{(:, i)}  Q^\top_{(:, i)} g \\
&= \sum_i \lambda_i (g^\top Q_{(:, i)})^2 \\
\end{split}
$$

- if we have very large eigenvalues alpha needs to be very small $\alpha \propto \frac{1}{\lambda_{max}}$
- however if we have directions with small eigenvalues too there is almost no progress in these directions
- in the case the [[hessian]] is ill [[condition|conditioned]]

$$
\kappa(H) = \frac{|\lambda_{max}|}{|\lambda_{min}|} \gg 1
$$
#### intuition
- Geometrically, an ill-conditioned Hessian corresponds to a **narrow canyon** or ravine. In this landscape, standard gradient descent tends to **oscillate across the narrow direction** (steep walls) while making slow progress along the flat direction, resulting in poor convergence

#### second order optimization
- second order methods like the [[newton methode]] would not suffer from this problem because since the step contains the inverse of the [[hessian]] the step size is scaled in each direction individually based on its curvature
	→ balanced curvature corrected step

$$
\begin{split}
\nabla\mathcal{R}(\theta) &\approx  g  +   H d = 0 \\
\Rightarrow d &= -H^{-1}g \\
\Rightarrow \theta_{t+1}  &= \theta_{t} -H^{-1}g
\end{split}
$$

#### when using the adam optimizer
- the [[adam optimizer]] acts as a **Diagonal Quasi-Newton** method. It effectively approximates the scaling of the inverted [[hessian]] using the **accumulated squared gradients** to normalize the step sizes for each parameter individually

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


Tags: mathematics WS2526 ml
<!--ID: 1769622930769-->
END