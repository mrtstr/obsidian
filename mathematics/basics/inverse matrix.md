### [[inverse function|inverse]] [[matrix]] $A^{-1}$
- exist for [[regular matrix]] (for a general [[matrix]] see [[pseudo inverse matrix]])
- the [[inverse matrix]] $A^{-1}$ induces a linear [[function]] $f^{-1}(y)=A^{-1}y$ which is the [[inverse function]] of the linear function induces by $A$ $f(x)=Ax$
- A [[regular matrix]] $A$ [[matrix product|multiplied]] with its inverse $A^{-1}$ is equal to the [[identity matrix]] $I$
$$
AA^{-1} = A^{-1}A = I
$$
### properties
1) $\left(A_1A_2 \: .. \:A_k\right)^{-1}=A_k^{-1}  \: .. \: A_2^{-1} A_1^{-1}$ 
2) $\left(A^{-1}\right)^{-1} = A$ 
3) $\left(A^\top\right)^{-1}=\left(A^{-1}\right)^{\top}$ 
4) $(cA)^{-1}=c^{-1}A^{-1}$
5) $rank(A)=rank(A^{-1})=n$ (same [[rank]])
6) $det(A^{-1}) = det(A)^{-1}$ ([[associative]] with the [[determinant]])

### inverse of a matrix $\in\mathbb{R}^{2\times 2}$ 

$$
\begin{split}
A
&=\left(
\begin{matrix}
a & b \\
c & d \\
\end{matrix}
\right) \\
A^{-1}
&=\frac{1}{\det(A)}\left(
\begin{matrix}
d & -b \\
-c & a \\
\end{matrix}
\right) \\
&=\frac{1}{ad-bc}\left(
\begin{matrix}
d & -b \\
-c & a \\
\end{matrix}
\right)
\end{split}
$$
#### proof
$$
\begin{split}
\left(
\begin{matrix}
a & b \\
c & d \\
\end{matrix}
\right) 
\frac{1}{ad-bc}\left(
\begin{matrix}
d & -b \\
-c & a \\
\end{matrix}
\right)
=\frac{1}{ad-bc}\left(
\begin{matrix}
ad-bc & ab-ab \\
cd-cd & ad-bc \\
\end{matrix}
\right) 
=\left(
\begin{matrix}
1 & 0 \\
0 & 1 \\
\end{matrix}
\right) 
\end{split}
$$
# -------------------
![[inverse function#inverse function]]

![[matrix#Matrix]]
# anki

START
Basic
matrix inverse
- definition
- properties (6)
 
Back: 
### [[inverse function|inverse]] [[matrix]] $A^{-1}$
- exist for [[regular matrix]] (for a general [[matrix]] see [[pseudo inverse matrix]])
- the [[inverse matrix]] $A^{-1}$ induces a linear [[function]] $f^{-1}(y)=A^{-1}y$ which is the [[inverse function]] of the linear function induces by $A$ $f(x)=Ax$
- A [[regular matrix]] $A$ [[matrix product|multiplied]] with its inverse $A^{-1}$ is equal to the [[identity matrix]] $I$
$$
AA^{-1} = A^{-1}A = I
$$
### Properties
1) $\left(A_1A_2 \: .. \:A_k\right)^{-1}=A_k^{-1}  \: .. \: A_2^{-1} A_1^{-1}$ 
2) $\left(A^{-1}\right)^{-1} = A$ 
3) $\left(A^\top\right)^{-1}=\left(A^{-1}\right)^{\top}$ 
4) $(cA)^{-1}=c^{-1}A^{-1}$
5) $rank(A)=rank(A^{-1})=n$ (same [[rank]])
6) $det(A^{-1}) = det(A)^{-1}$ ([[associative]] with the [[determinant]])

------------------------

### inverse function

Given a [[bijective]] [[function]] $f:X \rightarrow Y$ then $f^{-1}:Y \rightarrow X$ is the [[inverse function]] of $f$ if the following condition is true

$$
\begin{split}
\forall x \in X, y \in Y: f^{-1}(y) = x \Leftrightarrow f(x) = y
\end{split}
$$
#### implications

$$
\forall x \in X: f^{-1}\left(f(x)\right) = x
$$
$$
\forall y \in Y: f\left(f^{-1}(y)\right) = y
$$

### matrix
- can be represented by a two-dimensional [[array]]
- is a 2. Order [[tensor]] 
- [[matrix calculus]]
$$
\begin{split}
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} 
&= \left(a_{i,j} \right)_{i \in \mathcal{I}, j \in \mathcal{J}} \\
&= \left(A_{(*:j)} \right)_{j \in \mathcal{J}}
= 
\begin{pmatrix}   A_{(*:1)} &   ... & A_{(*:\left| \mathcal{J} \right|)}   \end{pmatrix}\\
&= \left(A_{(i:*)} \right)_{i \in \mathcal{I}}
=  
\begin{pmatrix}   A_{(1:*)} \\   ... \\ A_{(\left| \mathcal{I} \right|:*)}   \end{pmatrix}
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1665328452050-->
END


START
Basic
[[inverse matrix]] of $A$ (with proof)

$$
A
=\left(
\begin{matrix}
a & b \\
c & d \\
\end{matrix}
\right) \\
$$
 
Back: 
### inverse of a matrix $\in\mathbb{R}^{2\times 2}$ 

$$
\begin{split}
A
&=\left(
\begin{matrix}
a & b \\
c & d \\
\end{matrix}
\right) \\
A^{-1}
&=\frac{1}{\det(A)}\left(
\begin{matrix}
d & -b \\
-c & a \\
\end{matrix}
\right) \\
&=\frac{1}{ad-bc}\left(
\begin{matrix}
d & -b \\
-c & a \\
\end{matrix}
\right)
\end{split}
$$
#### proof

$$
\begin{split}
\left(
\begin{matrix}
a & b \\
c & d \\
\end{matrix}
\right) 
\frac{1}{ad-bc}\left(
\begin{matrix}
d & -b \\
-c & a \\
\end{matrix}
\right)
=\frac{1}{ad-bc}\left(
\begin{matrix}
ad-bc & ab-ab \\
cd-cd & ad-bc \\
\end{matrix}
\right) 
=\left(
\begin{matrix}
1 & 0 \\
0 & 1 \\
\end{matrix}
\right) 
\end{split}
$$

------------------------
### [[inverse function|inverse]] [[matrix]] $A^{-1}$
- exist for [[regular matrix]] (for a general [[matrix]] see [[pseudo inverse matrix]])
- the [[inverse matrix]] $A^{-1}$ induces a linear [[function]] $f^{-1}(y)=A^{-1}y$ which is the [[inverse function]] of the linear function induces by $A$ $f(x)=Ax$
- A [[regular matrix]] $A$ [[matrix product|multiplied]] with its inverse $A^{-1}$ is equal to the [[identity matrix]] $I$
$$
AA^{-1} = A^{-1}A = I
$$
### Properties
1) $\left(A_1A_2 \: .. \:A_k\right)^{-1}=A_k^{-1}  \: .. \: A_2^{-1} A_1^{-1}$ 
2) $\left(A^{-1}\right)^{-1} = A$ 
3) $\left(A^\top\right)^{-1}=\left(A^{-1}\right)^{\top}$ 
4) $(cA)^{-1}=c^{-1}A^{-1}$
5) $rank(A)=rank(A^{-1})=n$ (same [[rank]])
6) $det(A^{-1}) = det(A)^{-1}$ ([[associative]] with the [[determinant]])



### inverse function

Given a [[bijective]] [[function]] $f:X \rightarrow Y$ then $f^{-1}:Y \rightarrow X$ is the [[inverse function]] of $f$ if the following condition is true

$$
\begin{split}
\forall x \in X, y \in Y: f^{-1}(y) = x \Leftrightarrow f(x) = y
\end{split}
$$
#### implications

$$
\forall x \in X: f^{-1}\left(f(x)\right) = x
$$
$$
\forall y \in Y: f\left(f^{-1}(y)\right) = y
$$

### matrix
- can be represented by a two-dimensional [[array]]
- is a 2. Order [[tensor]] 
- [[matrix calculus]]
$$
\begin{split}
A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}} 
&= \left(a_{i,j} \right)_{i \in \mathcal{I}, j \in \mathcal{J}} \\
&= \left(A_{(*:j)} \right)_{j \in \mathcal{J}}
= 
\begin{pmatrix}   A_{(*:1)} &   ... & A_{(*:\left| \mathcal{J} \right|)}   \end{pmatrix}\\
&= \left(A_{(i:*)} \right)_{i \in \mathcal{I}}
=  
\begin{pmatrix}   A_{(1:*)} \\   ... \\ A_{(\left| \mathcal{I} \right|:*)}   \end{pmatrix}
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1721918246266-->
END