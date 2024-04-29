### function space
- [[set]] of [[function|functions]] $\{f: V \rightarrow W\}$ between the same [[vector space|vector spaces]] with a [[addition]] and a [[multiplication]] with a [[scalar]]

### examples
- [[set]] of [[linear function|linear functions]] $f: \mathbb{R}^m \rightarrow \mathbb{R}^n$ $\{Ax: A \in \mathbb{R}^{n \times m},  x \in \mathbb{R}^{m}\}$ 
$$
\begin{split}
&+: V \times V \rightarrow V:(f + g)(v) = f(v) + g(v) \\ 
& \: \cdot \: : V \times \mathbb{R} \rightarrow V:(\lambda \cdot f)(v) = \lambda \cdot + f(v) \\ 
\end{split}
$$
- [[set]] of [[function|functions]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ 

![[norm#examples norm for function space $f: Omega subset mathbb{R} d rightarrow mathbb{R}$]]

# ---------------------
![[function#function]]

![[linear function#linear function]]

![[vector space#vector space]]
# anki
START
Basic
[[function space]]
- definition
- two examples
- example: [[norm]] on a [[function space]]
Back: 
### function space
- [[set]] of [[function|functions]] $\{f: V \rightarrow W\}$ between the same [[vector space|vector spaces]] with a [[addition]] and a [[multiplication]] with a [[scalar]]

### examples
- [[set]] of [[linear function|linear functions]] $f: \mathbb{R}^m \rightarrow \mathbb{R}^n$ $\{Ax: A \in \mathbb{R}^{n \times m},  x \in \mathbb{R}^{m}\}$ 
$$
\begin{split}
&+: V \times V \rightarrow V:(f + g)(v) = f(v) + g(v) \\ 
& \: \cdot \: : V \times \mathbb{R} \rightarrow V:(\lambda \cdot f)(v) = \lambda \cdot + f(v) \\ 
\end{split}
$$
- [[set]] of [[function|functions]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ 

### [[norm]] for [[function space]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ 
#### $L$ [[norm]]

$$
||f||_L = \left(\int_{\Omega} |f(x)|^L dx \right)^{\frac{1}{L}}
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
<!--ID: 1714381242369-->
END