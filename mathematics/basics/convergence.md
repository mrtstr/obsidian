### convergence in $\mathbb{R}$
- given a [[sequence]] $a_n \in \mathbb{R}$  
- $a_n$ is converging against $a^*$ if the following is true

$$
\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow |a_n - a^*| \leq \epsilon
$$

### convergence in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
- given a [[sequence]] $v_n \in V$  
- $v_n$ is converging against $v^*$ if the following is true

$$
||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
$$
The following notations are equivalent:
$$
\lim_{n \rightarrow \infty} v_n  = v^*
$$
$$
v_n  \rightarrow v^*
$$

### convergence in $\mathbb{R}^n$
- given a [[sequence]] $a_n \in \mathbb{R}^n$  
- $a_n$ is converging against $a^*\in \mathbb{R}^n$ if every element is converging
$$
a_n  \rightarrow a^* \Leftrightarrow \forall i \in [n]: a_i \rightarrow a^*_i
$$
### examples [[convergence]]
- the followng [[sequence]] converges againt [[eulers number]]
$$
a_n =\left(1 + \frac{1}{n}\right)^n
$$
- converges against $0$
$$
a_n = \frac{1}{n}
$$

# -----------------

![[limit#limit]]

START
Basic
definitions
- [[convergence]] in $\mathbb{R}$ with examples
- [[convergence]] in $\mathbb{R}^n$
- [[convergence]] in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
Back: 
### convergence in $\mathbb{R}$
- given a [[sequence]] $a_n \in \mathbb{R}$  
- $a_n$ is converging against $a^*$ if the following is true

$$
\forall \epsilon>0: \exists N \in \mathbb{N}: n \geq N \Rightarrow |a_n - a^*| \leq \epsilon
$$

### convergence in a [[normed space]] $\left(V, +, \cdot, ||\cdot||\right)$
- given a [[sequence]] $v_n \in V$  
- $v_n$ is converging against $v^*$ if the following is true

$$
||v_n - v^* || \xrightarrow{n \rightarrow \infty} 0
$$
The following notations are equivalent:
$$
\lim_{n \rightarrow \infty} v_n  = v^*
$$
$$
v_n  \rightarrow v^*
$$

### convergence in $\mathbb{R}^n$
- given a [[sequence]] $a_n \in \mathbb{R}^n$  
- $a_n$ is converging against $a^*\in \mathbb{R}^n$ if every element is converging
$$
a_n  \rightarrow a^* \Leftrightarrow \forall i \in [n]: a_i \rightarrow a^*_i
$$
### examples [[convergence]]
- the followng [[sequence]] converges againt [[eulers number]]
$$
a_n =\left(1 + \frac{1}{n}\right)^n
$$
- converges against $0$
$$
a_n = \frac{1}{n}
$$

_______________________
### norm
- generalization of the concept of **length of a [[vector]]**
- let $V$ be a [[vector space]]
- the [[function]] $||\:.||: V \rightarrow \mathbb{R^+}$ is a [[norm]] is it satisfies the following conditions
1) [[positive definite]]
$$
||x||=0 \Leftrightarrow x = 0
$$

2) absolutely [[homogeneous]]
$$
\forall x \in V, \lambda \in \mathbb{K}: ||\lambda \cdot x|| = |\lambda| \cdot ||x||
$$
3) [[triangle inequality]]
$$
\forall v, w \in V: ||v + w|| \leq ||v|| + ||w||
$$

### vector space
a [[vector space]] $(V, +, \cdot)$ on a [[field]] $\mathbb{K}$ (e.g $\mathbb{R}$) is defined by 3 elements
1) a [[set]] $V$
2) a [[addition]] operation $+: V \times V \rightarrow V$
3) a [[multiplication]] operation $\cdot: \mathbb{K} \times V \rightarrow V$
- note: $v \in V$ is called [[vector]] and $\lambda \in \mathbb{K}$ is called a [[scalar]]

$(V, +, \cdot)$ is a [[vector space]] of the following conditions are true $u, v, w \in V$ and $\lambda, \mu \in \mathbb{K}$
1) $(V, +)$ is [[commutative]]: 
$$
v + w = w + v
$$
2) $(V, +)$ is [[associative]]: 
$$
(u + v) + w = u + (w + v)
$$

3) $(V, +)$ has a [[neutral element]] $0$ 
$$
v+0=v
$$
4) additive [[inverse elements]]
for every $v \in V$ has exists an additive [[inverse elements]] $v' \in V$ such that $v + v' = 0$

5) $(V, +, \cdot)$ are [[distributive]] for multiplications with scalars
$$
\begin{split}
\lambda \cdot (v + w) = \lambda \cdot v + \lambda \cdot w \\
v \cdot (\lambda + \mu) = v \cdot \lambda + v \cdot \mu
\end{split}
$$
6) $(V, \cdot)$ is [[associative]] with scalars 
$$
(\lambda \cdot \mu) + v = \lambda \cdot (\mu \cdot v)
$$
7) $(V, \cdot)$ has a [[neutral element]] $1$ 
$$
v \cdot 1 = v
$$


Tags: mathematics
<!--ID: 1714389589863-->
END