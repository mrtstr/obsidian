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

### singular value decomposition: squared matrices
- the column vectors of $U$ are [[orthonormal]] [[eigenvectors]] of $AA^\top$ and $\sigma_k^2$ are its [[eigenvalues]]
- the column vectors of $V$ are [[orthonormal]] [[eigenvectors]] of $A^\top A$ and $\sigma_k^2$ are its [[eigenvalues]]

$$
\begin{split}
AA^\top &= U \Sigma \Sigma^\top U^\top \\

A^\top A &= V \Sigma^\top \Sigma V^\top  \\
\end{split}
$$


#### proof

$$
\begin{split}
AA^\top 
&= U\Sigma V^\top \left( U\Sigma V^\top \right)^\top\\
&= U\Sigma V^\top  V\Sigma^\top U^\top \\
&= U \Sigma \Sigma^\top U^\top \\
A^\top A
&= \left( U\Sigma V^\top \right)^\top U\Sigma V^\top \\
&= V\Sigma^\top U^\top U\Sigma V^\top   \\
&= V\Sigma^\top\Sigma V^\top   \\

\end{split}
$$

TODO: add rest
# --------------------
![[orthogonal matrix#orthogonal matrix]]

![[diagonal matrix#diagonal matrix]]

![[diagonal matrix#properties of square diagonal matrices]]


# anki

START
Basic
[[singular value decomposition]] summary:
- definition
- spectral decomposition
- relationship of $U$ and $V$
- singular value decomposition of squared matrices
 
Back: 
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

### singular value decomposition: squared matrices

$$
\begin{split}
AA^\top &= U \Sigma \Sigma^\top U^\top \\

A^\top A &= V \Sigma^\top \Sigma V^\top  \\
\end{split}
$$
#### proof

$$
\begin{split}
AA^\top 
&= U\Sigma V^\top \left( U\Sigma V^\top \right)^\top\\
&= U\Sigma V^\top  V\Sigma^\top U^\top \\
&= U \Sigma \Sigma^\top U^\top \\
A^\top A
&= \left( U\Sigma V^\top \right)^\top U\Sigma V^\top \\
&= V\Sigma^\top U^\top U\Sigma V^\top   \\
&= V\Sigma^\top\Sigma V^\top   \\

\end{split}
$$


------------------------

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

END




START
Basic
[[singular value decomposition]] and spectral decomposition
- definition

 
Back: 
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


------------------------

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

END


START
Basic
proof that every [[matrix]] of [[rank]] $k$ can be expressed as a sum of $k$ [[rank]] one matrices

Back: 

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


------------------------

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

END


START
Basic
- given a [[singular value decomposition]] how are the colum vectors of $U$ and $V$ related?
$$
A = U\Sigma V^\top
$$
 
Back: 
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





------------------------

### singular value decomposition
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with [[rank]] $r$
- there exists an [[orthonormal]] [[matrix]] $U\in\mathbb{R}^{n\times n}$ and [[orthonormal]] [[matrix]] $V\in\mathbb{R}^{m\times m}$ and a [[diagonal matrix]] $\Sigma \in \mathbb{R}^{n \times m}$ auch that
$$
A = U\Sigma V^\top
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

END


START
Basic
- given a [[singular value decomposition]] 

$$
A = U\Sigma V^\top
$$
- prove the following

$$
\begin{split}

A^\top U_{(*,k)} &= \sigma_k V_{(*,k)} \\
\end{split}
$$
Back: 
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





------------------------

### singular value decomposition
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with [[rank]] $r$
- there exists an [[orthonormal]] [[matrix]] $U\in\mathbb{R}^{n\times n}$ and [[orthonormal]] [[matrix]] $V\in\mathbb{R}^{m\times m}$ and a [[diagonal matrix]] $\Sigma \in \mathbb{R}^{n \times m}$ auch that
$$
A = U\Sigma V^\top
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

END


START
Basic
how does a [[singular value decomposition]] of a [[square matrix]] $AA^\top$ and $A^\top A$ look like? 

Back: 
### singular value decomposition: squared matrices
- the column vectors of $U$ are [[orthonormal]] [[eigenvectors]] of $AA^\top$ and $\sigma_k^2$ are its [[eigenvalues]]
- the column vectors of $V$ are [[orthonormal]] [[eigenvectors]] of $A^\top A$ and $\sigma_k^2$ are its [[eigenvalues]]

$$
\begin{split}
AA^\top &= U \Sigma \Sigma^\top U^\top \\

A^\top A &= V \Sigma^\top \Sigma V^\top  \\
\end{split}
$$


#### proof

$$
\begin{split}
AA^\top 
&= U\Sigma V^\top \left( U\Sigma V^\top \right)^\top\\
&= U\Sigma V^\top  V\Sigma^\top U^\top \\
&= U \Sigma \Sigma^\top U^\top \\
A^\top A
&= \left( U\Sigma V^\top \right)^\top U\Sigma V^\top \\
&= V\Sigma^\top U^\top U\Sigma V^\top   \\
&= V\Sigma^\top\Sigma V^\top   \\

\end{split}
$$

TODO: add rest

------------------------
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

END