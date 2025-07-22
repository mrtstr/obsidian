### explained variance
- method of decomposing the variance in the part the is explained by a using representation in a [[latent space]] of dimension $r$ and a part that is not explained by it (using the [[principal component analysis]])

- let $X \in \mathbb{R}^{d \times n}$ be zero mean [[random variable]] with $\Sigma=\mathbb{VAR} \left[X\right]$
- since $\Sigma$ is a [[symmetric matrix]] it is always a [[eigendecomposition]] with a [[orthonormal]] bases

$$
\Sigma= \frac{1}{n} X^\top X =U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top
$$

- with $\lambda_1\geq ...\geq \lambda_d$ being the [[eigenvalue]] and $U=[U_1, ..., U_n] \in \mathbb{R}^{d \times d}$ its [[orthogonal matrix]] of[[eigenvector]]s

#### total variance
- let $TV$ be the total [[variance]] of $X$ defined as follows, which is equivalent to the sum of the [[eigenvalue]] of $\Sigma$


$$
\begin{split}
TV
&=\mathbb{E} \left[ \left\| X \right\|_2^2 \right]  \\
&=\mathbb{E} \left[\mathrm{tr}\left(X^\top X\right) \right] \\
&=\left[\mathrm{tr}\left(\mathbb{VAR} \left[X\right]\right) \right] \\
&=\left[\mathrm{tr}\left(\Sigma\right) \right] \\
&=\left[\mathrm{tr}\left(U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top\right) \right] \\
&=\left[\mathrm{tr}\left(\mathrm{diag}(\lambda_1,..., \lambda_n)\right) \right] \\
&= \sum_{i=1}^d \lambda_i \\
\end{split}
$$


#### residual variance
- let $V=[U_1, ..., U_r] \in \mathbb{R}^{d \times r}$ with $V \in \mathbb{R}^{d \times r}$ with $V^\top V = I_r$ but $V V^\top \neq I_d$
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general
- residual [[variance]] $RV(r)$ with $\mathrm{dim}(V)=r$ is the rest of the [[variance]] on the data that is not explained by the lower dimensional representation $P_V(X)$ is defined as follows


$$
\begin{split}
RV(r)
&= \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
&= \sum_{i=r+1}^d \lambda_i \\
\end{split}
$$
##### proof

- the following being the projection itself (see [[projection#projection into an orthonormal subspace]]) 
$$
P_V(X) = VV^\top X
$$

- $V^\top U=[I_r , 0]^\top$

$$
\begin{split}
\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| VV^\top X  \right\|_2^2 \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left((VV^\top X)^\top VV^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( X^\top VV^\top VV^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( X^\top VV^\top X\right) \right] \\
&= \mathbb{E} \left[ \mathrm{tr}(V^\top X X^\top V) \right] \\
&= \mathrm{tr}(V^\top \Sigma V) \\
&= \mathrm{tr}(V^\top U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top V) \\
&= \sum_{i=1}^r \lambda_i
\end{split}
$$

$$
\begin{split}
\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| VV^\top X  \right\|_2^2 \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left((V^\top X)^\top V^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( V^\top X\right)(V^\top X)^\top \right] \\
&= \mathbb{E} \left[ \mathrm{tr}(V^\top X X^\top V) \right] \\
&= \mathrm{tr}(V^\top \Sigma V) \\
&= \mathrm{tr}(V^\top U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top V) \\
&= \sum_{i=1}^r \lambda_i
\end{split}
$$


$$
\begin{split}
\mathbb{E} \left[ \left\| X \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| X -  P_V(X) + P_V(X) \right\|_2^2 \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] +2 \mathbb{E} \left[ \langle X,  X -  P_V(X)  \rangle \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
\end{split}
$$

$$
\begin{split}
\mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right]  
&= \mathbb{E} \left[ \left\| X \right\|_2^2 \right] - \left[ \left\| P_V(X)  \right\|_2^2 \right] \\
&= \sum_{i=r}^d \lambda_i  - \sum_{i=1}^r \lambda_i \\
&= \sum_{i=r+1}^d \lambda_i   \\
\end{split}
$$

#### proportion of explained variance
- proportion of the [[variance]] that is explained by a [[latent space]] representation in a space dimension $r$

$$
\begin{split}
PEV(r)
&= \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
&= \frac{TV - RV(r)}{TV} \\
&= \frac{\sum_{i=1}^d \lambda_i  - \sum_{i=r+1}^d \lambda_i }{\sum_{i=1}^d \lambda_i } \\
&= \frac{\sum_{i=r}^d \lambda_i   }{\sum_{i=1}^d \lambda_i } \\
\end{split}
$$

# -------------------


![[principal component analysis#principal component analysis]]

# anki



START
Basic
[[explained variance]]
- concept
- total variance (without proof)
- residual variance (without proof)
- proportion of explained variance (without proof)
Back: 
### explained variance
- method of decomposing the variance in the part the is explained by a using representation in a [[latent space]] of dimension $r$ and a part that is not explained by it (using the [[principal component analysis]])

- let $X \in \mathbb{R}^{d \times n}$ be zero mean [[random variable]] with $\Sigma=\mathbb{VAR} \left[X\right]$
- since $\Sigma$ is a [[symmetric matrix]] it is always a [[eigendecomposition]] with a [[orthonormal]] bases

$$
\Sigma= \frac{1}{n} X^\top X =U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top
$$

- with $\lambda_1\geq ...\geq \lambda_d$ being the [[eigenvalue]] and $U=[U_1, ..., U_n] \in \mathbb{R}^{d \times d}$ its [[orthogonal matrix]] of[[eigenvector]]s

#### total variance
- let $TV$ be the total [[variance]] of $X$ defined as follows, which is equivalent to the sum of the [[eigenvalue]] of $\Sigma$


$$
\begin{split}
TV
&=\mathbb{E} \left[ \left\| X \right\|_2^2 \right]  \\
&=\mathbb{E} \left[\mathrm{tr}\left(X^\top X\right) \right] \\
&=\left[\mathrm{tr}\left(\mathbb{VAR} \left[X\right]\right) \right] \\
&=\left[\mathrm{tr}\left(\Sigma\right) \right] \\
&=\left[\mathrm{tr}\left(U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top\right) \right] \\
&=\left[\mathrm{tr}\left(\mathrm{diag}(\lambda_1,..., \lambda_n)\right) \right] \\
&= \sum_{i=1}^d \lambda_i \\
\end{split}
$$


#### residual variance
- let $V=[U_1, ..., U_r] \in \mathbb{R}^{d \times r}$ with $V \in \mathbb{R}^{d \times r}$ with $V^\top V = I_r$ but $V V^\top \neq I_d$
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general
- residual [[variance]] $RV(r)$ with $\mathrm{dim}(V)=r$ is the rest of the [[variance]] on the data that is not explained by the lower dimensional representation $P_V(X)$ is defined as follows


$$
\begin{split}
RV(r)
&= \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
&= \sum_{i=r+1}^d \lambda_i \\
\end{split}
$$
##### proof

- the following being the projection itself (see [[projection#projection into an orthonormal subspace]]) 
$$
P_V(X) = VV^\top X
$$

- $V^\top U=[I_r , 0]^\top$

$$
\begin{split}
\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| VV^\top X  \right\|_2^2 \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left((VV^\top X)^\top VV^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( X^\top VV^\top VV^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( X^\top VV^\top X\right) \right] \\
&= \mathbb{E} \left[ \mathrm{tr}(V^\top X X^\top V) \right] \\
&= \mathrm{tr}(V^\top \Sigma V) \\
&= \mathrm{tr}(V^\top U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top V) \\
&= \sum_{i=1}^r \lambda_i
\end{split}
$$

$$
\begin{split}
\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| VV^\top X  \right\|_2^2 \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left((V^\top X)^\top V^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( V^\top X\right)(V^\top X)^\top \right] \\
&= \mathbb{E} \left[ \mathrm{tr}(V^\top X X^\top V) \right] \\
&= \mathrm{tr}(V^\top \Sigma V) \\
&= \mathrm{tr}(V^\top U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top V) \\
&= \sum_{i=1}^r \lambda_i
\end{split}
$$


$$
\begin{split}
\mathbb{E} \left[ \left\| X \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| X -  P_V(X) + P_V(X) \right\|_2^2 \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] +2 \mathbb{E} \left[ \langle X,  X -  P_V(X)  \rangle \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
\end{split}
$$

$$
\begin{split}
\mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right]  
&= \mathbb{E} \left[ \left\| X \right\|_2^2 \right] - \left[ \left\| P_V(X)  \right\|_2^2 \right] \\
&= \sum_{i=r}^d \lambda_i  - \sum_{i=1}^r \lambda_i \\
&= \sum_{i=r+1}^d \lambda_i   \\
\end{split}
$$

#### proportion of explained variance
- proportion of the [[variance]] that is explained by a [[latent space]] representation in a space dimension $r$

$$
\begin{split}
PEV(r)
&= \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
&= \frac{TV - RV(r)}{TV} \\
&= \frac{\sum_{i=1}^d \lambda_i  - \sum_{i=r+1}^d \lambda_i }{\sum_{i=1}^d \lambda_i } \\
&= \frac{\sum_{i=r}^r \lambda_i   }{\sum_{i=1}^d \lambda_i } \\
\end{split}
$$

______________

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



Tags: mathematics SS25
<!--ID: 1753118033405-->
END



START
Basic
[[explained variance]]
- total variance with proof

Back: 

### explained variance
- method of decomposing the variance in the part the is explained by a using representation in a [[latent space]] of dimension $r$ and a part that is not explained by it (using the [[principal component analysis]])

- let $X \in \mathbb{R}^{d \times n}$ be zero mean [[random variable]] with $\Sigma=\mathbb{VAR} \left[X\right]$
- since $\Sigma$ is a [[symmetric matrix]] it is always a [[eigendecomposition]] with a [[orthonormal]] bases

$$
\Sigma= \frac{1}{n} X^\top X =U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top
$$

- with $\lambda_1\geq ...\geq \lambda_d$ being the [[eigenvalue]] and $U=[U_1, ..., U_n] \in \mathbb{R}^{d \times d}$ its [[orthogonal matrix]] of[[eigenvector]]s

#### total variance
- let $TV$ be the total [[variance]] of $X$ defined as follows, which is equivalent to the sum of the [[eigenvalue]] of $\Sigma$


$$
\begin{split}
TV
&=\mathbb{E} \left[ \left\| X \right\|_2^2 \right]  \\
&=\mathbb{E} \left[\mathrm{tr}\left(X^\top X\right) \right] \\
&=\left[\mathrm{tr}\left(\mathbb{VAR} \left[X\right]\right) \right] \\
&=\left[\mathrm{tr}\left(\Sigma\right) \right] \\
&=\left[\mathrm{tr}\left(U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top\right) \right] \\
&=\left[\mathrm{tr}\left(\mathrm{diag}(\lambda_1,..., \lambda_n)\right) \right] \\
&= \sum_{i=1}^d \lambda_i \\
\end{split}
$$


#### residual variance
- let $V=[U_1, ..., U_r] \in \mathbb{R}^{d \times r}$ with $V \in \mathbb{R}^{d \times r}$ with $V^\top V = I_r$ but $V V^\top \neq I_d$
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general
- residual [[variance]] $RV(r)$ with $\mathrm{dim}(V)=r$ is the rest of the [[variance]] on the data that is not explained by the lower dimensional representation $P_V(X)$ is defined as follows


$$
\begin{split}
RV(r)
&= \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
&= \sum_{i=r+1}^d \lambda_i \\
\end{split}
$$
##### proof

- the following being the projection itself (see [[projection#projection into an orthonormal subspace]]) 
$$
P_V(X) = VV^\top X
$$

- $V^\top U=[I_r , 0]^\top$

$$
\begin{split}
\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| VV^\top X  \right\|_2^2 \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left((VV^\top X)^\top VV^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( X^\top VV^\top VV^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( X^\top VV^\top X\right) \right] \\
&= \mathbb{E} \left[ \mathrm{tr}(V^\top X X^\top V) \right] \\
&= \mathrm{tr}(V^\top \Sigma V) \\
&= \mathrm{tr}(V^\top U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top V) \\
&= \sum_{i=1}^r \lambda_i
\end{split}
$$

$$
\begin{split}
\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| VV^\top X  \right\|_2^2 \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left((V^\top X)^\top V^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( V^\top X\right)(V^\top X)^\top \right] \\
&= \mathbb{E} \left[ \mathrm{tr}(V^\top X X^\top V) \right] \\
&= \mathrm{tr}(V^\top \Sigma V) \\
&= \mathrm{tr}(V^\top U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top V) \\
&= \sum_{i=1}^r \lambda_i
\end{split}
$$


$$
\begin{split}
\mathbb{E} \left[ \left\| X \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| X -  P_V(X) + P_V(X) \right\|_2^2 \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] +2 \mathbb{E} \left[ \langle X,  X -  P_V(X)  \rangle \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
\end{split}
$$

$$
\begin{split}
\mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right]  
&= \mathbb{E} \left[ \left\| X \right\|_2^2 \right] - \left[ \left\| P_V(X)  \right\|_2^2 \right] \\
&= \sum_{i=r}^d \lambda_i  - \sum_{i=1}^r \lambda_i \\
&= \sum_{i=r+1}^d \lambda_i   \\
\end{split}
$$

#### proportion of explained variance
- proportion of the [[variance]] that is explained by a [[latent space]] representation in a space dimension $r$

$$
\begin{split}
PEV(r)
&= \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
&= \frac{TV - RV(r)}{TV} \\
&= \frac{\sum_{i=1}^d \lambda_i  - \sum_{i=r+1}^d \lambda_i }{\sum_{i=1}^d \lambda_i } \\
&= \frac{\sum_{i=r}^r \lambda_i   }{\sum_{i=1}^d \lambda_i } \\
\end{split}
$$

______________

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



Tags: mathematics SS25
<!--ID: 1753118033407-->
END



START
Basic
[[explained variance]]
- residual variance with proof

Back: 
### explained variance
- method of decomposing the variance in the part the is explained by a using representation in a [[latent space]] of dimension $r$ and a part that is not explained by it (using the [[principal component analysis]])

- let $X \in \mathbb{R}^{d \times n}$ be zero mean [[random variable]] with $\Sigma=\mathbb{VAR} \left[X\right]$
- since $\Sigma$ is a [[symmetric matrix]] it is always a [[eigendecomposition]] with a [[orthonormal]] bases

$$
\Sigma= \frac{1}{n} X^\top X =U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top
$$

- with $\lambda_1\geq ...\geq \lambda_d$ being the [[eigenvalue]] and $U=[U_1, ..., U_n] \in \mathbb{R}^{d \times d}$ its [[orthogonal matrix]] of[[eigenvector]]s

#### total variance
- let $TV$ be the total [[variance]] of $X$ defined as follows, which is equivalent to the sum of the [[eigenvalue]] of $\Sigma$


$$
\begin{split}
TV
&=\mathbb{E} \left[ \left\| X \right\|_2^2 \right]  \\
&=\mathbb{E} \left[\mathrm{tr}\left(X^\top X\right) \right] \\
&=\left[\mathrm{tr}\left(\mathbb{VAR} \left[X\right]\right) \right] \\
&=\left[\mathrm{tr}\left(\Sigma\right) \right] \\
&=\left[\mathrm{tr}\left(U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top\right) \right] \\
&=\left[\mathrm{tr}\left(\mathrm{diag}(\lambda_1,..., \lambda_n)\right) \right] \\
&= \sum_{i=1}^d \lambda_i \\
\end{split}
$$


#### residual variance
- let $V=[U_1, ..., U_r] \in \mathbb{R}^{d \times r}$ with $V \in \mathbb{R}^{d \times r}$ with $V^\top V = I_r$ but $V V^\top \neq I_d$
- note that $V \in \mathbb{R}^{d \times r}$ is a [[orthonormal matrix]] with $V^\top V = I_r$ but $V V^\top \neq I_d$ in general
- residual [[variance]] $RV(r)$ with $\mathrm{dim}(V)=r$ is the rest of the [[variance]] on the data that is not explained by the lower dimensional representation $P_V(X)$ is defined as follows


$$
\begin{split}
RV(r)
&= \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
&= \sum_{i=r+1}^d \lambda_i \\
\end{split}
$$
##### proof

- the following being the projection itself (see [[projection#projection into an orthonormal subspace]]) 
$$
P_V(X) = VV^\top X
$$

- $V^\top U=[I_r , 0]^\top$

$$
\begin{split}
\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| VV^\top X  \right\|_2^2 \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left((VV^\top X)^\top VV^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( X^\top VV^\top VV^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( X^\top VV^\top X\right) \right] \\
&= \mathbb{E} \left[ \mathrm{tr}(V^\top X X^\top V) \right] \\
&= \mathrm{tr}(V^\top \Sigma V) \\
&= \mathrm{tr}(V^\top U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top V) \\
&= \sum_{i=1}^r \lambda_i
\end{split}
$$

$$
\begin{split}
\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| VV^\top X  \right\|_2^2 \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left((V^\top X)^\top V^\top X\right) \right] \\
&=\mathbb{E} \left[\mathrm{tr}\left( V^\top X\right)(V^\top X)^\top \right] \\
&= \mathbb{E} \left[ \mathrm{tr}(V^\top X X^\top V) \right] \\
&= \mathrm{tr}(V^\top \Sigma V) \\
&= \mathrm{tr}(V^\top U\mathrm{diag}(\lambda_1,..., \lambda_n)U^\top V) \\
&= \sum_{i=1}^r \lambda_i
\end{split}
$$


$$
\begin{split}
\mathbb{E} \left[ \left\| X \right\|_2^2 \right]
&=\mathbb{E} \left[ \left\| X -  P_V(X) + P_V(X) \right\|_2^2 \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] +2 \mathbb{E} \left[ \langle X,  X -  P_V(X)  \rangle \right] \\
&=\mathbb{E} \left[ \left\| P_V(X)  \right\|_2^2 \right] + \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
\end{split}
$$

$$
\begin{split}
\mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right]  
&= \mathbb{E} \left[ \left\| X \right\|_2^2 \right] - \left[ \left\| P_V(X)  \right\|_2^2 \right] \\
&= \sum_{i=r}^d \lambda_i  - \sum_{i=1}^r \lambda_i \\
&= \sum_{i=r+1}^d \lambda_i   \\
\end{split}
$$

#### proportion of explained variance
- proportion of the [[variance]] that is explained by a [[latent space]] representation in a space dimension $r$

$$
\begin{split}
PEV(r)
&= \mathbb{E} \left[ \left\| X -  P_V(X)  \right\|_2^2 \right] \\
&= \frac{TV - RV(r)}{TV} \\
&= \frac{\sum_{i=1}^d \lambda_i  - \sum_{i=r+1}^d \lambda_i }{\sum_{i=1}^d \lambda_i } \\
&= \frac{\sum_{i=r}^r \lambda_i   }{\sum_{i=1}^d \lambda_i } \\
\end{split}
$$

______________

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



Tags: mathematics SS25
<!--ID: 1753118033410-->
END