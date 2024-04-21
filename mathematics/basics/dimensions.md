### dimensions of a [[vector space]]
- let $B$ be a [[vector space]] and $B$ be a [[basis]] of $V$
- the dimensions of $V$ are defines as the [[cardinality]] of its [[basis]]
- note: the [[vector space]] $\{{0}\}$ has per definition zero dimension 
- note: since every [[basis]] of a [[vector space]] has the same [[cardinality]] (see [[basis#every basis of a vector space has the same cardinality|here]]) the [[dimensions]] of a [[vector space]] is equal to the [[cardinality]] of all of its [[basis]]
$$
\dim(V) = |B|
$$

# ------------------
![[basis#basis]]


![[basis#every basis of a vector space has the same cardinality]]

# anki
START
Basic
definition dimensions of a [[vector space]] and concepts where its based on (3)
Back: 
### dimensions of a [[vector space]]
- let $B$ be a [[vector space]] and $B$ be a [[basis]] of $V$
- the dimensions of $V$ are defines as the [[cardinality]] of its [[basis]]
- note: the [[vector space]] $\{{0}\}$ has per definition zero dimension 
- note: since every [[basis]] of a [[vector space]] has the same [[cardinality]] (see [[basis#every basis of a vector space has the same cardinality|here]]) the [[dimensions]] of a [[vector space]] is equal to the [[cardinality]] of all of its [[basis]]
$$
\dim(V) = |B|
$$

_______________________
### basis
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- $\{v_1, ..., v_n\}$ is a [[basis]] of $V$ if
1) $\{v_1, ..., v_n\}$ is a spanning [[set]] of $V$
2) $\{v_1, ..., v_n\}$ is [[linear independent]]


### linear independent
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- $v_1, ..., v_n \in V$ are [[linear independent]] if the following condition is true
$$
\forall \lambda_i \in \mathbb{K} :\sum\limits_{i \in [n]} v_i \lambda_i = 0 \Rightarrow \forall \lambda_i \in \mathbb{K}:  \lambda_i = 0
$$

### spanning [[set]] of a [[vector space]]
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- the [[set]] $\{v_1, ..., v_n\}$ is a **spanning set** or **generating set** of $V$ if $\mathrm{span}(v_1, ..., v_n) = V$
$$
\mathrm{span}(v_1, ..., v_n) = \{w \in V: \lambda_1, ... \lambda_n \in \mathbb{K}: w = \lambda_1 \cdot v_1 + ... + \lambda_n \cdot v_n\} = V
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
(\lambda + \mu) + v = \lambda + (\mu + v)
$$
7) $(V, \cdot)$ has a [[neutral element]] $1$ 
$$
v \cdot 1 = v
$$

Tags: mathematics linear_algebra
<!--ID: 1713684157507-->
END

START
Basic
- example of a [[vector space]] with zero [[dimensions]]
- why is the definition of the [[dimensions]] of a [[vector space]] $V$ a general property of $V$?
Back: 
### dimensions of a [[vector space]]
- let $B$ be a [[vector space]] and $B$ be a [[basis]] of $V$
- the dimensions of $V$ are defines as the [[cardinality]] of its [[basis]]
- note: the [[vector space]] $\{{0}\}$ has per definition zero dimension 
- note: since every [[basis]] of a [[vector space]] has the same [[cardinality]] (see [[basis#every basis of a vector space has the same cardinality|here]]) the [[dimensions]] of a [[vector space]] is equal to the [[cardinality]] of all of its [[basis]]
$$
\dim(V) = |B|
$$

### every [[basis]] of a [[vector space]] has the same [[cardinality]]
- let $\{v_1, ..., v_n\}$ and $\{w_1, ..., w_m\}$ be a [[basis|bases]] of [[vector space]] $V$
- then $n=m$

_______________________

### basis
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- $\{v_1, ..., v_n\}$ is a [[basis]] of $V$ if
1) $\{v_1, ..., v_n\}$ is a spanning [[set]] of $V$
2) $\{v_1, ..., v_n\}$ is [[linear independent]]


### linear independent
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- $v_1, ..., v_n \in V$ are [[linear independent]] if the following condition is true
$$
\forall \lambda_i \in \mathbb{K} :\sum\limits_{i \in [n]} v_i \lambda_i = 0 \Rightarrow \forall \lambda_i \in \mathbb{K}:  \lambda_i = 0
$$

### spanning [[set]] of a [[vector space]]
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- the [[set]] $\{v_1, ..., v_n\}$ is a **spanning set** or **generating set** of $V$ if $\mathrm{span}(v_1, ..., v_n) = V$
$$
\mathrm{span}(v_1, ..., v_n) = \{w \in V: \lambda_1, ... \lambda_n \in \mathbb{K}: w = \lambda_1 \cdot v_1 + ... + \lambda_n \cdot v_n\} = V
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
(\lambda + \mu) + v = \lambda + (\mu + v)
$$
7) $(V, \cdot)$ has a [[neutral element]] $1$ 
$$
v \cdot 1 = v
$$

Tags: mathematics linear_algebra
<!--ID: 1713707296737-->
END