### linear function
- let $F:V \rightarrow W$ be a [[function]] from one [[vector space]] $(V, +, \cdot)$ to another [[vector space]] $(W,\oplus, \odot)$ 
- $F$ is a [[linear function]] if the following is true

$$
\forall v,w \in V, \lambda , \mu \in \mathbb{K}:F(\lambda v + \mu w) = \lambda \odot F(v) \oplus \mu \odot F(W) 
$$

### [[kernel]] if a [[linear function]]
- given a [[linear function]] $F:V \rightarrow W$ the [[kernel]] of $F$ is defined as follows
$$
\ker(F) = \{v \in V : F(v) = 0\} \subseteq V
$$
- note: the [[kernel]] of a [[linear function]] refers to the same comcept as the [[nullspace]] of a [[matrix]] because a [[matrix]] induces a [[linear function]]
### [[image]] if a [[linear function]]
- given a [[linear function]] $F:V \rightarrow W$ the [[image]] of $F$ is defined as follows
$$
F(S) = \{w \in W : \exists v \in S:  F(v) = w\} \subseteq W
$$

### range of a [[linear function]]
- given a [[linear function]] $F:V \rightarrow W$ the range of $F$ is defined as the [[image]] if its domain
$$
\mathrm{range} (F) = \{w \in W : \exists v \in V:  F(v) = w\} \subseteq W
$$
- note: the range of a [[linear function]] refers to the same comcept as the [[column space]] of a [[matrix]] because a [[matrix]] induces a [[linear function]]
# --------------------------

![[function#function]]

# anki

START
Basic
definitions
- [[linear function]]
- [[kernel]]
- [[image]]
- range

differences
- [[kernel]] vs [[nullspace]]
- [[image]] vs range vs [[column space]]
 
Back: 
### linear function
- let $F:V \rightarrow W$ be a [[function]] from one [[vector space]] $(V, +, \cdot)$ to another [[vector space]] $(W,\oplus, \odot)$ 
- $F$ is a [[linear function]] if the following is true

$$
\forall v,w \in V, \lambda , \mu \in \mathbb{K}:F(\lambda v + \mu w) = \lambda \odot F(v) \oplus \mu \odot F(W) 
$$

### [[kernel]] if a [[linear function]]
- given a [[linear function]] $F:V \rightarrow W$ the [[kernel]] of $F$ is defined as follows
$$
\ker(F) = \{v \in V : F(v) = 0\} \subseteq V
$$
- note: the [[kernel]] of a [[linear function]] refers to the same comcept as the [[nullspace]] of a [[matrix]] because a [[matrix]] induces a [[linear function]]

### [[image]] if a [[linear function]]
- given a [[linear function]] $F:V \rightarrow W$ the [[image]] of $F$ is defined as follows
$$
F(S) = \{w \in W : \exists v \in S:  F(v) = w\} \subseteq W
$$

### range of a [[linear function]]
- given a [[linear function]] $F:V \rightarrow W$ the range of $F$ is defined as the [[image]] if its domain
$$
\mathrm{range} (F) = \{w \in W : \exists v \in V:  F(v) = w\} \subseteq W
$$
- note: the range of a [[linear function]] refers to the same comcept as the [[column space]] of a [[matrix]] because a [[matrix]] induces a [[linear function]]

_________________

### function
- a [[function]] $f$ is map of elements from one [[set]] $A$ to the elements of another [[set]] $B$ such that all elements of $A$ are mapped to exactly one element from $B$
- the [[set]] $A$ is called the **domain** and the [[set]] $B$ is called the **co-domain**
- formal a [[function]] is a [[relation]] from one [[set]] to another [[set]] that satisfies the following two conditions:
$$
\begin{split}
&f: A \rightarrow B \\
\Rightarrow& R_f= \{(x, y): x \in A: f(x) = y\} = graph(f)\\
&\forall a \in A: \exists b \in B: (a, b) \in R_f \\
&(a, b) \in R_f \land  (a, c) \in R_f \Rightarrow b = c\\
\end{split}
$$
- for every subset of $C\subseteq A$ we define a [[set]] $f(C)$ as follows
$$
\begin{split}
f(C) = \{y \in B: \exists c \in C: f(c) = b\}
\end{split}
$$


### column space
- the [[column space]] of a [[matrix]] $A \in \mathbb{R}^{n \times m}$ is defined as the [[linear combinations]] if its column vectors $A_{(1, *)}, ..., A_{(n, *)}  \in \mathbb{R}^m$
$$
\begin{split}
\mathrm{colspace}(A)
&=\mathrm{span}\left(A_{(*, 1)}, ..., A_{(*, 1)}\right) \\
&=\left\{ Ax: x \in \mathbb{R}^m\right\} \subseteq\mathbb{R}^n \\
&=\{w \in \mathbb{R}^n: \lambda_1, ... \lambda_n \in \mathbb{R}: w = \lambda_1 \cdot A_{(*, 1)} + ... + \lambda_n \cdot A_{(*, m)}\} \\
\end{split}
$$

### nullspace
- the [[nullspace]] of a [[matrix]] is the [[set]] of [[vector|vectors]] that is mapped to the origin by the [[linear function]] induced by $A$
$$
N(A)=\left\{ x \in \mathbb{R}^{m} \mid Ax=0 \right\}
\subseteq\mathbb{R}^{m}
$$


Tags: mathematics linear_algebra
<!--ID: 1713765482794-->
END