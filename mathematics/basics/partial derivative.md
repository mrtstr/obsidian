### partial derivative
- given a [[function]] $f: \mathbb{R}^n \to Y$
- the [[partial derivative]] $\frac{\partial f}{\partial x_i}:X \to Y$ is defined as follows and mesures the rate of change of $f$ regarding the direction of die coordinate $x_i$ 

$$
\frac{\partial f}{\partial x_i}(x) = \lim_{h \to 0} \frac{f(x+h e_i) - f(x) }{h} \in Y
$$

### [[partial derivative]] to the general [[derivative]]
- given a [[function]] $f: \mathbb{R}^n \to Y$ and a point $x_0 \in X$ 
- the general [[derivative]] $Df(x_0)[h]: \mathbb{R}^n \to Y$ is a [[linear map]] approximating $f$ in the point $x_0$ and gives the rate of change in an arbitrary direction $h$
- the [[partial derivative]] in $x_0$ after a coodrinate $x_i$ gives the rate of change regarding the direction of the coordinate $x_i$
- when plugging the directional [[vector]] of the coordinate $i$  $e_i = (\begin{matrix}0 & ... & 1&0&0\end{matrix})$ in the general [[derivative]] it becomes the [[partial derivative]]
$$
Df(x_0)[e_i]:Ae_i = \frac{\partial f}{\partial x_i}(x_0) \to Y
$$

# -----------------------
![[derivative#general derivative]]

START
Basic
[[partial derivative]]
- definition and geometric interpretation
- what is the difference to the general [[derivative]]?
- can one be expressed as the other?
Back: 
### [[partial derivative]] to the general [[derivative]]
- given a [[function]] $f: \mathbb{R}^n \to Y$ and a point $x_0 \in X$ 
- the general [[derivative]] $Df(x_0)[h]: \mathbb{R}^n \to Y$ is a [[linear map]] approximating $f$ in the point $x_0$ and gives the rate of change in an arbitrary direction $h$
- the [[partial derivative]] in $x_0$ after a coodrinate $x_i$ gives the rate of change regarding the direction of the coordinate $x_i$
- when plugging the directional [[vector]] of the coordinate $i$  $e_i = (\begin{matrix}0 & ... & 1&0&0\end{matrix})$ in the general [[derivative]] it becomes the [[partial derivative]]
$$
Df(x_0)[e_i]:Ae_i = \frac{\partial f}{\partial x_i}(x_0) \to Y
$$

### partial derivative
- given a [[function]] $f: \mathbb{R}^n \to Y$
- the [[partial derivative]] $\frac{\partial f}{\partial x_i}:X \to Y$ is defined as follows and mesures the rate of change of $f$ regarding the direction of die coordinate $x_i$ 

$$
\frac{\partial f}{\partial x_i}(x) = \lim_{h \to 0} \frac{f(x+h e_i) - f(x) }{h} \in Y
$$


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


Tags: mathematics
<!--ID: 1716128307658-->
END


START
Basic
[[directional derivative]] vs [[partial derivative]]
- definitions
- difference

Back: 
#### [[directional derivative]] and [[partial derivative]]
- the [[directional derivative]] generalizes the [[partial derivative]] for an arbitrary direction $h$
	→ the [[partial derivative]] $\frac{\partial f}{\partial x_i}(x)$ is a [[directional derivative]] $D_hf(x)$ with the direction being the cordinate $i$ $h=e_i$ 
- while the [[partial derivative]] $\frac{\partial f}{\partial x_i}$ only gives the rate of change of a [[function]] $f$ in the direction of the coordinate its coodrinates the [[partial derivative]] does the same for an arbitrary direction

### partial derivative
- given a [[function]] $f: \mathbb{R}^n \to Y$
- the [[partial derivative]] $\frac{\partial f}{\partial x_i}$ is defined as follows and mesures the rate of change of $f$ regarding the direction of die coordinate $x_i$ 

$$
\frac{\partial f}{\partial x_i}(x) = \lim_{h \to 0} \frac{f(x+h e_i) - f(x) }{h} 
$$


### directional derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[directional derivative]] $D_hf(x): X \to L(X,Y)$ in point $x \in X$ in the direction of $h \in X$ is defined as follows
- like the [[derivative]] the [[function]] $D_hf(x): X \to L(X,Y)$ maps every point $x \in X$ to a [[bounded linear map]] $\in L(X, Y)$ 
- the [[directional derivative]] measures the rate at which a [[function]] changes in a particular direction at a given point

$$
D_hf(x) = \lim_{t\to0}  \frac{f(x+th) - f(x)}{t}
$$

____________________________________

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


Tags: mathematics
<!--ID: 1715629635958-->
END
