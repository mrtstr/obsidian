### learning rate scheduling
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



### learning rate scheduling for LLMs
- large models are extremely sensitive to the learning rate
- a learning rate scheduling ensures
	- stable early training
	- fast convergence
	- avoid divergence / loss spikes
- there are two stages **warm-up phase** and the **decay phase**

#### warm-up phase
- start slow and linear increase util the maximum learning rate $\eta_\mathrm{max}$ is reached after $T_\mathrm{warmup}$ steps
- prevents unstable gradients when weights are still random
$$
\eta(t) = \eta_\mathrm{max} \cdot \frac{1}{T_\mathrm{warmup}}
$$

#### decay phase
- after warm-up, LR gradually decreases for **smooth convergence** and **reduced loss oscillations** using cosine decay

$$
\eta(t) = \eta_\mathrm{min} + \frac{1}{2} (\eta_\mathrm{max} - \eta_\mathrm{min}) \cdot \left(1+\cos\left(\pi\frac{t-T_\mathrm{warmup}}{T_\mathrm{total} -T_\mathrm{warmup}}\right)\right)
$$

![[Pasted image 20251124144429.png]]

# ----------------

![[adam optimizer#adam optimizer]]


# anki

START
Basic
[[learning rate scheduling]]
- why is it important for LLM training?
- two phases with goal and equation

Back: 
### learning rate scheduling
- large models are extremely sensitive to the learning rate
- a learning rate scheduling ensures
	- stable early training
	- fast convergence
	- avoid divergence / loss spikes
- there are two stages **warm-up phase** and the **decay phase**

#### warm-up phase
- start slow and linear increase util the maximum learning rate $\eta_\mathrm{max}$ is reached after $T_\mathrm{warmup}$ steps
- prevents unstable gradients when weights are still random
$$
\eta(t) = \eta_\mathrm{max} \cdot \frac{1}{T_\mathrm{warmup}}
$$

#### decay phase
- after warm-up, LR gradually decreases for **smooth convergence** and **reduced loss oscillations** using cosine decay

$$
\eta(t) = \eta_\mathrm{min} + \frac{1}{2} (\eta_\mathrm{max} - \eta_\mathrm{min}) \cdot \left(1+\cos\left(\pi\frac{t-T_\mathrm{warmup}}{T_\mathrm{total} -T_\mathrm{warmup}}\right)\right)
$$

![[Pasted image 20251124145547.png]]

Tags: ml WS2526
<!--ID: 1763995026501-->
END


# anki


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
<!--ID: 1769529258452-->
END
