## optimization techniques
- optimization techniques for [[neural network]]

### dynamic learning rate

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

- we can see that the momentum acts as an exponential weighted average
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

- this means the parameters move with a speed of $\alpha ||g|| \frac{1}{1-\rho}$ 

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

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
r &= r +  g \odot g \\
\theta &=\theta - \frac{1}{\sqrt{r}+\epsilon} \odot \alpha g \\
\end{split}
$$

### RMSProp
- **Goal:** Fix the aggressive decay of AdaGrad to work in non-convex settings (like Neural Networks).
- **Mechanism:** Use an **exponential moving average** of squared gradients.
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
- combines a 

# anki
START
Basic
momentum for [[neural network]] training:
- equations
- show that the parameters move with a speed of $\alpha ||g|| \frac{1}{1-\rho}$ 

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

- we can see that the momentum acts as an exponential weighted average
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

- this means the parameters move with a speed of $\alpha ||g|| \frac{1}{1-\rho}$ 

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

- we can see that the momentum acts as an exponential weighted average
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

- this means the parameters move with a speed of $\alpha ||g|| \frac{1}{1-\rho}$ 



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

$$
\begin{split}
g &= \nabla\mathcal{R}(\theta) \\
r &= r +  g \odot g \\
\theta &=\theta - \frac{1}{\sqrt{r}+\epsilon} \odot \alpha g \\
\end{split}
$$

### RMSProp
- **Goal:** Fix the aggressive decay of AdaGrad to work in non-convex settings (like Neural Networks).
- **Mechanism:** Use an **exponential moving average** of squared gradients.
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
