### gradient
- let $f: \mathbb{R}^m \to \mathbb{R}^n$ be a [[function]] then the [[gradient]] is a [[linear map]] $\nabla f(x): \mathbb{R}^m \to \mathbb{R}^n$ and is defined as follows

$$
\nabla f(x) = 
\left(
\begin{matrix}
\frac{\partial f}{\partial x_1} \\
... \\
\frac{\partial f}{\partial x_n} \\
\end{matrix}

\right)
\in \mathbb{R}^{n \times m}
$$
- the [[gradient]] gives the direction and the rate of fastest increase of $f$ because every of its elements $\frac{\partial f}{\partial x_i}$ gives the rate of change in the direction of the coordinate $x_i$ 



### jacobian $f: \mathbb{R}^m \to \mathbb{R}$
- let $f: \mathbb{R}^n \to \mathbb{R}$ be a [[function]] mapping from a [[banach space]] $(\mathbb{R}^n, ||\cdot||)$ to a [[banach space]] $(\mathbb{R}, |\cdot|)$
- since the [[derivative]] $A: \mathbb{R}^m \to \mathbb{R}$ is a [[bounded linear map]] we can express it as a [[matrix]] $A \in \mathbb{R}^{1 \times m}$
- $x, h \in \mathbb{R}^m$ are [[vector|vectors]] from the [[domain]] of $f$
- we can follow that $h$ is the [[derivative]] exactly when each of its elements $h_i$ is the partial derivative of $f(x)$ after $x_i$
$$
\begin{split}
&\lim_{||h|| \to 0} \frac{|f(x+h) - f(x) - Ah|}{||h||} = 0 \\

\Leftrightarrow& \lim_{||h|| \to 0} \frac{\left|f(x+Ih) - f(x) - \sum_{j \in [m]} a_j h_j \right| }{||h||} = 0 \\

\Leftrightarrow& \lim_{||h|| \to 0} \frac{\left|f\left(x+\sum_{i \in [n]} I_{(*, j) h_j}\right) - f(x) - \sum_{j \in [m]} a_j h_j \right| }{||h||} = 0 \\

\Leftrightarrow& \forall j \in [m]: \lim_{|h_j| \to 0} \frac{\left|f\left(x+I_{(*, j) h_j}\right) - f(x) - a_j h_j \right| }{|h_i|} = 0 \\

\Leftrightarrow& \forall j \in [m]: h_j = \frac{\partial f(x)}{\partial x_j} \\

\Leftrightarrow&  h = Df(x) = \left(\nabla f(x)\right)^\top \\
\end{split}
$$

### jacobian $f: \mathbb{R}^m \to \mathbb{R}^n$
- let $f: \mathbb{R}^m \to \mathbb{R}^n$ be a [[function]] mapping from a [[banach space]] $(\mathbb{R}^m, ||\cdot||)$ to a [[banach space]] $(\mathbb{R}^n, ||\cdot||)$
- since the [[derivative]] $A: \mathbb{R}^m \to \mathbb{R}^n$ is a [[bounded linear map]] we can express it as a [[matrix]] $A \in \mathbb{R}^{n \times m}$
- since we can treat the $n$ dimensions of the [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ as $n$ different [[function|functions]] $i \in [n]: f_i: \mathbb{R}^m \to \mathbb{R}$ the following is the [[derivative]]

$$
D f(x) = 
\left(
\begin{matrix}
\left(\nabla f_1(x)\right)^\top\\
... \\
\left(\nabla f_n(x)\right)^\top \\
\end{matrix}
\right)
=
\left(
\begin{matrix}
\frac{\partial f_1}{\partial x_1} & ... & \frac{\partial f_1}{\partial x_m} \\
 & ... &  \\
\frac{\partial f_n}{\partial x_1} &...& \frac{\partial f_n}{\partial x_m} \\
\end{matrix}
\right)
\in \mathbb{R}^{n \times m}
$$
# ---------------------
![[derivative#general derivative]]

![[identity matrix#identity matrix]]

![[gradient#gradient]]



# anki

START
Basic

[[jacobian]] $f: \mathbb{R}^n \to \mathbb{R}$

[[jacobian]] $f: \mathbb{R}^m \to \mathbb{R}^n$

(with proof)


Back: 

### jacobian $f: \mathbb{R}^m \to \mathbb{R}$

- let $f: \mathbb{R}^n \to \mathbb{R}$ be a [[function]] mapping from a [[banach space]] $(\mathbb{R}^n, ||\cdot||)$ to a [[banach space]] $(\mathbb{R}, |\cdot|)$
- since the [[derivative]] $A: \mathbb{R}^m \to \mathbb{R}$ is a [[bounded linear map]] we can express it as a [[matrix]] $A \in \mathbb{R}^{1 \times m}$
- $x, h \in \mathbb{R}^m$ are [[vector|vectors]] from the [[domain]] of $f$
- we can follow that $h$ is the [[derivative]] exactly when each of its elements $h_j$ is the partial derivative of $f(x)$ after $x_j$

$$
\begin{split}
&\lim_{||h|| \to 0} \frac{|f(x+h) - f(x) - Ah|}{||h||} = 0 \\

\Leftrightarrow& \lim_{||h|| \to 0} \frac{\left|f(x+Ih) - f(x) - \sum_{j \in [m]} a_j h_j \right| }{||h||} = 0 \\

\Leftrightarrow& \lim_{||h|| \to 0} \frac{\left|f\left(x+\sum_{i \in [n]} I_{(*, j) h_j}\right) - f(x) - \sum_{j \in [m]} a_j h_j \right| }{||h||} = 0 \\

\Leftrightarrow& \forall j \in [m]: \lim_{|h_j| \to 0} \frac{\left|f\left(x+I_{(*, j) h_j}\right) - f(x) - a_j h_j \right| }{|h_i|} = 0 \\

\Leftrightarrow& \forall j \in [m]: h_j = \frac{\partial f(x)}{\partial x_j} \\

\Leftrightarrow&  h = Df(x) = \left(\nabla f(x)\right)^\top \\
\end{split}
$$


### jacobian $f: \mathbb{R}^m \to \mathbb{R}^n$
- let $f: \mathbb{R}^m \to \mathbb{R}^n$ be a [[function]] mapping from a [[banach space]] $(\mathbb{R}^m, ||\cdot||)$ to a [[banach space]] $(\mathbb{R}^n, ||\cdot||)$
- since the [[derivative]] $A: \mathbb{R}^m \to \mathbb{R}^n$ is a [[bounded linear map]] we can express it as a [[matrix]] $A \in \mathbb{R}^{n \times m}$
- since we can treat the $n$ dimensions of the [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ as $n$ different [[function|functions]] $i \in [n]: f_i: \mathbb{R}^m \to \mathbb{R}$ the following is the [[derivative]]

$$
D f(x) = 
\left(
\begin{matrix}
\left(\nabla f_1(x)\right)^\top\\
... \\
\left(\nabla f_n(x)\right)^\top \\
\end{matrix}
\right)
=
\left(
\begin{matrix}
\frac{\partial f_1}{\partial x_1} & ... & \frac{\partial f_1}{\partial x_m} \\
 & ... &  \\
\frac{\partial f_n}{\partial x_1} &...& \frac{\partial f_n}{\partial x_m} \\
\end{matrix}
\right)
\in \mathbb{R}^{n \times m}
$$

___________________

### derivative in a [[banach space]]
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[bounded linear map]] $A \in L(X, Y)$ is the [[derivative]] of $f$ in point $x \in X$ is the following is true

$$
\lim_{||h||_X \to 0} \frac{||f(x+h) - f(x) - Ah||_Y}{||h||_X} = 0
$$

- for every point $x \in X$ we will get a different [[bounded linear map]] $A: X \to Y$
- the [[derivative]] $Df: X \to L(X,Y)$ is a [[function]] that maps elements of $X$ to a [[bounded linear map]]
$$
A=Df(x) \in L(X,Y
$$


### bounded linear map
- given two [[banach space|banach spaces]] $(X, +, \cdot, ||\cdot||_X)$ and $(Y, \oplus, \odot , ||\cdot||_Y)$ and a [[linear map]] $A: X\rightarrow Y$
- $A$ is a [[bounded linear map]] if the followng is true

$$
\exists C>0: \forall x \in X : ||Ax||_Y \leq C ||x||_X
$$
$$
\forall x_1,x_2 \in X, \lambda , \mu \in \mathbb{R}:F(\lambda x_1 + \mu x_2) = \lambda \odot F(x_1) \oplus \mu \odot F(x_2) 
$$

- it says that the [[image]] of a [[bounded set]] also has to be a [[bounded set]]
- we define $L(X,Y)$ as the [[set]] of all [[bounded linear map|bounded linear maps]] mapping from $X$ to $Y$

$$
L(X,Y) = \{A: X\to Y: A \text{ is linear and bounded}\}
$$

- every [[bounded linear map]] in a finite space can be expressed as a [[matrix]]

### derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
### banach spaces
- [[norm|normed]] [[vector space|space]] that is [[cauchy complete]] with resprect to the [[metric]] induces by its norm is a [[banach space]]

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

Tags: mathematics
<!--ID: 1715629635949-->
END


START
Basic
[[gradient]] plus related concept
- definition
- geometric interpretation
Back: 
### gradient
- let $f: \mathbb{R}^m \to \mathbb{R}^n$ be a [[function]] then the [[gradient]] is a [[linear map]] $\nabla f(x): \mathbb{R}^m \to \mathbb{R}^n$ and is defined as follows

$$
\nabla f(x) = 
\left(
\begin{matrix}
\frac{\partial f}{\partial x_1} \\
... \\
\frac{\partial f}{\partial x_n} \\
\end{matrix}

\right)
\in \mathbb{R}^{n \times m}
$$
- the [[gradient]] gives the direction and the rate of fastest increase of $f$ because every of its elements $\frac{\partial f}{\partial x_i}$ gives the rate of change in the direction of the coordinate $x_i$ 

### partial derivative
- given a [[function]] $f: \mathbb{R}^n \to Y$
- the [[partial derivative]] $\frac{\partial f}{\partial x_i}$ is defined as follows and mesures the rate of change of $f$ regarding the direction of die coordinate $x_i$ 

$$
\frac{\partial f}{\partial x_i}(x) = \lim_{h \to 0} \frac{f(x+h e_i) - f(x) }{h}
$$

___________________



### derivative in a [[banach space]]
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[bounded linear map]] $A \in L(X, Y)$ is the [[derivative]] of $f$ in point $x \in X$ is the following is true
$$
\lim_{||h||_X \to 0} \frac{||f(x+h) - f(x) - Ah||_Y}{||h||_X} = 0
$$
- for every point $x \in X$ we will get a different [[bounded linear map]] $A: X \to Y$
- the [[derivative]] $Df: X \to L(X,Y)$ is a [[function]] that maps elements of $X$ to a [[bounded linear map]]

$$
A=Df(x) \in L(X,Y
$$

### derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$

### jacobian $f: \mathbb{R}^n \to \mathbb{R}$
- let $f: \mathbb{R}^n \to \mathbb{R}$ be a [[function]] mapping from a [[banach space]] $(\mathbb{R}^n, ||\cdot||)$ to a [[banach space]] $(\mathbb{R}, |\cdot|)$
- since the [[derivative]] $A: \mathbb{R}^n \to \mathbb{R}$ is a [[bounded linear map]] we can express it as a [[matrix]] $A \in \mathbb{R}^{1 \times n}$
- $x, h \in \mathbb{R}^n$ are [[vector|vectors]] from the [[domain]] of $f$
- we can follow that $h$ is the [[derivative]] exactly when each of its elements $h_i$ is the partial derivative of $f(x)$ after $x_i$

$$
\begin{split}
&\lim_{||h|| \to 0} \frac{|f(x+h) - f(x) - Ah|}{||h||} = 0 \\

\Leftrightarrow& \lim_{||h|| \to 0} \frac{\left|f(x+Ih) - f(x) - \sum_{i \in [n]} a_i h_i \right| }{||h||} = 0 \\

\Leftrightarrow& \lim_{||h|| \to 0} \frac{\left|f\left(x+\sum_{i \in [n]} I_{(*, i) h_i}\right) - f(x) - \sum_{i \in [n]} a_i h_i \right| }{||h||} = 0 \\

\Leftrightarrow& \forall i \in [n]: \lim_{|h_i| \to 0} \frac{\left|f\left(x+I_{(*, i) h_i}\right) - f(x) - a_i h_i \right| }{|h_i|} = 0 \\

\Leftrightarrow& \forall i \in [n]: h_i = \frac{\partial f(x)}{\partial x_i} \\

\Leftrightarrow&  h = Df(x) = \left(\nabla f(x)\right)^\top \\
\end{split}
$$



Tags: mathematics
<!--ID: 1715629635955-->
END


