
### directional derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- given a direction  $h \in X$ the [[directional derivative]] $D_hf(x): X \to Y$ mesures the rate at which $f$ is changing in point $x$ when going an infinesesimal small step in the direction $h$ and is defined as follows
$$
D_hf(x) = \lim_{t\to0}  \frac{f(x+th) - f(x)}{t} = Df(x)[h]
$$
- the [[directional derivative]] is equal to the general [[derivative]] $Df(x)[h]$ when plugging in a constant direction $h$


### [[directional derivative]] and [[differentiable|differentiability]]
- every [[differentiable]] [[function]] has a [[directional derivative]] in all directions because the [[directional derivative]] can be constructed from the [[gradient]]
- but not every [[function]] that has [[directional derivative]] in all directions is [[differentiable]]
- the following [[function]] $f(x, y)$ is not [[differentiable]] in point $(0,0)$
$$
f(x, y) = \left\{ 
\begin{split} 
&0 & \text{for } (x,y) = (0,0) \\ 
&\frac{x}{x^2 + y^2} \qquad& \text{for } (x,y) \neq (0,0)
\end{split} \right.
$$

# ------------------
![[derivative#general derivative]]


START
Basic
[[directional derivative]]
- definition
- concept
- difference to the general [[derivative]]
Back: 
### directional derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- given a direction  $h \in X$ the [[directional derivative]] $D_hf(x): X \to Y$ mesures the rate at which $f$ is changing in point $x$ when going an infinesesimal small step in the direction $h$ and is defined as follows
$$
D_hf(x) = \lim_{t\to0}  \frac{f(x+th) - f(x)}{t} = Df(x)[h]
$$
- the [[directional derivative]] is equal to the general [[derivative]] $Df(x)[h]$ when plugging in a constant direction $h$


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
<!--ID: 1716218737219-->
END


