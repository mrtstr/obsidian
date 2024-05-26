### basis
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- $\{v_1, ..., v_n\}$ is a [[basis]] of $V$ if
1) $\{v_1, ..., v_n\}$ is a spanning [[set]] of $V$
2) $\{v_1, ..., v_n\}$ is [[linear independent]]


![[linear independent#linear independent]]

![[span#spanning set of a vector space]]


### [[linear combinations]] of a [[basis]]
- let $\{v_1, ..., v_n\}$ be a [[basis]] of [[vector space]] $V$
1) $\forall w \in V: \exists \lambda_1, ..., \lambda_i \in \mathbb{K}: w= \lambda_i \cdot v_1 + ... + \lambda_n \cdot v_n$
2) $\lambda_1, ..., \lambda_i$ are uniqe
#### proof
1) results directly from $\{v_1, ..., v_n\}$ being a spanning set of $V$
2) follows from $\{v_1, ..., v_n\}$ being [[linear independent]]
$$
\begin{split}
&\lambda_i \cdot v_1 + ... + \lambda_n \cdot v_n = \lambda_i' \cdot v_1 + ... + \lambda_n' \cdot v_n \\
\Rightarrow& (\lambda_i- \lambda_i') \cdot v_1 + ... + (\lambda_n- \lambda_n') \cdot v_n = 0 \\
\Rightarrow& \forall i \in [n]: \lambda_i- \lambda_i' = 0 \quad \text{(linear independence)} \\
\end{split}
$$

### every [[basis]] of a [[vector space]] has the same [[cardinality]]
- let $\{v_1, ..., v_n\}$ and $\{w_1, ..., w_m\}$ be a [[basis|bases]] of [[vector space]] $V$
- then $n=m$
#### TODO add proof
# -----------------


# anki
START
Basic
definition of [[basis]]
Back: 
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

______________________
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
<!--ID: 1713633549046-->
END


# anki
START
Basic
proof for:
[[linear combinations]] of a [[basis]] are unique
Back: 
#### [[linear combinations]] of a [[basis]]
- let $\{v_1, ..., v_n\}$ be a [[basis]] of [[vector space]] $V$
1) $\forall w \in V: \exists \lambda_1, ..., \lambda_i \in \mathbb{K}: w= \lambda_i \cdot v_1 + ... + \lambda_n \cdot v_n$
2) $\lambda_1, ..., \lambda_i$ are uniqe
#### proof
1) results directly from $\{v_1, ..., v_n\}$ being a spanning set of $V$
2) follows from $\{v_1, ..., v_n\}$ being [[linear independent]]
$$
\begin{split}
&\lambda_i \cdot v_1 + ... + \lambda_n \cdot v_n = \lambda_i' \cdot v_1 + ... + \lambda_n' \cdot v_n \\
\Rightarrow& (\lambda_i- \lambda_i') \cdot v_1 + ... + (\lambda_n- \lambda_n') \cdot v_n = 0 \\
\Rightarrow& \forall i \in [n]: \lambda_i- \lambda_i' = 0 \quad \text{(linear independence)} \\
\end{split}
$$

______________________
#### basis
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- $\{v_1, ..., v_n\}$ is a [[basis]] of $V$ if
1) $\{v_1, ..., v_n\}$ is a spanning [[set]] of $V$
2) $\{v_1, ..., v_n\}$ is [[linear independent]]

#### linear independent
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- $v_1, ..., v_n \in V$ are [[linear independent]] if the following condition is true
$$
\forall \lambda_i \in \mathbb{K} :\sum\limits_{i \in [n]} v_i \lambda_i = 0 \Rightarrow \forall \lambda_i \in \mathbb{K}:  \lambda_i = 0
$$

#### spanning [[set]] of a [[vector space]]
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- the [[set]] $\{v_1, ..., v_n\}$ is a **spanning set** or **generating set** of $V$ if $\mathrm{span}(v_1, ..., v_n) = V$


#### vector space
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
<!--ID: 1713633549051-->
END