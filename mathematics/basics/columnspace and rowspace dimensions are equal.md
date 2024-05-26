### the [[column space]] has the same number of [[dimensions]] as the [[row space]]
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
$$
\begin{split}
\dim(\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right)) = \dim(\mathrm{span}\left(A_{(*, 1)}, ..., A_{(*, m)}\right)) 
\end{split}
$$
#### proof
- let $B = \left(\begin{matrix}b_1\ ... \ b_r \end{matrix}\right) \in \mathbb{R}^{n \times r}$ be a [[basis]] of the [[column space]] of $A \in \mathbb{R}^{n \times m}$

$$
\begin{split}
&\forall j \in [m]: A_{*,j} = \sum_{l \in [r]} \lambda_{l, j} \cdot b_l \\
\Rightarrow& A = B C \text{ with } C = (\lambda_{(l, j)})_{l \in [r], j \in [m]} \in \mathbb{R}^{r \times m} \\
\Rightarrow& A_{(i,*)} = \sum_{l \in [r]}  b_{i,l} C_{(l, *)} \\ 
\end{split}
$$
- that means that every row vector $A_{(i,*)}$ can be expressed as a [[linear combinations]] of $r$ [[vector|vectors]] $l \in [r]:C_{(l, *)}$
- it follows $r = \dim\left(\mathrm{span}\left(A_{(*, 1)}, ..., A_{(*, m)}\right)\right) \geq \dim\left(\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right)\right)$
- the proof for the other directions is equivalent so that $r = \dim\left(\mathrm{span}\left(A_{(*, 1)}, ..., A_{(*, m)}\right)\right) = \dim\left(\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right)\right) = \mathrm{rank}(A)$

# ------------------------

![[dimensions#dimensions of a vector space]]

![[column space#column space]]

# anki

START
Basic
proof that the [[column space]] has the same number of [[dimensions]] as the [[row space]]
 
Back: 
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
$$
\begin{split}
\dim(\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right)) = \dim(\mathrm{span}\left(A_{(*, 1)}, ..., A_{(*, m)}\right)) 
\end{split}
$$
#### proof
- let $B = \left(\begin{matrix}b_1\ ... \ b_r \end{matrix}\right) \in \mathbb{R}^{n \times r}$ be a [[basis]] of the [[column space]] of $A \in \mathbb{R}^{n \times m}$

$$
\begin{split}
&\forall j \in [m]: A_{*,j} = \sum_{l \in [r]} \lambda_{l, j} \cdot b_l \\
\Rightarrow& A = B C \text{ with } C = (\lambda_{(l, j)})_{l \in [r], j \in [m]} \in \mathbb{R}^{r \times m} \\
\Rightarrow& A_{(i,*)} = \sum_{l \in [r]}  b_{i,l} C_{(l, *)} \\ 
\end{split}
$$
- that means that every row vector $A_{(i,*)}$ can be expressed as a [[linear combinations]] of $r$ [[vector|vectors]] $l \in [r]:C_{(l, *)}$
- it follows $r = \dim\left(\mathrm{span}\left(A_{(*, 1)}, ..., A_{(*, m)}\right)\right) \geq \dim\left(\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right)\right)$
- the proof for the other directions is equivalent so that $r = \dim\left(\mathrm{span}\left(A_{(*, 1)}, ..., A_{(*, m)}\right)\right) = \dim\left(\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right)\right) = \mathrm{rank}(A)$

_________________
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


### dimensions of a [[vector space]]
- let $B$ be a [[vector space]] and $B$ be a [[basis]] of $V$
- the dimensions of $V$ are defines as the [[cardinality]] of its [[basis]]
- note: the [[vector space]] $\{{0}\}$ has per definition zero dimension 
- note: since every [[basis]] of a [[vector space]] has the same [[cardinality]] (see [[basis#every basis of a vector space has the same cardinality|here]]) the [[dimensions]] of a [[vector space]] is equal to the [[cardinality]] of all of its [[basis]]
$$
\dim(V) = |B|
$$

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

Tags: mathematics linear_algebra
<!--ID: 1713707296730-->
END