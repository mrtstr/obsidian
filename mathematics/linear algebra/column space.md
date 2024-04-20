### column space
- the [[column space]] of a [[matrix]] $A \in \mathbb{R}^{n \times m}$ is defined as the [[linear combinations]] if its column vectors $A_{(1, *)}, ..., A_{(n, *)}  \in \mathbb{R}^m$
$$
\begin{split}
\mathrm{range}(A)
&=\left\{ Ax: x \in \mathbb{R}^m\right\} \subseteq\mathbb{R}^n \\
&=\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right) \\
&=\{w \in \mathbb{R}^n: \lambda_1, ... \lambda_n \in \mathbb{R}: w = \lambda_1 \cdot A_{(1, *)} + ... + \lambda_n \cdot A_{(n, *)}\} \\
\end{split}
$$
### properties

- $dim(range(A)) + dim(kern(A)) = \left| \mathcal{J} \right|$ [[rank nullity theorem]]
- $dim(range(A)) = dim(rowspace(A)) = rank(A)$ (the [[column space]] and the [[row space]] have the same number of dimensions) and they are equal to the [[rank]]

# ------------------
![[linear combinations#linear combinations]]

![[matrix#matrix]]

# anki

START
Basic
definitions
- [[column space]]
- [[linear combinations]]
 
Back: 
### column space
- the [[column space]] of a [[matrix]] $A \in \mathbb{R}^{n \times m}$ is defined as the [[linear combinations]] if its column vectors $A_{(1, *)}, ..., A_{(n, *)}  \in \mathbb{R}^m$
$$
\begin{split}
\mathrm{range}(A)
&=\left\{ Ax: x \in \mathbb{R}^m\right\} \subseteq\mathbb{R}^n \\
&=\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right) \\
&=\{w \in \mathbb{R}^n: \lambda_1, ... \lambda_n \in \mathbb{R}: w = \lambda_1 \cdot A_{(1, *)} + ... + \lambda_n \cdot A_{(n, *)}\} \\
\end{split}
$$
### linear combinations
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- the [[linear combinations]] of $v_1, ..., v_n$ is defined as the following [[set]]
$$
\mathrm{span}(v_1, ..., v_n) = \{w \in V: \lambda_1, ... \lambda_n \in \mathbb{K}: w = \lambda_1 \cdot v_1 + ... + \lambda_n \cdot v_n\}
$$

_________________
### matrix
$$
\begin{split}
A  \in \mathbb{R}^{n  \times m}
&= \left(a_{i,j} \right)_{i \in [n], j \in [m]} \\
&= \left(A_{(*:j)} \right)_{j \in [m]}
= 
\begin{pmatrix}   A_{(*:1)} &   ... & A_{(*:m}   \end{pmatrix}\\
&= \left(A_{(i:*)} \right)_{i \in [n]}
=  
\begin{pmatrix}   A_{(1:*)} \\   ... \\ A_{(n:*)}   \end{pmatrix}
\end{split}
$$
Tags: mathematics linear_algebra
<!--ID: 1665328452058-->
END