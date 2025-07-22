### principal component analysis
- represent a [[random vector]] in a lower dimensional [[latent space]] of a given [[dimensions|dimension]] such that it captures the most amount of [[variance]]
- [[principal component analysis]] computes an **orthogonal [[projection]]** of the input data into a lower-dimensional space in order to represent it in a reduced [[latent space]].
- The amount of information retained by the projection can be measured using the **[[explained variance]]**, which quantifies how much of the original variance is preserved.
- let $X \in \mathbb{R}^{d}$ be zero mean [[random variable]] $X \in \mathbb{R}^{n}$ with $\Sigma=\mathbb{VAR} \left[X\right]$ with a [[eigendecomposition|spectral decomposition]]  
- since $\Sigma$ is a [[symmetric matrix]] it is always a [[eigendecomposition]] with a [[orthonormal]] bases, and it admits a [[eigendecomposition]]

$$
\Sigma= \frac{1}{n} X^\top X =U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top
$$

- with $\lambda_1\geq ...\geq \lambda_d$ being the [[eigenvalue]] and $U=[U_1, ..., U_d] \in \mathbb{R}^{d \times d}$ its [[orthogonal matrix]] of[[eigenvector]]s


- Then the principal components $V_1, \dots, V_r$ that solve the following minimization problems are the [[orthonormal]] [[eigenvector]] of $\Sigma$
- in other words the [[principal component analysis]] is a reduced form of the [[eigendecomposition]] of the empirical [[covariance matrix]]

$$
\begin{split}
V_1 &= \arg\min_{\|v\|=1} \; \mathbb{E} \left[ \left\| X - P_{\mathrm{span}(v)}(X) \right\|_2^2 \right] = \pm U_1 \\
V_r &= \arg\min_{\|v\|=1,\; v \perp V_1, \dots, V_{r-1}} \; \mathbb{E} \left[ \left\| X - P_{\mathrm{span}(u_1, \dots, u_{r-1}, v)}(X) \right\|_2^2 \right] = \pm U_r
\end{split}
$$

- Equivalently, the optimal $r$-dimensional [[subspace]] $V = \mathrm{span}( U_1, \dots, U_r)$ minimizes the [[projection]] error:
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general

$$
\begin{split}
V^{(r)}
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X - P_V(X) \right\|_2^2 \right] \\
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X \right\|_2^2 \right] - \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
&= \arg\max_{\dim(V)=k} \; \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
\end{split}
$$

- this works because of the [[orthogonal|orthogonality]] $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ can be decomposed as  follows with $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ being constant and thus doesn't matter in an optimization problem
- this means that $V = \mathrm{span}( U_1, \dots, U_r)$ is the $r$ dimensional [[subspace]] that computes the most amount of [[variance]] of the data $X$

$$
\begin{split}
\mathbb{E} \left[ \left\| X \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| X -  P_V(X) + P_V(X) \right\|_2^2 \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] +2 \mathbb{E} \left[ \langle X,  X -  P_V(X)  \rangle \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
\end{split}
$$

- with the following being the projection itself (see [[projection#projection into an orthonormal subspace]]) 

$$
P_V(X) = VV^\top X
$$
### PCA for denoising
- the [[principal component analysis]] can be used to remove [[white noise]] from data $X$
- lets assume the signal contained in $X\in\mathbb{R}^d$ is contained $Z\in\mathbb{R}^r$ which is transformed with the matrix $B \in \mathbb{R}^{d \times r}$ with [[white noise]] $\epsilon$ on it

$$
\begin{split}
Z&\sim P_Z \\
X &= BZ + \epsilon \sim \mathcal{N}(0, \sigma^2 I_d)
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[X] 
&= \mathbb{VAR}[BZ] + \mathbb{VAR}[\epsilon] \\
&= B\mathbb{VAR}[Z]B^\top + \sigma^2 I_d \\
&= VDV^\top \\
\end{split}
$$

- if we would do a [[principal component analysis]] we would have $r$ larger [[eigenvalue]]s and $d-r$ smaller
- the [[principal component analysis]] can detect that and set $r$ such that the [[white noise]] is filtered out and the signal is preserved
# -----------

![[projection#projection into an orthonormal subspace]]

![[projection#projection into the column space]]

![[eigendecomposition#eigendecomposition]]


# anki

START
Basic
[[principal component analysis]]
- concept
- existence
- relationship to [[explained variance]] and [[eigendecomposition]]

Back: 
### principal component analysis
- represent a [[random vector]] in a lower dimensional [[latent space]] of a given [[dimensions|dimension]] such that it captures the most amount of [[variance]]
- [[principal component analysis]] computes an **orthogonal [[projection]]** of the input data into a lower-dimensional space in order to represent it in a reduced [[latent space]].
- The amount of information retained by the projection can be measured using the **[[explained variance]]**, which quantifies how much of the original variance is preserved.
- let $X \in \mathbb{R}^{d}$ be zero mean [[random variable]] $X \in \mathbb{R}^{n}$ with $\Sigma=\mathbb{VAR} \left[X\right]$ with a [[eigendecomposition|spectral decomposition]]  
- since $\Sigma$ is a [[symmetric matrix]] it is always a [[eigendecomposition]] with a [[orthonormal]] bases, and it admits a [[eigendecomposition]]

$$
\Sigma= \frac{1}{n} X^\top X =U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top
$$

- with $\lambda_1\geq ...\geq \lambda_d$ being the [[eigenvalue]] and $U=[U_1, ..., U_d] \in \mathbb{R}^{d \times d}$ its [[orthogonal matrix]] of[[eigenvector]]s


- Then the principal components $V_1, \dots, V_r$ that solve the following minimization problems are the [[orthonormal]] [[eigenvector]] of $\Sigma$
- in other words the [[principal component analysis]] is a reduced form of the [[eigendecomposition]] of the empirical [[covariance matrix]]

$$
\begin{split}
V_1 &= \arg\min_{\|v\|=1} \; \mathbb{E} \left[ \left\| X - P_{\mathrm{span}(v)}(X) \right\|_2^2 \right] = \pm U_1 \\
V_r &= \arg\min_{\|v\|=1,\; v \perp V_1, \dots, V_{r-1}} \; \mathbb{E} \left[ \left\| X - P_{\mathrm{span}(u_1, \dots, u_{r-1}, v)}(X) \right\|_2^2 \right] = \pm U_r
\end{split}
$$

- Equivalently, the optimal $r$-dimensional [[subspace]] $V = \mathrm{span}( U_1, \dots, U_r)$ minimizes the [[projection]] error:
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general

$$
\begin{split}
V^{(r)}
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X - P_V(X) \right\|_2^2 \right] \\
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X \right\|_2^2 \right] - \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
&= \arg\max_{\dim(V)=k} \; \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
\end{split}
$$

- this works because of the [[orthogonal|orthogonality]] $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ can be decomposed as  follows with $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ being constant and thus doesn't matter in an optimization problem
- this means that $V = \mathrm{span}( U_1, \dots, U_r)$ is the $r$ dimensional [[subspace]] that computes the most amount of [[variance]] of the data $X$

$$
\begin{split}
\mathbb{E} \left[ \left\| X \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| X -  P_V(X) + P_V(X) \right\|_2^2 \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] +2 \mathbb{E} \left[ \langle X,  X -  P_V(X)  \rangle \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
\end{split}
$$

- with the following being the projection itself (see [[projection#projection into an orthonormal subspace]]) 

$$
P_V(X) = VV^\top X
$$


____________

### projection into the column space
- [[projection]] of a [[vector]] $b \in \mathbb{R}^n$ to the [[column space]] of [[matrix]] $A \in \mathbb{R}^{n \times d}$ is defined as $P_A(b)=Ax$ 
- $x=\mathrm{arg} \min \|Ax - b \|$ is the coefficient vector that writes the [[projection]]in the coordinates of $A$
- $b - P_A(b)$ has to be [[orthogonal]] to the [[column space]] of $A$ 
- thus the [[projection]] matrix is $P_A = A\left(A^\top A \right)^{-1}A^\top$ and the projection function is $P_A(b) = A\left(A^\top A \right)^{-1}A^\top b$

$$
\begin{split}
\langle A, b-P_A(b) \rangle &= A^\top \left(b-P_A(b)\right) = 0 \\
A^\top P_A(b) &= A^\top b  \\ 
A^\top Ax &= A^\top b  \\ 
x  &= \left(A^\top A \right)^{-1}A^\top b\\
P_A(b)=Ax  &= A \left(A^\top A \right)^{-1}A^\top b\\
\end{split}
$$


### projection into an orthonormal subspace
- given the [[orthonormal]] [[basis]] $V=V_1,..., V_n \in \mathbb{R}^{d \times n}$ with $V^\top V=I$
- let $P_V(X)=Vx$ be the [[projection]] of $X$ into $\mathrm{span}(V_1, ..., V_n)$
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general
- $x=\mathrm{arg} \min \|Vx - X \|$ is the coefficient vector that writes the [[projection]] in the coordinates of $V$

$$
\begin{split}
P_V(X) 
&= V \left(V^\top V \right)^{-1}V^\top X\\
&= V IV^\top X\\
&= V V^\top X\\
\end{split}
$$


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

#### eigendecomposition of symmetric matrices
- if $A$ is a [[symmetric matrix]] then $B$ is an [[orthogonal matrix]] because $B^T=B^{-1}$ 
- every [[symmetric matrix]] is a [[eigendecomposition]] but if $\mathrm{rank}(A)<d$ some of its [[eigenvalue]] are zero but it still has $d$ [[linear independent]] [[eigenvector]]


Tags: mathematics SS25
<!--ID: 1753118033414-->
END


START
Basic
[[principal component analysis]]
- proof for the following what 
- interpretation of the first statement

1) 

$$
\begin{split}
U 
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X - P_V(X) \right\|_2^2 \right] \\
&= \arg\max_{\dim(V)=k} \; \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
\end{split}
$$

2) 


$$
P_V(X) = VV^\top X
$$



Back: 
### principal component analysis
- represent a [[random vector]] in a lower dimensional [[latent space]] of a given [[dimensions|dimension]] such that it captures the most amount of [[variance]]
- [[principal component analysis]] computes an **orthogonal [[projection]]** of the input data into a lower-dimensional space in order to represent it in a reduced [[latent space]].
- The amount of information retained by the projection can be measured using the **[[explained variance]]**, which quantifies how much of the original variance is preserved.
- let $X \in \mathbb{R}^{d}$ be zero mean [[random variable]] $X \in \mathbb{R}^{n}$ with $\Sigma=\mathbb{VAR} \left[X\right]$ with a [[eigendecomposition|spectral decomposition]]  
- since $\Sigma$ is a [[symmetric matrix]] it is always a [[eigendecomposition]] with a [[orthonormal]] bases, and it admits a [[eigendecomposition]]

$$
\Sigma= \frac{1}{n} X^\top X =U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top
$$

- with $\lambda_1\geq ...\geq \lambda_d$ being the [[eigenvalue]] and $U=[U_1, ..., U_d] \in \mathbb{R}^{d \times d}$ its [[orthogonal matrix]] of[[eigenvector]]s


- Then the principal components $V_1, \dots, V_r$ that solve the following minimization problems are the [[orthonormal]] [[eigenvector]] of $\Sigma$
- in other words the [[principal component analysis]] is a reduced form of the [[eigendecomposition]] of the empirical [[covariance matrix]]

$$
\begin{split}
V_1 &= \arg\min_{\|v\|=1} \; \mathbb{E} \left[ \left\| X - P_{\mathrm{span}(v)}(X) \right\|_2^2 \right] = \pm U_1 \\
V_r &= \arg\min_{\|v\|=1,\; v \perp V_1, \dots, V_{r-1}} \; \mathbb{E} \left[ \left\| X - P_{\mathrm{span}(u_1, \dots, u_{r-1}, v)}(X) \right\|_2^2 \right] = \pm U_r
\end{split}
$$

- Equivalently, the optimal $r$-dimensional [[subspace]] $V = \mathrm{span}( U_1, \dots, U_r)$ minimizes the [[projection]] error:
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general

$$
\begin{split}
V^{(r)}
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X - P_V(X) \right\|_2^2 \right] \\
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X \right\|_2^2 \right] - \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
&= \arg\max_{\dim(V)=k} \; \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
\end{split}
$$

- this works because of the [[orthogonal|orthogonality]] $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ can be decomposed as  follows with $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ being constant and thus doesn't matter in an optimization problem
- this means that $V = \mathrm{span}( U_1, \dots, U_r)$ is the $r$ dimensional [[subspace]] that computes the most amount of [[variance]] of the data $X$

$$
\begin{split}
\mathbb{E} \left[ \left\| X \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| X -  P_V(X) + P_V(X) \right\|_2^2 \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] +2 \mathbb{E} \left[ \langle X,  X -  P_V(X)  \rangle \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
\end{split}
$$

- with the following being the projection itself (see [[projection#projection into an orthonormal subspace]]) 

$$
P_V(X) = VV^\top X
$$


____________

### projection into the column space
- [[projection]] of a [[vector]] $b \in \mathbb{R}^n$ to the [[column space]] of [[matrix]] $A \in \mathbb{R}^{n \times d}$ is defined as $P_A(b)=Ax$ 
- $x=\mathrm{arg} \min \|Ax - b \|$ is the coefficient vector that writes the [[projection]]in the coordinates of $A$
- $b - P_A(b)$ has to be [[orthogonal]] to the [[column space]] of $A$ 
- thus the [[projection]] matrix is $P_A = A\left(A^\top A \right)^{-1}A^\top$ and the projection function is $P_A(b) = A\left(A^\top A \right)^{-1}A^\top b$

$$
\begin{split}
\langle A, b-P_A(b) \rangle &= A^\top \left(b-P_A(b)\right) = 0 \\
A^\top P_A(b) &= A^\top b  \\ 
A^\top Ax &= A^\top b  \\ 
x  &= \left(A^\top A \right)^{-1}A^\top b\\
P_A(b)=Ax  &= A \left(A^\top A \right)^{-1}A^\top b\\
\end{split}
$$


### projection into an orthonormal subspace
- given the [[orthonormal]] [[basis]] $V=V_1,..., V_n \in \mathbb{R}^{d \times n}$ with $V^\top V=I$
- let $P_V(X)=Vx$ be the [[projection]] of $X$ into $\mathrm{span}(V_1, ..., V_n)$
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general
- $x=\mathrm{arg} \min \|Vx - X \|$ is the coefficient vector that writes the [[projection]] in the coordinates of $V$

$$
\begin{split}
P_V(X) 
&= V \left(V^\top V \right)^{-1}V^\top X\\
&= V IV^\top X\\
&= V V^\top X\\
\end{split}
$$


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

#### eigendecomposition of symmetric matrices
- if $A$ is a [[symmetric matrix]] then $B$ is an [[orthogonal matrix]] because $B^T=B^{-1}$ 
- every [[symmetric matrix]] is a [[eigendecomposition]] but if $\mathrm{rank}(A)<d$ some of its [[eigenvalue]] are zero but it still has $d$ [[linear independent]] [[eigenvector]]



Tags: mathematics SS25
<!--ID: 1753118033417-->
END



START
Basic
[[principal component analysis]]
vs
[[eigendecomposition]]
vs
[[singular value decomposition]]
Back: 

[[singular value decomposition]]
- general decomposition of a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with [[rank]] $r$
- always possible
- [[orthonormal]] [[matrix]] $U\in\mathbb{R}^{n\times n}$ and [[orthonormal]] [[matrix]] $V\in\mathbb{R}^{m\times m}$ and a [[diagonal matrix]] $\Sigma \in \mathbb{R}^{n \times m}$ such that

$$
A = U\Sigma V^\top =
$$

[[eigendecomposition]]
- only for [[square matrix]] $A \in \mathbb{R}^{n \times n}$ and does not always exist
- a [[matrix]] $A \in \mathbb{R}^{n\times n}$ is a [[eigendecomposition]] if there exists a [[inverse matrix|inverable matrix]] $B\in \mathbb{R}^{n\times n}$ and a [[diagonal matrix]] $D=diag(\lambda_1, ..., \lambda_n)\in \mathbb{R}^{n\times n}$ such that the following decomposition is possible with $\lambda_1$, ..., $\lambda_n$ being the [[eigenvalue]]

$$
A = U\Sigma U^{-1}
$$

- [[eigendecomposition]] and [[singular value decomposition]] are not equivalent in general even for $A \in \mathbb{R}^{n \times n}$

[[symmetric matrix]]
- [[eigendecomposition]] and [[singular value decomposition]] are identical
- always exist
- $U$ is a [[orthogonal matrix]]

$$
A = U\Sigma U^\top
$$

[[principal component analysis]]
- method for [[projection|projecting]] a [[random vector]] $X$ into a lower dimensional [[latent space]] 
- using an [[eigendecomposition]] of the empirical [[covariance matrix]] of $X$

$$
\Sigma = \frac{1}{n} X^\top X
$$

### principal component analysis
- represent a [[random vector]] in a lower dimensional [[latent space]] of a given [[dimensions|dimension]] such that it captures the most amount of [[variance]]
- [[principal component analysis]] computes an **orthogonal [[projection]]** of the input data into a lower-dimensional space in order to represent it in a reduced [[latent space]].
- The amount of information retained by the projection can be measured using the **[[explained variance]]**, which quantifies how much of the original variance is preserved.
- let $X \in \mathbb{R}^{d}$ be zero mean [[random variable]] $X \in \mathbb{R}^{n}$ with $\Sigma=\mathbb{VAR} \left[X\right]$ with a [[eigendecomposition|spectral decomposition]]  
- since $\Sigma$ is a [[symmetric matrix]] it is always a [[eigendecomposition]] with a [[orthonormal]] bases, and it admits a [[eigendecomposition]]

$$
\Sigma= \frac{1}{n} X^\top X =U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top
$$

- with $\lambda_1\geq ...\geq \lambda_d$ being the [[eigenvalue]] and $U=[U_1, ..., U_d] \in \mathbb{R}^{d \times d}$ its [[orthogonal matrix]] of[[eigenvector]]s


- Then the principal components $V_1, \dots, V_r$ that solve the following minimization problems are the [[orthonormal]] [[eigenvector]] of $\Sigma$
- in other words the [[principal component analysis]] is a reduced form of the [[eigendecomposition]] of the empirical [[covariance matrix]]

$$
\begin{split}
V_1 &= \arg\min_{\|v\|=1} \; \mathbb{E} \left[ \left\| X - P_{\mathrm{span}(v)}(X) \right\|_2^2 \right] = \pm U_1 \\
V_r &= \arg\min_{\|v\|=1,\; v \perp V_1, \dots, V_{r-1}} \; \mathbb{E} \left[ \left\| X - P_{\mathrm{span}(u_1, \dots, u_{r-1}, v)}(X) \right\|_2^2 \right] = \pm U_r
\end{split}
$$

- Equivalently, the optimal $r$-dimensional [[subspace]] $V = \mathrm{span}( U_1, \dots, U_r)$ minimizes the [[projection]] error:
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general

$$
\begin{split}
V^{(r)}
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X - P_V(X) \right\|_2^2 \right] \\
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X \right\|_2^2 \right] - \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
&= \arg\max_{\dim(V)=k} \; \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
\end{split}
$$

- this works because of the [[orthogonal|orthogonality]] $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ can be decomposed as  follows with $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ being constant and thus doesn't matter in an optimization problem
- this means that $V = \mathrm{span}( U_1, \dots, U_r)$ is the $r$ dimensional [[subspace]] that computes the most amount of [[variance]] of the data $X$

$$
\begin{split}
\mathbb{E} \left[ \left\| X \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| X -  P_V(X) + P_V(X) \right\|_2^2 \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] +2 \mathbb{E} \left[ \langle X,  X -  P_V(X)  \rangle \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
\end{split}
$$

- with the following being the projection itself (see [[projection#projection into an orthonormal subspace]]) 

$$
P_V(X) = VV^\top X
$$


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

#### eigendecomposition of symmetric matrices
- if $A$ is a [[symmetric matrix]] then $B$ is an [[orthogonal matrix]] because $B^T=B^{-1}$ 
- every [[symmetric matrix]] is a [[eigendecomposition]] but if $\mathrm{rank}(A)<d$ some of its [[eigenvalue]] are zero but it still has $d$ [[linear independent]] [[eigenvector]]

### singular value decomposition
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with [[rank]] $r$
- there exists an [[orthonormal]] [[matrix]] $U\in\mathbb{R}^{n\times n}$ and [[orthonormal]] [[matrix]] $V\in\mathbb{R}^{m\times m}$ and a [[diagonal matrix]] $\Sigma \in \mathbb{R}^{n \times m}$ auch that
$$
A = U\Sigma V^\top =
$$

- the [[diagonal matrix]] $\Sigma$ has of $r$ postive ordered values on the diagonal and apart from that only zeros
$$
\begin{split}
&\Sigma = \left( \begin{matrix}
\sigma_1 & \\
&...  \\
&&\sigma_r  \\
&&&0  \\
\end{matrix} \right) \\
&\text{with }\sigma_1 \geq ... \geq \sigma_r \ge 0
\end{split}
$$


Tags: mathematics SS25
<!--ID: 1753118033420-->
END


START
Basic
[[principal component analysis]]
- why can it be used for denoising?

Back: 

### PCA for denoising
- the [[principal component analysis]] can be used to remove [[white noise]] from data $X$
- lets assume the signal contained in $X\in\mathbb{R}^d$ is contained $Z\in\mathbb{R}^r$ which is transformed with the matrix $B \in \mathbb{R}^{d \times r}$ with [[white noise]] $\epsilon$ on it

$$
\begin{split}
Z&\sim P_Z \\
X &= BZ + \epsilon \sim \mathcal{N}(0, \sigma^2 I_d)
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[X] 
&= \mathbb{VAR}[BZ] + \mathbb{VAR}[\epsilon] \\
&= B\mathbb{VAR}[Z]B^\top + \sigma^2 I_d \\
&= VDV^\top \\
\end{split}
$$

- if we would do a [[principal component analysis]] we would have $r$ larger [[eigenvalue]]s and $d-r$ smaller
- the [[principal component analysis]] can detect that and set $r$ such that the [[white noise]] is filtered out and the signal is preserved
### principal component analysis
- represent a [[random vector]] in a lower dimensional [[latent space]] of a given [[dimensions|dimension]] such that it captures the most amount of [[variance]]
- [[principal component analysis]] computes an **orthogonal [[projection]]** of the input data into a lower-dimensional space in order to represent it in a reduced [[latent space]].
- The amount of information retained by the projection can be measured using the **[[explained variance]]**, which quantifies how much of the original variance is preserved.
- let $X \in \mathbb{R}^{d}$ be zero mean [[random variable]] $X \in \mathbb{R}^{n}$ with $\Sigma=\mathbb{VAR} \left[X\right]$ with a [[eigendecomposition|spectral decomposition]]  
- since $\Sigma$ is a [[symmetric matrix]] it is always a [[eigendecomposition]] with a [[orthonormal]] bases, and it admits a [[eigendecomposition]]

$$
\Sigma= \frac{1}{n} X^\top X =U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top
$$

- with $\lambda_1\geq ...\geq \lambda_d$ being the [[eigenvalue]] and $U=[U_1, ..., U_d] \in \mathbb{R}^{d \times d}$ its [[orthogonal matrix]] of[[eigenvector]]s


- Then the principal components $V_1, \dots, V_r$ that solve the following minimization problems are the [[orthonormal]] [[eigenvector]] of $\Sigma$
- in other words the [[principal component analysis]] is a reduced form of the [[eigendecomposition]] of the empirical [[covariance matrix]]

$$
\begin{split}
V_1 &= \arg\min_{\|v\|=1} \; \mathbb{E} \left[ \left\| X - P_{\mathrm{span}(v)}(X) \right\|_2^2 \right] = \pm U_1 \\
V_r &= \arg\min_{\|v\|=1,\; v \perp V_1, \dots, V_{r-1}} \; \mathbb{E} \left[ \left\| X - P_{\mathrm{span}(u_1, \dots, u_{r-1}, v)}(X) \right\|_2^2 \right] = \pm U_r
\end{split}
$$

- Equivalently, the optimal $r$-dimensional [[subspace]] $V = \mathrm{span}( U_1, \dots, U_r)$ minimizes the [[projection]] error:
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general

$$
\begin{split}
V^{(r)}
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X - P_V(X) \right\|_2^2 \right] \\
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X \right\|_2^2 \right] - \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
&= \arg\max_{\dim(V)=k} \; \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
\end{split}
$$

- this works because of the [[orthogonal|orthogonality]] $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ can be decomposed as  follows with $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ being constant and thus doesn't matter in an optimization problem
- this means that $V = \mathrm{span}( U_1, \dots, U_r)$ is the $r$ dimensional [[subspace]] that computes the most amount of [[variance]] of the data $X$

$$
\begin{split}
\mathbb{E} \left[ \left\| X \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| X -  P_V(X) + P_V(X) \right\|_2^2 \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] +2 \mathbb{E} \left[ \langle X,  X -  P_V(X)  \rangle \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
\end{split}
$$

- with the following being the projection itself (see [[projection#projection into an orthonormal subspace]]) 

$$
P_V(X) = VV^\top X
$$


____________

### projection into the column space
- [[projection]] of a [[vector]] $b \in \mathbb{R}^n$ to the [[column space]] of [[matrix]] $A \in \mathbb{R}^{n \times d}$ is defined as $P_A(b)=Ax$ 
- $x=\mathrm{arg} \min \|Ax - b \|$ is the coefficient vector that writes the [[projection]]in the coordinates of $A$
- $b - P_A(b)$ has to be [[orthogonal]] to the [[column space]] of $A$ 
- thus the [[projection]] matrix is $P_A = A\left(A^\top A \right)^{-1}A^\top$ and the projection function is $P_A(b) = A\left(A^\top A \right)^{-1}A^\top b$

$$
\begin{split}
\langle A, b-P_A(b) \rangle &= A^\top \left(b-P_A(b)\right) = 0 \\
A^\top P_A(b) &= A^\top b  \\ 
A^\top Ax &= A^\top b  \\ 
x  &= \left(A^\top A \right)^{-1}A^\top b\\
P_A(b)=Ax  &= A \left(A^\top A \right)^{-1}A^\top b\\
\end{split}
$$


### projection into an orthonormal subspace
- given the [[orthonormal]] [[basis]] $V=V_1,..., V_n \in \mathbb{R}^{d \times n}$ with $V^\top V=I$
- let $P_V(X)=Vx$ be the [[projection]] of $X$ into $\mathrm{span}(V_1, ..., V_n)$
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general
- $x=\mathrm{arg} \min \|Vx - X \|$ is the coefficient vector that writes the [[projection]] in the coordinates of $V$

$$
\begin{split}
P_V(X) 
&= V \left(V^\top V \right)^{-1}V^\top X\\
&= V IV^\top X\\
&= V V^\top X\\
\end{split}
$$


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

#### eigendecomposition of symmetric matrices
- if $A$ is a [[symmetric matrix]] then $B$ is an [[orthogonal matrix]] because $B^T=B^{-1}$ 
- every [[symmetric matrix]] is a [[eigendecomposition]] but if $\mathrm{rank}(A)<d$ some of its [[eigenvalue]] are zero but it still has $d$ [[linear independent]] [[eigenvector]]


Tags: mathematics SS25
<!--ID: 1753201807975-->
END