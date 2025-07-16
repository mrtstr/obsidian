### feature map
- (typically **non-learnable**) function $\varphi: \mathcal{X} \to \mathbb{R}^d$ that transforms the input features into a new representation, often to make learning easier or enable linear models to capture non-linear relationships.
Used in:
- [[linear models]] to enable them to learn **non-linear** functions via linear methods.
- [[neural networks]] as fixed feature extractors (e.g., embeddings, basis expansions), although modern networks often learn the feature map implicitly.
##### examples
- often a learnable bias that does not depend on the input is added

$$
\varphi\left(\left[\begin{matrix}x_1 \\ x_2\end{matrix}\right]\right)
=
\left[\begin{matrix}1 \\x_1 \\ x_2\end{matrix}\right]
$$
- example: [[polynomial]] feature map (second-order):

$$
\varphi\left(\left[\begin{matrix}x_1 \\ x_2\end{matrix}\right]\right)
=
\left[\begin{matrix}1 \\x_1\\x_2 \\ x_1^2 \\ x_2^2 \\ x_1x_2\end{matrix}\right]
$$
# anki


START
Basic
[[feature map]]
- concept
- where is it used
- example
- what is a bias in that context?

Back: 
### feature map
- (typically **non-learnable**) function $\varphi: \mathcal{X} \to \mathbb{R}^d$ that transforms the input features into a new representation, often to make learning easier or enable linear models to capture non-linear relationships.
Used in:
- [[linear models]] to enable them to learn **non-linear** functions via linear methods.
- [[neural networks]] as fixed feature extractors (e.g., embeddings, basis expansions), although modern networks often learn the feature map implicitly.
##### examples
- often a learnable bias that does not depend on the input is added

$$
\varphi\left(\left[\begin{matrix}x_1 \\ x_2\end{matrix}\right]\right)
=
\left[\begin{matrix}1 \\x_1 \\ x_2\end{matrix}\right]
$$
- example: [[polynomial]] feature map (second-order):

$$
\varphi\left(\left[\begin{matrix}x_1 \\ x_2\end{matrix}\right]\right)
=
\left[\begin{matrix}1 \\x_1\\x_2 \\ x_1^2 \\ x_2^2 \\ x_1x_2\end{matrix}\right]
$$

______________
### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon]=I\sigma^2$
- with the [[feature map]] $\varphi: \mathcal{X} \to \mathbb{R}^s$
$$
\begin{split}
Y 
&= \varphi(X) \theta + \epsilon \sim \mathcal{N}(\varphi(X) \theta, \sigma^ I) \\
&= \sum_{j \in [S]} \varphi(X_{(*, j)}) \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} \varphi(X_{(i, j)}) \theta_j + \epsilon_i \\
\end{split}
$$



Tags: mathematics statistics SS25
<!--ID: 1752658871318-->
END