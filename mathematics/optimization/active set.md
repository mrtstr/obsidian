### active set
- let $\bar x \in \mathcal{F}$ be a [[feasible set|feasible point]] with the inequality constraints $h_1(x), ..., h_1(x)$
- the [[active set]] is the containts the indices of inequality constraints that are zero
$$
\mathcal{A}(\bar x) = \left\{i \in [k]: h_i(\bar x) = 0\right\}
$$
- the inactive set contains the indices of inequality constraints greater zero

# ---------------------
![[constraint optimization problem#constraint optimization problem]]

![[feasible set#feasible set]]


START
Basic
definition for [[active set]]

Back: 
### active set
- let $\bar x \in \mathcal{F}$ be a [[feasible set|feasible point]] with the inequality constraints $h_1(x), ..., h_1(x)$
- the [[active set]] is the containts the indices of inequality constraints that are zero
$$
\mathcal{A}(\bar x) = \left\{i \in [k]: h_i(\bar x) = 0\right\}
$$
- the inactive set contains the indices of inequality constraints greater zero

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

### feasible set
- given an [[constraint optimization problem]]
- the feasible [[set]] contains all points where the contraints are satisfied
$$
\mathcal{F} = \{x \in \mathbb{R}^m : g(x) = 0\land h(x) \geq 0\}
$$


Tags: mathematics
<!--ID: 1721672977468-->
END