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
<!--ID: 1769357465562-->
END