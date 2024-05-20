### derivative in a [[banach space]]
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

### interpretation [[derivative]]

#### [[derivative]] as a [[linear map|linear]] approximation
- given a [[function]] $f: X \to Y$ the [[derivative]]  $Df(x)[h]: X \to Y$ is a [[linear map|linear]] approximation of $f$ in the point $x \in X$ relative to the origin
- since the [[derivative]] $Df(x)[h]: X \to Y$ is an approvimation relative to the origin the following would be a [[linear map|linear]] approximation of $f$ 
$$
\widehat{f_{x}}(h) = f(x) + Df(x)[h]
$$
- for example the [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ can be expressed in a $\mathbb{R}^3$ with each point in the plain $x \in \mathbb{R}^2$ is mapped to a $y \in \mathbb{R}$
- thus the [[derivative]] $Df(x)[h]: \mathbb{R}^2 \to \mathbb{R} = Ah$ with $A \in \mathbb{R}^{1 \times 2}$ would be a plain in the $\mathbb{R}^3$

#### [[derivative]] as a rate of change in a direction
- since the [[derivative]]  $Df(x_0)[h]: X \to Y$ is a [[linear map|linear]] approximation of $f$ in the point $x_0 \in X$ relative to the origin we can calculate the **rate of change** of $f$ in a point $x_0 \in X$ in the direction $h \in X$ by plugging the [[norm|normalized]] direction in $Df(x_0)[h]$
$$
Df(x_0)\left[\frac{h}{||h||}\right]
$$
- it answers how much would $f$ change when going an infinitesimal small step in the direction (normalized) direction $h \in X$ relative to the length of the infinitesimal small step which is a rate of change
- note: for a sclar function $f$ the rate of change is a [[scalar]] but in general its element of the codomain of $f$ ($Y$)

- in the case of a [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ the [[matrix]] $A = (\nabla f)^\top \in \mathbb{R}^{1 \times 2}$ can be expressed as a [[vector]] $a = \nabla f \in \mathbb{R}^{2}$ and the rate of change becomes the [[inner product]] between the direction and the [[gradient]]
$$
Df(x)\left[\frac{h}{||h||}\right] = A\frac{h}{||h||} = \frac{\left\langle a , h \right\rangle}{||h||} = \frac{\left\langle \nabla f , h \right\rangle}{||h||} \in \mathbb{R}
$$


#### [[derivative]] as a [[projection]]
- since the [[derivative]] $Df(x_0)[h]: X \to Y, Df(x_0)[h]=Ah$ is a [[bounded linear map]] it can be expressed as a [[inner product]] of the [[matrix]] $A$ (representing the [[derivative]]) and the direction $h \in X$
- thus the [[derivative]] can be interpreted as the [[projection]] of the [[matrix]] $A$ (e.g. the [[gradient]]) on the direction $h \in X$ (in case of the normalized direction [[vector]] with $||h|| = 1$ )
$$
Df(x)[h] = \langle A, h \rangle = ||proj_h(A)|| \cdot ||h||
$$

- in the case of a [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ the [[matrix]] $A = (\nabla f)^\top \in \mathbb{R}^{1 \times 2}$ can be expressed as a [[vector]] $a = \nabla f \in \mathbb{R}^{2}$ and the rate of change becomes the [[inner product]] between the direction and the [[gradient]]

![[inner product#relationship inner product to projection]]


#### [[derivative]] as a [[vector]] in the direction of the steepest ascent
- before the forcus was on what the [[derivative]] $Df(x_0)[h]: X \to Y, Df(x_0)[h]=Ah$ does, but now we will focus thee properties of $A$ itself
- we know that the $Df(x_0)[h]=Ah = \langle A, h \rangle = ||proj_h(A)|| \cdot ||h||$ is the rate of change in the direction $h$ and the length of the [[projection]] of $A$ on the direction $h$
- from the [[cauchy schwarz inequality]] we know that the length of the [[projection]] of $A$ on any $h$ is less pr equal then the length of $A$ itself $||proj_h(A)|| \leq ||A||$ with a maximum reachen at $h = A$ 
$$
\begin{split}
arg\max_{||h||=1} \langle A, h \rangle 
&= \frac{A}{||A||} \\ 
\max_{||h||=1} \langle A, h \rangle 
&= \frac{\langle A, A \rangle }{||A||}
&= \frac{||A||^2}{||A||} = ||A||  \\
\end{split}
$$

![[inner products and norms#every inner product induces a norm]]

![[cauchy schwarz inequality#geometric interpreation cauchy schwarz inequality]]

![[cauchy schwarz inequality#cauchy schwarz inequality]]
- generally the [[derivative]] $Df(x_0)[h]: X \to Y$ defines [[linear map]] from $X$ to $Y$ for every point $x_0 \in X$
- $Df(x_0)[h]: X \to Y$ gives the rate of change 
- in case of a [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ with [[derivative]] $Df(x)[h] = Ah = \langle \nabla f, h \rangle$ with $A \in \mathbb{R}^{1 \times 2}$ defines 
- $\nabla f \in \mathbb{R}^2$ is a [[vector]] in the domain of $f$ (in the case the plain) that has a **direction** and a **length**
- the **direction** is the direction of the steepest ascent of $f$ in point $x$ while the **length** descibes the rate of change in this direction
- in the case of $f: \mathbb{R}^2 \to \mathbb{R}$ it is easy to see that this is defining a plain $\in \mathbb{R}^3$ with the longer the [[vector]] $\nabla f \in \mathbb{R}^2$ the more tilted the plain

### [[directional derivative]] and [[partial derivative]]
- the [[directional derivative]] generalizes the [[partial derivative]] for an arbitrary direction $h$
	→ the [[partial derivative]] $\frac{\partial f}{\partial x_i}(x)$ is a [[directional derivative]] $D_hf(x)$ with the direction being the cordinate $i$ $h=e_i$ 
- while the [[partial derivative]] $\frac{\partial f}{\partial x_i}$ only gives the rate of change of a [[function]] $f$ in the direction of the coordinate its coodrinates the [[partial derivative]] does the same for an arbitrary direction

![[partial derivative#partial derivative]]

### [[directional derivative]] and [[differentiabe|differentiability]]
- every [[differentiabe]] [[function]] has a [[directional derivative]] in all directions because the [[directional derivative]] can be constructed from the [[gradient]]
- but not every [[function]] that has [[directional derivative]] in all directions is [[differentiabe]]
- the following [[function]] $f(x, y)$ is not [[differentiabe]] in point $(0,0)$
$$
f(x, y) = \left\{ 
\begin{split} 
&0 & \text{for } (x,y) = (0,0) \\ 
&\frac{x}{x^2 + y^2} \qquad& \text{for } (x,y) \neq (0,0)
\end{split} \right.
$$

### [[partial derivative]] example
- given a [[function]] $f$ with the [[gradient]] $\nabla f$ what is the [[directional derivative]] is the direction $h$?

$$
\nabla f = \left(\begin{matrix} a \\ b \\ c \end{matrix}\right)
$$
$$
h = \left(\begin{matrix} 1 \\ 1 \\ 0 \end{matrix}\right)
$$

$$
D_hf(x) = h \nabla f  = \left(\begin{matrix} a \\ b \\ 0 \end{matrix}\right)
$$



### examples

#### $f: \mathbb{R} \to \mathbb{R}, f(x) = 3x^2$
- the [[derivative]] $Df(x)[h]: \mathbb{R} \to L( \mathbb{R},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}$ to the $\mathbb{R}$ and $H \in \mathbb{R}$
$$
f(x + h) = f(x) + ah + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{\varphi(h)}{h} = 0 
$$
$$
\begin{split}
f(x + h) = 3(x+h)^2 = \underbrace{3x^2}_{f(x)} + \underbrace{3h^2}_{\varphi(h)} + \underbrace{6hx}_{Df(x)[h]}
\end{split}
$$
- $\varphi(h)$ converges fast enough against 0
$$
\lim_{h \to 0} \frac{\varphi(h)}{h} = \lim_{h \to 0} \frac{3h^2}{h}  = 0 
$$
- so the [[derivative]] in the point $x$ and in the direction $h$ is given as $Df(x)[h] = 6hx$ 


#### $f: \mathbb{R}^{n \times m} \to \mathbb{R}^{n \times n}, f(X) = XX^\top$

- the [[derivative]] $Df(X)[H]: X \to L( \mathbb{R}^{n \times m},  \mathbb{R}^{n \times n})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{n \times m}$ to the $\mathbb{R}^{n \times n}$ and $H \in \mathbb{R}^{n \times m}$
- from the definition we know the following:
$$
f(X + H) = f(X) + AH + \varphi(H) \quad \text{with} \quad \lim_{H \to 0} \frac{||\varphi(H)||_Y}{||H||_X} = 0 
$$
- the [[derivative]] $Df(X)[H] = XH^\top + HX^\top \in L( \mathbb{R}^{n \times m},  \mathbb{R}^{n \times n})$ is a [[bounded linear map]] 
$$
\begin{split}
f (X + H) 
&= \left(X + H\right)\left(X + H\right)^\top \\
&= \underbrace{XX^\top}_{f(X)} + \underbrace{HH^\top}_{\varphi(H)} +  \underbrace{XH^\top + HX^\top}_{Df(X)[H]}  \\
\end{split}
$$
- we only need to show that $\varphi(H) = HH^\top$ is [[convergence|converging]] fast enough
$$
\begin{split}
\frac{||\varphi(H)||}{||H||}
&= \frac{||HH^\top||}{||H||} \\
&\leq \frac{||H||||H^\top||}{||H||} 
&=||H^\top|| \\
||H^\top|| &\xrightarrow{H \to 0} 0
\end{split}
$$

![[operator norm#the operator norm is submultiplicative]]

# --------------------
![[bounded linear map#bounded linear map]]

![[banach space#banach spaces]]

![[norm#norm]]

### derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
# --------------------

### elementary derivative rules of differentiation


![[linearity of the derivative#linear function linearity of the derivative]]

![[product rule of derivative#multiplication product rule for derivative]]

![[chain rule of derivative#composition chain rule for derivative]]

![[inverse rule of derivative#inverse function inverse rule for derivative]]

### [[derivative]] laws

![[power rule for derivative#elementary power rulelinearity of the derivative]]

![[qutient rule for derivative#qutient rule for derivative]]

![[reciprocal rule for the derivative#reciprocal rule for derivative]]

![[derivative of exponential function#exponential rule for derivative]]
# anki
START
Basic
[[derivative]]
- definition
- elementary rules of differentiation (5 no proof)

Back: 

## Definition
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$

## elementary rules of differentiation
### derivative of a constant
$$
\begin{split}
f(x) &= c \\
\frac{df(x)}{dx} &= 0
\end{split}
$$
proof:
$$
\begin{split}
\frac{df(x)}{dx} 
&= \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h} \\
&= \lim_{h \rightarrow 0} \frac{c - c}{h} \\
&= 0 \\
\end{split}
$$
### linearity of the derivative
$$
\frac{d\left(af(x) + bg(x)\right)}{dx} = a \frac{df(x)}{dx} + b \frac{dg(x)}{dx}
$$
proof:
$$
\begin{split}
\frac{d\left(af(x) + bg(x)\right)}{dx} 
&= \lim_{h \rightarrow 0} \frac{af(x + h) + bg(x + h) - \left(af(x) + bg(x)\right)}{h} \\
&= \lim_{h \rightarrow 0} \frac{a\left(f(x + h) - f(x)\right) + b\left(g(x + h) - g(x)\right)}{h} \\
&= \lim_{h \rightarrow 0} a \frac{f(x + h) - f(x)}{h} + b \frac{g(x + h) - g(x)}{h} \\
&= a \lim_{h \rightarrow 0} \frac{f(x + h) -  f(x)}{h} + b \lim_{h \rightarrow 0} \frac{g(x + h) - g(x)}{h} \\
&= a \frac{df(x)}{dx} + b \frac{dg(x)}{dx} \\
\end{split}
$$

### [[product rule of derivative]]
$$
\frac{d\left(f(x) \cdot g(x)\right)}{dx} 
= f(x)\frac{dg(x)}{dx} + g(x) \frac{df(x)}{dx}
$$
proof:
$$
\begin{split}
\frac{d\left(f(x) \cdot g(x)\right)}{dx} 
&= \lim_{h \rightarrow 0} \frac{f(x+h) g(x+h) - f(x) g(x)}{h} \\
&= \lim_{h \rightarrow 0} \frac{
f(x+h) g(x+h) - f(x) g(x) + f(x+h)g(x) - f(x+h)g(x)
}{h} \\
&= \lim_{h \rightarrow 0} \frac{
f(x+h) \left(g(x+h) - g(x)\right) + g(x) \left(f(x+h) - g(x)\right)
}{h} \\
&= \frac{df(x)}{dx} \cdot g(x) + \frac{dg(x)}{dx} \cdot \lim_{h \rightarrow 0} f(x+h)  \\
&=  \frac{df(x)}{dx} g(x) + \frac{dg(x)}{dx}f(x) 
\end{split}
$$

### [[chain rule of derivative]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$
intuition:
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$
### [[inverse rule of derivative]]

$$
\frac{df^{-1(y)}}{dy} = \frac{1}{\frac{df\left(f^{-1}(y)\right)}{df^{-1}(y)}}
$$
proof:
$$
\begin{split}
\frac{dy}{dy} 
&= 1 \\
&= \frac{df\left(f^{-1}(y)\right)}{dy}  \qquad &\text{definition inverse} \\
&= \frac{df\left(f^{-1}(y)\right)}{df^{-1}(y)} \cdot \frac{df^{-1(y)}}{dy} \qquad &\text{chain rule} \\
\Rightarrow \frac{df^{-1(y)}}{dy} &= \frac{1}{\frac{df\left(f^{-1}(y)\right)}{df^{-1}(y)}}
\end{split}
$$

### [[derivative of exponential function]]
$$
\frac{dc^{ax}}{dx} = c^{ax} a \ln(c)
$$


$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
proof
$$
\begin{split}
\frac{dc^{x}}{dx} 
&= \lim_{h \rightarrow 0} \frac{c^{x + h} - c^x}{h} \\
&= \lim_{h \rightarrow 0} \frac{c^{x}c^{h} - c^x}{h} \\
&= \lim_{h \rightarrow 0} \frac{c^{x}\left(c^{h} - 1\right)}{h} \\
&= c^x \lim_{h \rightarrow 0} \frac{c^{h} - 1}{h} \\
&= c^x \ln(c)  \quad \quad \text{ln limit identity} \\ 
\\ \\
\frac{dc^{ax}}{dx} 
&= \frac{d(c^{x})^a}{dx} \\
&= \frac{d(c^{x})^a}{dc^{x}} \cdot \frac{dc^{x}}{dx} \quad \quad \text{chain rule} \\
&= a c^{x(a-1)}  \cdot  \frac{dc^{x}}{dx} \quad \quad \text{exponent rule} \\ 
&= a c^{x(a-1)}  \cdot  c^x \ln(c)  \\ 
&= a c^{xa} \ln(c)  \\ 

\end{split}
$$


Tags: mathematics
<!--ID: 1686036924132-->
END


START
Basic
derivative in a [[banach space]]
- definition (2 versions)
- what kind of function is it?

Back: 
### derivative in a [[banach space]]
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[bounded linear map]] $A \in L(X, Y)$ is the [[derivative]] of $f$ in point $x \in X$ is the following is true
$$
\lim_{||h||_X \to 0} \frac{||f(x+h) - f(x) - Ah||_Y}{||h||_X} = 0
$$
- for every point $x \in X$ we will get a different [[bounded linear map]] $A: X \to Y$
- the [[derivative]] $Df: X \to L(X,Y)$ is a [[function]] that maps elements of $X$ to a [[bounded linear map]]
$$
A=Df(x) \in L(X,Y)
$$
- this eqivalent definition is often easier to work with:
$$
f(x + h) = f(x) + Ah + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||_Y}{||h||_X} = 0
$$
___________________
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
<!--ID: 1715629635966-->
END


START
Basic
calculate the [[derivative]] of the [[function]] $f: \mathbb{R}^{n \times m} \to \mathbb{R}^{n \times n}, f(X) = XX^\top$


Back: 
#### $f: \mathbb{R}^{n \times m} \to \mathbb{R}^{n \times n}, f(X) = XX^\top$

- this the [[derivative]] $Df(X)[H]: X \to L( \mathbb{R}^{n \times m},  \mathbb{R}^{n \times n})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{n \times m}$ to the $\mathbb{R}^{n \times n}$ and $H \in \mathbb{R}^{n \times m}$
- from the definition we know the following:

$$
f(X + H) = f(X) + AH + \varphi(H) \quad \text{with} \quad \lim_{H \to 0} \frac{||\varphi(H)||_Y}{||H||_X} = 0 
$$

- the [[derivative]] $Df(X)[H] = XH^\top + HX^\top \in L( \mathbb{R}^{n \times m},  \mathbb{R}^{n \times n})$ is a [[bounded linear map]] 

$$
\begin{split}
f (X + H) 
&= \left(X + H\right)\left(X + H\right)^\top \\
&= \underbrace{XX^\top}_{f(X)} + \underbrace{HH^\top}_{\varphi(H)} +  \underbrace{XH^\top + HX^\top}_{Df(X)[H]}  \\
\end{split}
$$

- we only need to show that $\varphi(H) = HH^\top$ is [[convergence|converging]] fast enough 
- (using the fact the [[operator norm]] is submultiplicative)

$$
\begin{split}
\frac{||\varphi(H)||}{||H||}
&= \frac{||HH^\top||}{||H||} \\
&\leq \frac{||H||||H^\top||}{||H||} 
&=||H^\top|| \\
||H^\top|| &\xrightarrow{H \to 0} 0
\end{split}
$$

### the [[operator norm]] is submultiplicative
- given two [[linear map|linear maps]] $A: X \to Y$ and $B: Y \to Z$ the following inequallity holds true
$$
||BA||_{X \to Z} \leq ||A||_{X \to Y} ||B||_{Y \to Z}
$$
 $$
 \begin{split}
||BA||_{X \to Z} 
&= \sup_{x\neq 0} \frac{||BAx||_Z}{||x||_X} \\
&= \sup_{x\neq 0, Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{X \to Y}}  \frac{||Ax||_Y}{||x||_X} \\
&\leq \sup_{Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X} \\
&= \sup_{y \neq 0} \frac{||By||_Z}{||y||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X}  \\
&= ||A||_{X \to Y} ||B||_{Y \to Z}
\end{split}
$$

___________________

### operator norm
- an [[operator norm]] is a [[norm]] in a [[function space]] that is induced by the [[norm|norms]] of the [[domain]] and codomain [[banach space]]
- given two [[banach space|banach spaces]] $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ and a [[linear map]] $A: X\rightarrow Y$
$$
||A||_{X \rightarrow Y} = \inf\{C \geq 0: ||Ax||_Y \leq C ||x||_X\}
$$
- for a nonempty [[domain]] $X \neq \emptyset$ the [[operator norm]] can be exapressed as follows.
 $$
||A||_{X \rightarrow Y} = \sup_{x\neq 0} \frac{||Ax||_Y}{||x||_X} = \sup_{||x||_X = 1} ||Ax||_Y
$$

### derivative in a [[banach space]]
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[bounded linear map]] $A \in L(X, Y)$ is the [[derivative]] of $f$ in point $x \in X$ is the following is true
$$
\lim_{||h||_X \to 0} \frac{||f(x+h) - f(x) - Ah||_Y}{||h||_X} = 0
$$
- for every point $x \in X$ we will get a different [[bounded linear map]] $A: X \to Y$
- the [[derivative]] $Df: X \to L(X,Y)$ is a [[function]] that maps elements of $X$ to a [[bounded linear map]]
$$
A=Df(x) \in L(X,Y)
$$
- this eqivalent definition is often easier to work with:
$$
f(x + h) = f(x) + Ah + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||_Y}{||h||_X} = 0
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
<!--ID: 1716139877291-->
END


START
Basic
calculate the [[derivative]] of the [[function]] $f: \mathbb{R} \to \mathbb{R}, f(x) = 3x^2$ using the full definition

Back: 
#### $f: \mathbb{R} \to \mathbb{R}, f(x) = 3x^2$
- the [[derivative]] $Df(x)[h]: \mathbb{R} \to L( \mathbb{R},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}$ to the $\mathbb{R}$ and $H \in \mathbb{R}$
$$
f(x + h) = f(x) + ah + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{\varphi(h)}{h} = 0 
$$
$$
\begin{split}
f(x + h) = 3(x+h)^2 = \underbrace{3x^2}_{f(x)} + \underbrace{3h^2}_{\varphi(h)} + \underbrace{6hx}_{Df(x)[h]}
\end{split}
$$
- $\varphi(h)$ converges fast enough against 0
$$
\lim_{h \to 0} \frac{\varphi(h)}{h} = \lim_{h \to 0} \frac{3h^2}{h}  = 0 
$$
- so the [[derivative]] in the point $x$ and in the direction $h$ is given as $Df(x)[h] = 6hx$ 


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
A=Df(x) \in L(X,Y)
$$
- this eqivalent definition is often easier to work with:
$$
f(x + h) = f(x) + Ah + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||_Y}{||h||_X} = 0
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

Tags: mathematics
<!--ID: 1716141626057-->
END