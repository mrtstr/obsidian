### nullspace
- the [[nullspace]] of a [[matrix]] is the [[set]] of [[vector|vectors]] that is mapped to the origin by the [[linear function]] induced by $A$
$$
N(A)=\left\{ x \in \mathbb{R}^{m} \mid Ax=0 \right\}
\subseteq\mathbb{R}^{m}
$$

### properties of the [[nullspace]]
#### the [[nullspace]] is never empy because it always contains the origin $\mathbf{0} \in N(A)$ 
$$
\begin{split}
&\forall A \in \mathbb{R}^{n \times m}: A \left(\begin{matrix} 0 \\ ... \\ 0\end{matrix}\right)
= \left(\begin{matrix} 0 \\ ... \\ 0\end{matrix}\right) \\
&\Rightarrow \left(\begin{matrix} 0 \\ ... \\ 0\end{matrix}\right) \in N(A)
\end{split}
$$
#### the [[nullspace]] $N(A \in \mathbb{R}^{n \times m})$ is a [[subspace]] of $\mathbb{R}^m$

![[subspace#subspace]]

1) [[closure|closed]] unter [[multiplication]] with a [[scalar]]
$$
\begin{split}
v \in N(A) &\Rightarrow Av = 0 \\
&\Rightarrow \lambda \cdot Av =  
 \left(\begin{matrix} \lambda \cdot 0 \\ ... \\ \lambda \cdot 0\end{matrix}\right) \in N(A)
\end{split}
$$
2) [[closure|closed]] unter [[addition]]
$$
\begin{split}
v \in N(A) \land w \in N(A) &\Rightarrow Av = 0 \land Aw = 0 \\
&\Rightarrow A v w^\top =  
 \left(\begin{matrix} 0 \\ ... \\ 0\end{matrix}\right)w^\top \in N(A)
\end{split}
$$
#### dimension of the [[nullspace]]
- $dim(N(A)) = m - dim(range(A))$ [[rank nullity theorem]]
- $dim(N(A)) = nullity(A)$ (dimensions are the [[nullity]])
- $dim(N(A))$ = number of linear dependent rows


### Explanation 
In the [[nullspace]] are the vectors in the domain of $F(x)$ that map to zero. Thus, there are linear dependent column vectors $A^{(j)}$ needed for that to be the case. For $x$ to be in the [[nullspace]] the elements $(x)_{j}$ that is multiplied with the linear dependent column vectors $A^{(j)}$ has to be $\neq 0$ and all the other $(x)_{j}$ have to be $=0$. Thus, the dimensions of the [[nullspace]] are equal to the number of linear dependent column vectors $A^{(j)}$ and the [[nullity]]


# anki

START
Basic
proof that the [[nullspace]] $N(A \in \mathbb{R}^{n \times m})$ is a [[subspace]] of $\mathbb{R}^m$
Back: 
1) [[closure|closed]] unter [[multiplication]] with a [[scalar]]
$$
\begin{split}
v \in N(A) &\Rightarrow Av = 0 \\
&\Rightarrow \lambda \cdot Av =  
 \left(\begin{matrix} \lambda \cdot 0 \\ ... \\ \lambda \cdot 0\end{matrix}\right) \in N(A)
\end{split}
$$
2) [[closure|closed]] unter [[addition]]
$$
\begin{split}
v \in N(A) \land w \in N(A) &\Rightarrow Av = 0 \land Aw = 0 \\
&\Rightarrow A v w^\top =  
 \left(\begin{matrix} 0 \\ ... \\ 0\end{matrix}\right)w^\top \in N(A)
\end{split}
$$

______________________


### subspace
- a [[vector space]] $(V, +, \cdot)$ on a [[field]] $\mathbb{K}$
- $H \subseteq V$ is a [[subspace]] of $V$ if $H$ is a [[vector space]] itself equivalently the following conditions are true
1) $v \in H \land \lambda \in \mathbb{K} \rightarrow \lambda \cdot v \in H$ ([[closure|closed]] for [[multiplication]] with [[scalar|scalars]])
2) $v,w \in H \rightarrow v + w \in H$ ([[closure|closed]] for [[addition]])

### nullspace
- the [[nullspace]] of a [[matrix]] is the [[set]] of [[vector|vectors]] that is mapped to the origin by the [[linear function]] induced by $A$
$$
N(A)=\left\{ x \in \mathbb{R}^{m} \mid Ax=0 \right\}
\subseteq\mathbb{R}^{m}
$$
Tags: mathematics linear_algebra
<!--ID: 1713625090179-->
END

START
Basic
proof that the [[nullspace]] is allways non empty
Back: 
the [[nullspace]] is never empy because it always contains the origin $\mathbf{0} \in N(A)$ 
$$
\begin{split}
&\forall A \in \mathbb{R}^{n \times m}: A \left(\begin{matrix} 0 \\ ... \\ 0\end{matrix}\right)
= \left(\begin{matrix} 0 \\ ... \\ 0\end{matrix}\right) \\
&\Rightarrow \left(\begin{matrix} 0 \\ ... \\ 0\end{matrix}\right) \in N(A)
\end{split}
$$
______________________

### nullspace
- the [[nullspace]] of a [[matrix]] is the [[set]] of [[vector|vectors]] that is mapped to the origin by the [[linear function]] induced by $A$
$$
N(A)=\left\{ x \in \mathbb{R}^{m} \mid Ax=0 \right\}
\subseteq\mathbb{R}^{m}
$$
Tags: mathematics linear_algebra
<!--ID: 1713625090183-->
END

START
Basic
Nullspace or Kernel
- definition
- properties (5)
- explanation
Back: 
# Nullspace or Kernel

For a [[matrix]] $A$ with the column vectors $A^{(j)}$ and the represented linear function $F$.
$$
A =\left(A^{(j)} \right)_{j \in \mathcal{J}}
= 
\begin{pmatrix}   A^{(1)}    ... & A^{(\left| \mathcal{J} \right|)}  \end{pmatrix}
\in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}
$$
$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$


## Definition

$$
kernel(A)=\left\{ x \in \mathbb{R}^{\mathcal{\left|J\right |}} \mid Ax=0 \right\}
\subseteq\mathbb{R^{\left| \mathcal{J} \right|}}
$$
## Properties
- $kernel(A) \subseteq \mathbb{R^{\left| \mathcal{J} \right| }}$ 
- $\mathbf{0} \in kern(A)$ 
- $dim(kern(A)) = \left| \mathcal{J} \right| - dim(range(A))$ [[rank nullity theorem]]
- $dim(kern(A)) = nullity(A)$ (dimensions are the [[nullity]])
- $dim(kern(A))$ = number of linear dependent rows


## Explanation 
In the [[nullspace]] are the vectors in the domain of $F(x)$ that map to zero. Thus, there are linear dependent column vectors $A^{(j)}$ needed for that to be the case. For $x$ to be in the [[nullspace]] the elements $(x)_{j}$ that is multiplied with the linear dependent column vectors $A^{(j)}$ has to be $\neq 0$ and all the other $(x)_{j}$ have to be $=0$. Thus, the dimensions of the [[nullspace]] are equal to the number of linear dependent column vectors $A^{(j)}$ and the [[nullity]]
![[Pasted image 20221015081452.png]]
Tags: mathematics linear_algebra
<!--ID: 1665824261708-->
END