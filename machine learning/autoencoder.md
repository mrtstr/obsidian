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

- for example using the [[principal component analysis]] 


$$
\begin{split}
Z &=g(X) = P_V(X) = V^\top X \\
f(Z) &= P_{V^\top}(Z) = V Z \\
\tilde X &= f\left(g\left(X\right)\right) = f\left(V^\top X\right)= VV^\top X = X\\
\end{split}
$$

# ------------------

![[principal component analysis#principal component analysis]]

# anki


START
Basic
[[autoencoder]]
- concept
- example using the [[principal component analysis]]
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

- for example using the [[principal component analysis]] 


$$
\begin{split}
Z &=g(X) = P_V(X) = V^\top X \\
f(Z) &= P_{V^\top}(Z) = V Z \\
\tilde X &= f\left(g\left(X\right)\right) = f\left(V^\top X\right)= VV^\top X = X\\
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
P_V(X) = V^\top X
$$



Tags: mathematics SS25
<!--ID: 1753119123076-->
END