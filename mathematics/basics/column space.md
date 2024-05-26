### column space
- the [[column space]] of a [[matrix]] $A \in \mathbb{R}^{n \times m}$ is defined as the [[linear combinations]] if its column vectors $A_{(*, 1)}, ..., A_{(*, m)}  \in \mathbb{R}^n$
$$
\begin{split}
\mathrm{colspace}(A)
&=\mathrm{span}\left(A_{(*, 1)}, ..., A_{(*, m)}\right) \\
&=\left\{ Ax: x \in \mathbb{R}^m\right\} \subseteq\mathbb{R}^n \\
&=\{w \in \mathbb{R}^n: \lambda_1, ... \lambda_n \in \mathbb{R}: w = \lambda_1 \cdot A_{(*, 1)} + ... + \lambda_n \cdot A_{(*, m)}\} \\
\end{split}
$$


### properties

- $dim(range(A)) + dim(kern(A)) = \left| \mathcal{J} \right|$ [[rank nullity theorem]]


# ------------------
![[linear combinations#linear combinations]]

![[matrix#matrix]]

# anki

START
Basic
definitions
- [[column space]]
- [[row space]]
- [[linear combinations]]
 
Back: 
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
### row space
- the [[row space]] of a [[matrix]] $A \in \mathbb{R}^{n \times m}$ is defined as the [[linear combinations]] if its row [[vector|vectors]] $A_{(1, *)}, ..., A_{(n, *)}  \in \mathbb{R}^m$
$$
\begin{split}
\mathrm{rowspace}(A)
&=\mathrm{span}\left(A_{(1, *)}, ..., A_{(n, *)}\right) \\
&=\{w \in \mathbb{R}^m: \lambda_1, ... \lambda_n \in \mathbb{R}: w = \lambda_1 \cdot A_{(1, *)} + ... + \lambda_n \cdot A_{(n, *)}\} \\
\end{split}
$$

### linear combinations
- given a [[vector space]] $V$ and $n$ [[vector|vectors]] $v_1, ..., v_n \in V$ 
- the [[linear combinations]] of $v_1, ..., v_n$ is defined as the following [[set]]
$$
\mathrm{span}(v_1, ..., v_n) = \{w \in V: \lambda_1, ... \lambda_n \in \mathbb{K}: w = \lambda_1 \cdot v_1 + ... + \lambda_n \cdot v_n\}
$$


Tags: mathematics linear_algebra
<!--ID: 1665328452058-->
END


