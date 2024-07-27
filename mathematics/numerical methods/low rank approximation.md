### low rank approximation
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with [[rank]] $r$ and a [[singular value decomposition]] $A = U\Sigma V^\top$ 
$$
\begin{split}
A 
&= U\Sigma V^\top \\
&= \sum_{k \in [r]} \sigma_k  U_{(*,k)}  V_{(*,k)}^\top \\
\end{split}
$$
- the best approximation of $A$ with a [[rank]] $k$ is achived by taking the spectral decomposion of $A$ and keep only the first $k$ rank one matrices

$$
\begin{split}
A_k
&= \sum_{l \in [k]} \sigma_l  U_{(*,l)}  V_{(*,l)}^\top \\
&= \mathrm{arg\min}_{rank(A_k)=k} ||A-A_k|| \\
\end{split}
$$
- the difference between $A$ and its approximation $A_k$ regarding the [[spectral norm]] and the [[frobenius norm]] is as follows
$$
\begin{split}
||A-A_k||_F &= \sqrt{\sigma^2_{k+1}+ ... + \sigma^2_{\max\{n,m\}}} \\
||A-A_k||_2 &= \sigma^2_{k+1}
\end{split}
$$

# ---------------------------
![[singular value decomposition#spectral decomposition]]

![[frobenius norm#frobenius norm]]

![[spectral norm#spectral norm]]

# anki

START
Basic
best [[low rank approximation]] of a [[matrix]] (no proof)
- definition
- diffrence to original regarding the [[frobenius norm]] and [[spectral norm]]

Back: 
### low rank approximation
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with [[rank]] $r$ and a [[singular value decomposition]] $A = U\Sigma V^\top$ 
$$
\begin{split}
A 
&= U\Sigma V^\top \\
&= \sum_{k \in [r]} \sigma_k  U_{(*,k)}  V_{(*,k)}^\top \\
\end{split}
$$
- the best approximation of $A$ with a [[rank]] $k$ is achived by taking the spectral decomposion of $A$ and keep only the first $k$ rank one matrices

$$
\begin{split}
A_k
&= \sum_{l \in [k]} \sigma_l  U_{(*,l)}  V_{(*,l)}^\top \\
&= \mathrm{arg\min}_{rank(A_k)=k} ||A-A_k|| \\
\end{split}
$$
- the difference between $A$ and its approximation $A_k$ regarding the [[spectral norm]] and the [[frobenius norm]] is as follows
$$
\begin{split}
||A-A_k||_F &= \sqrt{\sigma^2_{k+1}+ ... + \sigma^2_{\max\{n,m\}}} \\
||A-A_k||_2 &= \sigma^2_{k+1}
\end{split}
$$

------------------------

### frobenius norm
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- the [[frobenius norm]] $||\cdot||_F$ is defined as follows

$$
||A||_F = \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |a_{ij}|^2}
$$

### spectral norm
- [[operator norm]] induces by the $l^2$ [[norm]]
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$

$$
||A||_{2\rightarrow 2} =  \sup_{x\neq 0} \frac{||Ax||_2}{||x||_2} = \sqrt{\sigma_{\max}(A^\top A)}
$$


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

### spectral decomposition
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with [[rank]] $r$ and a [[singular value decomposition]] $A = U\Sigma V^\top$ with [[orthonormal]] [[matrix]] $U\in\mathbb{R}^{n\times n}$ and [[orthonormal]] [[matrix]] $U\in\mathbb{R}^{m\times m}$ and a [[diagonal matrix]] $\Sigma \in \mathbb{R}^{n \times m}$ 
- there exists an [[orthonormal]] [[matrix]] $\widehat U\in\mathbb{R}^{n\times r}$ and [[orthonormal]] [[matrix]] $\widehat V\in\mathbb{R}^{m\times r}$ and a [[diagonal matrix]] $\Sigma \in \mathbb{R}^{r \times r}$ auch that
- this means the [[rank]] $r$ [[matrix]] $A$ can be expressed as a sum of $k$ [[rank]] one matrice $\widehat U_{(*,k)}  \widehat V_{(*,k)}^\top$ that are weighted by $\sigma_k$ which is called the **spectral decomposition**

#### proof
$$
\begin{split}
A 
&= U\Sigma V^\top \\
&=
\left(\begin{matrix}
\widehat U & \widetilde U
\end{matrix}\right)
\left(\begin{matrix}
\widehat \Sigma & 0 \\
0 & 0 \\
\end{matrix}\right)
\left(\begin{matrix}
\widehat U & \widetilde U
\end{matrix}\right)^\top \\
&= \widehat U \widehat\Sigma \widehat V^\top \\
&= \sum_{k \in [r]} \sigma_k \widehat U_{(*,k)}  \widehat V_{(*,k)}^\top \\
\end{split}
$$
### singular value decomposition: relationship of $U$ and $V$
- matrix $A$ mappes the column vactors auf $U$ to the column vectors auf $V$ and vice versa

$$
\begin{split}
A V_{(*,k)} &= \sigma_k U_{(*,k)} \\
A^\top U_{(*,k)} &= \sigma_k V_{(*,k)} \\
\end{split}
$$
#### proof


$$
\begin{split}
A &= U\Sigma V^\top \\
\Rightarrow AV &= U\Sigma V^\top V = U\Sigma \\
\Rightarrow AV_{(*, k)} &= U\Sigma_{(*, k)} \\
&= \sum_{j \in [m]} U_{(*,m)}\Sigma_{(m, k)} \\
&= \sigma_k U_{(*,k)} + 0 \cdot U_{(1,k)} + 0 \cdot U_{(2,k)} ... \\
&= \sigma_k U_{(*,k)} \\
\end{split}
$$


$$
\begin{split}
A &= U\Sigma V^\top \\
\Rightarrow A^\top &= V \Sigma U^\top \\
\Rightarrow A^\top U &=  V \Sigma U^\top U = V\Sigma \\
\Rightarrow A^\top U_{(*, k)} &= V\Sigma_{(*, k)} \\
&= \sum_{j \in [m]} V_{(*,m)}\Sigma_{(m, k)} \\
&= \sigma_k V_{(*,k)} + 0 \cdot V_{(1,k)} + 0 \cdot V_{(2,k)} ... \\
&= \sigma_k V_{(*,k)} \\
\end{split}
$$


### orthogonal matrix
- a [[orthogonal matrix]] is a [[matrix]] $Q \in \mathbb{R}^{n \times n}$ with a [[transpose]] that is equal to its [[inverse matrix]]  
$$
Q^{-1}=Q^{T} \Leftrightarrow Q^\top Q = QQ^\top = I
$$

- from $QQ^\top = Q^\top Q = I$ it follows that column [[vector|vectors]] $Q_{(*,j)}$ (and row [[vector|vectors]] $Q_{(i,*)}$) that are not on the diagonal are [[orthogonal]] (perpendicular) to each other 
$$
\left\langle Q_{(*,j)} Q_{(*,k)}\right\rangle = Q_{(*,j)}^\top Q_{(*,k)} = \left\{\begin{matrix} 1 &\text{if } j=k \\ 0 & \text{else} \end{matrix} \right.
$$
- from $\left\langle Q_{(*,j)} Q_{(*,j)}\right\rangle = 1$ follows that all column and row [[vector|vectors]] need to be normalized
$$
\begin{split}
&\left\langle Q_{(*,j)} Q_{(*,j)}\right\rangle = 1 \\ 
\Rightarrow& \sqrt{\left\langle Q_{(*,j)} Q_{(*,j)}\right\rangle} = ||Q_{(*,j)}|| = 1 \\ 

\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1722105316895-->
END