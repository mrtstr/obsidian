### QR decomposition
- for every [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ there exists a [[orthogonal matrix]] $Q \in \mathbb{R}^{n \times n}$ and a [[triangular matrix]] $R \in \mathbb{R}^{n \times m}$ auch that $A=QR$
- furthermore there exists an [[orthogonal matrix]] $Q_1 \in \mathbb{R}^{m \times m}$ and a [[triangular matrix]] $R \in \mathbb{R_1}^{m \times m}$ auch that $A=Q_1R_1$

$$
\begin{split}
A 
&= QR \\
&= \left(\begin{matrix}Q_1 & Q_2\end{matrix}\right)\left(\begin{matrix}R_1 \\ 0\end{matrix}\right) \\
&= Q_1R_1 \\
\end{split}
$$
- can be used for approximating the solution of an overdetermined [[linear equation system]] using [[linear least squares]]

# ---------------------------

![[orthogonal matrix#orthogonal matrix]]

![[triangular matrix#upper triangular matrix]]


# anki


START
Basic
[[QR decomposition]]
- definition
- existance
- potential usecase

Back: 
### QR decomposition
- for every [[matrix]] $A \in \mathbb{R}^{n \times m}$ with $n \geq m$ there exists a [[orthogonal matrix]] $Q \in \mathbb{R}^{n \times n}$ and a [[triangular matrix]] $R \in \mathbb{R}^{n \times m}$ auch that $A=QR$
- furthermore there exists an [[orthogonal matrix]] $Q_1 \in \mathbb{R}^{m \times m}$ and a [[triangular matrix]] $R \in \mathbb{R_1}^{m \times m}$ auch that $A=Q_1R_1$

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