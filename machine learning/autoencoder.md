### autoencoder
- mapping high dimensional input $X \in \mathbb{R}^d$ into a lower dimensional [[latent space]] representation $Z = g(X) \in \mathbb{R}^r$ while preserving as much information as possible
- for training a reconstruction function $f: \mathbb{R}^r \to \mathbb{R}^d$
- the reconstruction $\tilde{X} = f(Z) = f\left(g\left(X\right)\right) \in \mathbb{R}^d$ is then compared with the input in the following reconstruction loss

$$
\begin{split}
g, f 
&= \mathrm{arg} \min_{g, f} \| \tilde {X} - X \|^2_2 \\
&= \mathrm{arg} \min_{g, f} \| f\left(g\left(X\right)\right) - X \|^2_2 \\
\end{split}
$$
##### autoencoder with the PCA
- for example using the [[principal component analysis]] with the [[orthonormal matrix]] $V \in \mathbb{R}^{d \times r}$ with $V^\top V = I_r$ but $V V^\top \neq I_d$
- the reconstruction $\tilde X = P_V(X) = VV^\top X$ would be the [[projection]] into the [[orthonormal]] column space of $V$

$$
\begin{split}
Z &=g(X) = V^\top X \\
f(Z) &=   V Z \\
\tilde X &= f\left(g\left(X\right)\right) = f\left(V^\top X\right)= VV^\top X\\
\end{split}
$$
- a full recovery will never be possible for $r<d$ 
# ------------------

![[projection#projection into an orthonormal subspace]]


![[projection#projection into the column space]]

![[principal component analysis#principal component analysis]]

# anki


START
Basic
[[autoencoder]]
- general concept

Back: 
### autoencoder
- mapping high dimensional input $X \in \mathbb{R}^d$ into a lower dimensional [[latent space]] representation $Z = g(X) \in \mathbb{R}^r$ while preserving as much information as possible
- for training a reconstruction function $f: \mathbb{R}^r \to \mathbb{R}^d$
- the reconstruction $\tilde{X} = f(Z) = f\left(g\left(X\right)\right) \in \mathbb{R}^d$ is then compared with the input in the following reconstruction loss

$$
\begin{split}
g, f 
&= \mathrm{arg} \min_{g, f} \| \tilde {X} - X \|^2_2 \\
&= \mathrm{arg} \min_{g, f} \| f\left(g\left(X\right)\right) - X \|^2_2 \\
\end{split}
$$

### principal component analysis
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

$$
\begin{split}
V^{(r)}
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X - P_V(X) \right\|_2^2 \right] \\
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X \right\|_2^2 \right] - \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
&= \arg\max_{\dim(V)=k} \; \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
\end{split}
$$

- this works because of the [[orthogonal|orthogonality]] $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ can be decomposed as follows with $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ being constant and thus doesn't matter in an optimization problem

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


Tags: mathematics SS25
<!--ID: 1753119123076-->
END


START
Basic
[[autoencoder]]
- example: [[autoencoder]] with the [[principal component analysis]]
- how to interpret the recovered input in the context of a [[projection]]

Back: 

### autoencoder
- mapping high dimensional input $X \in \mathbb{R}^d$ into a lower dimensional [[latent space]] representation $Z = g(X) \in \mathbb{R}^r$ while preserving as much information as possible
- for training a reconstruction function $f: \mathbb{R}^r \to \mathbb{R}^d$
- the reconstruction $\tilde{X} = f(Z) = f\left(g\left(X\right)\right) \in \mathbb{R}^d$ is then compared with the input in the following reconstruction loss

$$
\begin{split}
g, f 
&= \mathrm{arg} \min_{g, f} \| \tilde {X} - X \|^2_2 \\
&= \mathrm{arg} \min_{g, f} \| f\left(g\left(X\right)\right) - X \|^2_2 \\
\end{split}
$$

##### autoencoder with the PCA
- for example using the [[principal component analysis]] with the [[orthonormal matrix]] $V \in \mathbb{R}^{d \times r}$ with $V^\top V = I_r$ but $V V^\top \neq I_d$
- the reconstruction $\tilde X = P_V(X) = VV^\top X$ would be the [[projection]] into the [[orthonormal]] column space of $V$

$$
\begin{split}
Z &=g(X) = V^\top X \\
f(Z) &=   V Z \\
\tilde X &= f\left(g\left(X\right)\right) = f\left(V^\top X\right)= VV^\top X\\
\end{split}
$$
- a full recovery will never be possible for $r<d$ 


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



### principal component analysis
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

$$
\begin{split}
V^{(r)}
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X - P_V(X) \right\|_2^2 \right] \\
&= \arg\min_{\dim(V)=k} \; \mathbb{E} \left[ \left\| X \right\|_2^2 \right] - \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
&= \arg\max_{\dim(V)=k} \; \mathbb{E} \left[ \left\| P_V(X) \right\|_2^2 \right] \\
\end{split}
$$

- this works because of the [[orthogonal|orthogonality]] $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ can be decomposed as follows with $\mathbb{E} \left[ \left\| X \right\|_2^2 \right]$ being constant and thus doesn't matter in an optimization problem

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


Tags: mathematics SS25
<!--ID: 1753171070154-->
END