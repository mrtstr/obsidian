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
(\lambda + \mu) + v = \lambda + (\mu + v)
$$
7) $(V, \cdot)$ has a [[neutral element]] $1$ 
$$
v \cdot 1 = v
$$

### examples
#### $(\{0\}, +, \cdot)$ is a [[vector space]]

#### $(\mathbb{R}^n, +, \cdot)$ is a [[vector space]]

#### $\{A \in \mathbb{R}^{n \times m}\}$ with element wise addition and [[matrix product]] is a [[vector space]]

#### all [[polynomial]] with a degree of at most $d$
# -------------------
![[closure#closure]]

![[field#field]]

![[scalar#scalar]]

![[vector#vector]]

![[commutative#commutative]]

![[associative#associative]]

![[neutral element#neutral element]]

![[distributive#distributive]]


# anki
START
Basic
[[vector space]]
- definition (with 7 conditions)
 
Back: 
### vector space
a [[vector space]] $(V, +, \cdot)$ on a field $\mathbb{K}$ (e.g $\mathbb{R}$) is defined by 3 elements
1) a [[set]] $V$
2) a [[addition]] operation $+: V \times V \rightarrow V$
3) a [[multiplication]] operation $\cdot: \mathbb{K} \times V \rightarrow V$
- note: $v \in V$ is called [[vector]] and $\lambda \in \mathbb{K}$ is called a [[scalar]]
### conditions
$(V, +, \cdot)$ is a [[vector space]] of the following conditions are true $u, v, w \in V$ and $\lambda, \mu \in \mathbb{K}$
#### $(V, +)$ is [[commutative]]: 
$$
v + w = w + v
$$
#### $(V, +)$ is [[associative]]: 
$$
(u + v) + w = u + (w + v)
$$

#### $(V, +)$ has a [[neutral element]] $0$ 
$$
v+0=v
$$
#### additive [[inverse elements]]
for every $v \in V$ has exists an additive [[inverse elements]] $v' \in V$ such that $v + v' = 0$
#### $(V, +, \cdot)$ are [[distributive]] for multiplications with scalars
$$
\begin{split}
\lambda \cdot (v + w) = \lambda \cdot v + \lambda \cdot w \\
v \cdot (\lambda + \mu) = v \cdot \lambda + v \cdot \mu
\end{split}
$$
#### $(V, \cdot)$ is [[associative]] with scalars 
$$
(\lambda + \mu) + v = \lambda + (\mu + v)
$$
#### $(V, \cdot)$ has a [[neutral element]] $1$ 
$$
v \cdot 1 = v
$$
_______________________

#### commutative
a operation is commutative if the following is true in general
$$
a \circ b = b \circ a
$$

#### associative
$$
a \circ (b \circ c) = (a \circ b) \circ c
$$

#### neutral element
$n$ is a [[neutral element]] of a [[operation]] $\circ$ if
$$
a \circ n = n \circ a = a 
$$

#### distributive
two operations $\circ$ and $\times$ are distributive if the following is true in general
$$
(a \times b) \circ b = (a \circ c) \times (b \circ c)
$$

Tags: mathematics linear_algebra
<!--ID: 1713102578308-->
END


START
Basic
definitions
- [[field]]
- [[scalar]]
- [[vector]]
 
Back: 

#### field
- a [[field]] $\mathbb{K}$ is a [[set]] on which operations like [[addition]], [[multiplication]], [[substraction]] and [[division]] are defined on and that are behaving similar to the [[rational numbers]] $\mathbb{Q}$ and [[real number]] $\mathbb{R}$

### scalar
- given a [[vector space]] $(V, +, \cdot)$ on a [[field]] $\mathbb{K}$ (e.g $\mathbb{R}$) every $v \in \mathbb{K}$ is called [[scalar]]
- example $V = \mathbb{R}^n$ defined on the [[field]] = [[real number]] $\mathbb{R}$ → ever [[real number]] is a [[scalar]]

### vector
- given a [[vector space]] $(V, +, \cdot)$ on a [[field]] $\mathbb{K}$ (e.g $\mathbb{R}$) every $v \in V$ is called [[vector]]
- example $V = \mathbb{R}^n$ defined on the [[field]] = [[real number]] $\mathbb{R}$
$$
\begin{split}
v  \in \mathbb{R}^{n}
&= \left(v_{i} \right)_{i \in [n]} \\
&=\begin{pmatrix}  v_{1} \\   ... \\ v_{n} \end{pmatrix}
\end{split}
$$
_______________________
## vector space
a [[vector space]] $(V, +, \cdot)$ on a field $\mathbb{K}$ (e.g $\mathbb{R}$) is defined by 3 elements
1) a [[set]] $V$
2) a [[addition]] operation $+: V \times V \rightarrow V$
3) a [[multiplication]] operation $\cdot: \mathbb{K} \times V \rightarrow V$
- note: $v \in V$ is called [[vector]] and $\lambda \in \mathbb{K}$ is called a [[scalar]]
### conditions
$(V, +, \cdot)$ is a [[vector space]] of the following conditions are true $u, v, w \in V$ and $\lambda, \mu \in \mathbb{K}$
#### $(V, +)$ is [[commutative]]: 
$$
v + w = w + v
$$
#### $(V, +)$ is [[associative]]: 
$$
(u + v) + w = u + (w + v)
$$

#### $(V, +)$ has a [[neutral element]] $0$ 
$$
v+0=v
$$
#### additive [[inverse elements]]
for every $v \in V$ has exists an additive [[inverse elements]] $v' \in V$ such that $v + v' = 0$
#### $(V, +, \cdot)$ are [[distributive]] for multiplications with scalars
$$
\begin{split}
\lambda \cdot (v + w) = \lambda \cdot v + \lambda \cdot w \\
v \cdot (\lambda + \mu) = v \cdot \lambda + v \cdot \mu
\end{split}
$$
#### $(V, \cdot)$ is [[associative]] with scalars 
$$
(\lambda + \mu) + v = \lambda + (\mu + v)
$$
#### $(V, \cdot)$ has a [[neutral element]] $1$ 
$$
v \cdot 1 = v
$$
#### commutative
a operation is commutative if the following is true in general
$$
a \circ b = b \circ a
$$

#### associative
$$
a \circ (b \circ c) = (a \circ b) \circ c
$$

#### neutral element
$n$ is a [[neutral element]] of a [[operation]] $\circ$ if
$$
a \circ n = n \circ a = a 
$$

#### distributive
two operations $\circ$ and $\times$ are distributive if the following is true in general
$$
(a \times b) \circ b = (a \circ c) \times (b \circ c)
$$

Tags: mathematics linear_algebra
<!--ID: 1713112345609-->
END


START
Basic
give 4 examples for [[vector space]]
Back: 
$(\{0\}, +, \cdot)$ is a [[vector space]]

$(\mathbb{R}^n, +, \cdot)$ is a [[vector space]]

$\{A \in \mathbb{R}^{n \times m}\}$ with element wise addition and [[matrix product]] is a [[vector space]]

all [[polynomial]] with a degree of at most $d$
_______________________
## vector space
a [[vector space]] $(V, +, \cdot)$ on a field $\mathbb{K}$ (e.g $\mathbb{R}$) is defined by 3 elements
1) a [[set]] $V$
2) a [[addition]] operation $+: V \times V \rightarrow V$
3) a [[multiplication]] operation $\cdot: \mathbb{K} \times V \rightarrow V$
- note: $v \in V$ is called [[vector]] and $\lambda \in \mathbb{K}$ is called a [[scalar]]
### conditions
$(V, +, \cdot)$ is a [[vector space]] of the following conditions are true $u, v, w \in V$ and $\lambda, \mu \in \mathbb{K}$
#### $(V, +)$ is [[commutative]]: 
$$
v + w = w + v
$$
#### $(V, +)$ is [[associative]]: 
$$
(u + v) + w = u + (w + v)
$$

#### $(V, +)$ has a [[neutral element]] $0$ 
$$
v+0=v
$$
#### additive [[inverse elements]]
for every $v \in V$ has exists an additive [[inverse elements]] $v' \in V$ such that $v + v' = 0$
#### $(V, +, \cdot)$ are [[distributive]] for multiplications with scalars
$$
\begin{split}
\lambda \cdot (v + w) = \lambda \cdot v + \lambda \cdot w \\
v \cdot (\lambda + \mu) = v \cdot \lambda + v \cdot \mu
\end{split}
$$
#### $(V, \cdot)$ is [[associative]] with scalars 
$$
(\lambda + \mu) + v = \lambda + (\mu + v)
$$
#### $(V, \cdot)$ has a [[neutral element]] $1$ 
$$
v \cdot 1 = v
$$
#### commutative
a operation is commutative if the following is true in general
$$
a \circ b = b \circ a
$$

#### associative
$$
a \circ (b \circ c) = (a \circ b) \circ c
$$

#### neutral element
$n$ is a [[neutral element]] of a [[operation]] $\circ$ if
$$
a \circ n = n \circ a = a 
$$

#### distributive
two operations $\circ$ and $\times$ are distributive if the following is true in general
$$
(a \times b) \circ b = (a \circ c) \times (b \circ c)
$$

Tags: mathematics linear_algebra
<!--ID: 1713625090173-->
END