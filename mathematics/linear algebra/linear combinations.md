### linear combinations
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- the [[linear combinations]] of $v_1, ..., v_n$ is defined as the following [[set]]
$$
\mathrm{span}(v_1, ..., v_n) = \{w \in V: \lambda_1, ... \lambda_n \in \mathbb{K}: w = \lambda_1 \cdot v_1 + ... + \lambda_n \cdot v_n\}
$$

### spanning [[set]] of a [[vector space]]
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- the [[set]] $\{v_1, ..., v_n\}$ is a **spanning set** or **generating set** of $V$ if $\mathrm{span}(v_1, ..., v_n) = V$
$$
\mathrm{span}(v_1, ..., v_n) = \{w \in V: \lambda_1, ... \lambda_n \in \mathbb{K}: w = \lambda_1 \cdot v_1 + ... + \lambda_n \cdot v_n\} = V
$$

### the span is a [[subspace]]
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- every span $\mathrm{span}(v_1, ..., v_n)$ is a [[subspace]] of $V$
#### proof
1) $\mathrm{span}(v_1, ..., v_n)$ is [[closure|closed]] regarding [[addition]] 
$$
\begin{split}
x \in \mathrm{span}(v_1, ..., v_n) &\Rightarrow \exists \lambda_i, i \in [n]: x = \sum_{i \in [n]} \lambda_i \cdot v_i \\
x' \in \mathrm{span}(v_1, ..., v_n) &\Rightarrow \exists \lambda_i', i \in [n]: x']' = \sum_{i \in [n]} \lambda_i' \cdot v_i \\
&\Rightarrow x + x' = \sum_{i \in [n]} (\lambda_i+\lambda_i') \cdot v_i \in \mathrm{span}(v_1, ..., v_n) \\ 
&(\text{since } \lambda_i+\lambda_i' \in \mathbb{K})
\end{split}
$$
2) $\mathrm{span}(v_1, ..., v_n)$ is [[closure|closed]] for [[multiplication]] with [[scalar|scalars]]
$$
\begin{split}
x \in \mathrm{span}(v_1, ..., v_n) &\Rightarrow \exists \lambda_i, i \in [n]: x = \sum_{i \in [n]} \lambda_i \cdot v_i \\
\gamma \in \mathbb{K}: \gamma \cdot x &= \sum_{i \in [n]} \gamma \cdot \lambda_i \cdot v_i \in \mathrm{span}(v_1, ..., v_n) \\
&(\text{since } \lambda_i \cdot \gamma' \in \mathbb{K})
\end{split}
$$

# ---------------------
![[subspace#subspace]]

![[vector space#vector space]]

# anki

START
Basic
proof that

Back: 


_______________________
#### linear combinations
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- the [[linear combinations]] of $v_1, ..., v_n$ is defined as the following [[set]]
$$
\mathrm{span}(v_1, ..., v_n) = \{w \in V: \lambda_1, ... \lambda_n \in \mathbb{K}: w = \lambda_1 \cdot v_1 + ... + \lambda_n \cdot v_n\}
$$

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

Tags: mathematics linear_algebra
<!--ID: 1713631630218-->
END


START
Basic
proof that
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- every span $\mathrm{span}(v_1, ..., v_n)$ is a [[subspace]] of $V$
Back: 
### the span is a [[subspace]]

1) $\mathrm{span}(v_1, ..., v_n)$ is [[closure|closed]] regarding [[addition]] 
$$
\begin{split}
x \in \mathrm{span}(v_1, ..., v_n) &\Rightarrow \exists \lambda_i, i \in [n]: x = \sum_{i \in [n]} \lambda_i \cdot v_i \\
x' \in \mathrm{span}(v_1, ..., v_n) &\Rightarrow \exists \lambda_i', i \in [n]: x']' = \sum_{i \in [n]} \lambda_i' \cdot v_i \\
&\Rightarrow x + x' = \sum_{i \in [n]} (\lambda_i+\lambda_i') \cdot v_i \in \mathrm{span}(v_1, ..., v_n) \\ 
&(\text{since } \lambda_i+\lambda_i' \in \mathbb{K})
\end{split}
$$
2) $\mathrm{span}(v_1, ..., v_n)$ is [[closure|closed]] for [[multiplication]] with [[scalar|scalars]]
$$
\begin{split}
x \in \mathrm{span}(v_1, ..., v_n) &\Rightarrow \exists \lambda_i, i \in [n]: x = \sum_{i \in [n]} \lambda_i \cdot v_i \\
\gamma \in \mathbb{K}: \gamma \cdot x &= \sum_{i \in [n]} \gamma \cdot \lambda_i \cdot v_i \in \mathrm{span}(v_1, ..., v_n) \\
&(\text{since } \lambda_i \cdot \gamma' \in \mathbb{K})
\end{split}
$$


_______________________
#### linear combinations
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- the [[linear combinations]] of $v_1, ..., v_n$ is defined as the following [[set]]
$$
\mathrm{span}(v_1, ..., v_n) = \{w \in V: \lambda_1, ... \lambda_n \in \mathbb{K}: w = \lambda_1 \cdot v_1 + ... + \lambda_n \cdot v_n\}
$$

#### subspace
- a [[vector space]] $(V, +, \cdot)$ on a [[field]] $\mathbb{K}$
- $H \subseteq V$ is a [[subspace]] of $V$ if $H$ is a [[vector space]] itself equivalently the following conditions are true
1) $v \in H \land \lambda \in \mathbb{K} \rightarrow \lambda \cdot v \in H$ ([[closure|closed]] for [[multiplication]] with [[scalar|scalars]])
2) $v,w \in H \rightarrow v + w \in H$ ([[closure|closed]] for [[addition]])

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

Tags: mathematics linear_algebra
<!--ID: 1713631630223-->
END