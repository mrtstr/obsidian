### feature map
- can be generalized by introducing a function $\varphi: \mathcal{X} \to \mathbb{R}^d$ that transforms the input features
- in this way the model can lean non-linear relationships between input and output

$$
\begin{split}
Y = f_\theta(X) + \epsilon = \varphi(X)^\top\theta  + \epsilon
\end{split}
$$
- often a learnable bias that does not depend on the input is added

$$
\varphi\left(\left[\begin{matrix}x_1 \\ x_2\end{matrix}\right]\right)
=
\left[\begin{matrix}1 \\x_1 \\ x_2\end{matrix}\right]
$$
