### tanget cone
- given a [[feasible set]] $\mathcal{F}$ and a point $\bar{x} \in \mathcal{F}$
- the [[tanget cone]] of $\mathcal{F}$ in $\bar x$ is defined as follows

$$
\mathcal{T}(\mathcal{F}, \bar x) = \left\{d \in \mathbb{R}^m: \exists t^{(k)}, x^{(k)} \in \mathcal{F}: \lim_{k \to \infty} x^{(k)} = \bar x, \lim_{k \to \infty } t^{(k)} \left(x-x^{(k)}\right) = d \right\}
$$

![[Nlp_g1_g2_kegel 4.jpg]]

- it's hard to works with the [[tanget cone]] because it is asking for the existence of infinite [[series]] but when a [[constraint qualification]] is satisfied its prossible to work with the [[linearized cone]] $\mathcal{L} \supset \mathcal{T}$

- the [[tanget cone]] contains all directions that does not point outside if the [[feasible set]]
# ---------------

![[feasible set#feasible set]]

![[cone#cone]]

![[linearized cone#linearized cone]]

![[constraint qualification#constraint qualification]]

START
Basic
[[tanget cone]]
- definition and general [[cone]]
- interpretation with pic
- problem with the difintion and what to do instead
Back: 
### tanget cone
- given a [[feasible set]] $\mathcal{F}$ and a point $\bar{x} \in \mathcal{F}$
- the [[tanget cone]] of $\mathcal{F}$ in $\bar x$ is defined as follows

$$
\mathcal{T}(\mathcal{F}, \bar x) = \left\{d \in \mathbb{R}^m: \exists t^{(k)}, x^{(k)} \in \mathcal{F}: \lim_{k \to \infty} x^{(k)} = \bar x, \lim_{k \to \infty } t^{(k)} \left(x-x^{(k)}\right) = d \right\}
$$

![[Nlp_g1_g2_kegel 3.jpg]]

- it's hard to works with the [[tanget cone]] because it is asking for the existence of infinite [[series]] but when a [[constraint qualification]] is satisfied its prossible to work with the [[linearized cone]] $\mathcal{L} \supset \mathcal{T}$
- the [[tanget cone]] contains all directions that does not point outside if the [[feasible set]]

### cone
- a [[set]] $C$ is a [[cone]] if it satisfies the following condition
$$
x \in C \Rightarrow \forall \lambda>0:  \lambda x \in C: 
$$

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


Tags: mathematics
<!--ID: 1721636790461-->
END