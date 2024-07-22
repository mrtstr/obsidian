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

### sufficient optimality condition of second order
- given an [[constraint optimization problem]]
- a **stationary point** $x^*$ with a [[positive definite]] [[hessian]]  for all [[feasible set|feasable]] is a [[local minimum]] 
$$
\begin{split}
&\forall d \in \mathcal{L}\left(\mathcal{F}, x^*\right): d^\top\nabla^2 f\left(x^*\right)d^\top > 0
\end{split}
$$
- this is eqivalent to the [[unconstraint optimization optimality criteria#sufficient optimality condition of second order|sufficient optimality condition of second order for uncontrains problems]] with the difference that we restrict the condition on [[feasible set|feasable]] directions

# ---------------------------

![[constraint optimization problem#constraint optimization problem]]

![[linearized cone#linearized cone]]

# anki

START
Basic
necessary optimality condition of first order for [[constraint optimization problem]]
- definition
- interpretation

definition stationary point
Back: 
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
- 

### linearized cone
- given a [[feasible set]] $\mathcal{F}$ and a point $\bar{x} \in \mathcal{F}$
- the [[linearized cone]] of $\mathcal{F}$ in $\bar x$ is defined as follows
$$
\mathcal{L}(\mathcal{F}, \bar x) = \left\{d \in \mathbb{R}^m : \nabla g(\bar x)^\top d = 0 \land \nabla h(\bar x)^\top d \geq 0 \right\}
$$
- can be used instead of the [[tanget cone]] under certain conditions because its easier wo work with
- the [[linearized cone]] is a superset of the [[tanget cone]]
$$
\mathcal{T}(\mathcal{F}, \bar x) \subset \mathcal{L}(\mathcal{F}, \bar x)
$$

![[IMG-20240722-WA0000 1.jpg]]

_____________________________

### constraint qualification
- when a [[constraint qualification]] holds in a [[feasible set|feasible point]] $\bar x$ the [[linearized cone]] and the [[tanget cone]] are eqivalent

$$
\mathcal{T}(\mathcal{F}, \bar x) = \mathcal{L}(\mathcal{F}, \bar x)
$$


### feasible set
- given an [[constraint optimization problem]]
- the feasible [[set]] contains all points where the contraints are satisfied
$$
\mathcal{F} = \{x \in \mathbb{R}^m : g(x) = 0\land h(x) \geq 0\}
$$

### tanget cone
- given a [[feasible set]] $\mathcal{F}$ and a point $\bar{x} \in \mathcal{F}$
- the [[tanget cone]] of $\mathcal{F}$ in $\bar x$ is defined as follows

$$
\mathcal{T}(\mathcal{F}, \bar x) = \left\{d \in \mathbb{R}^m: \exists t^{(k)}, x^{(k)} \in \mathcal{F}: \lim_{k \to \infty} x^{(k)} = \bar x, \lim_{k \to \infty } t^{(k)} \left(x-x^{(k)}\right) = d \right\}
$$

- it's hard to works with the [[tanget cone]] because it is asking for the existence of infinite [[series]] but when a [[constraint qualification]] is satisfied its prossible to work with the [[linearized cone]] $\mathcal{L} \supset \mathcal{T}$
- the [[tanget cone]] contains all directions that does not point outside if the [[feasible set]]

### cone
- a [[set]] $C$ is a [[cone]] if it satisfies the following condition
$$
x \in C \Rightarrow \forall \lambda>0:  \lambda x \in C: 
$$


Tags: mathematics
<!--ID: 1721636790452-->
END

START
Basic
necessary optimality condition of second order for [[constraint optimization problem]]
- definition
- difference to the [[unconstraint optimization optimality criteria|unconstraint case]]

definition stationary point
Back: 
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


### linearized cone
- given a [[feasible set]] $\mathcal{F}$ and a point $\bar{x} \in \mathcal{F}$
- the [[linearized cone]] of $\mathcal{F}$ in $\bar x$ is defined as follows
$$
\mathcal{L}(\mathcal{F}, \bar x) = \left\{d \in \mathbb{R}^m : \nabla g(\bar x)^\top d = 0 \land \nabla h(\bar x)^\top d \geq 0 \right\}
$$
- can be used instead of the [[tanget cone]] under certain conditions because its easier wo work with
- the [[linearized cone]] is a superset of the [[tanget cone]]
$$
\mathcal{T}(\mathcal{F}, \bar x) \subset \mathcal{L}(\mathcal{F}, \bar x)
$$

![[IMG-20240722-WA0000 4.jpg]]

_____________________________

### constraint qualification
- when a [[constraint qualification]] holds in a [[feasible set|feasible point]] $\bar x$ the [[linearized cone]] and the [[tanget cone]] are eqivalent

$$
\mathcal{T}(\mathcal{F}, \bar x) = \mathcal{L}(\mathcal{F}, \bar x)
$$


### feasible set
- given an [[constraint optimization problem]]
- the feasible [[set]] contains all points where the contraints are satisfied
$$
\mathcal{F} = \{x \in \mathbb{R}^m : g(x) = 0\land h(x) \geq 0\}
$$

### tanget cone
- given a [[feasible set]] $\mathcal{F}$ and a point $\bar{x} \in \mathcal{F}$
- the [[tanget cone]] of $\mathcal{F}$ in $\bar x$ is defined as follows

$$
\mathcal{T}(\mathcal{F}, \bar x) = \left\{d \in \mathbb{R}^m: \exists t^{(k)}, x^{(k)} \in \mathcal{F}: \lim_{k \to \infty} x^{(k)} = \bar x, \lim_{k \to \infty } t^{(k)} \left(x-x^{(k)}\right) = d \right\}
$$

- it's hard to works with the [[tanget cone]] because it is asking for the existence of infinite [[series]] but when a [[constraint qualification]] is satisfied its prossible to work with the [[linearized cone]] $\mathcal{L} \supset \mathcal{T}$
- the [[tanget cone]] contains all directions that does not point outside if the [[feasible set]]

### cone
- a [[set]] $C$ is a [[cone]] if it satisfies the following condition
$$
x \in C \Rightarrow \forall \lambda>0:  \lambda x \in C: 
$$


### necessary optimality condition of second order for unconstraind problems
- let $x^*$ be a [[local minimum]] then the [[gradient]] has to be zero and its [[hessian]] has to be a [[definiteness of matrices#positive semi definite matrix|positive semi definite matrix]]

$$
\nabla f(x^*) = 0 \land \nabla^2 f(x^*) \text{ is positive semidefinite}
$$
- example for a non [[local minimum]] that satisfies the condition: $f(x) = x^3$ with $x^* =0$ 


Tags: mathematics
<!--ID: 1721639533575-->
END

START
Basic
sufficient optimality condition of second order for [[constraint optimization problem]]
- definition
- difference to the [[unconstraint optimization optimality criteria|unconstraint case]]

Back: 

### sufficient optimality condition of second order
- given an [[constraint optimization problem]]
- a **stationary point** $x^*$ with a [[positive definite]] [[hessian]]  for all [[feasible set|feasable]] is a [[local minimum]] 
$$
\begin{split}
&\forall d \in \mathcal{L}\left(\mathcal{F}, x^*\right): d^\top\nabla^2 f\left(x^*\right)d^\top > 0
\end{split}
$$
- this is eqivalent to the [[unconstraint optimization optimality criteria#sufficient optimality condition of second order|sufficient optimality condition of second order for uncontrains problems]] with the difference that we restrict the condition on [[feasible set|feasable]] directions


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



### linearized cone
- given a [[feasible set]] $\mathcal{F}$ and a point $\bar{x} \in \mathcal{F}$
- the [[linearized cone]] of $\mathcal{F}$ in $\bar x$ is defined as follows
$$
\mathcal{L}(\mathcal{F}, \bar x) = \left\{d \in \mathbb{R}^m : \nabla g(\bar x)^\top d = 0 \land \nabla h(\bar x)^\top d \geq 0 \right\}
$$
- can be used instead of the [[tanget cone]] under certain conditions because its easier wo work with
- the [[linearized cone]] is a superset of the [[tanget cone]]
$$
\mathcal{T}(\mathcal{F}, \bar x) \subset \mathcal{L}(\mathcal{F}, \bar x)
$$

![[IMG-20240722-WA0000 5.jpg]]

_____________________________

### sufficient optimality condition of second order
- let $x^*$ be a point with [[gradient]] that is zero and its [[hessian]] has to be a [[definiteness of matrices#positive semi definite matrix|positive definite matrix]] then it has to be a [[local minimum]]

$$
\nabla f(x^*) = 0 \land \nabla^2 f(x^*) \text{ is positive definite}
$$

- example for a [[local minimum]] that does not satisfyhe condition: $f(x) = x^4$ with $x^* =0$ 

### constraint qualification
- when a [[constraint qualification]] holds in a [[feasible set|feasible point]] $\bar x$ the [[linearized cone]] and the [[tanget cone]] are eqivalent

$$
\mathcal{T}(\mathcal{F}, \bar x) = \mathcal{L}(\mathcal{F}, \bar x)
$$


### feasible set
- given an [[constraint optimization problem]]
- the feasible [[set]] contains all points where the contraints are satisfied
$$
\mathcal{F} = \{x \in \mathbb{R}^m : g(x) = 0\land h(x) \geq 0\}
$$

### tanget cone
- given a [[feasible set]] $\mathcal{F}$ and a point $\bar{x} \in \mathcal{F}$
- the [[tanget cone]] of $\mathcal{F}$ in $\bar x$ is defined as follows

$$
\mathcal{T}(\mathcal{F}, \bar x) = \left\{d \in \mathbb{R}^m: \exists t^{(k)}, x^{(k)} \in \mathcal{F}: \lim_{k \to \infty} x^{(k)} = \bar x, \lim_{k \to \infty } t^{(k)} \left(x-x^{(k)}\right) = d \right\}
$$

- it's hard to works with the [[tanget cone]] because it is asking for the existence of infinite [[series]] but when a [[constraint qualification]] is satisfied its prossible to work with the [[linearized cone]] $\mathcal{L} \supset \mathcal{T}$
- the [[tanget cone]] contains all directions that does not point outside if the [[feasible set]]

### cone
- a [[set]] $C$ is a [[cone]] if it satisfies the following condition
$$
x \in C \Rightarrow \forall \lambda>0:  \lambda x \in C: 
$$



Tags: mathematics
<!--ID: 1721639533581-->
END

