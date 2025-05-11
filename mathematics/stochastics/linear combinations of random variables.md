### linear combinations of random variables
- given a non-random [[vector]] $\mathrm{w}$ and a [[random vector]] $X$ with $\mathrm{m}=\mathbb{E}\left[X\right]$ and $\Sigma=\mathbb{VAR}\left[X\right]$ 
- let $Y=\mathrm{w}^\top X$

$$
\begin{split}
\mathbb{E}\left[Y\right] &= \mathrm{w}^\top \mathrm{m} \\
\mathbb{VAR}\left[Y\right] &= \mathrm{w}^\top \Sigma \mathrm{w} \\
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}\left[Y\right] 
&= \mathbb{E}\left[\left(Y - \mathbb{E}\left[Y\right]\right)^2\right]  \\
&= \mathbb{E}\left[\left(\mathrm{w}^\top X - \mathbb{E}\left[(\mathrm{w}^\top X)\right]\right)^2\right]  \\
&= \mathbb{E}\left[\left(\mathrm{w}^\top X - \mathrm{w}^\top\mathbb{E}\left[ X\right]\right)^2\right]  \\
&= \mathbb{E}\left[\left(\mathrm{w}^\top \left(X - \mathrm{m}\right)\right)^2\right]  \\
&= \mathbb{E}\left[\mathrm{w}^\top \left(X - \mathrm{m}\right) \left(X - \mathrm{m}\right)^\top\mathrm{w}\right]  \\
&= \mathrm{w}^\top \Sigma \mathrm{w} \\
\end{split}
$$


# anki

START
Basic
### linear combinations of random variables
- given a non-random [[vector]] $\mathrm{w}$ and a [[random vector]] $X$ with $\mathrm{m}=\mathbb{E}\left[X\right]$ and $\Sigma=\mathbb{VAR}\left[X\right]$ 
- let $Y=\mathrm{w}^\top X$


- $\mathbb{E}\left[Y\right]$ and $\mathbb{VAR}\left[Y\right]$ (with proof)

Back: 



$$
\begin{split}
\mathbb{E}\left[Y\right] &= \mathrm{w}^\top \mathrm{m} \\
\mathbb{VAR}\left[Y\right] &= \mathrm{w}^\top \Sigma \mathrm{w} \\
\end{split}
$$

$$
\begin{split}
\mathbb{VAR}\left[Y\right] 
&= \mathbb{E}\left[\left(Y - \mathbb{E}\left[Y\right]\right)^2\right]  \\
&= \mathbb{E}\left[\left(\mathrm{w}^\top X - \mathbb{E}\left[(\mathrm{w}^\top X)\right]\right)^2\right]  \\
&= \mathbb{E}\left[\left(\mathrm{w}^\top X - \mathrm{w}^\top\mathbb{E}\left[ X\right]\right)^2\right]  \\
&= \mathbb{E}\left[\left(\mathrm{w}^\top \left(X - \mathrm{m}\right)\right)^2\right]  \\
&= \mathbb{E}\left[\mathrm{w}^\top \left(X - \mathrm{m}\right) \left(X - \mathrm{m}\right)^\top\mathrm{w}\right]  \\
&= \mathrm{w}^\top \Sigma \mathrm{w} \\
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
<!--ID: 1746976937202-->
END