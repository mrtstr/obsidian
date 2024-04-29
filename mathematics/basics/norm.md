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

### [[norm|norms]] for $V \subseteq \mathbb{R}^n$
![[615px-Vector-p-Norms_qtl1.svg.png]]

#### $l^p$ [[norm]]

$$
||x||_p = \left(\sum_{i \in [n]} |x_i|^p \right)^{\frac{1}{p}}
$$
#### $l^1$ [[norm]]
$$
||x||_1 = \sum_{i \in [n]} |x_i| 
$$
#### euclidian [[norm]] ($l^2$)
$$
||x||_2 = \left(\sum_{i \in [n]} |x_i|^2 \right)^{\frac{1}{2}}
$$

#### infinity [[norm]] ($l^\infty$)
$$
||x||_\infty = \left(\sum_{i \in [n]} |x_i|^\infty \right)^{\frac{1}{\infty}} = \max_{i \in [n]} |x_i|
$$

### [[norm]] for [[function space]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ 
#### $L^p$ [[norm]]

$$
||f||_p = \left(\int_{\Omega} |f(x)|^p dx \right)^{\frac{1}{p}}
$$
#### $L^\infty$ [[norm]]
$$
||f||_\infty = \max_{x \in \Omega} |f(x)|
$$

# ---------------------
![[function space#function space]]



![[positive definite#positive definite]]

![[homogeneous#homogeneous]]

![[vector space#vector space]]


# anki
START
Basic
definition: [[norm]]
Back: 
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

_______________________

### positive definite
- a [[function]] $f: A \rightarrow B$ is [[positive definite]] on a neighbourhood $D$ of the [[origin]] if the following is true
$$
f(0) = 0 \land \forall v \in D: f(v) > 0
$$


### homogeneous
- a [[function]] $f: V \rightarrow W$ is [[homogeneous]] with degree $k$ is the following is true
$$
\forall v \in V, \lambda \in \mathbb{K}: \lambda \neq 0: f\left(\lambda v\right) = \lambda^k f\left(v\right)
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
<!--ID: 1714373701537-->
END


START
Basic
examples for [[norm|norms]] of $V \subseteq \mathbb{R}^n$ (4)
Back: 
#### $l^p$ [[norm]]

$$
||x||_p = \left(\sum_{i \in [n]} |x_i|^p \right)^{\frac{1}{p}}
$$
#### $l^1$ [[norm]]
$$
||x||_1 = \sum_{i \in [n]} |x_i| 
$$
#### euclidian [[norm]] ($l^2$)
$$
||x||_2 = \left(\sum_{i \in [n]} |x_i|^2 \right)^{\frac{1}{2}}
$$

#### infinity [[norm]] ($l^\infty$)
$$
||x||_\infty = \left(\sum_{i \in [n]} |x_i|^\infty \right)^{\frac{1}{\infty}} = \max_{i \in [n]} |x_i|
$$


![[615px-Vector-p-Norms_qtl1.svg 1.png]]

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

### positive definite
- a [[function]] $f: A \rightarrow B$ is [[positive definite]] on a neighbourhood $D$ of the [[origin]] if the following is true
$$
f(0) = 0 \land \forall v \in D: f(v) > 0
$$


### homogeneous
- a [[function]] $f: V \rightarrow W$ is [[homogeneous]] with degree $k$ is the following is true
$$
\forall v \in V, \lambda \in \mathbb{K}: \lambda \neq 0: f\left(\lambda v\right) = \lambda^k f\left(v\right)
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
<!--ID: 1714375065844-->
END


START
Basic
[[norm|norms]] for [[function space]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ (2)
Back: 

### [[norm]] for [[function space]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ 
#### $L^p$ [[norm]]

$$
||f||_p = \left(\int_{\Omega} |f(x)|^p dx \right)^{\frac{1}{p}}
$$
#### $L^\infty$ [[norm]]
$$
||f||_\infty = \max_{x \in \Omega} |f(x)|
$$

_______________________
### function space
- [[set]] of [[function|functions]] $\{f: V \rightarrow W\}$ between the same [[vector space|vector spaces]] with a [[addition]] and a [[multiplication]] with a [[scalar]]


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
<!--ID: 1714411582377-->
END