# Nullity
## Definition
![[matrix#Matrix#Matrix Definition]]
For a [[matrix]] $A$ with the column vectors $A^{(j)}$ and the represented linear function $F$.
$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$

- The nullity is equal to the dimensions of the [[nullspace]]
$$
nullity(A) = dim(kern(A))
$$
- the nullity is equal to the number of columns $\left| \mathcal{J} \right|$ minus the [[rank]] (rank = number of [[linear independent]] column vectors $A^{(j)}$) (see [[rank nullity theorem]])
$$
\underbrace{
nullity(A)
}_\text{\# linear dependent column vectors Aj}  = 
\underbrace{
\left| \mathcal{J} \right|
}_\text{\# all column vectors Aj}
-
\underbrace{
rank(A)
}_\text{\# linear independent column vectors Aj}
$$



![[Pasted image 20221015081452.png]]

START
Basic
nullity 
- definitions (3) (verbal +relationship to rank and [[nullspace]])
- verbal explanation
Back: 
# Nullity
## Definition
For a [[matrix]] $A$ with the column vectors $A^{(j)}$ and the represented linear function $F$.
$$
A =\left(A^{(j)} \right)_{j \in \mathcal{J}}
= 
\begin{pmatrix}   A^{(1)}    ... & A^{(\left| \mathcal{J} \right|)}  \end{pmatrix}
\in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}
$$
$$F(x) = Ax: \mathbb{R}^{\left| \mathcal{J} \right|} \mapsto Im(A) = Span\left((A_{(j)})_{i \in \mathcal{I}}\right) \in \mathbb{R}^{\left| \mathcal{I} \right|}$$

- The nullity is equal to the dimensions of the [[nullspace]]
$$
nullity(A) = dim(kern(A))
$$
- the nullity is equal to the number of columns $\left| \mathcal{J} \right|$ minus the [[rank]] (rank = number of [[linear independent]] column vectors $A^{(j)}$) (see [[rank nullity theorem]])
$$
\underbrace{
nullity(A)
}_\text{\# linear dependent column vectors Aj}  = 
\underbrace{
\left| \mathcal{J} \right|
}_\text{\# all column vectors Aj}
-
\underbrace{
rank(A)
}_\text{\# linear independent column vectors Aj}
$$

## Explanation 
In the [[nullspace]] are the vectors in the domain of $F(x)$ that map to zero. Thus, there are linear dependent column vectors $A^{(j)}$ needed for that to be the case. For $x$ to be in the [[nullspace]] the elements $(x)_{j}$ that is multiplied with the linear dependent column vectors $A^{(j)}$ has to be $\neq 0$ and all the other $(x)_{j}$ have to be $=0$. Thus, the dimensions of the [[nullspace]] are equal to the number of linear dependent column vectors $A^{(j)}$ and the [[nullity]]

![[Pasted image 20221015081452.png]]

Tags: mathematics linear_algebra
<!--ID: 1665824261692-->
END