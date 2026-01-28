## activation function

![[softmax function#softmax function]]

![[rectified linear unit#rectified linear unit]]

![[hyperbolic tangent#hyperbolic tangent]]

![[softsign function#softsign function]]

![[sigmoid function#sigmoid function]]


# anki

START
Basic
[[activation function]] (5)

Back: 
### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z) 
&= \frac{\exp{(Z_{(i,j)})}}{\sum_{k} \exp{(Z_{(i,k)})}}
\end{split}
$$

- used as output function in [[classification]] problems, for example with [[neural network]] and [[multinomial logistic regresssion]]


### rectified linear unit
- most widely used [[activation function]] for hidden layers of [[neural network]] 
- $\mathrm{ReLu}: \mathbb{R} \to \mathbb{R}^+$ is defined as follows

$$
\mathrm{ReLu}(z)=\max(0, z)
$$

### sigmoid function
- the [[sigmoid function]] $\sigma: \mathbb{R} \to (0,1)$ is defined as follows:
- its the inverse of the [[logit function]]

$$
\sigma(u) = \frac{1}{1+e^{-u}}
$$

#### properties
$$
\sigma(0) = \frac{1}{2}
$$

$$
\begin{split}
\lim_{u\to\infty}\sigma(u) &= 1 \\
\lim_{u\to-\infty}\sigma(u) &= 0 \\
\end{split}
$$

$$
1-\sigma(u) = \frac{1}{1+e^{+u}} = \sigma(-u)
$$

### hyperbolic tangent
- the [[hyperbolic tangent]] can be used as [[activation function]] for [[neural network]] and is defined a $\tanh: \mathbb{R} \to (-1, 1)$

$$
\tanh(z) = \frac{e^z - e^{-z}}{e^z + e^{-z}}
$$

- the [[hyperbolic tangent]] is a scaled and shifted version of the [[sigmoid function]] in a way that it's zero centered and is mapping to $(-1, 1)$

$$
\begin{split}
\tanh(z) &= 2\sigma(2z)-1 \\
\sigma(z) &= \frac{1+\tanh\left(\frac{z}{2}\right)}{2} \\
\end{split}
$$


$$
\begin{split}
\tanh(z) 
&= 2\sigma(2z)-1 \\
&= \frac{2}{1+e^{-2z}}-1 \\
&= \frac{1-e^{-2z}}{1+e^{-2z}} \\
&= \frac{e^{z}-e^{-z}}{e^{z}+e^{-z}} \\
\end{split}
$$

### softsign function
- the [[softsign function]] can be used as [[activation function]] for [[neural network]] and is defined a $\mathrm{softsign}: \mathbb{R} \to (-1, 1)$

$$
\mathrm{softsign}(z) = \frac{z}{1+|z|}
$$

- similar shape to the [[hyperbolic tangent]] in a sense that its mapping to $(-1, 1)$ and is centered around zero but is smoother
	→ computationally simpler and fewer problems with vanishing gradients

Tags: mathematics ml WS2526
<!--ID: 1763312447277-->
END