

### cauchy sequence
- given a [[metric]] [[vector space|space]] $(X, d)$
- a [[sequence]] $x_n$ is a [[cauchy sequence]] if the following is true

$$
\forall \epsilon > 0:\exists N: 
\forall n,m \geq N: d(x_n,x_m) < \epsilon
$$
→ the elements become arbitrarily close to each other as the [[sequence]] progresses
#### note
- the following conndiction is not sufficient to show that $x_n$ is a [[cauchy sequence]]
$$
\forall \epsilon > 0:\exists N: 
\forall n \geq N: d(x_n,x_{n+1}) < \epsilon
$$
- e.g: $x_n = \sqrt{n}$: eventhough $\sqrt{n}-\sqrt{n+1}$ becomes arbitrary small $\sqrt{n}-\sqrt{m}$ does not

### relationship to [[convergence|converging]] [[sequence]]
#### every [[convergence|converging]] [[sequence]] is a [[cauchy sequence]]
- let $x_n$ be a [[sequence]] [[convergence|converging]] against $x^*$ in a [[norm|normed]] [[vector space|space]] with [[norm]] $||\cdot||$
- for each $\epsilon > 0$ we can construct an $N, M$ such that the following is true

$$
\begin{split}
\forall \epsilon >0 :\left(
\exists N: \forall n>N: || x_n - x^* || \leq \frac{\epsilon}{2}
\land
\exists M: \forall m>M: || x_m - x^* || \leq \frac{\epsilon}{2} 
\right)
\end{split}
$$
- by taking $\hat{N} = \max{(N,M)}$ and applying the [[triangle inequality]] of the [[metric]] we can follow that 
$$
\begin{split}
&\forall n,m > \hat{N}: d(x_n - x^*) + d(x_m - x^*) > \epsilon \\
&d(x_n - x^*) + d(x_m - x^*) \geq d(x_n - x_m) \\
\Rightarrow & \forall n,m > \hat{N}: \epsilon \geq d(x_n - x_m) \\
\end{split}
$$
- thus $x_n$ is also a [[cauchy sequence]] with the [[metric]] induced by the [[norm]] $||\cdot||$

#### not every [[cauchy sequence]] is [[convergence|converging]]
- let $x_n$ be a [[cauchy sequence]] in a [[norm|normed]] [[vector space|space]] $(X, ||\cdot||)$ 
- generally $x_n$ does not have to [[convergence|converge]] in $X$ because [[limit]] can be outside $X$ eventhough $x_n \in X$
- only if $X$ is [[cauchy complete]] $x_n$ has to [[convergence|converge]] in $X$
# -----------------
![[cauchy complete#cauchy complete]]

![[convergence#convergence in a normed space $ left(V, +, cdot, cdot right)$]]

![[metric#metric]]


# Anki

START
Basic
definition [[cauchy sequence]]
Back: 
### cauchy sequence
- given a [[metric]] [[vector space|space]] $(X, d)$
- a [[sequence]] $x_n$ is a [[cauchy sequence]] if the following is true

$$
\forall \epsilon > 0:\exists N: 
\forall n,m \geq N: d(x_n,x_m) < \epsilon
$$
→ the elements become arbitrarily close to each other as the [[sequence]] progresses
#### note
- the following conndiction is not sufficient to show that $x_n$ is a [[cauchy sequence]]
$$
\forall \epsilon > 0:\exists N: 
\forall n \geq N: d(x_n,x_{n+1}) < \epsilon
$$
- e.g: $x_n = \sqrt{n}$: eventhough $\sqrt{n}-\sqrt{n+1}$ becomes arbitrary small $\sqrt{n}-\sqrt{m}$ does not

___________________________
### metric
- generalization of the distance between [[vector|vectors]]
- let $V$ be a [[set]]
- a [[function]] $d: V \times V \rightarrow (0, \infty)$ is a [[metric]] if the followng conditions are true

1) [[symmetric]]
$$
\forall x, y \in V: d(x,y) = d(y,x)
$$
2) [[positive definite]]
$$
d(x, y) \leftrightarrow x=y
$$
$$
\forall x, y \in V: d(x, y) \geq 0
$$
3) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1715357713947-->
END


START
Basic
- given a [[sequence]] $x_n$ that is satisfying the following condition:
- is it necessarily a [[cauchy sequence]]?
$$
\forall \epsilon > 0:\exists N: 
\forall n \geq N: d(x_n,x_{n+1}) < \epsilon
$$

Back: 
### cauchy sequence
- given a [[metric]] [[vector space|space]] $(X, d)$
- a [[sequence]] $x_n$ is a [[cauchy sequence]] if the following is true

$$
\forall \epsilon > 0:\exists N: 
\forall n,m \geq N: d(x_n,x_m) < \epsilon
$$
→ the elements become arbitrarily close to each other as the [[sequence]] progresses
#### note
- the following conndiction is not sufficient to show that $x_n$ is a [[cauchy sequence]]
$$
\forall \epsilon > 0:\exists N: 
\forall n \geq N: d(x_n,x_{n+1}) < \epsilon
$$
- e.g: $x_n = \sqrt{n}$: eventhough $\sqrt{n}-\sqrt{n+1}$ becomes arbitrary small $\sqrt{n}-\sqrt{m}$ does not

___________________________
### metric
- generalization of the distance between [[vector|vectors]]
- let $V$ be a [[set]]
- a [[function]] $d: V \times V \rightarrow (0, \infty)$ is a [[metric]] if the followng conditions are true

1) [[symmetric]]
$$
\forall x, y \in V: d(x,y) = d(y,x)
$$
2) [[positive definite]]
$$
d(x, y) \leftrightarrow x=y
$$
$$
\forall x, y \in V: d(x, y) \geq 0
$$
3) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1715357713950-->
END

START
Basic
- relationship of [[convergence|converging]] [[sequence]] and [[cauchy sequence]] (in a general [[norm|normed]] [[vector space|space]])
Back: 
### relationship to [[convergence|converging]] [[sequence]]
#### every [[convergence|converging]] [[sequence]] is a [[cauchy sequence]]
- let $x_n$ be a [[sequence]] [[convergence|converging]] against $x^*$ in a [[norm|normed]] [[vector space|space]] with [[norm]] $||\cdot||$
- for each $\epsilon > 0$ we can construct an $N, M$ such that the following is true

$$
\begin{split}
\forall \epsilon >0 :\left(
\exists N: \forall n>N: || x_n - x^* || \leq \frac{\epsilon}{2}
\land
\exists M: \forall m>M: || x_m - x^* || \leq \frac{\epsilon}{2} 
\right)
\end{split}
$$
- by taking $\hat{N} = \max{(N,M)}$ and applying the [[triangle inequality]] of the [[metric]] we can follow that 
$$
\begin{split}
&\forall n,m > \hat{N}: d(x_n - x^*) + d(x_m - x^*) > \epsilon \\
&d(x_n - x^*) + d(x_m - x^*) \geq d(x_n - x_m) \\
\Rightarrow & \forall n,m > \hat{N}: \epsilon \geq d(x_n - x_m) \\
\end{split}
$$
- thus $x_n$ is also a [[cauchy sequence]] with the [[metric]] induced by the [[norm]] $||\cdot||$

#### not every [[cauchy sequence]] is [[convergence|converging]]
- let $x_n$ be a [[cauchy sequence]] in a [[norm|normed]] [[vector space|space]] $(X, ||\cdot||)$ 
- generally $x_n$ does not have to [[convergence|converge]] in $X$ because [[limit]] can be outside $X$ eventhough $x_n \in X$
- only if $X$ is [[cauchy complete]] $x_n$ has to [[convergence|converge]] in $X$


___________________________

### cauchy complete
- a [[metric]] [[vector space|space]] $(X, d)$ is **complete** if every [[cauchy sequence]] in $X$ also has a [[limit]] in $X$
	→ no points are missing inside or at the boundarys
- the [[rational numbers]] $\mathbb{Q}$ are not complete because e.g. $\sqrt{2}$ is missing

### convergence in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
- given a [[sequence]] $v_n \in V$  
- $v_n$ is converging against $v^*$ if the following is true

$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow ||a_n - a^*|| \leq \epsilon \\
&\Leftrightarrow \\
&||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
\end{split}
$$


### cauchy sequence
- given a [[metric]] [[vector space|space]] $(X, d)$
- a [[sequence]] $x_n$ is a [[cauchy sequence]] if the following is true

$$
\forall \epsilon > 0:\exists N: 
\forall n,m \geq N: d(x_n,x_m) < \epsilon
$$
→ the elements become arbitrarily close to each other as the [[sequence]] progresses
#### note
- the following conndiction is not sufficient to show that $x_n$ is a [[cauchy sequence]]
$$
\forall \epsilon > 0:\exists N: 
\forall n \geq N: d(x_n,x_{n+1}) < \epsilon
$$
- e.g: $x_n = \sqrt{n}$: eventhough $\sqrt{n}-\sqrt{n+1}$ becomes arbitrary small $\sqrt{n}-\sqrt{m}$ does not


### metric
- generalization of the distance between [[vector|vectors]]
- let $V$ be a [[set]]
- a [[function]] $d: V \times V \rightarrow (0, \infty)$ is a [[metric]] if the followng conditions are true

1) [[symmetric]]
$$
\forall x, y \in V: d(x,y) = d(y,x)
$$
2) [[positive definite]]
$$
d(x, y) \leftrightarrow x=y
$$
$$
\forall x, y \in V: d(x, y) \geq 0
$$
3) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1715357713955-->
END


START
Basic
proof that every [[convergence|converging]] [[sequence]] is a [[cauchy sequence]]
Back: 
#### every [[convergence|converging]] [[sequence]] is a [[cauchy sequence]]
- let $x_n$ be a [[sequence]] [[convergence|converging]] against $x^*$ in a [[norm|normed]] [[vector space|space]] with [[norm]] $||\cdot||$
- for each $\epsilon > 0$ we can construct an $N, M$ such that the following is true

$$
\begin{split}
\forall \epsilon >0 :\left(
\exists N: \forall n>N: || x_n - x^* || \leq \frac{\epsilon}{2}
\land
\exists M: \forall m>M: || x_m - x^* || \leq \frac{\epsilon}{2} 
\right)
\end{split}
$$
- by taking $\hat{N} = \max{(N,M)}$ and applying the [[triangle inequality]] of the [[metric]] we can follow that 
$$
\begin{split}
&\forall n,m > \hat{N}: d(x_n - x^*) + d(x_m - x^*) > \epsilon \\
&d(x_n - x^*) + d(x_m - x^*) \geq d(x_n - x_m) \\
\Rightarrow & \forall n,m > \hat{N}: \epsilon \geq d(x_n - x_m) \\
\end{split}
$$
- thus $x_n$ is also a [[cauchy sequence]] with the [[metric]] induced by the [[norm]] $||\cdot||$


#### not every [[cauchy sequence]] is [[convergence|converging]]
- let $x_n$ be a [[cauchy sequence]] in a [[norm|normed]] [[vector space|space]] $(X, ||\cdot||)$ 
- generally $x_n$ does not have to [[convergence|converge]] in $X$ because [[limit]] can be outside $X$ eventhough $x_n \in X$
- only if $X$ is [[cauchy complete]] $x_n$ has to [[convergence|converge]] in $X$


___________________________

### cauchy complete
- a [[metric]] [[vector space|space]] $(X, d)$ is **complete** if every [[cauchy sequence]] in $X$ also has a [[limit]] in $X$
	→ no points are missing inside or at the boundarys
- the [[rational numbers]] $\mathbb{Q}$ are not complete because e.g. $\sqrt{2}$ is missing

### convergence in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
- given a [[sequence]] $v_n \in V$  
- $v_n$ is converging against $v^*$ if the following is true

$$
\begin{split}
&\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow ||a_n - a^*|| \leq \epsilon \\
&\Leftrightarrow \\
&||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
\end{split}
$$


### cauchy sequence
- given a [[metric]] [[vector space|space]] $(X, d)$
- a [[sequence]] $x_n$ is a [[cauchy sequence]] if the following is true

$$
\forall \epsilon > 0:\exists N: 
\forall n,m \geq N: d(x_n,x_m) < \epsilon
$$
→ the elements become arbitrarily close to each other as the [[sequence]] progresses
#### note
- the following conndiction is not sufficient to show that $x_n$ is a [[cauchy sequence]]
$$
\forall \epsilon > 0:\exists N: 
\forall n \geq N: d(x_n,x_{n+1}) < \epsilon
$$
- e.g: $x_n = \sqrt{n}$: eventhough $\sqrt{n}-\sqrt{n+1}$ becomes arbitrary small $\sqrt{n}-\sqrt{m}$ does not


### metric
- generalization of the distance between [[vector|vectors]]
- let $V$ be a [[set]]
- a [[function]] $d: V \times V \rightarrow (0, \infty)$ is a [[metric]] if the followng conditions are true

1) [[symmetric]]
$$
\forall x, y \in V: d(x,y) = d(y,x)
$$
2) [[positive definite]]
$$
d(x, y) \leftrightarrow x=y
$$
$$
\forall x, y \in V: d(x, y) \geq 0
$$
3) [[triangle inequality]]
$$
\forall x, y, z \in V: d(x,z) \leq d(x,y) + d(y,z)
$$


Tags: mathematics
<!--ID: 1715357713959-->
END