### function space
- [[set]] of [[function|functions]] $\{f: V \rightarrow W\}$ between the same [[vector space|vector spaces]] with a [[addition]] and a [[multiplication]] with a [[scalar]]

### examples
- [[set]] of [[linear map|linear functions]] $f: \mathbb{R}^m \rightarrow \mathbb{R}^n$ $\{Ax: A \in \mathbb{R}^{n \times m},  x \in \mathbb{R}^{m}\}$ 
$$
\begin{split}
&+: V \times V \rightarrow V:(f + g)(v) = f(v) + g(v) \\ 
& \: \cdot \: : V \times \mathbb{R} \rightarrow V:(\lambda \cdot f)(v) = \lambda \cdot + f(v) \\ 
\end{split}
$$
- [[set]] of [[function|functions]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ 

### [[norm]] for [[function space]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ 
#### $L^p$ [[norm]]

$$
||f||_p = \left(\int_{\Omega} |f(x)|^p dx \right)^{\frac{1}{p}}
$$
#### $L^\infty$ [[norm]]
$$
||f||_\infty = \max_{x \in \Omega} |f(x)|
$$

### [[convergence]] of a [[sequence]] of [[function]]
- given a [[sequence]] of [[function|functions]] $f_n: [a,b] \rightarrow \mathbb{R}$ 

#### [[convergence]] for the $L^1$ [[norm]]
- $f_n$ converges to $f$ for the $L^1$ [[norm]] in the following is true
$$
||f_n - f ||_1 \rightarrow 0 \Leftrightarrow \int^b_a |f_n(x) - f(x)| dx \rightarrow 0
$$
#### [[convergence]] for the $L^p$ [[norm]]
- $f_n$ converges to $f$ for the $L^p$ [[norm]] in the following is true
$$
||f_n - f ||_p \rightarrow 0 \Leftrightarrow \left(\int^b_a |f_n(x) - f(x)|^p dx\right)^{\frac{1}{p}} \rightarrow 0
$$
#### [[convergence]] for the $L^\infty$ [[norm]]
- $f_n$ converges to $f$ for the $L^\infty$ [[norm]] in the following is true
$$
||f_n - f ||_\infty \rightarrow 0 \Leftrightarrow \max_{a \leq x \leq b} |f_n(x) - f(x)| dx \rightarrow 0
$$
- this means that the distance between the functions has to go to zero for the complete domain
#### $||f_n - f ||_\infty \rightarrow 0 \Rightarrow ||f_n - f ||_1 \rightarrow 0$ but not the other way around


![[convergence#convergence in a normed space $ left(V, +, cdot, cdot right)$]]
# ---------------------
![[function#function]]

![[linear map#linear function]]

![[vector space#vector space]]
# anki
START
Basic
[[function space]]
- definition
- two examples
- example: [[norm]] on a [[function space]] (2)
Back: 
### function space
- [[set]] of [[function|functions]] $\{f: V \rightarrow W\}$ between the same [[vector space|vector spaces]] with a [[addition]] and a [[multiplication]] with a [[scalar]]

### examples
- [[set]] of [[linear map|linear functions]] $f: \mathbb{R}^m \rightarrow \mathbb{R}^n$ $\{Ax: A \in \mathbb{R}^{n \times m},  x \in \mathbb{R}^{m}\}$ 
$$
\begin{split}
&+: V \times V \rightarrow V:(f + g)(v) = f(v) + g(v) \\ 
& \: \cdot \: : V \times \mathbb{R} \rightarrow V:(\lambda \cdot f)(v) = \lambda \cdot + f(v) \\ 
\end{split}
$$
- [[set]] of [[function|functions]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ 


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


START
Basic
geometric interpretation 
- $L^1$ [[norm]]
- $L^\infty$ [[norm]]
- [[convergence]] regarding the $L^1$ [[norm]]
- [[convergence]] regarding the $L^\infty$ [[norm]]
Back: 
### [[norm]] for [[function space]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ 
#### $L^1$ [[norm]]
- absolute area between the function and 0 over the complete domain
$$
||f||_p = \int_{\Omega} |f(x)| dx 
$$
#### $L^\infty$ [[norm]]
- absolute maximum of a function has to be zero to it has to be zero over the complete domain
$$
||f||_\infty = \max_{x \in \Omega} |f(x)|
$$

### [[convergence]] of a [[sequence]] of [[function]]
- given a [[sequence]] of [[function|functions]] $f_n: [a,b] \rightarrow \mathbb{R}$ 

#### [[convergence]] for the $L^1$ [[norm]]
- $f_n$ converges to $f$ for the $L^1$ [[norm]] in the following is true
$$
||f_n - f ||_1 \rightarrow 0 \Leftrightarrow \int^b_a |f_n(x) - f(x)| dx \rightarrow 0
$$
- the absolute area between the functions has to go to zero
#### [[convergence]] for the $L^\infty$ [[norm]]
- $f_n$ converges to $f$ for the $L^\infty$ [[norm]] in the following is true
$$
||f_n - f ||_\infty \rightarrow 0 \Leftrightarrow \max_{a \leq x \leq b} |f_n(x) - f(x)| dx \rightarrow 0
$$
- this means that the distance between the functions has to go to zero for the complete domain
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

Tags: mathematics
<!--ID: 1714546780232-->
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

Tags: mathematics
<!--ID: 1714411582377-->
END

START
Basic
definitions
[[convergence]] of a [[sequence]] of [[function]]
- for the $L^1$ [[norm]]
- for the $L^\infty$ [[norm]]
- is it equivalent?
Back: 
### [[convergence]] of a [[sequence]] of [[function]]
- given a [[sequence]] of [[function|functions]] $f_n: [a,b] \rightarrow \mathbb{R}$ 

#### [[convergence]] for the $L^1$ [[norm]]
- $f_n$ converges to $f$ for the $L^1$ [[norm]] in the following is true
$$
||f_n - f ||_1 \rightarrow 0 \Leftrightarrow \int^b_a |f_n(x) - f(x)| dx \rightarrow 0
$$
#### [[convergence]] for the $L^p$ [[norm]]
- $f_n$ converges to $f$ for the $L^p$ [[norm]] in the following is true
$$
||f_n - f ||_p \rightarrow 0 \Leftrightarrow \left(\int^b_a |f_n(x) - f(x)|^p dx\right)^{\frac{1}{p}} \rightarrow 0
$$
#### [[convergence]] for the $L^\infty$ [[norm]]
- $f_n$ converges to $f$ for the $L^\infty$ [[norm]] in the following is true
$$
||f_n - f ||_\infty \rightarrow 0 \Leftrightarrow \max_{a \leq x \leq b} |f_n(x) - f(x)| dx \rightarrow 0
$$
- this means that the distance between the functions has to go to zero for the complete domain
#### $||f_n - f ||_\infty \rightarrow 0 \Rightarrow ||f_n - f ||_1 \rightarrow 0$ but not the other way around

_______________________
### [[norm]] for [[function space]] $f: \Omega \subset \mathbb{R}^d \rightarrow \mathbb{R}$ 
#### $L^p$ [[norm]]

$$
||f||_p = \left(\int_{\Omega} |f(x)|^p dx \right)^{\frac{1}{p}}
$$
#### $L^\infty$ [[norm]]
$$
||f||_\infty = \max_{x \in \Omega} |f(x)|
$$


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



Tags: mathematics
<!--ID: 1714411582368-->
END
