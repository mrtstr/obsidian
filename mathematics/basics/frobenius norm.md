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

# ----------------

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