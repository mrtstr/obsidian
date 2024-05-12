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