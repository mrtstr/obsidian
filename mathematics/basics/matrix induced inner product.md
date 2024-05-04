### matrix induced inner product
- every [[symmetric matrix|symmetric]] and [[positive definite]] [[matrix]] $A \in \mathbb{R}^{n \times n}$ induces an [[inner product]] $\langle \cdot, \cdot \rangle_A: \mathbb{R}^{n} \times \mathbb{R}^n \rightarrow \mathbb{R}$
$$
\langle x, y \rangle_A = y^\top Ax
$$
1) [[symmetric]]: following from $A$ being [[symmetric]]


$$
\begin{split}
y^\top Ax 
&= \sum_{i \in [n]} \sum_{j \in [n]} y_i A_{(i,j)} x_j \\
&= \sum_{i \in [n]} \sum_{j \in [n]} y_j A_{(i,j)} x_i \\
&= x^\top Ay  \\
\end{split}
$$
2) [[positive definite]]: followns from $A$ being [[positive definite]]
3) [[linear function|linearity]] 
# ------------------
![[inner product#inner product]]

![[symmetric matrix#symmetric matrix]]

![[positive definite#positive definite matrix]]

# anki

START
Basic
[[matrix]] induced [[inner product]]
- with proof
Back: 
### matrix induced inner product
- every [[symmetric matrix|symmetric]] and [[positive definite]] [[matrix]] $A \in \mathbb{R}^{n \times n}$ induces an [[inner product]] $\langle \cdot, \cdot \rangle_A: \mathbb{R}^{n} \times \mathbb{R}^n \rightarrow \mathbb{R}$
$$
\langle x, y \rangle_A = y^\top Ax
$$
1) [[symmetric]]: following from $A$ being [[symmetric]]


$$
\begin{split}
y^\top Ax 
&= \sum_{i \in [n]} \sum_{j \in [n]} y_i A_{(i,j)} x_j \\
&= \sum_{i \in [n]} \sum_{j \in [n]} y_j A_{(i,j)} x_i \\
&= x^\top Ay  \\
\end{split}
$$
2) [[positive definite]]: followns from $A$ being [[positive definite]]
3) [[linear function|linearity]] 

### symmetric matrix
A [[square matrix]] $A  \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{I} \right|}}$ is symmetric when:
1) $A = A^\top$ ($A$ is equal to its [[transpose]])
2) $\forall i,j \in \mathcal{I}: a_{ij} = a_{ji}$
3) $A^{(i)} = A_{(i)}$ (the ith column vector is equal to the ith row vector)


### positive definite [[matrix]]
- a [[matrix]] $A \in \mathbb{R}^{n \times n}$ is [[positive definite]] if the following is true
$$
\forall x \in \mathbb{R}^n \setminus{0}: x^\top A x >0
$$

___________________
### inner product
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear function|linearity]] (regarding both elemements because of the [[symmetric]])

$$
\forall x,y,z \in V, \lambda \in \mathbb{R}:\langle x + \lambda y , z \rangle = \langle x , z  \rangle + \lambda \langle  y , z \rangle
$$
2) [[symmetric]]

$$
\forall x,y \in V: \langle x  , y \rangle = \langle y  , x \rangle
$$
3) [[positive definite]]

$$
\forall x \in V: \langle x  , x \rangle  \leftrightarrow x=0 
$$
$$
\forall x \in V: \langle x  , x \rangle  \geq 0
$$

Tags: mathematics
<!--ID: 1714495264983-->
END