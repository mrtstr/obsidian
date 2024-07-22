### linearized cone
- given a [[feasible set]] $\mathcal{F}$ and a point $\bar{x} \in \mathcal{F}$
- the [[linearized cone]] of $\mathcal{F}$ in $\bar x$ is defined as follows
$$
\mathcal{L}(\mathcal{F}, \bar x) = \left\{d \in \mathbb{R}^m : \nabla g(\bar x)^\top d = 0 \land \nabla h(\bar x)^\top d \geq 0 \right\}
$$
- can be used instead of the [[tanget cone]] (directions that do not point outside the [[feasible set]]) when a [[constraint qualification]] is satisfied because its easier wo work with
- the [[linearized cone]] is a superset of the [[tanget cone]] but when a [[constraint qualification]] holds they are eqivalent
$$
\mathcal{T}(\mathcal{F}, \bar x) \subset \mathcal{L}(\mathcal{F}, \bar x)
$$

![[IMG-20240722-WA0000 2.jpg]]

# -----------------
![[tanget cone#tanget cone]]

![[cone#cone]]

![[constraint qualification#constraint qualification]]

START
Basic
[[linearized cone]]
- definition and general [[cone]]
- relationship to the [[tanget cone]] (no proof)

Back: 
### linearized cone
- given a [[feasible set]] $\mathcal{F}$ and a point $\bar{x} \in \mathcal{F}$
- the [[linearized cone]] of $\mathcal{F}$ in $\bar x$ is defined as follows
$$
\mathcal{L}(\mathcal{F}, \bar x) = \left\{d \in \mathbb{R}^m : \nabla g(\bar x)^\top d = 0 \land \nabla h(\bar x)^\top d \geq 0 \right\}
$$


![[IMG-20240722-WA0000 3.jpg]]

- can be used instead of the [[tanget cone]] (directions that do not point outside the [[feasible set]]) when a [[constraint qualification]] is satisfied because its easier wo work with
- the [[linearized cone]] is a superset of the [[tanget cone]] but when a [[constraint qualification]] holds they are eqivalent

$$
\mathcal{T}(\mathcal{F}, \bar x) \subset \mathcal{L}(\mathcal{F}, \bar x)
$$
_______________________

### cone
- a [[set]] $C$ is a [[cone]] if it satisfies the following condition
$$
x \in C \Rightarrow \forall \lambda>0:  \lambda x \in C: 
$$


### tanget cone
- given a [[feasible set]] $\mathcal{F}$ and a point $\bar{x} \in \mathcal{F}$
- the [[tanget cone]] of $\mathcal{F}$ in $\bar x$ is defined as follows

$$
\mathcal{T}(\mathcal{F}, \bar x) = \left\{d \in \mathbb{R}^m: \exists t^{(k)}, x^{(k)} \in \mathcal{F}: \lim_{k \to \infty} x^{(k)} = \bar x, \lim_{k \to \infty } t^{(k)} \left(x-x^{(k)}\right) = d \right\}
$$


### constraint qualification
- when a [[constraint qualification]] holds in a [[feasible set|feasible point]] $\bar x$ the [[linearized cone]] and the [[tanget cone]] are eqivalent

$$
\mathcal{T}(\mathcal{F}, \bar x) = \mathcal{L}(\mathcal{F}, \bar x)
$$


Tags: mathematics
<!--ID: 1721589221962-->
END