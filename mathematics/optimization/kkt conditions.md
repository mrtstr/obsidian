### kkt conditions
- provide an alternative nesseary optimality condition for [[constraint optimization problem]] that does not rely on the [[linearized cone]]
- if $x^*$ is a [[local minimum]] and a [[constraint qualification]] holds in $x^*$
- then there exists lagrange multipliers $\lambda^* \in \mathbb{R}^n$ and $\mu^* \in \mathbb{R}^k$ that satisfy the [[kkt conditions]]

#### stationarity
$$
\nabla f\left(x^*\right) = \nabla h\left(x^*\right) \mu^* = \nabla g\left(x^*\right) \lambda^*
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
 \nabla h\left(x^*\right)^\top \mu^* = 0
$$

- either $\mu^*_i = 0 \Leftrightarrow$ 
	- inequality constraint is $h_i$ is [[active set|inactive]] / $h_i$ does not bind
	- no shadow price because 
- or $\nabla h\left(x^*\right)=0 \Leftrightarrow$
	- or the inequality constraint is [[active set|active]]
- neither can happen e.g. when the optimum of $f$ is in a point where $h(x)=0$
- both cant happen because that would mean that a non-active inequality condition would prevent a better solution

# -------------------------
![[constraint optimization problem#constraint optimization problem]]

![[constraint optimization optimality criteria#necessary optimality condition of first order]]

![[constraint optimization optimality criteria#necessary optimality condition of second order]]



START
Basic
[[kkt conditions]]
- defintion
- what are they used for?

Back: 
### kkt conditions
- provide an alternative nesseary optimality condition for [[constraint optimization problem]] that does not rely on the [[linearized cone]]
- if $x^*$ is a [[local minimum]] and a [[constraint qualification]] holds in $x^*$
- then there exists lagrange multipliers $\lambda^* \in \mathbb{R}^n$ and $\mu^* \in \mathbb{R}^k$ that satisfy the [[kkt conditions]]

#### stationarity
$$
\nabla f\left(x^*\right) = \nabla h\left(x^*\right) \mu^* = \nabla g\left(x^*\right) \lambda^*
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
 \nabla h\left(x^*\right)^\top \mu^* = 0
$$

- either $\mu^*_i = 0 \Leftrightarrow$ 
	- inequality constraint is $h_i$ is [[active set|inactive]] / $h_i$ does not bind
	- no shadow price because 
- or $\nabla h\left(x^*\right)=0 \Leftrightarrow$
	- or the inequality constraint is [[active set|active]]
- neither can happen e.g. when the optimum of $f$ is in a point where $h(x)=0$
- both cant happen because that would mean that a non-active inequality condition would prevent a better solution


___________________________

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

### necessary optimality condition of first order
- given an [[constraint optimization problem]]
- lf $x^*$ is a [[local minimum]] and a [[constraint qualification]] holds in $x^*$ then the following is true
$$
\begin{split}
&g\left(x^*\right) = 0, h\left(x^*\right) \geq 0  \\
&\forall d \in \mathcal{L}\left(\mathcal{F}, x^*\right): \nabla f\left(x^*\right)^\top d \geq 0
\end{split}
$$
- every point $x^*$ that satisfies this conditions is called a **stationary point**
#### interpretation
- when a [[constraint qualification]] is statisfied the [[linearized cone]] is eqivalent to the [[tanget cone]] and thus the [[set]] of all directions that do not point outside the [[feasible set]]
- thus the **necessary optimality condition of first order** says the point $x^* \in \mathcal{F}$ is in the [[feasible set]] and that there are no feasable directions $d \in \mathcal{L}\left(\mathcal{F}, x^*\right)$ that can improve the objective function $f$


### necessary optimality condition of second order
- given an [[constraint optimization problem]]
- lf $x^*$ is a [[local minimum]] and a [[constraint qualification]] holds in $x^*$ then the [[hessian]] is [[positive definite|PSD]] for all [[feasible set|feasable]] directions and $x^*$ is a **stationary point**
$$
\begin{split}
&x^* \text{ is a stationary point} \\
&\forall d \in \mathcal{L}\left(\mathcal{F}, x^*\right): d^\top\nabla^2 f\left(x^*\right)d^\top \geq 0
\end{split}
$$
- this is eqivalent to the [[unconstraint optimization optimality criteria#necessary optimality condition of second order|necessary optimality condition of second order for unconstraint problems]] with the difference that we restrict the condition on [[feasible set|feasable]] directions


### feasible set
- given an [[constraint optimization problem]]
- the feasible [[set]] contains all points where the contraints are satisfied
$$
\mathcal{F} = \{x \in \mathbb{R}^m : g(x) = 0\land h(x) \geq 0\}
$$


Tags: mathematics
<!--ID: 1721674950988-->
END


START
Basic
[[kkt conditions]]
- defintion
- interpretation
- What does it mean when $\mu_i=0$ and $\nabla h(x^*)_i=0$? Can both or neither be zero and why?
- What would $\mu^* \leq 0$ mean?

Back: 
### kkt conditions
- provide an alternative nesseary optimality condition for [[constraint optimization problem]] that does not rely on the [[linearized cone]]
- if $x^*$ is a [[local minimum]] and a [[constraint qualification]] holds in $x^*$
- then there exists lagrange multipliers $\lambda^* \in \mathbb{R}^n$ and $\mu^* \in \mathbb{R}^k$ that satisfy the [[kkt conditions]]

#### stationarity
$$
\nabla f\left(x^*\right) = \nabla h\left(x^*\right) \mu^* = \nabla g\left(x^*\right) \lambda^*
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
 \nabla h\left(x^*\right)^\top \mu^* = 0
$$

- either $\mu^*_i = 0 \Leftrightarrow$ 
	- inequality constraint is $h_i$ is [[active set|inactive]] / $h_i$ does not bind
	- no shadow price because 
- or $\nabla h\left(x^*\right)=0 \Leftrightarrow$
	- or the inequality constraint is [[active set|active]]
- neither can happen e.g. when the optimum of $f$ is in a point where $h(x)=0$
- both cant happen because that would mean that a non-active inequality condition would prevent a better solution


___________________________

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

### necessary optimality condition of first order
- given an [[constraint optimization problem]]
- lf $x^*$ is a [[local minimum]] and a [[constraint qualification]] holds in $x^*$ then the following is true
$$
\begin{split}
&g\left(x^*\right) = 0, h\left(x^*\right) \geq 0  \\
&\forall d \in \mathcal{L}\left(\mathcal{F}, x^*\right): \nabla f\left(x^*\right)^\top d \geq 0
\end{split}
$$
- every point $x^*$ that satisfies this conditions is called a **stationary point**
#### interpretation
- when a [[constraint qualification]] is statisfied the [[linearized cone]] is eqivalent to the [[tanget cone]] and thus the [[set]] of all directions that do not point outside the [[feasible set]]
- thus the **necessary optimality condition of first order** says the point $x^* \in \mathcal{F}$ is in the [[feasible set]] and that there are no feasable directions $d \in \mathcal{L}\left(\mathcal{F}, x^*\right)$ that can improve the objective function $f$


### necessary optimality condition of second order
- given an [[constraint optimization problem]]
- lf $x^*$ is a [[local minimum]] and a [[constraint qualification]] holds in $x^*$ then the [[hessian]] is [[positive definite|PSD]] for all [[feasible set|feasable]] directions and $x^*$ is a **stationary point**
$$
\begin{split}
&x^* \text{ is a stationary point} \\
&\forall d \in \mathcal{L}\left(\mathcal{F}, x^*\right): d^\top\nabla^2 f\left(x^*\right)d^\top \geq 0
\end{split}
$$
- this is eqivalent to the [[unconstraint optimization optimality criteria#necessary optimality condition of second order|necessary optimality condition of second order for unconstraint problems]] with the difference that we restrict the condition on [[feasible set|feasable]] directions


### feasible set
- given an [[constraint optimization problem]]
- the feasible [[set]] contains all points where the contraints are satisfied
$$
\mathcal{F} = \{x \in \mathbb{R}^m : g(x) = 0\land h(x) \geq 0\}
$$


Tags: mathematics
<!--ID: 1721728965048-->
END


START
Basic
relationship between [[kkt conditions]] and [[constraint qualification]]

Back: 
- Only when a [[constraint qualification]] holds a [[local minimum]] has to be nessarily a [[kkt conditions|kkt point]]

### constraint qualification
- when a [[constraint qualification]] holds in a [[feasible set|feasible point]] $\bar x$ the [[linearized cone]] and the [[tanget cone]] are eqivalent

$$
\mathcal{T}(\mathcal{F}, \bar x) = \mathcal{L}(\mathcal{F}, \bar x)
$$


### kkt conditions
- provide an alternative nesseary optimality condition for [[constraint optimization problem]] that does not rely on the [[linearized cone]]
- if $x^*$ is a [[local minimum]] and a [[constraint qualification]] holds in $x^*$
- then there exists lagrange multipliers $\lambda^* \in \mathbb{R}^n$ and $\mu^* \in \mathbb{R}^k$ that satisfy the [[kkt conditions]]

#### stationarity
$$
\nabla f\left(x^*\right) = \nabla h\left(x^*\right) \mu^* = \nabla g\left(x^*\right) \lambda^*
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
 \nabla h\left(x^*\right)^\top \mu^* = 0
$$

- either $\mu^*_i = 0 \Leftrightarrow$ 
	- inequality constraint is $h_i$ is [[active set|inactive]] / $h_i$ does not bind
	- no shadow price because 
- or $\nabla h\left(x^*\right)=0 \Leftrightarrow$
	- or the inequality constraint is [[active set|active]]
- neither can happen e.g. when the optimum of $f$ is in a point where $h(x)=0$
- both cant happen because that would mean that a non-active inequality condition would prevent a better solution


___________________________

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

### necessary optimality condition of first order
- given an [[constraint optimization problem]]
- lf $x^*$ is a [[local minimum]] and a [[constraint qualification]] holds in $x^*$ then the following is true
$$
\begin{split}
&g\left(x^*\right) = 0, h\left(x^*\right) \geq 0  \\
&\forall d \in \mathcal{L}\left(\mathcal{F}, x^*\right): \nabla f\left(x^*\right)^\top d \geq 0
\end{split}
$$
- every point $x^*$ that satisfies this conditions is called a **stationary point**
#### interpretation
- when a [[constraint qualification]] is statisfied the [[linearized cone]] is eqivalent to the [[tanget cone]] and thus the [[set]] of all directions that do not point outside the [[feasible set]]
- thus the **necessary optimality condition of first order** says the point $x^* \in \mathcal{F}$ is in the [[feasible set]] and that there are no feasable directions $d \in \mathcal{L}\left(\mathcal{F}, x^*\right)$ that can improve the objective function $f$


### necessary optimality condition of second order
- given an [[constraint optimization problem]]
- lf $x^*$ is a [[local minimum]] and a [[constraint qualification]] holds in $x^*$ then the [[hessian]] is [[positive definite|PSD]] for all [[feasible set|feasable]] directions and $x^*$ is a **stationary point**
$$
\begin{split}
&x^* \text{ is a stationary point} \\
&\forall d \in \mathcal{L}\left(\mathcal{F}, x^*\right): d^\top\nabla^2 f\left(x^*\right)d^\top \geq 0
\end{split}
$$
- this is eqivalent to the [[unconstraint optimization optimality criteria#necessary optimality condition of second order|necessary optimality condition of second order for unconstraint problems]] with the difference that we restrict the condition on [[feasible set|feasable]] directions


### feasible set
- given an [[constraint optimization problem]]
- the feasible [[set]] contains all points where the contraints are satisfied
$$
\mathcal{F} = \{x \in \mathbb{R}^m : g(x) = 0\land h(x) \geq 0\}
$$


Tags: mathematics
<!--ID: 1721728965052-->
END