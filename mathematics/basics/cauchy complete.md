### cauchy complete
- a [[metric]] [[vector space|space]] $(X, d)$ is **complete** if every [[cauchy sequence]] in $X$ also has a [[limit]] in $X$
	→ no points are missing inside or at the boundarys

### Examples
#### missing inner point
- the [[rational numbers]] $\mathbb{Q}$ with the [[metric]] $d(a, b) = |a - b|$ is not [[cauchy complete]] because some numbers "inside" are missing
- for example the following is a [[cauchy sequence]] but it's not [[convergence|converging]] in $\mathbb{Q}$ because $e \notin \mathbb{Q}$
$$
x_n = \left(1+\frac{1}{n}\right)^n
$$
#### missing boundarys
- $\mathbb{R}_{>0}$ are not [[cauchy complete]] because $0$ is missing
- the [[sequence]] $x_n = \frac{1}{n}$ is a [[cauchy sequence]] in $\mathbb{R}_{>0}$ but its [[convergence|converging]] against $0$ which is not in $\mathbb{R}_{>0}$ 

# ------------------

![[cauchy sequence#cauchy sequence]]

# anki

START
Basic
[[cauchy complete]]
- definition
- reasons for a [[metric]] [[vector space|space]] $(X, d)$ not being [[cauchy complete]] with examples (2)
Back: 
### cauchy complete
- a [[metric]] [[vector space|space]] $(X, d)$ is **complete** if every [[cauchy sequence]] in $X$ also has a [[limit]] in $X$
	→ no points are missing inside or at the boundarys

### examples
#### missing inner point
- the [[rational numbers]] $\mathbb{Q}$ with the [[metric]] $d(a, b) = |a - b|$ is not [[cauchy complete]] because some numbers "inside" are missing
- for example the following is a [[cauchy sequence]] but it's not [[convergence|converging]] in $\mathbb{Q}$ because $e \notin \mathbb{Q}$
$$
x_n = \left(1+\frac{1}{n}\right)^n
$$
#### missing boundarys
- $\mathbb{R}_{>0}$ are not [[cauchy complete]] because $0$ is missing
- the [[sequence]] $x_n = \frac{1}{n}$ is a [[cauchy sequence]] in $\mathbb{R}_{>0}$ but its [[convergence|converging]] against $0$ which is not in $\mathbb{R}_{>0}$ 



___________________________



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


### relationship to [[convergence|converging]] [[sequence]]
#### every [[convergence|converging]] [[sequence]] is a [[cauchy sequence]]
- let $x_n$ be a [[sequence]] [[convergence|converging]] against $x^*$ in a [[norm|normed]] [[vector space|space]] with [[norm]] $||\cdot||$
- for each $n, m > N$ we can convstruct an $\epsilon_1, \epsilon_2$ and $N_1, N_2$ such that the following is true

$$
\begin{split}
&\forall \epsilon_1 > 0: \exists N_1: \forall n>N_1: || x_n - x^* || \leq \epsilon_1 \\
&\forall \epsilon_2 > 0: \exists N_2: \forall m>N_2: || x_m - x^* || \leq \epsilon_2 \\
\end{split}
$$

- with the [[triangle inequality]] of the [[metric]] we can follow that $x_n$ is also a [[cauchy sequence]] with the [[metric]] induced by the [[norm]] $||\cdot||$

$$
\begin{split}
&2 \epsilon \geq d(x_n - x^*) + d(x_m - x^*) \geq d(x_n - x_m) \\
&\Rightarrow \hat{\epsilon} \geq d(x_n - x_m) \\
\end{split}
$$

#### not every [[cauchy sequence]] is [[convergence|converging]]
- let $x_n$ be a [[cauchy sequence]] in a [[norm|normed]] [[vector space|space]] $(X, ||\cdot||)$ 
- generally $x_n$ does not have to [[convergence|converge]] in $X$ because [[limit]] can be outside $X$ eventhough $x_n \in X$
- only if $X$ is [[cauchy complete]] $x_n$ has to [[convergence|converge]] in $X$

Tags: mathematics
<!--ID: 1715357713944-->
END