### jacobian
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[derivative]] $Df(x)[h]=Ah$ is a [[bounded linear map]] that can be represented by a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- for a general $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[matrix]] $A\in \mathbb{R}^{n \times m}$ called the [[jacobian]] $\nabla f = A \in \mathbb{R}^{n \times m}$ 
- if $f: \mathbb{R}^m \to \mathbb{R}$ is a scalar [[function]] [[transpose]] of [[matrix]] $A$ is a [[vector]]called the [[gradient]] $\nabla f = A^\top \in \mathbb{R}^m$ 


#### jacobian $f: \mathbb{R}^m \to \mathbb{R}$
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

#### jacobian $f: \mathbb{R}^m \to \mathbb{R}^n$
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

#### gradient
- let $f: \mathbb{R}^m \to \mathbb{R}$ be a [[function]] then the [[gradient]] is a [[linear map]] $\nabla f(x): \mathbb{R}^m \to \mathbb{R}$ and is defined as follows

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


# ---------------------
![[derivative#general derivative]]

![[partial derivative#partial derivative]]

![[identity matrix#identity matrix]]





# anki

START
Basic

[[jacobian]] 
- concept
- $f: \mathbb{R}^n \to \mathbb{R}$
- $f: \mathbb{R}^m \to \mathbb{R}^n$
(with proof)


Back: 
### jacobian
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[derivative]] $Df(x)[h]=Ah$ is a [[bounded linear map]] that can be represented by a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- for a general $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[matrix]] $A\in \mathbb{R}^{n \times m}$ called the [[jacobian]] $\nabla f = A \in \mathbb{R}^{n \times m}$ 
- if $f: \mathbb{R}^m \to \mathbb{R}$ is a scalar [[function]] [[transpose]] of [[matrix]] $A$ is a [[vector]]called the [[gradient]] $\nabla f = A^\top \in \mathbb{R}^m$ 

#### jacobian $f: \mathbb{R}^m \to \mathbb{R}$

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


#### jacobian $f: \mathbb{R}^m \to \mathbb{R}^n$
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

### general derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[derivative]] operator $Df: X \to L(X,Y)$ is a [[function]] that maps elements of $X$ to a [[bounded linear map]] $Df(x)[h]: X \to Y$
- the [[bounded linear map]] $Df(x)[h]: X \to Y$ is the [[derivative]] of $f$ in point $x \in X$ and can be interpreted as a linear approximation of $f$ in point $x$
- in the case of $f: \mathbb{R}^{m} \to \mathbb{R}^{n}$ the [[derivative]] $Df(x)[h] = Ah$ can be expressed as a [[matrix]] $A \in \mathbb{R}^{n \times m}$
$$
\lim_{||h||_X \to 0} \frac{||f(x+h) - f(x) - Df(x)[h]||_Y}{||h||_X} = 0
$$

- this eqivalent definition is often easier to work with:
$$
f(x + h) = f(x) + Df(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||_Y}{||h||_X} = 0
$$


### partial derivative
- given a [[function]] $f: \mathbb{R}^n \to Y$
- the [[partial derivative]] $\frac{\partial f}{\partial x_i}$ is defined as follows and mesures the rate of change of $f$ regarding the direction of die coordinate $x_i$ 

$$
\frac{\partial f}{\partial x_i}(x) = \lim_{h \to 0} \frac{f(x+h e_i) - f(x) }{h} 
$$

Tags: mathematics
<!--ID: 1715629635949-->
END


START
Basic
[[gradient]]
- concept
- defnition

[[jacobian]]
- concept
- defnition

what is the difference?
Back: 

### jacobian
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[derivative]] $Df(x)[h]=Ah$ is a [[bounded linear map]] that can be represented by a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- for a general $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[matrix]] $A\in \mathbb{R}^{n \times m}$ called the [[jacobian]] $\nabla f = A \in \mathbb{R}^{n \times m}$ 
- if $f: \mathbb{R}^m \to \mathbb{R}$ is a scalar [[function]] [[transpose]] of [[matrix]] $A$ is a [[vector]]called the [[gradient]] $\nabla f = A^\top \in \mathbb{R}^m$ 

#### jacobian $f: \mathbb{R}^m \to \mathbb{R}$

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


#### jacobian $f: \mathbb{R}^m \to \mathbb{R}^n$
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

#### gradient
- let $f: \mathbb{R}^m \to \mathbb{R}$ be a [[function]] then the [[gradient]] is a [[linear map]] $\nabla f(x): \mathbb{R}^m \to \mathbb{R}$ and is defined as follows

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


___________________

### general derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[derivative]] operator $Df: X \to L(X,Y)$ is a [[function]] that maps elements of $X$ to a [[bounded linear map]] $Df(x)[h]: X \to Y$
- the [[bounded linear map]] $Df(x)[h]: X \to Y$ is the [[derivative]] of $f$ in point $x \in X$ and can be interpreted as a linear approximation of $f$ in point $x$
- in the case of $f: \mathbb{R}^{m} \to \mathbb{R}^{n}$ the [[derivative]] $Df(x)[h] = Ah$ can be expressed as a [[matrix]] $A \in \mathbb{R}^{n \times m}$
$$
\lim_{||h||_X \to 0} \frac{||f(x+h) - f(x) - Df(x)[h]||_Y}{||h||_X} = 0
$$

- this eqivalent definition is often easier to work with:
$$
f(x + h) = f(x) + Df(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||_Y}{||h||_X} = 0
$$


### partial derivative
- given a [[function]] $f: \mathbb{R}^n \to Y$
- the [[partial derivative]] $\frac{\partial f}{\partial x_i}$ is defined as follows and mesures the rate of change of $f$ regarding the direction of die coordinate $x_i$ 

$$
\frac{\partial f}{\partial x_i}(x) = \lim_{h \to 0} \frac{f(x+h e_i) - f(x) }{h} 
$$

Tags: mathematics
<!--ID: 1715629635955-->
END


