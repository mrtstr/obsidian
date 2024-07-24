### lagrangian of a CNLP
- methode for seaching for stanary points of an [[constraint optimization problem]] by tansforming it in an unconstrain optimization problem → searching for [[kkt conditions|kkt points]]
- the [[lagrangian of a CNLP]] is defined as follows:
$$
\mathcal{L}\left(x, \lambda, \mu\right) = f(x) - \lambda^\top  g(x) - \mu^\top  h(x)
$$

- to find [[kkt conditions|kkt points]] we solve the following system of equations:

$$
\begin{split}
\nabla_x \mathcal{L}\left(x, \lambda, \mu\right)&=f(x) - \lambda^\top  \nabla g(x) - \mu^\top  \nabla h(x)= 0 \\
\nabla_\lambda \mathcal{L}\left(x, \lambda, \mu\right)&= g(x)= 0 \\
\nabla_\mu \mathcal{L}\left(x, \lambda, \mu\right)&= h(x) \geq 0 \\
\end{split}
$$
# ---------------------------

![[constraint optimization problem#constraint optimization problem]]

![[kkt conditions#kkt conditions]]


START
Basic
[[lagrangian of a CNLP]]
- what is it used for
- definition
- how to use it
Back: 
### lagrangian of a CNLP
- methode for seaching for stanary points of an [[constraint optimization problem]] by tansforming it in an unconstrain optimization problem → searching for [[kkt conditions|kkt points]]
- the [[lagrangian of a CNLP]] is defined as follows:
$$
\mathcal{L}\left(x, \lambda, \mu\right) = f(x) - \lambda^\top  g(x) - \mu^\top  h(x)
$$

- to find [[kkt conditions|kkt points]] we solve the following system of equations:

$$
\begin{split}
\nabla_x \mathcal{L}\left(x, \lambda, \mu\right)&=f(x) - \lambda^\top  \nabla g(x) - \mu^\top  \nabla h(x)= 0 \\
\nabla_\lambda \mathcal{L}\left(x, \lambda, \mu\right)&= g(x)= 0 \\
\nabla_\mu \mathcal{L}\left(x, \lambda, \mu\right)&= h(x) \geq 0 \\
\end{split}
$$


__________________

### constraint optimization problem
- given an objective [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ 
- given equality constraints $g: \mathbb{R}^m \to \mathbb{R}^n$ 
- given inequality constraints $h: \mathbb{R}^m \to \mathbb{R}^k$ 

$$
\begin{split}
\min_{x \in \mathbb{R}^m} &f(x) \\
\mathrm{s.t.} \: &g(x)=0 \\
&h(x) \geq 0 \\
\end{split}
$$

### kkt conditions
- provide an alternative nesseary optimality condition for [[constraint optimization problem]] that does not rely on the [[linearized cone]]
- if $x^*$ is a [[local minimum]] and a [[constraint qualification]] holds in $x^*$
- then there exists lagrange multipliers $\lambda^* \in \mathbb{R}^n$ and $\mu^* \in \mathbb{R}^k$ that satisfy the [[kkt conditions]]

#### stationarity
$$
\nabla f\left(x^*\right) = \nabla h\left(x^*\right) \mu^* + \nabla g\left(x^*\right) \lambda^*
$$

- the [[gradient]] of the objective function $f$ has to be a [[linear combinations|linear combination]] of the [[gradient|gradient]] of the contraint functions $g$ and $h$ with $\lambda^*$ and $\mu^*$ being the multiplier
- for [[active set|active]] conditions the multiplier $\mu_i^*$ / $\lambda_i^*$ can be interpreted as the shadow price → how much could $f$ be inproved if inequality condition $h_i(x^*)$ would not be there

#### feasibility
$$
 h\left(x^*\right) \geq 0, \: g\left(x^*\right) = 0
$$
#### optimality

$$
\mu^* \geq 0
$$

- the multiplier cant be negative because that would mean that the [[gradient|gradients]] of the objective function $\nabla f_i$ would point in the oposit direction as the [[gradient]] of the inequality contraint $\nabla h_i$ regardien one dimension $i$ → an impovement of $f$ would be possible

#### complementary slackness

$$
 h\left(x^*\right)^\top \mu^* = 0
$$

- either $\mu^*_i = 0 \Leftrightarrow$ 
	- inequality constraint is $h_i$ is [[active set|inactive]] / $h_i$ does not bind
	- no shadow price 
- or $h\left(x^*\right)=0 \Leftrightarrow$
	- the inequality constraint is [[active set|active]]
- neither can happen e.g. when the optimum of $f$ is in a point where $h(x)=0$
- both cant happen because that would mean that a non-active inequality condition would prevent a better solution

Tags: mathematics
<!--ID: 1721728965042-->
END