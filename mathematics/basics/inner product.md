### inner product
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear function|linearity]] (regarding both elemements because of the [[symmetric]])

$$
\forall x,y,z \in V, \lambda \in \mathbb{R}:\langle x + \lambda y , z \rangle = \langle x , z  \rangle + \lambda \langle  y , z \rangle
$$
2) [[symmetric]]

$$
\forall x,y \in V: \langle x  , y \rangle = \langle y  , x \rangle
$$
3) [[positive definite]]

$$
\forall x \in V: \langle x  , x \rangle  \leftrightarrow x=0 
$$
$$
\forall x \in V: \langle x  , x \rangle  \geq 0
$$
### [[inner product]] examples

![[matrix induced inner product#matrix induced inner product]]

#### dot product on $\langle\cdot, \cdot \rangle:\mathbb{R}^n \times \mathbb{R}^n \rightarrow \mathbb{R}$
$$
\langle x, y \rangle = \sum_{i \in [n]} x_i y_i = xy^\top
$$

#### $L^2$ [[inner product]] for the [[function space]] 
- the $L^2$ [[inner product]] for the [[function space]] $u: \Omega \rightarrow \mathbb{R}$ is defined as follows
$$
\langle u, v \rangle_{L^2} = \int_{\Omega} u(x)v(x) dx
$$
![[norm#norm for function space $f: Omega subset mathbb{R} d rightarrow mathbb{R}$]]

# ------------
![[vector space#vector space]]

# anki 
START
Basic
[[inner product]]
- definition
Back: 
### inner product
- generalization of the 
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear function|linearity]] (regarding both elemements because of the [[symmetric]])

$$
\forall x,y,z \in V, \lambda \in \mathbb{R}:\langle x + \lambda y , z \rangle = \langle x , z  \rangle + \lambda \langle  y , z \rangle
$$
2) [[symmetric]]

$$
\forall x,y \in V: \langle x  , y \rangle = \langle y  , x \rangle
$$
3) [[positive definite]]

$$
\forall x \in V: \langle x  , x \rangle  \leftrightarrow x=0 
$$
$$
\forall x \in V: \langle x  , x \rangle  \geq 0
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
<!--ID: 1714488374207-->
END


START
Basic
[[inner product]]
- example $\mathbb{R}^n$ (2)
- example [[function space]]
Back: 


### matrix induced inner product
- every [[symmetric matrix]] $A \in \mathbb{R}^{n \times n}$ induces an [[inner product]]
$$
\langle x, y \rangle_A = y^\top Ax
$$
TODO: add proof

#### dot product on $\langle\cdot, \cdot \rangle:\mathbb{R}^n \times \mathbb{R}^n \rightarrow \mathbb{R}$
$$
\langle x, y \rangle = \sum_{i \in [n]} x_i y_i = xy^\top
$$

#### $L^2$ [[inner product]] for the [[function space]] 
- the $L^2$ [[inner product]] for the [[function space]] $u: \Omega \rightarrow \mathbb{R}$ is defined as follows
$$
\langle u, v \rangle_{L^2} = \int_{\Omega} u(x)v(x) dx
$$

_______________________
### inner product
- generalization of the 
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear function|linearity]] (regarding both elemements because of the [[symmetric]])

$$
\forall x,y,z \in V, \lambda \in \mathbb{R}:\langle x + \lambda y , z \rangle = \langle x , z  \rangle + \lambda \langle  y , z \rangle
$$
2) [[symmetric]]

$$
\forall x,y \in V: \langle x  , y \rangle = \langle y  , x \rangle
$$
3) [[positive definite]]

$$
\forall x \in V: \langle x  , x \rangle  \leftrightarrow x=0 
$$
$$
\forall x \in V: \langle x  , x \rangle  \geq 0
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

### function space
- [[set]] of [[function|functions]] $\{f: V \rightarrow W\}$ between the same [[vector space|vector spaces]] with a [[addition]] and a [[multiplication]] with a [[scalar]]


Tags: mathematics
<!--ID: 1714495264989-->
END