### quadratic forms of random variables
- give a [[symmetric]] non-random [[matrix]] $A$ and B and a [[random vector]] $X$
- let $\Sigma = \mathbb{VAR}[X]$ and $\mathrm{m}=\mathbb{E}[X]$

____________

$$
\begin{split}
\mathbb{E}\left[X^\top A X\right] 
&= \mathrm{TR}\left(A\Sigma\right) + \mathrm{m}^\top A \mathrm{m}
\end{split}
$$


$$
\begin{split}
X^\top A X
&= \left(X + \mathrm{m} - \mathrm{m} \right)^\top A \left(X + \mathrm{m} - \mathrm{m} \right) \\
&= \left(X  - \mathrm{m} \right)^\top A \left(X - \mathrm{m} \right) + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left(\left(X  - \mathrm{m} \right)^\top A \left(X - \mathrm{m} \right)\right) + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left( A \left(X - \mathrm{m} \right) \left(X  - \mathrm{m} \right)^\top\right) + \mathrm{m}^\top A \mathrm{m} \\
\mathbb{E}\left[X^\top A X\right]
&= \mathbb{E}\left[\mathrm{TR}\left( A \left(X - \mathrm{m} \right) \left(X  - \mathrm{m} \right)^\top\right)\right] + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left( A \mathbb{E}\left[\left(X - \mathrm{m} \right) \left(X  - \mathrm{m} \right)^\top\right]\right) + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left(A\Sigma\right) + \mathrm{m}^\top A \mathrm{m} \\
\end{split}
$$


_________

$$
\begin{split}
\mathbb{E}\left[X  X^\top\right] 
&= \Sigma + \mathrm{m}\mathrm{m}^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[X  X^\top\right] 
&= \mathbb{E}\left[\left(X + \mathrm{m} - \mathrm{m} \right)  \left(X + \mathrm{m} - \mathrm{m} \right)^\top\right]  \\
&= \mathbb{E}\left[\left(X  - \mathrm{m} \right)  \left(X  - \mathrm{m} \right)^\top\right] + \mathrm{m}\mathrm{m}^\top \\
&= \Sigma + \mathrm{m}\mathrm{m}^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[X^\top  X \right] 
&= \mathrm{TR}\left(\Sigma \right) + \mathrm{m}\mathrm{m}^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[X^\top  X \right] 
&=\mathbb{E}\left[||X||^2 \right]  \\
&=\mathbb{E}\left[||(X- \mathrm{m}) + \mathrm{m}||^2 \right]  \\
&=\mathbb{E}\left[||(X- \mathrm{m})||^2 + ||\mathrm{m}||^2  + 2\langle X- \mathrm{m}, m  \rangle \right] \\
&=\mathbb{E}\left[||(X- \mathrm{m})||^2\right] + ||\mathrm{m}||^2  + 2\langle \mathbb{E}\left[X- \mathrm{m}\right], m  \rangle  \\
&=\mathbb{E}\left[||(X- \mathrm{m})||^2\right] + ||\mathrm{m}||^2   \\
&= \mathrm{TR}\left(\Sigma \right) + \mathrm{m}\mathrm{m}^\top \\
\end{split}
$$


_________

$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)\left(BX+ \mathrm{b}\right)^\top \right] 
&= A\Sigma B^\top + \left(A\mathrm{m} + \mathrm{a}\right)\left(B\mathrm{m}+ \mathrm{b}\right)^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)\left(BX+ \mathrm{b}\right)^\top \right] 
&= \mathbb{E}\left[\left(A\left(X+ \mathrm{m} - \mathrm{m}\right) + \mathrm{a}\right)\left(B\left(X+ \mathrm{m} - \mathrm{m}\right)^\top + \mathrm{b}^\top\right) \right]  \\
&= \mathbb{E}\left[\left(A\left(X  - \mathrm{m}\right) + \left(A \mathrm{m} +\mathrm{a} \right)\right)\left(\left(X  - \mathrm{m}\right)^\top B^\top + \left(B \mathrm{m} +\mathrm{b} \right)^\top\right) \right]  \\
&= A\mathbb{E}\left[\left(X  - \mathrm{m}\right)\left(X  - \mathrm{m}\right)^\top \right]B^\top  + \left(A\mathrm{m} + \mathrm{a}\right)\left(B\mathrm{m}+ \mathrm{b}\right)^\top \\
& + A\mathbb{E}\left[X  - \mathrm{m}\right]\left(B \mathrm{m} +\mathrm{b} \right)^\top + \left(A \mathrm{m} +\mathrm{a} \right)B\mathbb{E}\left[X  - \mathrm{m}\right]^\top    \\
&= A\Sigma B^\top + \left(A\mathrm{m} + \mathrm{a}\right)\left(B\mathrm{m}+ \mathrm{b}\right)^\top \\
\end{split}
$$


$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)^\top\left(BX+ \mathrm{b}\right) \right] 
&= \mathrm{TR}\left(A\Sigma B^\top \right) + \left(A\mathrm{m} + \mathrm{a}\right)^\top\left(B\mathrm{m}+ \mathrm{b}\right) \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)^\top\left(BX+ \mathrm{b}\right) \right] 
&= \mathbb{E}\left[\left\langle A\left(X - \mathrm{m} + \mathrm{m}\right) + \mathrm{a}, B\left(X - \mathrm{m} + \mathrm{m}\right) + \mathrm{b}\right\rangle \right]  \\
&= \mathbb{E}\left[\left\langle A\left(X - \mathrm{m} \right) + (A\mathrm{m}+\mathrm{a}), B\left(X - \mathrm{m} \right) + (B\mathrm{m}+\mathrm{b})\right\rangle \right]  \\
&= \mathbb{E}\left[\left\langle A\left(X - \mathrm{m} \right) , B\left(X - \mathrm{m} \right)\right\rangle \right] + \left\langle A\mathrm{m}+\mathrm{a},  B\mathrm{m}+\mathrm{b}\right\rangle + 0 + 0  \\
&= \mathrm{TR}\left(B \mathbb{E}\left[\left(X - \mathrm{m} \right)\left(X - \mathrm{m} \right)^\top\right] A^\top  \right)  + \left\langle A\mathrm{m}+\mathrm{a},  B\mathrm{m}+\mathrm{b}\right\rangle  \\
&= \mathrm{TR}\left(B \Sigma A^\top  \right)  + \left\langle A\mathrm{m}+\mathrm{a},  B\mathrm{m}+\mathrm{b}\right\rangle  \\
&= \mathrm{TR}\left(A\Sigma B^\top \right) + \left(A\mathrm{m} + \mathrm{a}\right)^\top\left(B\mathrm{m}+ \mathrm{b}\right) \\
\end{split}
$$

# ----------

![[trace#trace]]


![[covariance matrix#covariance matrix]]

![[inner product#inner product]]

![[inner products and norms#every inner product induces a norm]]

# anki

START
Basic
### quadratic forms of random variables
- give a [[symmetric]] non-random [[matrix]] $A$ and B and a [[random vector]] $X$
- let $\Sigma = \mathbb{VAR}[X]$ and $\mathrm{m}=\mathbb{E}[X]$

calculate $\mathbb{E}\left[X^\top A X\right]$

Back: 


$$
\begin{split}
\mathbb{E}\left[X^\top A X\right] 
&= \mathrm{TR}\left(A\Sigma\right) + \mathrm{m}^\top A \mathrm{m}
\end{split}
$$


$$
\begin{split}
X^\top A X
&= \left(X + \mathrm{m} - \mathrm{m} \right)^\top A \left(X + \mathrm{m} - \mathrm{m} \right) \\
&= \left(X  - \mathrm{m} \right)^\top A \left(X - \mathrm{m} \right) + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left(\left(X  - \mathrm{m} \right)^\top A \left(X - \mathrm{m} \right)\right) + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left( A \left(X - \mathrm{m} \right) \left(X  - \mathrm{m} \right)^\top\right) + \mathrm{m}^\top A \mathrm{m} \\
\mathbb{E}\left[X^\top A X\right]
&= \mathbb{E}\left[\mathrm{TR}\left( A \left(X - \mathrm{m} \right) \left(X  - \mathrm{m} \right)^\top\right)\right] + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left( A \mathbb{E}\left[\left(X - \mathrm{m} \right) \left(X  - \mathrm{m} \right)^\top\right]\right) + \mathrm{m}^\top A \mathrm{m} \\
&= \mathrm{TR}\left(A\Sigma\right) + \mathrm{m}^\top A \mathrm{m} \\
\end{split}
$$


________________

### covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- the cross [[covariance matrix]] $K_{XY} = \mathbb{COV}[X, Y] \in \mathbb{R}^{n\times m}$ of $X$ and $Y$ is defined as follows

$$
\begin{split}
K_{XY} 
&= \mathbb{COV}[X, Y]\\
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \left( \mathbb{E}\left[\left( X -\mathbb{E}[X_i]\right) \left( Y -\mathbb{E}[Y_j]\right)^\top\right]\right)_{i,j \in [n]} \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

- the [[covariance matrix]] of one [[random variable]] is the cross [[covariance matrix]] with itself

$$
\begin{split}
\mathbb{VAR}[X]
&= K_{XX}   \\
\end{split}
$$
#### base properties

- $K_{XX}$ is [[symmetric]]
- $K_{XX}$ is [[positive definite]]

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= A\mathbb{VAR}[X]A^\top \\
\mathbb{COV}[AX + a, BY + b]
&= A\mathbb{COV}[X,Y]B^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$

##### trace of a matrix product
- for $A, B \in \mathbb{R}^{n \times n}$ 
$$
\mathrm{trace}(AB) = \mathrm{trace}(BA)
$$

$$
\begin{split}
\mathrm{trace}(AB) 
&=\sum_{i \in [n]} \sum_{k \in [n]} a_{i,k} b_{k,i} \\
&=\sum_{k \in [n]} \sum_{i \in [n]} b_{k,i} a_{i,k} \\
&= \mathrm{trace}(BA)\\
\end{split}
$$

### inner product
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear map|linearity]] (regarding both elemements because of the [[symmetric]])

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
### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$


Tags: mathematics statistics SS25
<!--ID: 1746974641777-->
END


START
Basic
### quadratic forms of random variables
- give a [[symmetric]] non-random [[matrix]] $A$ and B and a [[random vector]] $X$
- let $\Sigma = \mathbb{VAR}[X]$ and $\mathrm{m}=\mathbb{E}[X]$

- calculate $\mathbb{E}\left[X  X^\top\right]$ and $\mathbb{E}\left[X^\top  X\right]$

Back: 



$$
\begin{split}
\mathbb{E}\left[X  X^\top\right] 
&= \Sigma + \mathrm{m}\mathrm{m}^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[X  X^\top\right] 
&= \mathbb{E}\left[\left(X + \mathrm{m} - \mathrm{m} \right)  \left(X + \mathrm{m} - \mathrm{m} \right)^\top\right]  \\
&= \mathbb{E}\left[\left(X  - \mathrm{m} \right)  \left(X  - \mathrm{m} \right)^\top\right] + \mathrm{m}\mathrm{m}^\top \\
&= \Sigma + \mathrm{m}\mathrm{m}^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[X^\top  X \right] 
&= \mathrm{TR}\left(\Sigma \right) + \mathrm{m}\mathrm{m}^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[X^\top  X \right] 
&=\mathbb{E}\left[||X||^2 \right]  \\
&=\mathbb{E}\left[||(X- \mathrm{m}) + \mathrm{m}||^2 \right]  \\
&=\mathbb{E}\left[||(X- \mathrm{m})||^2 + ||\mathrm{m}||^2  + 2\langle X- \mathrm{m}, m  \rangle \right] \\
&=\mathbb{E}\left[||(X- \mathrm{m})||^2\right] + ||\mathrm{m}||^2  + 2\langle \mathbb{E}\left[X- \mathrm{m}\right], m  \rangle  \\
&=\mathbb{E}\left[||(X- \mathrm{m})||^2\right] + ||\mathrm{m}||^2   \\
&= \mathrm{TR}\left(\Sigma \right) + \mathrm{m}\mathrm{m}^\top \\
\end{split}
$$



________________

### covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- the cross [[covariance matrix]] $K_{XY} = \mathbb{COV}[X, Y] \in \mathbb{R}^{n\times m}$ of $X$ and $Y$ is defined as follows

$$
\begin{split}
K_{XY} 
&= \mathbb{COV}[X, Y]\\
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \left( \mathbb{E}\left[\left( X -\mathbb{E}[X_i]\right) \left( Y -\mathbb{E}[Y_j]\right)^\top\right]\right)_{i,j \in [n]} \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

- the [[covariance matrix]] of one [[random variable]] is the cross [[covariance matrix]] with itself

$$
\begin{split}
\mathbb{VAR}[X]
&= K_{XX}   \\
\end{split}
$$
#### base properties

- $K_{XX}$ is [[symmetric]]
- $K_{XX}$ is [[positive definite]]

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= A\mathbb{VAR}[X]A^\top \\
\mathbb{COV}[AX + a, BY + b]
&= A\mathbb{COV}[X,Y]B^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$

##### trace of a matrix product
- for $A, B \in \mathbb{R}^{n \times n}$ 
$$
\mathrm{trace}(AB) = \mathrm{trace}(BA)
$$

$$
\begin{split}
\mathrm{trace}(AB) 
&=\sum_{i \in [n]} \sum_{k \in [n]} a_{i,k} b_{k,i} \\
&=\sum_{k \in [n]} \sum_{i \in [n]} b_{k,i} a_{i,k} \\
&= \mathrm{trace}(BA)\\
\end{split}
$$

### inner product
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear map|linearity]] (regarding both elemements because of the [[symmetric]])

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
### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$


Tags: mathematics statistics SS25
<!--ID: 1746974641781-->
END


START
Basic
### quadratic forms of random variables
- give a [[symmetric]] non-random [[matrix]] $A$ and B and a [[random vector]] $X$
- let $\Sigma = \mathbb{VAR}[X]$ and $\mathrm{m}=\mathbb{E}[X]$


- calculate $\mathbb{E}\left[\left(AX + \mathrm{a}\right)\left(BX+ \mathrm{b}\right)^\top \right]$
- how does $\mathbb{E}\left[\left(AX + \mathrm{a}\right)^\top\left(BX+ \mathrm{b}\right) \right]$ look like? (no proof)
Back: 



_________

$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)\left(BX+ \mathrm{b}\right)^\top \right] 
&= A\Sigma B^\top + \left(A\mathrm{m} + \mathrm{a}\right)\left(B\mathrm{m}+ \mathrm{b}\right)^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)\left(BX+ \mathrm{b}\right)^\top \right] 
&= \mathbb{E}\left[\left(A\left(X+ \mathrm{m} - \mathrm{m}\right) + \mathrm{a}\right)\left(B\left(X+ \mathrm{m} - \mathrm{m}\right)^\top + \mathrm{b}^\top\right) \right]  \\
&= \mathbb{E}\left[\left(A\left(X  - \mathrm{m}\right) + \left(A \mathrm{m} +\mathrm{a} \right)\right)\left(\left(X  - \mathrm{m}\right)^\top B^\top + \left(B \mathrm{m} +\mathrm{b} \right)^\top\right) \right]  \\
&= A\mathbb{E}\left[\left(X  - \mathrm{m}\right)\left(X  - \mathrm{m}\right)^\top \right]B^\top  + \left(A\mathrm{m} + \mathrm{a}\right)\left(B\mathrm{m}+ \mathrm{b}\right)^\top \\
& + A\mathbb{E}\left[X  - \mathrm{m}\right]\left(B \mathrm{m} +\mathrm{b} \right)^\top + \left(A \mathrm{m} +\mathrm{a} \right)B\mathbb{E}\left[X  - \mathrm{m}\right]^\top    \\
&= A\Sigma B^\top + \left(A\mathrm{m} + \mathrm{a}\right)\left(B\mathrm{m}+ \mathrm{b}\right)^\top \\
\end{split}
$$


$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)^\top\left(BX+ \mathrm{b}\right) \right] 
&= \mathrm{TR}\left(A\Sigma B^\top \right) + \left(A\mathrm{m} + \mathrm{a}\right)^\top\left(B\mathrm{m}+ \mathrm{b}\right) \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)^\top\left(BX+ \mathrm{b}\right) \right] 
&= \mathbb{E}\left[\left\langle A\left(X - \mathrm{m} + \mathrm{m}\right) + \mathrm{a}, B\left(X - \mathrm{m} + \mathrm{m}\right) + \mathrm{b}\right\rangle \right]  \\
&= \mathbb{E}\left[\left\langle A\left(X - \mathrm{m} \right) + (A\mathrm{m}+\mathrm{a}), B\left(X - \mathrm{m} \right) + (B\mathrm{m}+\mathrm{b})\right\rangle \right]  \\
&= \mathbb{E}\left[\left\langle A\left(X - \mathrm{m} \right) , B\left(X - \mathrm{m} \right)\right\rangle \right] + \left\langle A\mathrm{m}+\mathrm{a},  B\mathrm{m}+\mathrm{b}\right\rangle + 0 + 0  \\
&= \mathrm{TR}\left(B \mathbb{E}\left[\left(X - \mathrm{m} \right)\left(X - \mathrm{m} \right)^\top\right] A^\top  \right)  + \left\langle A\mathrm{m}+\mathrm{a},  B\mathrm{m}+\mathrm{b}\right\rangle  \\
&= \mathrm{TR}\left(B \Sigma A^\top  \right)  + \left\langle A\mathrm{m}+\mathrm{a},  B\mathrm{m}+\mathrm{b}\right\rangle  \\
&= \mathrm{TR}\left(A\Sigma B^\top \right) + \left(A\mathrm{m} + \mathrm{a}\right)^\top\left(B\mathrm{m}+ \mathrm{b}\right) \\
\end{split}
$$


________________

### covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- the cross [[covariance matrix]] $K_{XY} = \mathbb{COV}[X, Y] \in \mathbb{R}^{n\times m}$ of $X$ and $Y$ is defined as follows

$$
\begin{split}
K_{XY} 
&= \mathbb{COV}[X, Y]\\
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \left( \mathbb{E}\left[\left( X -\mathbb{E}[X_i]\right) \left( Y -\mathbb{E}[Y_j]\right)^\top\right]\right)_{i,j \in [n]} \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

- the [[covariance matrix]] of one [[random variable]] is the cross [[covariance matrix]] with itself

$$
\begin{split}
\mathbb{VAR}[X]
&= K_{XX}   \\
\end{split}
$$
#### base properties

- $K_{XX}$ is [[symmetric]]
- $K_{XX}$ is [[positive definite]]

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= A\mathbb{VAR}[X]A^\top \\
\mathbb{COV}[AX + a, BY + b]
&= A\mathbb{COV}[X,Y]B^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$

##### trace of a matrix product
- for $A, B \in \mathbb{R}^{n \times n}$ 
$$
\mathrm{trace}(AB) = \mathrm{trace}(BA)
$$

$$
\begin{split}
\mathrm{trace}(AB) 
&=\sum_{i \in [n]} \sum_{k \in [n]} a_{i,k} b_{k,i} \\
&=\sum_{k \in [n]} \sum_{i \in [n]} b_{k,i} a_{i,k} \\
&= \mathrm{trace}(BA)\\
\end{split}
$$

### inner product
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear map|linearity]] (regarding both elemements because of the [[symmetric]])

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
### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$


Tags: mathematics statistics SS25
<!--ID: 1746974641783-->
END


START
Basic
### quadratic forms of random variables
- give a [[symmetric]] non-random [[matrix]] $A$ and B and a [[random vector]] $X$
- let $\Sigma = \mathbb{VAR}[X]$ and $\mathrm{m}=\mathbb{E}[X]$

- calculate  $\mathbb{E}\left[\left(AX + \mathrm{a}\right)^\top\left(BX+ \mathrm{b}\right) \right]$ 
- how does $\mathbb{E}\left[\left(AX + \mathrm{a}\right)\left(BX+ \mathrm{b}\right)^\top \right]$ look like? (no proof)

Back: 



_________

$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)\left(BX+ \mathrm{b}\right)^\top \right] 
&= A\Sigma B^\top + \left(A\mathrm{m} + \mathrm{a}\right)\left(B\mathrm{m}+ \mathrm{b}\right)^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)\left(BX+ \mathrm{b}\right)^\top \right] 
&= \mathbb{E}\left[\left(A\left(X+ \mathrm{m} - \mathrm{m}\right) + \mathrm{a}\right)\left(B\left(X+ \mathrm{m} - \mathrm{m}\right)^\top + \mathrm{b}^\top\right) \right]  \\
&= \mathbb{E}\left[\left(A\left(X  - \mathrm{m}\right) + \left(A \mathrm{m} +\mathrm{a} \right)\right)\left(\left(X  - \mathrm{m}\right)^\top B^\top + \left(B \mathrm{m} +\mathrm{b} \right)^\top\right) \right]  \\
&= A\mathbb{E}\left[\left(X  - \mathrm{m}\right)\left(X  - \mathrm{m}\right)^\top \right]B^\top  + \left(A\mathrm{m} + \mathrm{a}\right)\left(B\mathrm{m}+ \mathrm{b}\right)^\top \\
& + A\mathbb{E}\left[X  - \mathrm{m}\right]\left(B \mathrm{m} +\mathrm{b} \right)^\top + \left(A \mathrm{m} +\mathrm{a} \right)B\mathbb{E}\left[X  - \mathrm{m}\right]^\top    \\
&= A\Sigma B^\top + \left(A\mathrm{m} + \mathrm{a}\right)\left(B\mathrm{m}+ \mathrm{b}\right)^\top \\
\end{split}
$$


$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)^\top\left(BX+ \mathrm{b}\right) \right] 
&= \mathrm{TR}\left(A\Sigma B^\top \right) + \left(A\mathrm{m} + \mathrm{a}\right)^\top\left(B\mathrm{m}+ \mathrm{b}\right) \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}\left[\left(AX + \mathrm{a}\right)^\top\left(BX+ \mathrm{b}\right) \right] 
&= \mathbb{E}\left[\left\langle A\left(X - \mathrm{m} + \mathrm{m}\right) + \mathrm{a}, B\left(X - \mathrm{m} + \mathrm{m}\right) + \mathrm{b}\right\rangle \right]  \\
&= \mathbb{E}\left[\left\langle A\left(X - \mathrm{m} \right) + (A\mathrm{m}+\mathrm{a}), B\left(X - \mathrm{m} \right) + (B\mathrm{m}+\mathrm{b})\right\rangle \right]  \\
&= \mathbb{E}\left[\left\langle A\left(X - \mathrm{m} \right) , B\left(X - \mathrm{m} \right)\right\rangle \right] + \left\langle A\mathrm{m}+\mathrm{a},  B\mathrm{m}+\mathrm{b}\right\rangle + 0 + 0  \\
&= \mathrm{TR}\left(B \mathbb{E}\left[\left(X - \mathrm{m} \right)\left(X - \mathrm{m} \right)^\top\right] A^\top  \right)  + \left\langle A\mathrm{m}+\mathrm{a},  B\mathrm{m}+\mathrm{b}\right\rangle  \\
&= \mathrm{TR}\left(B \Sigma A^\top  \right)  + \left\langle A\mathrm{m}+\mathrm{a},  B\mathrm{m}+\mathrm{b}\right\rangle  \\
&= \mathrm{TR}\left(A\Sigma B^\top \right) + \left(A\mathrm{m} + \mathrm{a}\right)^\top\left(B\mathrm{m}+ \mathrm{b}\right) \\
\end{split}
$$


________________

### covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- the cross [[covariance matrix]] $K_{XY} = \mathbb{COV}[X, Y] \in \mathbb{R}^{n\times m}$ of $X$ and $Y$ is defined as follows

$$
\begin{split}
K_{XY} 
&= \mathbb{COV}[X, Y]\\
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \left( \mathbb{E}\left[\left( X -\mathbb{E}[X_i]\right) \left( Y -\mathbb{E}[Y_j]\right)^\top\right]\right)_{i,j \in [n]} \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

- the [[covariance matrix]] of one [[random variable]] is the cross [[covariance matrix]] with itself

$$
\begin{split}
\mathbb{VAR}[X]
&= K_{XX}   \\
\end{split}
$$
#### base properties

- $K_{XX}$ is [[symmetric]]
- $K_{XX}$ is [[positive definite]]

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= A\mathbb{VAR}[X]A^\top \\
\mathbb{COV}[AX + a, BY + b]
&= A\mathbb{COV}[X,Y]B^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$

##### trace of a matrix product
- for $A, B \in \mathbb{R}^{n \times n}$ 
$$
\mathrm{trace}(AB) = \mathrm{trace}(BA)
$$

$$
\begin{split}
\mathrm{trace}(AB) 
&=\sum_{i \in [n]} \sum_{k \in [n]} a_{i,k} b_{k,i} \\
&=\sum_{k \in [n]} \sum_{i \in [n]} b_{k,i} a_{i,k} \\
&= \mathrm{trace}(BA)\\
\end{split}
$$

### inner product
- let $(V, +, \cdot)$ be a [[vector space]]
-  [[function]]  $\langle\cdot,\cdot\rangle: V \times V \rightarrow \mathbb{R}$ is an [[inner product]] if the following conditions are true
1) [[linear map|linearity]] (regarding both elemements because of the [[symmetric]])

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
### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$


Tags: mathematics statistics SS25
<!--ID: 1746974641785-->
END