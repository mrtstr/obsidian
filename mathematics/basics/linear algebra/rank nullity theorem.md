# Rank Nullity Theorem
For a [[matrix]] $A$ with the column vectors $A^{(j)}$ and the represented linear function $F$.
$$
A =\left(A^{(j)} \right)_{j \in \mathcal{J}}
= 
\begin{pmatrix}   A^{(1)}    ... & A^{(\left| \mathcal{J} \right|)}  \end{pmatrix}
\in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}
$$
$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$


- The dimensions of the [[column space]] plus the dimensions of the [[nullspace]] are equal to the dimensions of the domain of $F$ 
$$dim(range(A)) + dim(kern(A)) = \left| \mathcal{J} \right|$$
The [[rank]] plus the [[nullity]] is equal to the total number of column vectors
$$
\underbrace{
rank(A)
}_\text{\# linear independent column vectors Aj} 
+
\underbrace{
nullity(A)
}_\text{\# linear dependent column vectors Aj} 
= 
\underbrace{
\left| \mathcal{J} \right|
}_\text{\# all column vectors Aj}
$$
![[Pasted image 20221015081452.png]]

START
Basic
rank nullity theorem two equivalent definitions
Back: 
For a [[matrix]] $A$ with the column vectors $A^{(j)}$ and the represented linear function $F$.
$$
A =\left(A^{(j)} \right)_{j \in \mathcal{J}}
= 
\begin{pmatrix}   A^{(1)}    ... & A^{(\left| \mathcal{J} \right|)}  \end{pmatrix}
\in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}
$$
$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$


- The dimensions of the [[column space]] plus the dimensions of the [[nullspace]] are equal to the dimensions of the domain of $F$ 
$$dim(range(A)) + dim(kern(A)) = \left| \mathcal{J} \right|$$
The [[rank]] plus the [[nullity]] is equal to the total number of column vectors
$$
\underbrace{
rank(A)
}_\text{\# linear independent column vectors Aj} 
+
\underbrace{
nullity(A)
}_\text{\# linear dependent column vectors Aj} 
= 
\underbrace{
\left| \mathcal{J} \right|
}_\text{\# all column vectors Aj}
$$
![[Pasted image 20221015081452.png]]


Tags: mathematics, linear algebra
<!--ID: 1665824261696-->
END