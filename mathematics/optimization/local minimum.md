### local minimum
- given a [[function]] $f: X \to Y$
- the point $x^* \in X$ is called a [[local minimum]] if the following is true

$$
\forall y \in B_\epsilon(x^*) : f(x^*) \leq f(y)
$$

- with $\epsilon \to \infty$ the local minumum $x^*$ becomes a global minimum 
- if $\leq$ is replaced by $<$ the minimum $x^*$ becomes a strick minimum
- for a [[convex function]] $f(x)$ every [[local minimum]] is a gloabl [[minimum]]  

### local minimum for a constraint optimization problem
- given a [[constraint optimization problem]] with an objective [[function]] $f: X \to Y$ and a [[feasible set]] $\mathcal{F}$
- the point $x^* \in \mathcal{F}$ is called a [[local minimum]] if the following is true

$$
\forall y \in B_\epsilon(x^*) \cup \mathcal{F} : f(x^*) \leq f(y)
$$

# -----------------

![[ball#ball]]

![[constraint optimization problem#constraint optimization problem]]

![[feasible set#feasible set]]

START
Basic
[[local minimum]]
- definition
- difference strict and global minimum
- when are gloabla and local minima equivalent?
Back: 
### local minimum
- given a [[function]] $f: X \to Y$
- the point $x^* \in X$ is called a [[local minimum]] if the following is true

$$
\forall y \in B_\epsilon(x^*) : f(x^*) \leq f(y)
$$

- with $\epsilon \to \infty$ the local minumum $x^*$ becomes a global minimum 
- if $\leq$ is replaced by $<$ the minimum $x^*$ becomes a strick minimum
- for a [[convex function]] $f(x)$ every [[local minimum]] is a gloabl [[minimum]]  
### ball
- given a [[set]] $A$ with a [[metric]] $d(\cdot,\cdot)$
- for each $x \in A$ and $\epsilon > 0$ the $\epsilon$-ball ($\epsilon$-nighbouhood) is defined as follows

$$
B_\epsilon(x) = \{y \in A: d(x, y) < \epsilon\}
$$
Tags: mathematics
<!--ID: 1720971143048-->
END


START
Basic
definition for [[local minimum]] in a [[constraint optimization problem]]

Back: 

### local minimum for a constraint optimization problem
- given a [[constraint optimization problem]] with an objective [[function]] $f: X \to Y$ and a [[feasible set]] $\mathcal{F}$
- the point $x^* \in \mathcal{F}$ is called a [[local minimum]] if the following is true

$$
\forall y \in B_\epsilon(x^*) \cup \mathcal{F} : f(x^*) \leq f(y)
$$

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



### feasible set
- given an [[constraint optimization problem]]
- the feasible [[set]] contains all points where the contraints are satisfied
$$
\mathcal{F} = \{x \in \mathbb{R}^m : g(x) = 0\land h(x) \geq 0\}
$$


### ball
- given a [[set]] $A$ with a [[metric]] $d(\cdot,\cdot)$
- for each $x \in A$ and $\epsilon > 0$ the $\epsilon$-ball ($\epsilon$-nighbouhood) is defined as follows

$$
B_\epsilon(x) = \{y \in A: d(x, y) < \epsilon\}
$$
Tags: mathematics
<!--ID: 1721589221973-->
END