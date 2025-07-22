### power iteration
- algorithm for finding the [[eigenvector]] of the largest [[eigenvalue]] of a [[symmetric matrix]] $M \in \mathbb{R}^{d \times d}$ with the following update rule with $v^{(0)}\neq 0$

$$
\begin{split}
v^{(t+1)} = \frac{1}{\|M v^{(t)} \|} Mv^{(t)} \xrightarrow{t\to \infty} U_1
\end{split}
$$

- let $M=UDU^\top$ be the [[eigendecomposition]] of $M$ with $D=\mathrm{diag}(\lambda_1, ..., \lambda_d)$ and $U=[U_1, ..., U_d]$ with $\lambda_1\geq \lambda_2... \geq \lambda_d$ being the [[eigenvalue]]s and $U_i$ the [[orthonormal]] [[eigenvector]]
- let $\alpha \in \mathbb{R}^d$ be the representation of $v^{(t)}$ in the eigenbasis $U$
- as $t \to \infty$ the $\lambda_1^k  U_1 \alpha_1$ is dominating and the iteration converges to the [[eigenvector]] of $\lambda_1$ while the normalization scales down the other terms

$$
\begin{split}
v^{(t)} &= U\alpha = \sum U_i \alpha_i \\
Mv^{(t)} 
&= MU\alpha = UDU^\top U\alpha \\
&= UD\alpha \\
&= \sum_{i=1}^{d}  \sum_{j=1}^{d} U_{(*,i)}  D_{(i,j)} \alpha_j \\
&= \sum_{i=1}^{d}  \sum_{j=1}^{d} U_i  D_{(i,j)} \alpha_j \\
&= \sum_{i=1}^{d}  \lambda_i  U_i \alpha_i \\
v^{(t+1)} 
&= \frac{1}{C_1} Mv^{(t)} \\
&= \frac{1}{C_1} \sum_{i=1}^{d}  \lambda_i  U_i \alpha_i \\
v^{(t+k)} 
&= \frac{1}{C_2} M^kv^{(t)} \\
&= \frac{1}{C_2} \sum_{i=1}^{d}  \lambda_i^k  U_i \alpha_i \\
\end{split}
$$
# ---------------

![[eigendecomposition#eigendecomposition]]


# anki

START
Basic
[[power iteration]]
- what does the algorithm do
- update rule
- show that it converges and conditions
Back: 
### power iteration
- algorithm for finding the [[eigenvector]] of the largest [[eigenvalue]] of a [[symmetric matrix]] $M \in \mathbb{R}^{d \times d}$ with the following update rule with $v^{(0)}\neq 0$

$$
\begin{split}
v^{(t+1)} = \frac{1}{\|M v^{(t)} \|} Mv^{(t)} \xrightarrow{t\to \infty} U_1
\end{split}
$$

- let $M=UDU^\top$ be the [[eigendecomposition]] of $M$ with $D=\mathrm{diag}(\lambda_1, ..., \lambda_d)$ and $U=[U_1, ..., U_d]$ with $\lambda_1\geq \lambda_2... \geq \lambda_d$ being the [[eigenvalue]]s and $U_i$ the [[orthonormal]] [[eigenvector]]
- let $\alpha \in \mathbb{R}^d$ be the representation of $v^{(t)}$ in the eigenbasis $U$
- as $t \to \infty$ the $\lambda_1^k  U_1 \alpha_1$ is dominating and the iteration converges to the [[eigenvector]] of $\lambda_1$ while the normalization scales down the other terms

$$
\begin{split}
v^{(t)} &= U\alpha = \sum U_i \alpha_i \\
Mv^{(t)} 
&= MU\alpha = UDU^\top U\alpha \\
&= UD\alpha \\
&= \sum_{i=1}^{d}  \sum_{j=1}^{d} U_{(*,i)}  D_{(i,j)} \alpha_j \\
&= \sum_{i=1}^{d}  \sum_{j=1}^{d} U_i  D_{(i,j)} \alpha_j \\
&= \sum_{i=1}^{d}  \lambda_i  U_i \alpha_i \\
v^{(t+1)} 
&= \frac{1}{C_1} Mv^{(t)} \\
&= \frac{1}{C_1} \sum_{i=1}^{d}  \lambda_i  U_i \alpha_i \\
v^{(t+k)} 
&= \frac{1}{C_2} M^kv^{(t)} \\
&= \frac{1}{C_2} \sum_{i=1}^{d}  \lambda_i^k  U_i \alpha_i \\
\end{split}
$$

_______________


### eigendecomposition
- a [[matrix]] $A \in \mathbb{R}^{n\times n}$ is a [[eigendecomposition]] if there exists a [[inverse matrix|inverable matrix]] $B\in \mathbb{R}^{n\times n}$ and a [[diagonal matrix]] $D=diag(\lambda_1, ..., \lambda_n)\in \mathbb{R}^{n\times n}$ such that the following decomposition is possible with $\lambda_1$, ..., $\lambda_n$ being the [[eigenvalue]]

$$
A = BDB^{-1}
$$
#### existence of eigendecomposition
- a [[matrix]] $A$ is [[eigendecomposition]] exactly when has  $n$ [[linear independent]] [[eigenvector]]
- a [[matrix]] $A$ has  $n$ [[linear independent]] [[eigenvector]] and thus is a [[eigendecomposition]] when it has $n$ distinct [[eigenvalue]] 

- note: the reverse is not true i.e. if $A$ doesn't have distinct eigenvalues it can still have $n$ [[linear independent]] [[eigenvector]] and thus still be a [[eigendecomposition]]
###### proof
- let $\lambda_1, ..., \lambda_n$ be the [[eigenvalue]] of $A$ with the corresponding [[eigenvector]] $v_i$ $\Rightarrow Av_i = \lambda_iv_i$
- since $v_1,..., v_n$ are [[linear independent]] $B=(v_1, ..., v_n)$ is invertable

$$
\begin{split}
Av_i &= \lambda_iv_i \\
\Rightarrow AB_{(*, j)} &= (BD)_{(*, j)} \\
\Rightarrow AB &= BD \\
\Rightarrow A &= BDB^{-1} \\
\end{split}
$$


Tags: mathematics SS25
<!--ID: 1753188946231-->
END