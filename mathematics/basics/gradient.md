### gradient
- let $f: \mathbb{R}^m \to \mathbb{R}^n$ be a [[function]]

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
# anki


START
Basic
definition [[gradient]]
Back: 
### gradient

- let $f: \mathbb{R}^m \to \mathbb{R}^n$ be a [[function]]

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