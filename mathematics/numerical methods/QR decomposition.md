### QR decomposition
- for every [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ there exists a [[orthogonal matrix]] $Q \in \mathbb{R}^{n \times n}$ and a [[triangular matrix]] $R \in \mathbb{R}^{n \times m}$ auch that $A=QR$
- furthermore there exists an [[orthogonal matrix]] $Q_1 \in \mathbb{R}^{n \times m}$ and a [[triangular matrix]] $R_1 \in \mathbb{R}^{m \times m}$ auch that $A=Q_1R_1$ which is called the **slim QR decomposition**

$$
\begin{split}
A 
&= QR \\
&= \left(\begin{matrix}Q_1 & Q_2\end{matrix}\right)\left(\begin{matrix}R_1 \\ 0\end{matrix}\right) \\
&= Q_1R_1 \\
\end{split}
$$
- can be used for approximating the solution of an overdetermined [[linear equation system]] using [[linear least squares]]

### orthonormal basis
- give a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ an [[QR decomposition]] $A=QR$
- the column vectors of $Q$ are [[orthonormal]] [[basis]] of the [[column space]] of $A$
$$
\mathrm{span}(A_{(*, 1)}, ..., A_{(*, m)}) = \mathrm{span}(Q_{(*, 1)}, ..., A_{(*, m)})
$$
#### proof
- based on the definition of an [[orthogonal matrix]] the column vectors $Q_{(*, 1)}, ..., Q_{(*, m)}$ have to be [[orthogonal]] to each other and normalized $||Q_{(*, j)}||=1$
- since every column vector of $A_{(*, j)}$ can be expressed as a [[linear combinations]] of $Q_{(*, 1)}, ..., Q_{(*, m)}$ the column vectors auf $Q$ are a [[basis]]
$$
\begin{split}
&A = QR \\
\Leftrightarrow& A_{(*, j)} = QR_{(*, j)} = \sum_{k \in [m]} Q_{(*, k)}R_{(k, j)} \\
\end{split}
$$

### complement of the [[image]]
- given the [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ with the [[QR decomposition]] $A=QR$  ([[orthogonal matrix]] $Q \in \mathbb{R}^{n \times n}$ and a [[triangular matrix]] $R \in \mathbb{R}^{n \times m}$) and the slim QR decomposition $A=Q_1R_1$ ([[orthogonal matrix]] $Q_1 \in \mathbb{R}^{m \times m}$ and a [[triangular matrix]] $R \in \mathbb{R}_1^{m \times m}$)

$$
\begin{split}
A 
&= QR \\
&= \left(\begin{matrix}Q_1 & Q_2\end{matrix}\right)\left(\begin{matrix}R_1 \\ 0\end{matrix}\right) \\
\end{split}
$$

- the [[complement]] of $A$ which is equal to its [[nullspace]] is equal to the [[image]] auf $Q_2$
$$
\begin{split}
\mathrm{image}(A) = \mathrm{span}(A_{(*, 1)}, ..., A_{(*, m)}) = \mathrm{image}(Q_1) \\
\mathrm{image}(A)^\bot = N(A) = \{x: Ax=0\} = \mathrm{image}(Q_2)
\end{split}
$$

TODO add proof
# ---------------------------

![[orthogonal matrix#orthogonal matrix]]

![[triangular matrix#upper triangular matrix]]


# anki


START
Basic
proof that every [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ and $rank(A) = m$ has a [[orthonormal]] [[basis]]

Back: 
### orthonormal basis
- give a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ an [[QR decomposition]] $A=QR$
- the column vectors of $Q$ are [[orthonormal]] [[basis]] of the [[column space]] of $A$

$$
\mathrm{span}(A_{(*, 1)}, ..., A_{(*, m)}) = \mathrm{span}(Q_{(*, 1)}, ..., A_{(*, m)})
$$

#### proof
- based on the definition of an [[orthogonal matrix]] the column vectors $Q_{(*, 1)}, ..., Q_{(*, m)}$ have to be [[orthogonal]] to each other and normalized $||Q_{(*, j)}||=1$
- since every column vector of $A_{(*, j)}$ can be expressed as a [[linear combinations]] of $Q_{(*, 1)}, ..., Q_{(*, m)}$ the column vectors auf $Q$ are a [[basis]]
$$
\begin{split}
&A = QR \\
\Leftrightarrow& A_{(*, j)} = QR_{(*, j)} = \sum_{k \in [m]} Q_{(*, k)}R_{(k, j)} \\
\end{split}
$$


### QR decomposition
- for every [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ there exists a [[orthogonal matrix]] $Q \in \mathbb{R}^{n \times n}$ and a [[triangular matrix]] $R \in \mathbb{R}^{n \times m}$ auch that $A=QR$
- furthermore there exists an [[orthogonal matrix]] $Q_1 \in \mathbb{R}^{n \times m}$ and a [[triangular matrix]] $R_1 \in \mathbb{R}^{m \times m}$ auch that $A=Q_1R_1$ which is called the **slim QR decomposition**

$$
\begin{split}
A 
&= QR \\
&= \left(\begin{matrix}Q_1 & Q_2\end{matrix}\right)\left(\begin{matrix}R_1 \\ 0\end{matrix}\right) \\
&= Q_1R_1 \\
\end{split}
$$

- can be used for approximating the solution of an overdetermined [[linear equation system]] using [[linear least squares]]

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

### upper triangular matrix 
A [[matrix]] $U$ is an upper [[triangular matrix]] if all values obove the diagonal line are zero $\forall i < j: a_{ij} = 0$ 
$$
\begin{split}
U = \begin{pmatrix}
u_{(1:1)} &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ u_{(2:2)} &\ l_{(2:3)} \\
0         &\ 0         &\ u_{(3:3)} \\  
\end{pmatrix}
\end{split}
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


Tags: mathematics linear_algebra
<!--ID: 1722347436750-->
END


START
Basic
[[QR decomposition]]
- definition
- existance
- potential usecase

Back: 
### QR decomposition
- for every [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ there exists a [[orthogonal matrix]] $Q \in \mathbb{R}^{n \times n}$ and a [[triangular matrix]] $R \in \mathbb{R}^{n \times m}$ auch that $A=QR$
- furthermore there exists an [[orthogonal matrix]] $Q_1 \in \mathbb{R}^{n \times m}$ and a [[triangular matrix]] $R_1 \in \mathbb{R}^{m \times m}$ auch that $A=Q_1R_1$ which is called the **slim QR decomposition**

$$
\begin{split}
A 
&= QR \\
&= \left(\begin{matrix}Q_1 & Q_2\end{matrix}\right)\left(\begin{matrix}R_1 \\ 0\end{matrix}\right) \\
&= Q_1R_1 \\
\end{split}
$$

- can be used for approximating the solution of an overdetermined [[linear equation system]] using [[linear least squares]]

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

### upper triangular matrix 
A [[matrix]] $U$ is an upper [[triangular matrix]] if all values obove the diagonal line are zero $\forall i < j: a_{ij} = 0$ 
$$
\begin{split}
U = \begin{pmatrix}
u_{(1:1)} &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ u_{(2:2)} &\ l_{(2:3)} \\
0         &\ 0         &\ u_{(3:3)} \\  
\end{pmatrix}
\end{split}
$$



Tags: mathematics linear_algebra
<!--ID: 1722342554299-->
END



START
Basic
- given the [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ with the [[QR decomposition]] $A=QR$ ([[orthogonal matrix]] $Q \in \mathbb{R}^{n \times n}$ and a [[triangular matrix]] $R \in \mathbb{R}^{n \times m}$) and the slim QR decomposition $A=Q_1R_1$ ([[orthogonal matrix]] $Q_1 \in \mathbb{R}^{m \times m}$ and a [[triangular matrix]] $R_1 \in \mathbb{R}^{m \times m}$)

$$
\begin{split}
A 
&= QR \\
&= \left(\begin{matrix}Q_1 & Q_2\end{matrix}\right)\left(\begin{matrix}R_1 \\ 0\end{matrix}\right) \\
\end{split}
$$

- expression for the [[nullspace]] of $A$ (without proof)

Back: 
### complement of the [[image]]

- the [[complement]] of $A$ which is equal to its [[nullspace]] is equal to the [[image]] auf $Q_2$
$$
\begin{split}
\mathrm{image}(A) = \mathrm{span}(A_{(*, 1)}, ..., A_{(*, m)}) = \mathrm{image}(Q_1) \\
\mathrm{image}(A)^\bot = N(A) = \{x: Ax=0\} = \mathrm{image}(Q_2)
\end{split}
$$


### orthonormal basis
- give a [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ an [[QR decomposition]] $A=QR$
- the column vectors of $Q$ are [[orthonormal]] [[basis]] of the [[column space]] of $A$

$$
\mathrm{span}(A_{(*, 1)}, ..., A_{(*, m)}) = \mathrm{span}(Q_{(*, 1)}, ..., A_{(*, m)})
$$

#### proof
- based on the definition of an [[orthogonal matrix]] the column vectors $Q_{(*, 1)}, ..., Q_{(*, m)}$ have to be [[orthogonal]] to each other and normalized $||Q_{(*, j)}||=1$
- since every column vector of $A_{(*, j)}$ can be expressed as a [[linear combinations]] of $Q_{(*, 1)}, ..., Q_{(*, m)}$ the column vectors auf $Q$ are a [[basis]]
$$
\begin{split}
&A = QR \\
\Leftrightarrow& A_{(*, j)} = QR_{(*, j)} = \sum_{k \in [m]} Q_{(*, k)}R_{(k, j)} \\
\end{split}
$$


### QR decomposition
- for every [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ there exists a [[orthogonal matrix]] $Q \in \mathbb{R}^{n \times n}$ and a [[triangular matrix]] $R \in \mathbb{R}^{n \times m}$ auch that $A=QR$
- furthermore there exists an [[orthogonal matrix]] $Q_1 \in \mathbb{R}^{n \times m}$ and a [[triangular matrix]] $R_1 \in \mathbb{R}^{m \times m}$ auch that $A=Q_1R_1$ which is called the **slim QR decomposition**

$$
\begin{split}
A 
&= QR \\
&= \left(\begin{matrix}Q_1 & Q_2\end{matrix}\right)\left(\begin{matrix}R_1 \\ 0\end{matrix}\right) \\
&= Q_1R_1 \\
\end{split}
$$

- can be used for approximating the solution of an overdetermined [[linear equation system]] using [[linear least squares]]

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

### upper triangular matrix 
A [[matrix]] $U$ is an upper [[triangular matrix]] if all values obove the diagonal line are zero $\forall i < j: a_{ij} = 0$ 
$$
\begin{split}
U = \begin{pmatrix}
u_{(1:1)} &\ u_{(1:2)} &\ u_{(1:3)} \\
0         &\ u_{(2:2)} &\ l_{(2:3)} \\
0         &\ 0         &\ u_{(3:3)} \\  
\end{pmatrix}
\end{split}
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


Tags: mathematics linear_algebra
<!--ID: 1722348410268-->
END