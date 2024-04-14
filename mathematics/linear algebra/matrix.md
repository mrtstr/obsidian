
### matrix
- can be represented by a two-dimensional [[array]]
- is a 2. Order [[tensor]] 
$$
\begin{split}
A  \in \mathbb{R}^{n  \times m}
&= \left(a_{i,j} \right)_{i \in [n], j \in [m]} \\
&= \left(A_{(*:j)} \right)_{j \in [m]}
= 
\begin{pmatrix}   A_{(*:1)} &   ... & A_{(*:m}   \end{pmatrix}\\
&= \left(A_{(i:*)} \right)_{i \in [n]}
=  
\begin{pmatrix}   A_{(1:*)} \\   ... \\ A_{(n:*)}   \end{pmatrix}
\end{split}
$$


### operations

![[matrix product#matrix product]]

![[transpose#transpose]]

![[inverse matrix#inverse function inverse matrix $A {-1}$]]

### properties
[[determinant]]

# anki

START
Basic
matrix transpose
- definition
- properties (6)
 
Back: 
#### [[transpose]]
The [[transpose]] of [[matrix]] A is defined as follows 
$$
\begin{split}
A^\top  \in \mathbb{R^{\left| \mathcal{J} \right| \times \left| \mathcal{I} \right|}} 
&= \left(a_{i,j} \right)_{j \in \mathcal{J}, i \in \mathcal{I}} \\
&= \left(A_{(*:j)} \right)_{j \in \mathcal{J}}
= 
\begin{pmatrix}   A_{(*:1)} &   ... & A_{(*:\left| \mathcal{J} \right|)}  \end{pmatrix}\\
&= \left(A_{(i:*)} \right)_{i \in \mathcal{I}}
=  
\begin{pmatrix}   A_{(1:*)} \\   ... \\ A_{(\left| \mathcal{I} \right|:*)}    \end{pmatrix}
\end{split}
$$
 
#### Properties
1) $\left(A_1A_2 \: .. \:A_k\right)^\top=A_k^\top  \: .. \: A_2^\top A_1^\top$ 
2) $\left(A+B\right)^\top=A^\top + B^\top$
3) $(cA)^\top =cA^\top$
4) $det(A)=det(A^\top)$ with its [[determinant]] $A^\top$
5) $A^\top A$ is [[definite quadratic form|positive-semidefinite]]
6) $\left(A^\top\right)^{-1}=\left(A^{-1}\right)^{\top}$ 

Tags: mathematics linear_algebra
END


START
Basic
matrix
- definition
- induced map 
Back: 
### [[matrix]]
$$
\begin{split}
A  \in \mathbb{R}^{n  \times m}
&= \left(a_{i,j} \right)_{i \in [n], j \in [m]} \\
&= \left(A_{(*:j)} \right)_{j \in [m]}
= 
\begin{pmatrix}   A_{(*:1)} &   ... & A_{(*:m}   \end{pmatrix}\\
&= \left(A_{(i:*)} \right)_{i \in [n]}
=  
\begin{pmatrix}   A_{(1:*)} \\   ... \\ A_{(n:*)}   \end{pmatrix}
\end{split}
$$

### induced [[linear function]]
A matrix $A\in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}$ represents a [[unique]] linear [[function]] $F(x)$ that maps the $\mathbb{R}^{\left| \mathcal{J} \right|}$ to its [[column space]] $Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$

$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$
_________________
#### function
- a [[function]] $f$ is map of elements from one [[set]] $A$ to the elements of another [[set]] $B$ such that all elements of $A$ are mapped to exactly one element from $B$
- the [[set]] $A$ is called the **domain** and the [[set]] $B$ is called the **co-domain**
- formal a [[function]] is a [[relation]] from one [[set]] to another [[set]] that satisfies the following two conditions:
$$
\begin{split}
&f: A \rightarrow B \\
\Rightarrow& R_f= \{(x, y): x \in A: f(x) = y\} = graph(f)\\
&\forall a \in A: \exists b \in B: (a, b) \in R_f \\
&(a, b) \in R_f \land  (a, c) \in R_f \Rightarrow b = c\\
\end{split}
$$
Tags: mathematics linear_algebra
<!--ID: 1665308790802-->
END