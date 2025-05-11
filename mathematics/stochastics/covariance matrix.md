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

- if we combine two random vectors $X_1 \in \mathbb{R}^n$ and $X_2 \in \mathbb{R}^m$ to one random vector $X \in \mathbb{R}^{n+m}$ the [[covariance matrix]] of $K_{XX} \in  \in \mathbb{R}^{n\times m}$ can be constructed as follows

$$
\begin{split}
K_{XX} 
&= \mathbb{COV}[X, X] \\
&= \left[\begin{matrix}
K_{X_1X_1} & K_{X_1X_2} \\
K_{X_2X_1} & K_{X_2X_2} \\
\end{matrix}\right]

\end{split}
$$

### decomposition of the covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- the [[covariance matrix]] can be expressed as follows

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[ XY^\top + \mathbb{E}[X]\mathbb{E}[Y]^\top - X\mathbb{E}[Y]^\top - Y\mathbb{E}[X]^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] + \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top - 2 \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

### covariance of a linear function
- for every constant [[matrix]] $A \in \mathbb{R}^{n \times m}$ and constant [[vector]] $b \in \mathbb{R}^{n}$ 

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= A\mathbb{VAR}[X]A^\top \\
\mathbb{COV}[AX + a, BY + b]
&= A\mathbb{COV}[X,Y]B^\top \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= \mathbb{E}\left[\left(AX + b\right) \left(AX + b\right)^\top\right] - \mathbb{E}[AX + b] \mathbb{E}[AX + b]^\top \\
&= \mathbb{E}\left[AXX^\top A^\top\right] + bb^\top + \mathbb{E}\left[AXb^\top\right] + \mathbb{E}\left[b(AX)^\top\right] \\
&- \mathbb{E}[AX] \mathbb{E}[AX ]^\top - bb^\top - \mathbb{E}\left[AXb^\top\right] - \mathbb{E}\left[b(AX)^\top\right] \\
&= \mathbb{E}\left[AXX^\top A^\top\right] - \mathbb{E}[AX] \mathbb{E}[AX ]^\top \\
&= A\mathbb{E}\left[XX^\top\right] A^\top - A\mathbb{E}[X] \left(A\mathbb{E}[X ]\right)^\top \\
&= A\mathbb{E}\left[XX^\top\right] A^\top - A\mathbb{E}[X] \mathbb{E}[X]^\top A^\top \\
&= A\left(\mathbb{E}\left[XX^\top\right] -\mathbb{E}[X] \mathbb{E}[X]^\top \right) A^\top  \\
&= A\mathbb{VAR}[X]A^\top  \\
\end{split}
$$

### covariance matrix of the sum of two random vectors
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- then the following is true

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{E}\left[\left(X + Y\right) \left(X + Y\right)^\top\right] - \mathbb{E}[X + Y] \mathbb{E}[X + Y]^\top \\
&= \mathbb{E}\left[XX^\top\right] + \mathbb{E}\left[YY^\top\right] + \mathbb{E}\left[XY^\top\right] +\mathbb{E}\left[YX^\top\right] \\
&- \mathbb{E}\left[X\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[Y^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[X\right]\mathbb{E}\left[Y^\top\right] \\
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

# anki

START
Basic
[[covariance matrix]] summary
- two definitions
- 5 base properties without proof
- [[covariance matrix]] of a combined random vectors

Back: 
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

- if we combine two random vectors $X_1 \in \mathbb{R}^n$ and $X_2 \in \mathbb{R}^m$ to one random vector $X \in \mathbb{R}^{n+m}$ the [[covariance matrix]] of $K_{XX} \in  \in \mathbb{R}^{n\times m}$ can be constructed as follows

$$
\begin{split}
K_{XX} 
&= \mathbb{COV}[X, X] \\
&= \left[\begin{matrix}
K_{X_1X_1} & K_{X_1X_2} \\
K_{X_2X_1} & K_{X_2X_2} \\
\end{matrix}\right]

\end{split}
$$

__________

### decomposition of the covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- the [[covariance matrix]] can be expressed as follows

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[ XY^\top + \mathbb{E}[X]\mathbb{E}[Y]^\top - X\mathbb{E}[Y]^\top - Y\mathbb{E}[X]^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] + \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top - 2 \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

### covariance of a linear function
- for every constant [[matrix]] $A \in \mathbb{R}^{n \times m}$ and constant [[vector]] $b \in \mathbb{R}^{n}$ 

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= A\mathbb{VAR}[X]A^\top \\
\mathbb{COV}[AX + a, BY + b]
&= A\mathbb{COV}[X,Y]B^\top \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= \mathbb{E}\left[\left(AX + b\right) \left(AX + b\right)^\top\right] - \mathbb{E}[AX + b] \mathbb{E}[AX + b]^\top \\
&= \mathbb{E}\left[AXX^\top A^\top\right] + bb^\top + \mathbb{E}\left[AXb^\top\right] + \mathbb{E}\left[b(AX)^\top\right] \\
&- \mathbb{E}[AX] \mathbb{E}[AX ]^\top - bb^\top - \mathbb{E}\left[AXb^\top\right] - \mathbb{E}\left[b(AX)^\top\right] \\
&= \mathbb{E}\left[AXX^\top A^\top\right] - \mathbb{E}[AX] \mathbb{E}[AX ]^\top \\
&= A\mathbb{E}\left[XX^\top\right] A^\top - A\mathbb{E}[X] \left(A\mathbb{E}[X ]\right)^\top \\
&= A\mathbb{E}\left[XX^\top\right] A^\top - A\mathbb{E}[X] \mathbb{E}[X]^\top A^\top \\
&= A\left(\mathbb{E}\left[XX^\top\right] -\mathbb{E}[X] \mathbb{E}[X]^\top \right) A^\top  \\
&= A\mathbb{VAR}[X]A^\top  \\
\end{split}
$$

### covariance matrix of the sum of two random vectors
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- then the following is true

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{E}\left[\left(X + Y\right) \left(X + Y\right)^\top\right] - \mathbb{E}[X + Y] \mathbb{E}[X + Y]^\top \\
&= \mathbb{E}\left[XX^\top\right] + \mathbb{E}\left[YY^\top\right] + \mathbb{E}\left[XY^\top\right] +\mathbb{E}\left[YX^\top\right] \\
&- \mathbb{E}\left[X\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[Y^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[X\right]\mathbb{E}\left[Y^\top\right] \\
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

Tags: mathematics statistics SS25
<!--ID: 1746883317041-->
END


START
Basic
- proof for the following property of the [[covariance matrix]]

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

Back: 
### decomposition of the covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- the [[covariance matrix]] can be expressed as follows

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[ XY^\top + \mathbb{E}[X]\mathbb{E}[Y]^\top - X\mathbb{E}[Y]^\top - Y\mathbb{E}[X]^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] + \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top - 2 \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

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

- if we combine two random vectors $X_1 \in \mathbb{R}^n$ and $X_2 \in \mathbb{R}^m$ to one random vector $X \in \mathbb{R}^{n+m}$ the [[covariance matrix]] of $K_{XX} \in  \in \mathbb{R}^{n\times m}$ can be constructed as follows

$$
\begin{split}
K_{XX} 
&= \mathbb{COV}[X, X] \\
&= \left[\begin{matrix}
K_{X_1X_1} & K_{X_1X_2} \\
K_{X_2X_1} & K_{X_2X_2} \\
\end{matrix}\right]

\end{split}
$$

__________

### decomposition of the covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- the [[covariance matrix]] can be expressed as follows

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[ XY^\top + \mathbb{E}[X]\mathbb{E}[Y]^\top - X\mathbb{E}[Y]^\top - Y\mathbb{E}[X]^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] + \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top - 2 \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

### covariance of a linear function
- for every constant [[matrix]] $A \in \mathbb{R}^{n \times m}$ and constant [[vector]] $b \in \mathbb{R}^{n}$ 

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= A\mathbb{VAR}[X]A^\top \\
\mathbb{COV}[AX + a, BY + b]
&= A\mathbb{COV}[X,Y]B^\top \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= \mathbb{E}\left[\left(AX + b\right) \left(AX + b\right)^\top\right] - \mathbb{E}[AX + b] \mathbb{E}[AX + b]^\top \\
&= \mathbb{E}\left[AXX^\top A^\top\right] + bb^\top + \mathbb{E}\left[AXb^\top\right] + \mathbb{E}\left[b(AX)^\top\right] \\
&- \mathbb{E}[AX] \mathbb{E}[AX ]^\top - bb^\top - \mathbb{E}\left[AXb^\top\right] - \mathbb{E}\left[b(AX)^\top\right] \\
&= \mathbb{E}\left[AXX^\top A^\top\right] - \mathbb{E}[AX] \mathbb{E}[AX ]^\top \\
&= A\mathbb{E}\left[XX^\top\right] A^\top - A\mathbb{E}[X] \left(A\mathbb{E}[X ]\right)^\top \\
&= A\mathbb{E}\left[XX^\top\right] A^\top - A\mathbb{E}[X] \mathbb{E}[X]^\top A^\top \\
&= A\left(\mathbb{E}\left[XX^\top\right] -\mathbb{E}[X] \mathbb{E}[X]^\top \right) A^\top  \\
&= A\mathbb{VAR}[X]A^\top  \\
\end{split}
$$

### covariance matrix of the sum of two random vectors
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- then the following is true

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{E}\left[\left(X + Y\right) \left(X + Y\right)^\top\right] - \mathbb{E}[X + Y] \mathbb{E}[X + Y]^\top \\
&= \mathbb{E}\left[XX^\top\right] + \mathbb{E}\left[YY^\top\right] + \mathbb{E}\left[XY^\top\right] +\mathbb{E}\left[YX^\top\right] \\
&- \mathbb{E}\left[X\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[Y^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[X\right]\mathbb{E}\left[Y^\top\right] \\
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$


Tags: mathematics statistics SS25
<!--ID: 1746883317045-->
END


START
Basic
- proof for the following property of the [[covariance matrix]]

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

Back: 

### decomposition of the covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- then the following is true

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{E}\left[\left(X + Y\right) \left(X + Y\right)^\top\right] - \mathbb{E}[X + Y] \mathbb{E}[X + Y]^\top \\
&= \mathbb{E}\left[XX^\top\right] + \mathbb{E}\left[YY^\top\right] + \mathbb{E}\left[XY^\top\right] +\mathbb{E}\left[YX^\top\right] \\
&- \mathbb{E}\left[X\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[Y^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[X\right]\mathbb{E}\left[Y^\top\right] \\
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

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

- if we combine two random vectors $X_1 \in \mathbb{R}^n$ and $X_2 \in \mathbb{R}^m$ to one random vector $X \in \mathbb{R}^{n+m}$ the [[covariance matrix]] of $K_{XX} \in  \in \mathbb{R}^{n\times m}$ can be constructed as follows

$$
\begin{split}
K_{XX} 
&= \mathbb{COV}[X, X] \\
&= \left[\begin{matrix}
K_{X_1X_1} & K_{X_1X_2} \\
K_{X_2X_1} & K_{X_2X_2} \\
\end{matrix}\right]

\end{split}
$$

__________
### decomposition of the covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- the [[covariance matrix]] can be expressed as follows

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[ XY^\top + \mathbb{E}[X]\mathbb{E}[Y]^\top - X\mathbb{E}[Y]^\top - Y\mathbb{E}[X]^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] + \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top - 2 \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

### covariance of a linear function
- for every constant [[matrix]] $A \in \mathbb{R}^{n \times m}$ and constant [[vector]] $b \in \mathbb{R}^{n}$ 

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= A\mathbb{VAR}[X]A^\top \\
\mathbb{COV}[AX + a, BY + b]
&= A\mathbb{COV}[X,Y]B^\top \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= \mathbb{E}\left[\left(AX + b\right) \left(AX + b\right)^\top\right] - \mathbb{E}[AX + b] \mathbb{E}[AX + b]^\top \\
&= \mathbb{E}\left[AXX^\top A^\top\right] + bb^\top + \mathbb{E}\left[AXb^\top\right] + \mathbb{E}\left[b(AX)^\top\right] \\
&- \mathbb{E}[AX] \mathbb{E}[AX ]^\top - bb^\top - \mathbb{E}\left[AXb^\top\right] - \mathbb{E}\left[b(AX)^\top\right] \\
&= \mathbb{E}\left[AXX^\top A^\top\right] - \mathbb{E}[AX] \mathbb{E}[AX ]^\top \\
&= A\mathbb{E}\left[XX^\top\right] A^\top - A\mathbb{E}[X] \left(A\mathbb{E}[X ]\right)^\top \\
&= A\mathbb{E}\left[XX^\top\right] A^\top - A\mathbb{E}[X] \mathbb{E}[X]^\top A^\top \\
&= A\left(\mathbb{E}\left[XX^\top\right] -\mathbb{E}[X] \mathbb{E}[X]^\top \right) A^\top  \\
&= A\mathbb{VAR}[X]A^\top  \\
\end{split}
$$

### covariance matrix of the sum of two random vectors
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- then the following is true

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{E}\left[\left(X + Y\right) \left(X + Y\right)^\top\right] - \mathbb{E}[X + Y] \mathbb{E}[X + Y]^\top \\
&= \mathbb{E}\left[XX^\top\right] + \mathbb{E}\left[YY^\top\right] + \mathbb{E}\left[XY^\top\right] +\mathbb{E}\left[YX^\top\right] \\
&- \mathbb{E}\left[X\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[Y^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[X\right]\mathbb{E}\left[Y^\top\right] \\
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$


Tags: mathematics statistics SS25
<!--ID: 1746883317047-->
END



START
Basic
- given a constant [[matrix]] $A \in \mathbb{R}^{n \times m}$ and constant [[vector]] $b \in \mathbb{R}^{n}$ and a [[random vector]] $X$
- [[covariance matrix]] of $\mathbb{VAR}[AX + b]$ (with proof)
- [[covariance matrix]] of $\mathbb{COV}[AX + a, BY + b]$ (no proof)

Back: 
### covariance of a linear function
- for every constant [[matrix]] $A \in \mathbb{R}^{n \times m}$ and constant [[vector]] $b \in \mathbb{R}^{n}$ 

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= A\mathbb{VAR}[X]A^\top \\
\mathbb{COV}[AX + a, BY + b]
&= A\mathbb{COV}[X,Y]B^\top \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= \mathbb{E}\left[\left(AX + b\right) \left(AX + b\right)^\top\right] - \mathbb{E}[AX + b] \mathbb{E}[AX + b]^\top \\
&= \mathbb{E}\left[AXX^\top A^\top\right] + bb^\top + \mathbb{E}\left[AXb^\top\right] + \mathbb{E}\left[b(AX)^\top\right] \\
&- \mathbb{E}[AX] \mathbb{E}[AX ]^\top - bb^\top - \mathbb{E}\left[AXb^\top\right] - \mathbb{E}\left[b(AX)^\top\right] \\
&= \mathbb{E}\left[AXX^\top A^\top\right] - \mathbb{E}[AX] \mathbb{E}[AX ]^\top \\
&= A\mathbb{E}\left[XX^\top\right] A^\top - A\mathbb{E}[X] \left(A\mathbb{E}[X ]\right)^\top \\
&= A\mathbb{E}\left[XX^\top\right] A^\top - A\mathbb{E}[X] \mathbb{E}[X]^\top A^\top \\
&= A\left(\mathbb{E}\left[XX^\top\right] -\mathbb{E}[X] \mathbb{E}[X]^\top \right) A^\top  \\
&= A\mathbb{VAR}[X]A^\top  \\
\end{split}
$$

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

- if we combine two random vectors $X_1 \in \mathbb{R}^n$ and $X_2 \in \mathbb{R}^m$ to one random vector $X \in \mathbb{R}^{n+m}$ the [[covariance matrix]] of $K_{XX} \in  \in \mathbb{R}^{n\times m}$ can be constructed as follows

$$
\begin{split}
K_{XX} 
&= \mathbb{COV}[X, X] \\
&= \left[\begin{matrix}
K_{X_1X_1} & K_{X_1X_2} \\
K_{X_2X_1} & K_{X_2X_2} \\
\end{matrix}\right]

\end{split}
$$

____________


### decomposition of the covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- the [[covariance matrix]] can be expressed as follows

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$
#### proof
$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \mathbb{E}\left[ XY^\top + \mathbb{E}[X]\mathbb{E}[Y]^\top - X\mathbb{E}[Y]^\top - Y\mathbb{E}[X]^\top\right] \\
&= \mathbb{E}\left[X Y^\top\right] + \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top - 2 \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$


### covariance matrix of the sum of two random vectors
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- then the following is true

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{E}\left[\left(X + Y\right) \left(X + Y\right)^\top\right] - \mathbb{E}[X + Y] \mathbb{E}[X + Y]^\top \\
&= \mathbb{E}\left[XX^\top\right] + \mathbb{E}\left[YY^\top\right] + \mathbb{E}\left[XY^\top\right] +\mathbb{E}\left[YX^\top\right] \\
&- \mathbb{E}\left[X\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[Y^\top\right] - \mathbb{E}\left[Y\right]\mathbb{E}\left[X^\top\right] - \mathbb{E}\left[X\right]\mathbb{E}\left[Y^\top\right] \\
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$


Tags: mathematics statistics SS25
<!--ID: 1746883317050-->
END