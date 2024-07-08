### subspace
- a [[vector space]] $(V, +, \cdot)$ on a [[field]] $\mathbb{K}$
- $H \subseteq V$ is a [[subspace]] of $V$ if $H$ is a [[vector space]] itself equivalently the following conditions are true
1) $v \in H \land \lambda \in \mathbb{K} \rightarrow \lambda \cdot v \in H$ ([[closure|closed]] for [[multiplication]] with [[scalar|scalars]])
2) $v,w \in H \rightarrow v + w \in H$ ([[closure|closed]] for [[addition]])



### [[subspace|subspaces]] of $\mathbb{R}^3$
- trivial subspaces: $\mathbb{R}^3$ and $\{(0, 0, 0)\}$
- every line or plane that contains the origin $(0,0,0)$ is a [[subspace]] of $\mathbb{R}^3$
→ $H = \{\lambda \cdot v + \mu \cdot w: \lambda, \mu \in \mathbb{R}\}$ with [[vector|vectors]] $v \in \mathbb{R}^3$ and $w \in \mathbb{R}^3$ is a [[subspace]] of $\mathbb{R}^3$ 
- note: is $v \perp w$ $H$ and $v, w \neq (0,0,0)$ $H$ is a plane, if $v = w = (0,0,0)$ its the trivial [[subspace]] $\{(0, 0, 0)\}$ and otherwise $H$ is a line
#### proof
- let $H = \{\lambda \cdot v + \mu \cdot w: \lambda, \mu \in \mathbb{R}\}$ be a general plane or line spanned by the [[vector|vectors]] $v \in \mathbb{R}^3$ and $w \in \mathbb{R}^3$ 
- $H \subseteq \mathbb{R}^3$ and $(0,0,0) \in H$
- $H$ is [[closure|closed]] regarding [[addition]] 
$$
\begin{split}
x \in H &\Rightarrow \exists \lambda, \mu \in \mathbb{R}: x = \lambda \cdot v + \mu \cdot w \\
x' \in H &\Rightarrow   \exists \lambda', \mu' \in \mathbb{R}: x' = \lambda \cdot v' + \mu' \cdot w' \\
x + x' &= v \cdot (\lambda + \lambda') + w \cdot (\mu + \mu')  \in H \quad (\text{since } \mathbb{K} \text{ is closed for addtion}) 
\end{split}
$$
- $H$ is [[closure|closed]] for [[multiplication]] with [[scalar|scalars]]
$$
\begin{split}
x \in H &\Rightarrow \exists \lambda, \mu \in \mathbb{R}: x = \lambda \cdot v + \mu \cdot w \\
\gamma \in \mathbb{K}: \gamma \cdot x &= (\lambda \cdot \gamma) \cdot v + (\mu \cdot \gamma) \cdot w \\
\Rightarrow &= \gamma \cdot x  \in H \quad (\text{since } \mathbb{K} \text{ is closed for multiplication}) 
\end{split}
$$


# -----------------------
![[vector space#vector space]]
# anki
START
Basic
[[subspace]] of a [[vector space]]
- definition
Back: 
### subspace
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
_______________________
#### closure
- a [[set|subset]] $H \subseteq V$ is closed under an operation $\circ$ if the following condition is true
$$
v, w \in H \rightarrow v \circ w \in H
$$
- example $(\mathbb{Z}, +)$ is [[closure|closed]] but $(\mathbb{Z}, :)$ is not

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
<!--ID: 1713592163920-->
END


START
Basic
- all [[subspace|subspaces]] of $(\mathbb{R}^3, +, \cdot)$ with proof
Back: 
### [[subspace|subspaces]] of $\mathbb{R}^3$
- trivial subspaces: $\mathbb{R}^3$ and $\{(0, 0, 0)\}$
- every line or plane that contains the origin $(0,0,0)$ is a [[subspace]] of $\mathbb{R}^3$
→ $H = \{\lambda \cdot v + \mu \cdot w: \lambda, \mu \in \mathbb{R}\}$ with [[vector|vectors]] $v \in \mathbb{R}^3$ and $w \in \mathbb{R}^3$ is a [[subspace]] of $\mathbb{R}^3$ 
- note: is $v \perp w$ $H$ and $v, w \neq (0,0,0)$ $H$ is a plane, if $v = w = (0,0,0)$ its the trivial [[subspace]] $\{(0, 0, 0)\}$ and otherwise $H$ is a line

#### proof
- let $H = \{\lambda \cdot v + \mu \cdot w: \lambda, \mu \in \mathbb{R}\}$ be a general plane or line spanned by the [[vector|vectors]] $v \in \mathbb{R}^3$ and $w \in \mathbb{R}^3$ 
- $H \subseteq \mathbb{R}^3$ and $(0,0,0) \in H$
- $H$ is [[closure|closed]] regarding [[addition]] 
$$
\begin{split}
x \in H &\Rightarrow \exists \lambda, \mu \in \mathbb{R}: x = \lambda \cdot v + \mu \cdot w \\
x' \in H &\Rightarrow   \exists \lambda', \mu' \in \mathbb{R}: x' = \lambda \cdot v' + \mu' \cdot w' \\
x + x' &= v \cdot (\lambda + \lambda') + w \cdot (\mu + \mu')  \in H \quad (\text{since } \mathbb{K} \text{ is closed for addtion}) 
\end{split}
$$
- $H$ is [[closure|closed]] for [[multiplication]] with [[scalar|scalars]]
$$
\begin{split}
x \in H &\Rightarrow \exists \lambda, \mu \in \mathbb{R}: x = \lambda \cdot v + \mu \cdot w \\
\gamma \in \mathbb{K}: \gamma \cdot x &= (\lambda \cdot \gamma) \cdot v + (\mu \cdot \gamma) \cdot w \\
\Rightarrow &= \gamma \cdot x  \in H \quad (\text{since } \mathbb{K} \text{ is closed for multiplication}) 
\end{split}
$$



#### subspace
- a [[vector space]] $(V, +, \cdot)$ on a [[field]] $\mathbb{K}$
- $H \subseteq V$ is a [[subspace]] of $V$ if $H$ is a [[vector space]] itself equivalently the following conditions are true
1) $v \in H \land \lambda \in \mathbb{K} \rightarrow \lambda \cdot v \in H$ ([[closure|closed]] for [[multiplication]] with [[scalar|scalars]])
2) $v,w \in H \rightarrow v + w \in H$ ([[closure|closed]] for [[addition]])



_______________________
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
### closure
- a [[set|subset]] $H \subseteq V$ is closed under an operation $\circ$ if the following condition is true
$$
v, w \in H \rightarrow v \circ w \in H
$$
- example $(\mathbb{Z}, +)$ is [[closure|closed]] but $(\mathbb{Z}, :)$ is not

### commutative
a operation is commutative if the following is true in general
$$
a \circ b = b \circ a
$$

### associative
$$
a \circ (b \circ c) = (a \circ b) \circ c
$$

### neutral element
$n$ is a [[neutral element]] of a [[operation]] $\circ$ if
$$
a \circ n = n \circ a = a 
$$

### distributive
two operations $\circ$ and $\times$ are distributive if the following is true in general
$$
(a \times b) \circ b = (a \circ c) \times (b \circ c)
$$

Tags: mathematics linear_algebra
<!--ID: 1713612993498-->
END



START
Basic
Is the statement "the empty set is a subspace of every vector space" true of false?
Back: 
Vector spaces can't be empty, because they have to contain additive identity and therefore at least 1 element!

#### subspace
- a [[vector space]] $(V, +, \cdot)$ on a [[field]] $\mathbb{K}$
- $H \subseteq V$ is a [[subspace]] of $V$ if $H$ is a [[vector space]] itself equivalently the following conditions are true
1) $v \in H \land \lambda \in \mathbb{K} \rightarrow \lambda \cdot v \in H$ ([[closure|closed]] for [[multiplication]] with [[scalar|scalars]])
2) $v,w \in H \rightarrow v + w \in H$ ([[closure|closed]] for [[addition]])



_______________________
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
### closure
- a [[set|subset]] $H \subseteq V$ is closed under an operation $\circ$ if the following condition is true
$$
v, w \in H \rightarrow v \circ w \in H
$$
- example $(\mathbb{Z}, +)$ is [[closure|closed]] but $(\mathbb{Z}, :)$ is not

### commutative
a operation is commutative if the following is true in general
$$
a \circ b = b \circ a
$$

### associative
$$
a \circ (b \circ c) = (a \circ b) \circ c
$$

### neutral element
$n$ is a [[neutral element]] of a [[operation]] $\circ$ if
$$
a \circ n = n \circ a = a 
$$

### distributive
two operations $\circ$ and $\times$ are distributive if the following is true in general
$$
(a \times b) \circ b = (a \circ c) \times (b \circ c)
$$

Tags: mathematics linear_algebra

END


