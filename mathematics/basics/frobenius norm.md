### frobenius norm
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- the [[frobenius norm]] $||\cdot||_F$ is defined as follows

$$
||A||_F = \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |a_{ij}|^2}
$$
- the [[frobenius norm]] is not a [[operator norm]] but it is induced by the [[frobenius inner product]] $\langle A, B\rangle_F = trace(A^\top B)$
$$
||A||_F = \sqrt{\langle A, A\rangle_F} = \sqrt{trace(A^\top A)} 
$$
### proof that the [[frobenius norm]] is a [[norm]]
1) [[positive definite]]
$$
\begin{split}
||A||_F &= \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |a_{ij}|^2} = 0 \\
\Leftrightarrow A &= 0
\end{split}
$$
2) absolutely [[homogeneous]]
$$
\begin{split}
||A \cdot \lambda ||_F 
&= \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |\lambda \cdot a_{ij}|^2} = 0 \\
&= |\lambda| \cdot \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} | a_{ij}|^2} = 0 \\
&= |\lambda| \cdot ||A ||_F \\
\end{split}
$$
3) [[triangle inequality]]
$$
\begin{split}
||A + B||_F^2 \leq& \left(||A||_F + ||B||_F\right)^2 \\
\langle A + B, A + B\rangle_F \leq& ||A||_F^2 + ||B||_F^2 + 2||A||_F||B||_F \\
\langle A , A\rangle_F + \langle B, B\rangle_F + \langle A ,  B\rangle_F \leq& ||A||_F^2 + ||B||_F^2 + 2||A||_F||B||_F \\
\langle A ,  B\rangle_F \leq&  ||A||_F||B||_F \qquad \text{(cauchy schwarz)} \\
\end{split}
$$

### [[frobenius norm]] of the [[identity matrix]]
- given $I_n  \in \mathbb{R}^{n\times n}$

$$
||I_n||_F = \sqrt{n}
$$

$$
\begin{split}
||I_n||_F
&= \sqrt{\langle I_n, I_n \rangle} \\
&= \sqrt{trace(I_n^\top I_n)} \\
&= \sqrt{trace(I_n)} \\
&= \sqrt{n} \\
\end{split}
$$

### [[frobenius norm]] of a [[orthogonal matrix]]
- given the [[orthogonal matrix]] $Q  \in \mathbb{R}^{n\times m}$

$$
||Q|_F = \sqrt{n}
$$

$$
\begin{split}
||Q||_F
&= \sqrt{\langle Q, Q \rangle} \\
&= \sqrt{trace(Q^\top Q)} \\
&= \sqrt{trace(I_n)} \\
&= \sqrt{m} \\
\end{split}
$$

### multiplication with a [[orthogonal matrix]] is neutral for the [[frobenius norm]] 
- given the [[matrix]] $A \in \mathbb{R}^{n \times m}$ and the [[orthogonal matrix]] $Q_n  \in \mathbb{R}^{n\times n}$ and $Q_m  \in \mathbb{R}^{m\times m}$


$$
||A|_F = ||Q_1 A|_F = || AQ_2|_F  = || Q_1AQ_2|_F
$$
$$
\begin{split}
||Q_n A|_F
&= \sqrt{\langle Q_n A, Q_n A \rangle} \\
&= \sqrt{trace\left((Q_n A)^\top Q_n A\right)} \\
&= \sqrt{trace\left( A^\top Q_n^\top Q_n A\right)} \\
&= \sqrt{trace\left( A^\top  A\right)} \\
&= \sqrt{\langle  A,  A \rangle} \\
&= ||A|_F \\
\end{split}
$$

$$
\begin{split}
|| AQ_m||_F
&= || (AQ_m)^\top||_F \\
&= || Q_m^\top A^\top||_F \\
&= \sqrt{\langle Q_m^\top A^\top, Q_m^\top A^\top\rangle} \\
&= \sqrt{trace\left((Q_m^\top A^\top)^\top Q_m^\top A^\top\right)} \\
&= \sqrt{trace\left(  A Q_m Q_m^\top A^\top\right)} \\
&= \sqrt{trace\left( A  A^\top\right)} \\
&= \sqrt{\langle  A^\top,  A^\top \rangle} \\
&= ||A^\top||_F \\
&= ||A|_F \\
\end{split}
$$

### frobenius norm and euclidian norm
- given a [[matrix]] $A\in \mathbb{R}^{n \times m}$
- the sqared [[frobenius norm]] can be expressed as the sum of the [[norm#euclidian norm ($l 2$)|euclidian norms]] of the column or row vectors auf $A$

$$
||A||_F^2 = \sum_{j \in [m]} ||A_{(*,j)}||_2^2 = \sum_{i \in [n]} ||A_{(i,*)}||_2^2
$$
![[norm#euclidian norm ($l 2$)|euclidian norm]]

### frobenius norm and the spectral norm
- given a [[matrix]] $A\in \mathbb{R}^{n \times m}$
- the [[frobenius norm]] of $||A||_F$ is greater or equal than the [[spectral norm]] $||A||_{2\to2}=||A||_{2}$ 

$$
||A||_F \geq ||A||_2 
$$
#### proof
$$
\begin{split}
||Ax||_2^2
\geq ||A||_2 \\
\Leftrightarrow&||A||_F^2 \geq ||A||_2^2 \\
\end{split}
$$
![[spectral norm#spectral norm]]

# ----------------


![[cauchy schwarz inequality#cauchy schwarz inequality]]

![[frobenius inner product#frobenius inner product]]

![[norm#norm]]

![[inner product#inner product]]


# anki

START
Basic
[[matrix norm]] induced by an [[inner product]]
 
Back: 
### frobenius norm
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- the [[frobenius norm]] $||\cdot||_F$ is defined as follows

$$
||A||_F = \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |a_{ij}|^2}
$$
- the [[frobenius norm]] is not a [[operator norm]] but it is induced by the [[frobenius inner product]] $\langle A, B\rangle_F = trace(A^\top B)$
$$
||A||_F = \sqrt{\langle A, A\rangle_F} = \sqrt{trace(A^\top A)} 
$$
### frobenius inner product
- given [[matrix]] $A, B \in \mathbb{R}^{n \times m}$
- the [[frobenius inner product]] is defined as follows
$$
\langle A, B\rangle_F = \sum_{i \in [n]} \sum_{j \in [m]} a_{ij} b_{ij} 
$$
- the [[frobenius inner product]] can be expressed as the [[trace]] of the [[matrix product]]
$$
\langle A, B\rangle_F = \mathrm{trace}\left(A^\top B\right) = \mathrm{trace}\left(A B^\top\right)
$$
- the [[frobenius inner product]] induces the [[frobenius norm]]


Tags: mathematics linear_algebra
<!--ID: 1715458120896-->
END



START
Basic
proof that the [[frobenius norm]] is a [[norm]]
 
Back: 

### proof that the [[frobenius norm]] is a [[norm]]
1) [[positive definite]]
$$
\begin{split}
||A||_F &= \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |a_{ij}|^2} = 0 \\
\Leftrightarrow A &= 0
\end{split}
$$
2) absolutely [[homogeneous]]
$$
\begin{split}
||A \cdot \lambda ||_F 
&= \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |\lambda \cdot a_{ij}|^2} = 0 \\
&= |\lambda| \cdot \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} | a_{ij}|^2} = 0 \\
&= |\lambda| \cdot ||A ||_F \\
\end{split}
$$
3) [[triangle inequality]]
$$
\begin{split}
||A + B||_F^2 \leq& \left(||A||_F + ||B||_F\right)^2 \\
\langle A + B, A + B\rangle_F \leq& ||A||_F^2 + ||B||_F^2 + 2||A||_F||B||_F \\
\langle A , A\rangle_F + \langle B, B\rangle_F + \langle A ,  B\rangle_F \leq& ||A||_F^2 + ||B||_F^2 + 2||A||_F||B||_F \\
\langle A ,  B\rangle_F \leq&  ||A||_F||B||_F \qquad \text{(cauchy schwarz)} \\
\end{split}
$$


### frobenius norm
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- the [[frobenius norm]] $||\cdot||_F$ is defined as follows

$$
||A||_F = \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |a_{ij}|^2}
$$
- the [[frobenius norm]] is not a [[operator norm]] but it is induced by the [[frobenius inner product]] $\langle A, B\rangle_F = trace(A^\top B)$
$$
||A||_F = \sqrt{\langle A, A\rangle_F} = \sqrt{trace(A^\top A)} 
$$
_________________________

### norm
- generalization of the concept of **length of a [[vector]]**
- let $V$ be a [[vector space]]
- the [[function]] $||\:.||: V \rightarrow \mathbb{R^+}$ is a [[norm]] is it satisfies the following conditions
1) [[positive definite]]
$$
||x||=0 \Leftrightarrow x = 0
$$

2) absolutely [[homogeneous]]
$$
\forall x \in V, \lambda \in \mathbb{K}: ||\lambda \cdot x|| = |\lambda| \cdot ||x||
$$
3) [[triangle inequality]]
$$
\forall v, w \in V: ||v + w|| \leq ||v|| + ||w||
$$


### frobenius inner product
- given [[matrix]] $A, B \in \mathbb{R}^{n \times m}$
- the [[frobenius inner product]] is defined as follows
$$
\langle A, B\rangle_F = \sum_{i \in [n]} \sum_{j \in [m]} a_{ij} b_{ij} 
$$
- the [[frobenius inner product]] can be expressed as the [[trace]] of the [[matrix product]]
$$
\langle A, B\rangle_F = \mathrm{trace}\left(A^\top B\right) = \mathrm{trace}\left(A B^\top\right)
$$
- the [[frobenius inner product]] induces the [[frobenius norm]]

### cauchy schwarz inequality
- let $V$ be a [[vector space]] with an [[inner product]] $\langle \cdot , \cdot \rangle$ 
- then the following is true for all $x, y \in V$

$$
|\langle x , y \rangle|^2 \leq \langle x , x \rangle \cdot \langle y , y \rangle
$$
eqivalent:
$$
|\langle x , y \rangle| \leq || x || \cdot || y ||
$$
#### proof
$$
\begin{split}
0 &\leq \left\langle \frac{x}{||x||} - \frac{y}{||y||} , \frac{x}{||x||} - \frac{y}{||y||}  \right\rangle \quad \text{(positive definit)} \\
0 &\leq   \frac{\left\langle x,x\right\rangle}{||x||^2} + \frac{\left\langle y,y\right\rangle}{||y||^2} - 2 \frac{\left\langle x,y\right\rangle}{||x|| \cdot ||y||} \\
0 &\leq   \frac{\left\langle x,x\right\rangle}{\sqrt{\langle x, x \rangle}^2} + \frac{\left\langle y,y\right\rangle}{\sqrt{\langle y, y \rangle}^2} - 2 \frac{\left\langle x,y\right\rangle}{||x|| \cdot ||y||} \\ 
0 &\leq   2 - 2 \frac{\left\langle x,y\right\rangle}{||x|| \cdot ||y||} \\ 
0 &\leq   ||x|| \cdot ||y|| -  \left\langle x,y\right\rangle \\ 
\left\langle x,y\right\rangle &\leq   ||x|| \cdot ||y||  \\ 
\end{split}
$$


Tags: mathematics linear_algebra
<!--ID: 1715530896393-->
END


START
Basic
[[frobenius norm]] of the [[identity matrix]] (proof)
Back: 
### [[frobenius norm]] of the [[identity matrix]]
- given $I_n  \in \mathbb{R}^{n\times n}$

$$
||I_n||_F = \sqrt{n}
$$

$$
\begin{split}
||I_n||_F
&= \sqrt{\langle I_n, I_n \rangle} \\
&= \sqrt{trace(I_n^\top I_n)} \\
&= \sqrt{trace(I_n)} \\
&= \sqrt{\min\{n, m\}} \\
\end{split}
$$


_________________________

### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$

### frobenius norm
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- the [[frobenius norm]] $||\cdot||_F$ is defined as follows

$$
||A||_F = \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |a_{ij}|^2}
$$
- the [[frobenius norm]] is not a [[operator norm]] but it is induced by the [[frobenius inner product]] $\langle A, B\rangle_F = trace(A^\top B)$
$$
||A||_F = \sqrt{\langle A, A\rangle_F} = \sqrt{trace(A^\top A)} 
$$

### norm
- generalization of the concept of **length of a [[vector]]**
- let $V$ be a [[vector space]]
- the [[function]] $||\:.||: V \rightarrow \mathbb{R^+}$ is a [[norm]] is it satisfies the following conditions
1) [[positive definite]]
$$
||x||=0 \Leftrightarrow x = 0
$$

2) absolutely [[homogeneous]]
$$
\forall x \in V, \lambda \in \mathbb{K}: ||\lambda \cdot x|| = |\lambda| \cdot ||x||
$$
3) [[triangle inequality]]
$$
\forall v, w \in V: ||v + w|| \leq ||v|| + ||w||
$$


### frobenius inner product
- given [[matrix]] $A, B \in \mathbb{R}^{n \times m}$
- the [[frobenius inner product]] is defined as follows
$$
\langle A, B\rangle_F = \sum_{i \in [n]} \sum_{j \in [m]} a_{ij} b_{ij} 
$$
- the [[frobenius inner product]] can be expressed as the [[trace]] of the [[matrix product]]
$$
\langle A, B\rangle_F = \mathrm{trace}\left(A^\top B\right) = \mathrm{trace}\left(A B^\top\right)
$$
- the [[frobenius inner product]] induces the [[frobenius norm]]


Tags: mathematics linear_algebra
<!--ID: 1722180274146-->
END




START
Basic
[[frobenius norm]] of a [[orthogonal matrix]] $Q  \in \mathbb{R}^{n\times m}$ (proof)
Back: 
### [[frobenius norm]] of a [[orthogonal matrix]]
- given the [[orthogonal matrix]] $Q  \in \mathbb{R}^{n\times m}$

$$
||Q|_F = \sqrt{n}
$$

$$
\begin{split}
||Q||_F
&= \sqrt{\langle Q, Q \rangle} \\
&= \sqrt{trace(Q^\top Q)} \\
&= \sqrt{trace(I_n)} \\
&= \sqrt{m} \\
\end{split}
$$

_________________________

### [[frobenius norm]] of the [[identity matrix]]
- given $I_n  \in \mathbb{R}^{n\times n}$

$$
||I_n||_F = \sqrt{n}
$$

$$
\begin{split}
||I_n||_F
&= \sqrt{\langle I_n, I_n \rangle} \\
&= \sqrt{trace(I_n^\top I_n)} \\
&= \sqrt{trace(I_n)} \\
&= \sqrt{\min\{n, m\}} \\
\end{split}
$$



### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$

### frobenius norm
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- the [[frobenius norm]] $||\cdot||_F$ is defined as follows

$$
||A||_F = \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |a_{ij}|^2}
$$
- the [[frobenius norm]] is not a [[operator norm]] but it is induced by the [[frobenius inner product]] $\langle A, B\rangle_F = trace(A^\top B)$
$$
||A||_F = \sqrt{\langle A, A\rangle_F} = \sqrt{trace(A^\top A)} 
$$

### norm
- generalization of the concept of **length of a [[vector]]**
- let $V$ be a [[vector space]]
- the [[function]] $||\:.||: V \rightarrow \mathbb{R^+}$ is a [[norm]] is it satisfies the following conditions
1) [[positive definite]]
$$
||x||=0 \Leftrightarrow x = 0
$$

2) absolutely [[homogeneous]]
$$
\forall x \in V, \lambda \in \mathbb{K}: ||\lambda \cdot x|| = |\lambda| \cdot ||x||
$$
3) [[triangle inequality]]
$$
\forall v, w \in V: ||v + w|| \leq ||v|| + ||w||
$$


### frobenius inner product
- given [[matrix]] $A, B \in \mathbb{R}^{n \times m}$
- the [[frobenius inner product]] is defined as follows
$$
\langle A, B\rangle_F = \sum_{i \in [n]} \sum_{j \in [m]} a_{ij} b_{ij} 
$$
- the [[frobenius inner product]] can be expressed as the [[trace]] of the [[matrix product]]
$$
\langle A, B\rangle_F = \mathrm{trace}\left(A^\top B\right) = \mathrm{trace}\left(A B^\top\right)
$$
- the [[frobenius inner product]] induces the [[frobenius norm]]


Tags: mathematics linear_algebra


<!--ID: 1722180274148-->
END



START
Basic
- given the [[matrix]] $A \in \mathbb{R}^{n \times m}$ and the [[orthogonal matrix]] $Q_n  \in \mathbb{R}^{n\times n}$ and $Q_m  \in \mathbb{R}^{m\times m}$
- how does the [[frobenius norm]] of $||A|_F$ change when multiping with the [[orthogonal matrix]] ($||A|_F$ $, ||Q_1 A|_F$, $|| AQ_2|_F$, $|| Q_1AQ_2|_F$) (proof)
Back: 

### multiplication with a [[orthogonal matrix]] is neutral for the [[frobenius norm]] 
- given the [[matrix]] $A \in \mathbb{R}^{n \times m}$ and the [[orthogonal matrix]] $Q_n  \in \mathbb{R}^{n\times n}$ and $Q_m  \in \mathbb{R}^{m\times m}$


$$
||A|_F = ||Q_1 A|_F = || AQ_2|_F  = || Q_1AQ_2|_F
$$
$$
\begin{split}
||Q_n A|_F
&= \sqrt{\langle Q_n A, Q_n A \rangle} \\
&= \sqrt{trace\left((Q_n A)^\top Q_n A\right)} \\
&= \sqrt{trace\left( A^\top Q_n^\top Q_n A\right)} \\
&= \sqrt{trace\left( A^\top  A\right)} \\
&= \sqrt{\langle  A,  A \rangle} \\
&= ||A|_F \\
\end{split}
$$

$$
\begin{split}
|| AQ_m||_F
&= || (AQ_m)^\top||_F \\
&= || Q_m^\top A^\top||_F \\
&= \sqrt{\langle Q_m^\top A^\top, Q_m^\top A^\top\rangle} \\
&= \sqrt{trace\left((Q_m^\top A^\top)^\top Q_m^\top A^\top\right)} \\
&= \sqrt{trace\left(  A Q_m Q_m^\top A^\top\right)} \\
&= \sqrt{trace\left( A  A^\top\right)} \\
&= \sqrt{\langle  A^\top,  A^\top \rangle} \\
&= ||A^\top||_F \\
&= ||A|_F \\
\end{split}
$$



_________________________

### [[frobenius norm]] of the [[identity matrix]]
- given $I_n  \in \mathbb{R}^{n\times n}$

$$
||I_n||_F = \sqrt{n}
$$

$$
\begin{split}
||I_n||_F
&= \sqrt{\langle I_n, I_n \rangle} \\
&= \sqrt{trace(I_n^\top I_n)} \\
&= \sqrt{trace(I_n)} \\
&= \sqrt{\min\{n, m\}} \\
\end{split}
$$



### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$

### frobenius norm
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- the [[frobenius norm]] $||\cdot||_F$ is defined as follows

$$
||A||_F = \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |a_{ij}|^2}
$$
- the [[frobenius norm]] is not a [[operator norm]] but it is induced by the [[frobenius inner product]] $\langle A, B\rangle_F = trace(A^\top B)$
$$
||A||_F = \sqrt{\langle A, A\rangle_F} = \sqrt{trace(A^\top A)} 
$$

### norm
- generalization of the concept of **length of a [[vector]]**
- let $V$ be a [[vector space]]
- the [[function]] $||\:.||: V \rightarrow \mathbb{R^+}$ is a [[norm]] is it satisfies the following conditions
1) [[positive definite]]
$$
||x||=0 \Leftrightarrow x = 0
$$

2) absolutely [[homogeneous]]
$$
\forall x \in V, \lambda \in \mathbb{K}: ||\lambda \cdot x|| = |\lambda| \cdot ||x||
$$
3) [[triangle inequality]]
$$
\forall v, w \in V: ||v + w|| \leq ||v|| + ||w||
$$


### frobenius inner product
- given [[matrix]] $A, B \in \mathbb{R}^{n \times m}$
- the [[frobenius inner product]] is defined as follows
$$
\langle A, B\rangle_F = \sum_{i \in [n]} \sum_{j \in [m]} a_{ij} b_{ij} 
$$
- the [[frobenius inner product]] can be expressed as the [[trace]] of the [[matrix product]]
$$
\langle A, B\rangle_F = \mathrm{trace}\left(A^\top B\right) = \mathrm{trace}\left(A B^\top\right)
$$
- the [[frobenius inner product]] induces the [[frobenius norm]]

Tags: mathematics linear_algebra
<!--ID: 1722180274151-->
END



START
Basic
- relationship of the [[frobenius norm]] and the [[norm#euclidian norm ($l 2$)|euclidian norm]]
Back: 
### frobenius norm and euclidian norm
- given a [[matrix]] $A\in \mathbb{R}^{n \times m}$
- the sqared [[frobenius norm]] can be expressed as the sum of the [[norm#euclidian norm ($l 2$)|euclidian norms]] of the column or row vectors auf $A$

$$
||A||_F^2 = \sum_{j \in [m]} ||A_{(*,j)}||_2^2 = \sum_{i \in [n]} ||A_{(i,*)}||_2^2
$$

_________________________
#### euclidian [[norm]] ($l^2$)
$$
||x||_2 = \left(\sum_{i \in [n]} |x_i|^2 \right)^{\frac{1}{2}}
$$


### frobenius norm
- given a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- the [[frobenius norm]] $||\cdot||_F$ is defined as follows

$$
||A||_F = \sqrt{\sum_{i \in [n]}\sum_{j \in [m]} |a_{ij}|^2}
$$
- the [[frobenius norm]] is not a [[operator norm]] but it is induced by the [[frobenius inner product]] $\langle A, B\rangle_F = trace(A^\top B)$
$$
||A||_F = \sqrt{\langle A, A\rangle_F} = \sqrt{trace(A^\top A)} 
$$

### norm
- generalization of the concept of **length of a [[vector]]**
- let $V$ be a [[vector space]]
- the [[function]] $||\:.||: V \rightarrow \mathbb{R^+}$ is a [[norm]] is it satisfies the following conditions
1) [[positive definite]]
$$
||x||=0 \Leftrightarrow x = 0
$$

2) absolutely [[homogeneous]]
$$
\forall x \in V, \lambda \in \mathbb{K}: ||\lambda \cdot x|| = |\lambda| \cdot ||x||
$$
3) [[triangle inequality]]
$$
\forall v, w \in V: ||v + w|| \leq ||v|| + ||w||
$$


### frobenius inner product
- given [[matrix]] $A, B \in \mathbb{R}^{n \times m}$
- the [[frobenius inner product]] is defined as follows
$$
\langle A, B\rangle_F = \sum_{i \in [n]} \sum_{j \in [m]} a_{ij} b_{ij} 
$$
- the [[frobenius inner product]] can be expressed as the [[trace]] of the [[matrix product]]
$$
\langle A, B\rangle_F = \mathrm{trace}\left(A^\top B\right) = \mathrm{trace}\left(A B^\top\right)
$$
- the [[frobenius inner product]] induces the [[frobenius norm]]

Tags: mathematics linear_algebra
<!--ID: 1722180274154-->
END