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
- note: for a sclar function $f$ the rate of change is a [[scalar]] but in general its element of the codomain of $f$ (in this case: $Y$)

- in the case of a [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ the [[matrix]] $A = (\nabla f)^\top \in \mathbb{R}^{1 \times 2}$ can be expressed as a [[vector]] $a = \nabla f \in \mathbb{R}^{2}$ and the rate of change becomes the [[inner product]] between the direction and the [[gradient]]
$$
Df(x)\left[\frac{h}{||h||}\right] = A\frac{h}{||h||} = \frac{\left\langle a , h \right\rangle}{||h||} = \frac{\left\langle \nabla f , h \right\rangle}{||h||} \in \mathbb{R}
$$


#### [[derivative]] as a [[projection]]
- let's assume that $f: \mathbb{R}^m \to \mathbb{R}$ and thus $h, A^\top \in \mathbb{R}^m$ 
- since the [[derivative]] $Df(x_0)[h]=Ah$ is a [[bounded linear map]] it can be expressed as a [[inner product]] of the [[matrix]] $A$ (representing the [[derivative]]) and the direction $h \in X$
- thus the [[derivative]] can be interpreted as the [[projection]] of the [[matrix]] $A$ (e.g. the [[gradient]]) on the direction $h \in X$ (in case of the normalized direction [[vector]] with $||h|| = 1$)
$$
Df(x)[h] = Ah =\langle A^\top, h \rangle = ||proj_h(A^\top)|| \cdot ||h||
$$

- this result can be generalized for a function $f: \mathbb{R}^m \to \mathbb{R}^n$ by treating $f$ as $n$ scalar functions $f_i$ 

![[inner product#relationship inner product to projection]]


#### [[derivative]] as a [[vector]] in the direction of the steepest ascent
- before the forcus was on what the [[derivative]] $Df(x_0)[h]: X \to Y, Df(x_0)[h]=Ah$ does, but now we will focus thee properties of $A$ itself
- let's assume that $f: \mathbb{R}^m \to \mathbb{R}$ and thus $h, A^\top \in \mathbb{R}^m$ 
- we know that the [[derivative]] $Df(x_0)[h]=Ah = \langle A^\top, h \rangle = ||proj_h(A^\top)|| \cdot ||h||$ is the rate of change in the direction $h$ and the length of the [[projection]] of $A$ on the direction $h$
- from the [[cauchy schwarz inequality]] we know that the length of the [[projection]] of $A^\top$ on any $h$ is less or equal then the length of $A^\top$ itself with a maximum reachen at $h = A^\top$ 
$$
||proj_h(A^\top)|| \leq ||A^\top||
$$
- thus the [[vector]] $\frac{A^\top}{||A^\top||}$ is pointing in the direction of the steepest ascent
$$
\begin{split}
arg\max_{||h||=1} ||proj_h\left(A^\top\right)|| 
=arg\max_{||h||=1} \langle A^\top, h \rangle 
&= \frac{A^\top}{||A^\top||} \\ 
\end{split}
$$
- to get the rate of change in the direction of the steepest asecent we can just plug $h^* = \frac{A^\top}{||A^\top||}$ it into the [[derivative]] to see that the steepest rate if ascent is equal to the length of the [[vector]] $A^\top$
$$
Df(x)\left[\frac{A^\top}{||A^\top||}\right] = \frac{AA^\top}{||A^\top||} = \frac{\langle A, A \rangle}{||A^\top||} = \frac{||A^\top||^2}{||A^\top||} = ||A^\top||\in \mathbb{R}
$$
- this result can be generalized for a function $f: \mathbb{R}^m \to \mathbb{R}^n$ by treating $f$ as $n$ scalar functions $f_i$ 

### ------------------
![[inner products and norms#every inner product induces a norm]]

![[cauchy schwarz inequality#geometric interpreation cauchy schwarz inequality]]

![[cauchy schwarz inequality#cauchy schwarz inequality]]



### examples

#### $f: \mathbb{R} \to \mathbb{R}, f(x) = 3x^2$
- the [[derivative]] $Df(x)[h]: \mathbb{R} \to L( \mathbb{R},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}$ to the $\mathbb{R}$ thus
$$
f(x + h) = f(x) + Df(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{\varphi(h)}{h} = 0 
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
- for a [[function]] $f: \mathbb{R} \to \mathbb{R}$ the [[derivative]] for different directions does not make sense so with $h=1$ we have $Df(x) = 6x$ 

#### $f: \mathbb{R}^{n \times m} \to \mathbb{R}^{n \times n}, f(X) = XX^\top$

- the [[derivative]] $Df(X)[H]: X \to L( \mathbb{R}^{n \times m},  \mathbb{R}^{n \times n})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{n \times m}$ to the $\mathbb{R}^{n \times n}$ and $H \in \mathbb{R}^{n \times m}$
- from the definition we know the following:
$$
f(X + H) = f(X) + Df(X)[H] + \varphi(H) \quad \text{with} \quad \lim_{H \to 0} \frac{||\varphi(H)||_Y}{||H||_X} = 0 
$$

$$
\begin{split}
f (X + H) 
&= \left(X + H\right)\left(X + H\right)^\top \\
&= \underbrace{XX^\top}_{f(X)} + \underbrace{HH^\top}_{\varphi(H)} +  \underbrace{XH^\top + HX^\top}_{Df(X)[H]}  \\
\end{split}
$$
- to show that $Df(X)[H] = XH^\top + HX^\top \in L( \mathbb{R}^{n \times m},  \mathbb{R}^{n \times n})$ is the [[derivative]]  we only need to show that $\varphi(H) = HH^\top$ is [[convergence|converging]] fast enough
-  (using the fact the [[operator norm]] is submultiplicative)
$$
\begin{split}
\frac{||\varphi(H)||}{||H||}
&= \frac{||HH^\top||}{||H||} \\
&\leq \frac{||H||||H^\top||}{||H||} 
&=||H^\top|| \\
||H^\top|| &\xrightarrow{H \to 0} 0
\end{split}
$$



#### $F(A): \mathbb{R}^{n \times m} \to \mathbb{R} = \frac{1}{2}||Ax -b||_2^2$
- the [[derivative]] $DF(A)[H]: \mathbb{R}^{n \times m} \to L( \mathbb{R}^{n \times m},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{n \times m}$ to $\mathbb{R}$ with $H \in \mathbb{R}^{n \times m}$
- from the definition we know the following:
$$
F(A + H) = f(X) + DF(A)[H] + \varphi(H) \quad \text{with} \quad \lim_{H \to 0} \frac{||\varphi(H)||}{||H||} = 0 
$$


$$
\begin{split}
F (X + H) 
&= \frac{1}{2}||(A+H)x -b||_2^2 \\
&= \frac{1}{2}\langle (Ax -b) + Hx, (Ax -b) + Hx\rangle \\
&= \frac{1}{2}\langle Ax -b, Ax -b\rangle + \frac{1}{2}\langle Hx, Hx\rangle + \langle Ax -b, Hx\rangle \\
&= \underbrace{\frac{1}{2}||Ax-b||_2^2}_{f(X)} + \underbrace{\frac{1}{2}||Hx||_2^2}_{\varphi(H)} +  \underbrace{\langle Ax -b, Hx \rangle}_{Df(X)[H]}  \\
\end{split}
$$

- show that $\varphi(H)$ is converging fast enough

$$
\begin{split}
\frac{\varphi(H)}{||H||} 
&= \frac{1}{2} \frac{||Hx||^2}{||H||} \\
&= \frac{1}{2} \frac{1}{||H||}  \frac{||Hx||^2 ||x||^2}{||x||^2} \\
&= \frac{1}{2}  \frac{||x||^2}{||H||} \frac{||Hx||^2 }{||x||^2} \\
&\leq \frac{1}{2}  \frac{||x||^2}{||H||} \sup_{||y|| \neq 0} \frac{||Hy||^2 }{||y||^2} \\
&= \frac{1}{2}  \frac{||x||^2}{||H||} ||H||^2 \\
&= \frac{1}{2} ||H|| \cdot ||x||^2 \xrightarrow{H \to 0} 0 \\
\end{split}
$$

- a [[scalar]] is its own [[trace]] and $\mathrm{trace}(AB) = \mathrm{trace}(BA)$


$$
\begin{split}
DF(A)[H] 
&= \langle Ax -b, Hx \rangle \\
&= \left(Ax -b\right)^\top Hx \\
&= trace\left(\left(Ax -b\right)^\top Hx\right) \\
&= trace\left(x\left(Ax -b\right)^\top H\right) \\
&= trace\left(x\left(x^\top A^\top  -b^\top\right) H\right) \\
&= trace\left(\left(xx^\top A^\top  -xb^\top\right) H\right) \\
&= \left\langle\left(xx^\top A^\top  -xb^\top\right)^\top, H \right\rangle_F \\
DF(A)
&= \left(xx^\top A^\top  -xb^\top\right)^\top\\
\nabla F(A)
&= xx^\top A^\top  -xb^\top\\
\end{split}
$$


#### $f(x) = x^\top Ax$

$$
\begin{split}
DF(A)[H] 
&= h^\top A x + x^\top A h \\
&= \left\langle h, Ax \right\rangle + \left\langle\left(x^\top A \right)^\top , h \right\rangle \\
&= \left\langle Ax, h  \right\rangle + \left\langle\left(x^\top A \right)^\top , h \right\rangle \\
DF(A)&= (Ax)^\top + x^\top A\\
\nabla F(A)
&= Ax + A^\top x \\
\end{split}
$$

![[trace#trace]]

![[frobenius inner product#frobenius inner product]]

#### $F(x): \mathbb{R}^{m} \to \mathbb{R} = \frac{1}{2}||Ax -b||_2^2$
- the [[derivative]] $DF(x)[h]: \mathbb{R}^{m} \to L( \mathbb{R}^{m},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{m}$ to $\mathbb{R}$ with $h \in \mathbb{R}^{m}$
- from the definition we know the following:
$$
F(x + h) = F(x) + DF(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||}{||h||} = 0 
$$


$$
\begin{split}
F (x + h) 
&= \frac{1}{2}||A(x+h) -b||_2^2 \\
&= \frac{1}{2}\langle (Ax -b) + Ah, (Ax -b) + Ah\rangle \\
&= \frac{1}{2}\langle Ax -b, Ax -b\rangle + \frac{1}{2}\langle Ah, Ah\rangle + \langle Ax -b, Ah\rangle \\
&= \underbrace{\frac{1}{2}||Ax-b||_2^2}_{f(X)} + \underbrace{\frac{1}{2}||Ah||_2^2}_{\varphi(H)} +  \underbrace{\langle Ax -b, Ah \rangle}_{Df(x)[h]}  \\
\end{split}
$$

- show that $\varphi(h)$ is converging fast enough

$$
\begin{split}
\frac{\varphi(h)}{||h||} 
&= \frac{1}{2} \frac{||Ah||^2}{||h||} \\
&= \frac{1}{2} ||h|| \frac{||Ah||^2}{||h||^2} \\
&= \frac{1}{2} ||h|| \left(\frac{||Ah||}{||h||}\right)^2 \\
&\leq \frac{1}{2} ||h|| \left(\sup_{||y|| \neq 0}\frac{||Ay||}{||y||}\right)^2 \\
&= \frac{1}{2} ||h|| \cdot ||A||^2 \xrightarrow{h \to 0} 0 \\
\end{split}
$$


$$
\begin{split}
Df(x)[h] 
&= \langle Ax -b, Ah \rangle \\
&= \left(Ax -b\right)^\top Ah \\
Df(x)
&= \left(Ax -b\right)^\top A \\
\nabla f (x)
&= \left(\left(Ax -b\right)^\top A\right)^\top \\
&= A^\top\left(Ax -b\right)  \\
\end{split}
$$

#### $F(b): \mathbb{R}^{m} \to \mathbb{R} = \frac{1}{2}||Ax -b||_2^2$
- the [[derivative]] $DF(b)[h]: \mathbb{R}^{m} \to L( \mathbb{R}^{m},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{m}$ to $\mathbb{R}$ with $h \in \mathbb{R}^{m}$
- from the definition we know the following:
$$
F(b + h) = F(b) + DF(b)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||}{||h||} = 0 
$$


$$
\begin{split}
F (b + h) 
&= \frac{1}{2}||Ax -b -h||_2^2 \\
&= \frac{1}{2}\langle (Ax -b) -h, (Ax -b) -h\rangle \\
&= \frac{1}{2}\langle Ax -b, Ax -b\rangle + \frac{1}{2}\langle h, h\rangle - \langle Ax -b, h\rangle \\
&= \underbrace{\frac{1}{2}||Ax-b||_2^2}_{f(X)} + \underbrace{\frac{1}{2}||h||_2^2}_{\varphi(H)} +  \underbrace{-\langle Ax -b, h \rangle}_{Df(x)[h]}  \\
\end{split}
$$

- show that $\varphi(h)$ is converging fast enough

$$
\begin{split}
\frac{\varphi(h)}{||h||} 
&= \frac{1}{2} \frac{||h||^2}{||h||} \\
&= \frac{1}{2} ||h||  \xrightarrow{h \to 0} 0 \\
\end{split}
$$



$$
\begin{split}
Df(x)[h] &= -\langle Ax -b, h \rangle \\
Df(x) &= -(Ax -b)^\top \\
\nabla f(x) &= -(Ax -b) \\
\end{split}
$$

# --------------------

![[operator norm#the operator norm is submultiplicative]]

![[bounded linear map#bounded linear map]]

![[banach space#banach spaces]]

![[norm#norm]]

### derivative for $f: \mathbb{R} \to \mathbb{R}$
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
# --------------------

#### elementary derivative rules of differentiation


![[product rule of derivative#multiplication product rule for derivative]]

![[chain rule of derivative#composition chain rule for derivative]]

![[inverse rule of derivative#inverse function inverse rule for derivative]]

#### [[derivative]] laws

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
general derivative
- definition (2 versions)
- what kind of function is it?

Back: 
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

- the [[derivative]] $Df(X)[H]: X \to L( \mathbb{R}^{n \times m},  \mathbb{R}^{n \times n})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{n \times m}$ to the $\mathbb{R}^{n \times n}$ and $H \in \mathbb{R}^{n \times m}$
- from the definition we know the following:
$$
f(X + H) = f(X) + Df(X)[H] + \varphi(H) \quad \text{with} \quad \lim_{H \to 0} \frac{||\varphi(H)||_Y}{||H||_X} = 0 
$$

$$
\begin{split}
f (X + H) 
&= \left(X + H\right)\left(X + H\right)^\top \\
&= \underbrace{XX^\top}_{f(X)} + \underbrace{HH^\top}_{\varphi(H)} +  \underbrace{XH^\top + HX^\top}_{Df(X)[H]}  \\
\end{split}
$$
- to show that $Df(X)[H] = XH^\top + HX^\top \in L( \mathbb{R}^{n \times m},  \mathbb{R}^{n \times n})$ is the [[derivative]]  we only need to show that $\varphi(H) = HH^\top$ is [[convergence|converging]] fast enough
$$
\begin{split}
\frac{||\varphi(H)||}{||H||}
&= \frac{||HH^\top||}{||H||} \\
&\leq \frac{||H||||H^\top||}{||H||} 
&=||H^\top|| \\
||H^\top|| &\xrightarrow{H \to 0} 0
\end{split}
$$

- (using the fact the [[operator norm]] is submultiplicative)

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

Tags: mathematics
<!--ID: 1716139877291-->
END


START
Basic
calculate the [[derivative]] of the [[function]] $f: \mathbb{R} \to \mathbb{R}, f(x) = 3x^2$ using the general definition

Back: 
#### $f: \mathbb{R} \to \mathbb{R}, f(x) = 3x^2$
- the [[derivative]] $Df(x)[h]: \mathbb{R} \to L( \mathbb{R},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}$ to the $\mathbb{R}$ thus
$$
f(x + h) = f(x) + Df(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{\varphi(h)}{h} = 0 
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
- for a [[function]] $f: \mathbb{R} \to \mathbb{R}$ the [[derivative]] for different directions does not make sense so with $h=1$ we have $Df(x) = 6x$ 


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


### derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$

Tags: mathematics
<!--ID: 1716141626057-->
END



START
Basic
- geometric interpretation of the [[derivative]] $Df(x)[h]: X \to Y$
- with example for $f: \mathbb{R}^2 \to \mathbb{R}$
Back: 

#### [[derivative]] as a [[linear map|linear]] approximation
- given a [[function]] $f: X \to Y$ the [[derivative]]  $Df(x)[h]: X \to Y$ is a [[linear map|linear]] approximation of $f$ in the point $x \in X$ relative to the origin
- since the [[derivative]] $Df(x)[h]: X \to Y$ is an approvimation relative to the origin the following would be a [[linear map|linear]] approximation of $f$ 
$$
\widehat{f_{x}}(h) = f(x) + Df(x)[h]
$$
- for example the [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ can be expressed in a $\mathbb{R}^3$ with each point in the plain $x \in \mathbb{R}^2$ is mapped to a $y \in \mathbb{R}$
- thus the [[derivative]] $Df(x)[h]: \mathbb{R}^2 \to \mathbb{R} = Ah$ with $A \in \mathbb{R}^{1 \times 2}$ would be a plain in the $\mathbb{R}^3$



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
<!--ID: 1716210599096-->
END



START
Basic
- given a general [[function]] $f: X \to Y$ and its [[derivative]] $Df(x)[h]$
- how to calculate the rate of cange of $f$ in a point $x_0 \in X$ in a arbitrary direction?
- is the rate of change a [[scalar]] or a [[vector]]?
- with example $f: \mathbb{R}^2 \to \mathbb{R}$
Back:
#### [[derivative]] as a rate of change in a direction
- since the [[derivative]]  $Df(x_0)[h]: X \to Y$ is a [[linear map|linear]] approximation of $f$ in the point $x_0 \in X$ relative to the origin we can calculate the **rate of change** of $f$ in a point $x_0 \in X$ in the direction $h \in X$ by plugging the [[norm|normalized]] direction in $Df(x_0)[h]$
$$
Df(x_0)\left[\frac{h}{||h||}\right]
$$
- it answers how much would $f$ change when going an infinitesimal small step in the direction (normalized) direction $h \in X$ relative to the length of the infinitesimal small step which is a rate of change
- note: for a sclar function $f$ the rate of change is a [[scalar]] but in general its element of the codomain of $f$ (in this case: $Y$)

- in the case of a [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ the [[matrix]] $A = (\nabla f)^\top \in \mathbb{R}^{1 \times 2}$ can be expressed as a [[vector]] $a = \nabla f \in \mathbb{R}^{2}$ and the rate of change becomes the [[inner product]] between the direction and the [[gradient]]
$$
Df(x)\left[\frac{h}{||h||}\right] = A\frac{h}{||h||} = \frac{\left\langle a , h \right\rangle}{||h||} = \frac{\left\langle \nabla f , h \right\rangle}{||h||} \in \mathbb{R}
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

#### [[derivative]] as a [[linear map|linear]] approximation
- given a [[function]] $f: X \to Y$ the [[derivative]]  $Df(x)[h]: X \to Y$ is a [[linear map|linear]] approximation of $f$ in the point $x \in X$ relative to the origin
- since the [[derivative]] $Df(x)[h]: X \to Y$ is an approvimation relative to the origin the following would be a [[linear map|linear]] approximation of $f$ 
$$
\widehat{f_{x}}(h) = f(x) + Df(x)[h]
$$
- for example the [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ can be expressed in a $\mathbb{R}^3$ with each point in the plain $x \in \mathbb{R}^2$ is mapped to a $y \in \mathbb{R}$
- thus the [[derivative]] $Df(x)[h]: \mathbb{R}^2 \to \mathbb{R} = Ah$ with $A \in \mathbb{R}^{1 \times 2}$ would be a plain in the $\mathbb{R}^3$



___________________


#### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$

#### geometric interpreation [[cauchy schwarz inequality]]
- since $\langle a, b \rangle$ is equal to the length of [[vector]] $b$ times the length of [[vector]] $a$ on $b$ $(proj_b(a))$ the [[cauchy schwarz inequality]] says that the [[projection]] of one [[vector]] to another can never be longer than the [[vector]] itself
- equality can only happen when $a$ and $b$ are a scaled version of each other (they are [[linear independent|linear dependent]] and the angle between them is $0$ or $180$)
- when $a$ and $b$ are [[orthogonal]] the [[projection]] of one to the other is zero which is the other extreme case
$$
\begin{split}
&\langle a, b \rangle = ||b|| \cdot ||proj_b(a)|| \leq ||a || \cdot ||b|| \\
\Rightarrow& ||proj_b(a)|| \leq ||a||
\end{split}
$$

Tags: mathematics
<!--ID: 1716210599101-->
END



START
Basic
- relationship of the [[derivative]] $Df(x)[h]: X \to Y$ with the concept of the [[projection]] (with proof)

Back: 

#### [[derivative]] as a [[projection]]
- let's assume that $f: \mathbb{R}^m \to \mathbb{R}$ and thus $h, A^\top \in \mathbb{R}^m$ 
- since the [[derivative]] $Df(x_0)[h]=Ah$ is a [[bounded linear map]] it can be expressed as a [[inner product]] of the [[matrix]] $A$ (representing the [[derivative]]) and the direction $h \in X$
- thus the [[derivative]] can be interpreted as the [[projection]] of the [[matrix]] $A$ (e.g. the [[gradient]]) on the direction $h \in X$ (in case of the normalized direction [[vector]] with $||h|| = 1$)
$$
Df(x)[h] = Ah =\langle A^\top, h \rangle = ||proj_h(A^\top)|| \cdot ||h||
$$

- this result can be generalized for a function $f: \mathbb{R}^m \to \mathbb{R}^n$ by treating $f$ as $n$ scalar functions $f_i$ 


#### relationship [[inner product]] to [[projection]]
- given a [[vector]] $a$ and a [[vector]] $b$ then $\langle a, b \rangle$ is equal to the length of the [[projection]] of $a$ on $b$ ($=porj_b(a)$) [[multiplication|multiplied]] with the length of $b$ (and vice versa) 
- thus the [[inner product]] contains the information about the (unnormalized) length of the [[projection]] of one [[vector]] to another

$$
\begin{split}
\langle a,b \rangle 
&= ||b|| \cdot ||b'|| = ||b|| \cdot \cos(\phi) ||a|| \\
&=||b|| \cdot ||proj_b(a)|| \\
\end{split}
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

___________________

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

#### [[derivative]] as a [[linear map|linear]] approximation
- given a [[function]] $f: X \to Y$ the [[derivative]]  $Df(x)[h]: X \to Y$ is a [[linear map|linear]] approximation of $f$ in the point $x \in X$ relative to the origin
- since the [[derivative]] $Df(x)[h]: X \to Y$ is an approvimation relative to the origin the following would be a [[linear map|linear]] approximation of $f$ 
$$
\widehat{f_{x}}(h) = f(x) + Df(x)[h]
$$
- for example the [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ can be expressed in a $\mathbb{R}^3$ with each point in the plain $x \in \mathbb{R}^2$ is mapped to a $y \in \mathbb{R}$
- thus the [[derivative]] $Df(x)[h]: \mathbb{R}^2 \to \mathbb{R} = Ah$ with $A \in \mathbb{R}^{1 \times 2}$ would be a plain in the $\mathbb{R}^3$



#### [[derivative]] as a [[vector]] in the direction of the steepest ascent
- before the forcus was on what the [[derivative]] $Df(x_0)[h]: X \to Y, Df(x_0)[h]=Ah$ does, but now we will focus thee properties of $A$ itself
- let's assume that $f: \mathbb{R}^m \to \mathbb{R}$ and thus $h, A^\top \in \mathbb{R}^m$ 
- we know that the [[derivative]] $Df(x_0)[h]=Ah = \langle A^\top, h \rangle = ||proj_h(A^\top)|| \cdot ||h||$ is the rate of change in the direction $h$ and the length of the [[projection]] of $A$ on the direction $h$
- from the [[cauchy schwarz inequality]] we know that the length of the [[projection]] of $A^\top$ on any $h$ is less or equal then the length of $A^\top$ itself with a maximum reachen at $h = A^\top$ 
$$
||proj_h(A^\top)|| \leq ||A^\top||
$$
- thus the [[vector]] $\frac{A^\top}{||A^\top||}$ is pointing in the direction of the steepest ascent
$$
\begin{split}
arg\max_{||h||=1} ||proj_h\left(A^\top\right)|| 
=arg\max_{||h||=1} \langle A^\top, h \rangle 
&= \frac{A^\top}{||A^\top||} \\ 
\end{split}
$$
- to get the rate of change in the direction of the steepest asecent we can just plug $h^* = \frac{A^\top}{||A^\top||}$ it into the [[derivative]] to see that the steepest rate if ascent is equal to the length of the [[vector]] $A^\top$
$$
Df(x)\left[\frac{A^\top}{||A^\top||}\right] = \frac{AA^\top}{||A^\top||} = \frac{\langle A, A \rangle}{||A^\top||} = \frac{||A^\top||^2}{||A^\top||} = ||A^\top||\in \mathbb{R}
$$
- this result can be generalized for a function $f: \mathbb{R}^m \to \mathbb{R}^n$ by treating $f$ as $n$ scalar functions $f_i$ 

Tags: mathematics
<!--ID: 1716210599104-->
END



START
Basic
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}$ with a [[derivative]] $Df(x_0)[h]=Ah$
- proof that $A$ points in the direction of the steepest ascent
- how steep is the ascent?

Back: 
#### [[derivative]] as a [[vector]] in the direction of the steepest ascent
- let's assume that $f: \mathbb{R}^m \to \mathbb{R}$ and thus $h, A^\top \in \mathbb{R}^m$ 
- we know that the [[derivative]] $Df(x_0)[h]=Ah = \langle A^\top, h \rangle = ||proj_h(A^\top)|| \cdot ||h||$ is the rate of change in the direction $h$ and the length of the [[projection]] of $A$ on the direction $h$
- from the [[cauchy schwarz inequality]] we know that the length of the [[projection]] of $A^\top$ on any $h$ is less or equal then the length of $A^\top$ itself with a maximum reachen at $h = A^\top$ 
$$
||proj_h(A^\top)|| \leq ||A^\top||
$$
- thus the [[vector]] $\frac{A^\top}{||A^\top||}$ is pointing in the direction of the steepest ascent
$$
\begin{split}
arg\max_{||h||=1} ||proj_h\left(A^\top\right)|| 
=arg\max_{||h||=1} \langle A^\top, h \rangle 
&= \frac{A^\top}{||A^\top||} \\ 
\end{split}
$$
- to get the rate of change in the direction of the steepest asecent we can just plug $h^* = \frac{A^\top}{||A^\top||}$ it into the [[derivative]] to see that the steepest rate if ascent is equal to the length of the [[vector]] $A^\top$
$$
Df(x)\left[\frac{A^\top}{||A^\top||}\right] = \frac{AA^\top}{||A^\top||} = \frac{\langle A, A \rangle}{||A^\top||} = \frac{||A^\top||^2}{||A^\top||} = ||A^\top||\in \mathbb{R}
$$
- this result can be generalized for a function $f: \mathbb{R}^m \to \mathbb{R}^n$ by treating $f$ as $n$ scalar functions $f_i$ 

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

___________________

#### [[derivative]] as a [[projection]]
- let's assume that $f: \mathbb{R}^m \to \mathbb{R}$ and thus $h, A^\top \in \mathbb{R}^m$ 
- since the [[derivative]] $Df(x_0)[h]=Ah$ is a [[bounded linear map]] it can be expressed as a [[inner product]] of the [[matrix]] $A$ (representing the [[derivative]]) and the direction $h \in X$
- thus the [[derivative]] can be interpreted as the [[projection]] of the [[matrix]] $A$ (e.g. the [[gradient]]) on the direction $h \in X$ (in case of the normalized direction [[vector]] with $||h|| = 1$)
$$
Df(x)[h] = Ah =\langle A^\top, h \rangle = ||proj_h(A^\top)|| \cdot ||h||
$$

- this result can be generalized for a function $f: \mathbb{R}^m \to \mathbb{R}^n$ by treating $f$ as $n$ scalar functions $f_i$ 


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

#### [[derivative]] as a [[linear map|linear]] approximation
- given a [[function]] $f: X \to Y$ the [[derivative]]  $Df(x)[h]: X \to Y$ is a [[linear map|linear]] approximation of $f$ in the point $x \in X$ relative to the origin
- since the [[derivative]] $Df(x)[h]: X \to Y$ is an approvimation relative to the origin the following would be a [[linear map|linear]] approximation of $f$ 
$$
\widehat{f_{x}}(h) = f(x) + Df(x)[h]
$$
- for example the [[function]] $f: \mathbb{R}^2 \to \mathbb{R}$ can be expressed in a $\mathbb{R}^3$ with each point in the plain $x \in \mathbb{R}^2$ is mapped to a $y \in \mathbb{R}$
- thus the [[derivative]] $Df(x)[h]: \mathbb{R}^2 \to \mathbb{R} = Ah$ with $A \in \mathbb{R}^{1 \times 2}$ would be a plain in the $\mathbb{R}^3$


#### relationship [[inner product]] to [[projection]]
- given a [[vector]] $a$ and a [[vector]] $b$ then $\langle a, b \rangle$ is equal to the length of the [[projection]] of $a$ on $b$ ($=porj_b(a)$) [[multiplication|multiplied]] with the length of $b$ (and vice versa) 
- thus the [[inner product]] contains the information about the (unnormalized) length of the [[projection]] of one [[vector]] to another

$$
\begin{split}
\langle a,b \rangle 
&= ||b|| \cdot ||b'|| = ||b|| \cdot \cos(\phi) ||a|| \\
&=||b|| \cdot ||proj_b(a)|| \\
\end{split}
$$

#### every [[inner product]] induces a [[norm]]
$$
||x|| = \sqrt{\langle x, x \rangle}
$$
$$
||x||^2 = \langle x, x \rangle
$$

#### geometric interpreation [[cauchy schwarz inequality]]
- since $\langle a, b \rangle$ is equal to the length of [[vector]] $b$ times the length of [[vector]] $a$ on $b$ $(proj_b(a))$ the [[cauchy schwarz inequality]] says that the [[projection]] of one [[vector]] to another can never be longer than the [[vector]] itself
- equality can only happen when $a$ and $b$ are a scaled version of each other (they are [[linear independent|linear dependent]] and the angle between them is $0$ or $180$)
- when $a$ and $b$ are [[orthogonal]] the [[projection]] of one to the other is zero which is the other extreme case
$$
\begin{split}
&\langle a, b \rangle = ||b|| \cdot ||proj_b(a)|| \leq ||a || \cdot ||b|| \\
\Rightarrow& ||proj_b(a)|| \leq ||a||
\end{split}
$$

Tags: mathematics
<!--ID: 1716210599108-->
END



START
Basic
- 4 ways the [[derivative]] can be interpreted germetricly

Back: 
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
- let's assume that $f: \mathbb{R}^m \to \mathbb{R}$ and thus $h, A^\top \in \mathbb{R}^m$ 
- since the [[derivative]] $Df(x_0)[h]=Ah$ is a [[bounded linear map]] it can be expressed as a [[inner product]] of the [[matrix]] $A$ (representing the [[derivative]]) and the direction $h \in X$
- thus the [[derivative]] can be interpreted as the [[projection]] of the [[matrix]] $A$ (e.g. the [[gradient]]) on the direction $h \in X$ (in case of the normalized direction [[vector]] with $||h|| = 1$)
$$
Df(x)[h] = Ah =\langle A^\top, h \rangle = ||proj_h(A^\top)|| \cdot ||h||
$$

- this result can be generalized for a function $f: \mathbb{R}^m \to \mathbb{R}^n$ by treating $f$ as $n$ scalar functions $f_i$ 

#### [[derivative]] as a [[vector]] in the direction of the steepest ascent
- let's assume that $f: \mathbb{R}^m \to \mathbb{R}$ and thus $h, A^\top \in \mathbb{R}^m$ 
- we know that the [[derivative]] $Df(x_0)[h]=Ah = \langle A^\top, h \rangle = ||proj_h(A^\top)|| \cdot ||h||$ is the rate of change in the direction $h$ and the length of the [[projection]] of $A$ on the direction $h$
- from the [[cauchy schwarz inequality]] we know that the length of the [[projection]] of $A^\top$ on any $h$ is less or equal then the length of $A^\top$ itself with a maximum reachen at $h = A^\top$ 
$$
||proj_h(A^\top)|| \leq ||A^\top||
$$
- thus the [[vector]] $\frac{A^\top}{||A^\top||}$ is pointing in the direction of the steepest ascent
$$
\begin{split}
arg\max_{||h||=1} ||proj_h\left(A^\top\right)|| 
=arg\max_{||h||=1} \langle A^\top, h \rangle 
&= \frac{A^\top}{||A^\top||} \\ 
\end{split}
$$
- to get the rate of change in the direction of the steepest asecent we can just plug $h^* = \frac{A^\top}{||A^\top||}$ it into the [[derivative]] to see that the steepest rate if ascent is equal to the length of the [[vector]] $A^\top$
$$
Df(x)\left[\frac{A^\top}{||A^\top||}\right] = \frac{AA^\top}{||A^\top||} = \frac{\langle A, A \rangle}{||A^\top||} = \frac{||A^\top||^2}{||A^\top||} = ||A^\top||\in \mathbb{R}
$$
- this result can be generalized for a function $f: \mathbb{R}^m \to \mathbb{R}^n$ by treating $f$ as $n$ scalar functions $f_i$ 

Tags: mathematics
<!--ID: 1716210599111-->
END


START
Basic
relationship and differences of the following concepts
- general derivative
- [[directional derivative]] (differenct to the general derivative)
- [[partial derivative]] (differenct to the general derivative)
- [[jacobian]]
- [[gradient]] (difference to the [[jacobian]])
Back: 
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

### directional derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- given a direction  $h \in X$ the [[directional derivative]] $D_hf(x): X \to Y$ mesures the rate at which $f$ is changing in point $x$ when going an infinesesimal small step in the direction $h$ and is defined as follows
$$
D_hf(x) = \lim_{t\to0}  \frac{f(x+th) - f(x)}{t} = Df(x)[h]
$$
- the [[directional derivative]] is equal to the general [[derivative]] $Df(x)[h]$ when plugging in a constant direction $h$


### partial derivative
- given a [[function]] $f: \mathbb{R}^n \to Y$
- the [[partial derivative]] $\frac{\partial f}{\partial x_i}:X \to Y$ is defined as follows and mesures the rate of change of $f$ regarding the direction of die coordinate $x_i$ 

$$
\frac{\partial f}{\partial x_i}(x) = \lim_{h \to 0} \frac{f(x+h e_i) - f(x) }{h} \in Y
$$

#### [[partial derivative]] to the general [[derivative]]
- given a [[function]] $f: \mathbb{R}^n \to Y$ and a point $x_0 \in X$ 
- the general [[derivative]] $Df(x_0)[h]: \mathbb{R}^n \to Y$ is a [[linear map]] approximating $f$ in the point $x_0$ and gives the rate of change in an arbitrary direction $h$
- the [[partial derivative]] in $x_0$ after a coodrinate $x_i$ gives the rate of change regarding the direction of the coordinate $x_i$
- when plugging the directional [[vector]] of the coordinate $i$  $e_i = (\begin{matrix}0 & ... & 1&0&0\end{matrix})$ in the general [[derivative]] it becomes the [[partial derivative]]
$$
Df(x_0)[e_i]:Ae_i = \frac{\partial f}{\partial x_i}(x_0) \to Y
$$


### jacobian
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[derivative]] $Df(x)[h]=Ah$ is a [[bounded linear map]] that can be represented by a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- for a general $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[matrix]] $A\in \mathbb{R}^{n \times m}$ called the [[jacobian]] $\nabla f = A \in \mathbb{R}^{n \times m}$ 
- if $f: \mathbb{R}^m \to \mathbb{R}$ is a scalar [[function]] [[transpose]] of [[matrix]] $A$ is a [[vector]]called the [[gradient]] $\nabla f = A^\top \in \mathbb{R}^m$ 


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


Tags: mathematics
<!--ID: 1716128307662-->
END


START
Basic
given the [[function]] $F(x): \mathbb{R}^{m} \to \mathbb{R} = \frac{1}{2}||Ax -b||_2^2$

calculate
- $Df(x)[h]$
- $Df(x)$
- $\nabla f(x)$

Back: 
#### $F(x): \mathbb{R}^{m} \to \mathbb{R} = \frac{1}{2}||Ax -b||_2^2$
- the [[derivative]] $DF(x)[h]: \mathbb{R}^{m} \to L( \mathbb{R}^{m},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{m}$ to $\mathbb{R}$ with $h \in \mathbb{R}^{m}$
- from the definition we know the following:
$$
F(x + h) = F(x) + DF(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||}{||h||} = 0 
$$


$$
\begin{split}
F (x + h) 
&= \frac{1}{2}||A(x+h) -b||_2^2 \\
&= \frac{1}{2}\langle (Ax -b) + Ah, (Ax -b) + Ah\rangle \\
&= \frac{1}{2}\langle Ax -b, Ax -b\rangle + \frac{1}{2}\langle Ah, Ah\rangle + \langle Ax -b, Ah\rangle \\
&= \underbrace{\frac{1}{2}||Ax-b||_2^2}_{f(X)} + \underbrace{\frac{1}{2}||Ah||_2^2}_{\varphi(H)} +  \underbrace{\langle Ax -b, Ah \rangle}_{Df(x)[h]}  \\
\end{split}
$$

- show that $\varphi(h)$ is converging fast enough

$$
\begin{split}
\frac{\varphi(h)}{||h||} 
&= \frac{1}{2} \frac{||Ah||^2}{||h||} \\
&= \frac{1}{2} ||h|| \frac{||Ah||^2}{||h||^2} \\
&= \frac{1}{2} ||h|| \left(\frac{||Ah||}{||h||}\right)^2 \\
&\leq \frac{1}{2} ||h|| \left(\sup_{||y|| \neq 0}\frac{||Ay||}{||y||}\right)^2 \\
&= \frac{1}{2} ||h|| \cdot ||A||^2 \xrightarrow{h \to 0} 0 \\
\end{split}
$$


$$
\begin{split}
Df(x)[h] 
&= \langle Ax -b, Ah \rangle \\
&= \left(Ax -b\right)^\top Ah \\
Df(x)
&= \left(Ax -b\right)^\top A \\
\nabla f (x)
&= \left(\left(Ax -b\right)^\top A\right)^\top \\
&= A^\top\left(Ax -b\right)  \\
\end{split}
$$

_______________________

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

### the [[operator norm]] is submultiplicative
- given two [[linear map|linear maps]] $A: X \to Y$ and $B: Y \to Z$ the following inequallity holds true
$$
||BA||_{X \to Z} \leq ||A||_{X \to Y} ||B||_{Y \to Z}
$$
 $$
 \begin{split}
||BA||_{X \to Z} 
&= \sup_{x\neq 0} \frac{||BAx||_Z}{||x||_X} \\
&= \sup_{x\neq 0, Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}}  \frac{||Ax||_Y}{||x||_X} \\
&\leq \sup_{Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X} \\
&= \sup_{y \neq 0} \frac{||By||_Z}{||y||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X}  \\
&= ||A||_{X \to Y} ||B||_{Y \to Z}
\end{split}
$$

### jacobian
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[derivative]] $Df(x)[h]=Ah$ is a [[bounded linear map]] that can be represented by a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- for a general $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[matrix]] $A\in \mathbb{R}^{n \times m}$ called the [[jacobian]] $\nabla f = A \in \mathbb{R}^{n \times m}$ 
- if $f: \mathbb{R}^m \to \mathbb{R}$ is a scalar [[function]] [[transpose]] of [[matrix]] $A$ is a [[vector]]called the [[gradient]] $\nabla f = A^\top \in \mathbb{R}^m$ 


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


Tags: mathematics
<!--ID: 1716309337739-->
END



START
Basic
given the [[function]] $F(b): \mathbb{R}^{m} \to \mathbb{R} = \frac{1}{2}||Ax -b||_2^2$

calculate
- $Df(x)[h]$
- $Df(x)$
- $\nabla f(x)$

Back: 
#### $F(b): \mathbb{R}^{m} \to \mathbb{R} = \frac{1}{2}||Ax -b||_2^2$
- the [[derivative]] $DF(b)[h]: \mathbb{R}^{m} \to L( \mathbb{R}^{m},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{m}$ to $\mathbb{R}$ with $h \in \mathbb{R}^{m}$
- from the definition we know the following:
$$
F(b + h) = F(b) + DF(b)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||}{||h||} = 0 
$$


$$
\begin{split}
F (b + h) 
&= \frac{1}{2}||Ax -b -h||_2^2 \\
&= \frac{1}{2}\langle (Ax -b) -h, (Ax -b) -h\rangle \\
&= \frac{1}{2}\langle Ax -b, Ax -b\rangle + \frac{1}{2}\langle h, h\rangle - \langle Ax -b, h\rangle \\
&= \underbrace{\frac{1}{2}||Ax-b||_2^2}_{f(X)} + \underbrace{\frac{1}{2}||h||_2^2}_{\varphi(H)} +  \underbrace{-\langle Ax -b, h \rangle}_{Df(x)[h]}  \\
\end{split}
$$

- show that $\varphi(h)$ is converging fast enough

$$
\begin{split}
\frac{\varphi(h)}{||h||} 
&= \frac{1}{2} \frac{||h||^2}{||h||} \\
&= \frac{1}{2} ||h||  \xrightarrow{h \to 0} 0 \\
\end{split}
$$



$$
\begin{split}
Df(x)[h] &= -\langle Ax -b, h \rangle \\
Df(x) &= -(Ax -b)^\top \\
\nabla f(x) &= -(Ax -b) \\
\end{split}
$$

_______________________

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

### the [[operator norm]] is submultiplicative
- given two [[linear map|linear maps]] $A: X \to Y$ and $B: Y \to Z$ the following inequallity holds true
$$
||BA||_{X \to Z} \leq ||A||_{X \to Y} ||B||_{Y \to Z}
$$
 $$
 \begin{split}
||BA||_{X \to Z} 
&= \sup_{x\neq 0} \frac{||BAx||_Z}{||x||_X} \\
&= \sup_{x\neq 0, Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}}  \frac{||Ax||_Y}{||x||_X} \\
&\leq \sup_{Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X} \\
&= \sup_{y \neq 0} \frac{||By||_Z}{||y||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X}  \\
&= ||A||_{X \to Y} ||B||_{Y \to Z}
\end{split}
$$

### jacobian
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[derivative]] $Df(x)[h]=Ah$ is a [[bounded linear map]] that can be represented by a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- for a general $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[matrix]] $A\in \mathbb{R}^{n \times m}$ called the [[jacobian]] $\nabla f = A \in \mathbb{R}^{n \times m}$ 
- if $f: \mathbb{R}^m \to \mathbb{R}$ is a scalar [[function]] [[transpose]] of [[matrix]] $A$ is a [[vector]]called the [[gradient]] $\nabla f = A^\top \in \mathbb{R}^m$ 


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


Tags: mathematics
<!--ID: 1716309337744-->
END



START
Basic
given the [[function]] $F(A): \mathbb{R}^{n \times m} \to \mathbb{R} = \frac{1}{2}||Ax -b||_2^2$

calculate
- $Df(x)[h]$
- $Df(x)$
- $\nabla f(x)$

Back: 
#### $F(A): \mathbb{R}^{n \times m} \to \mathbb{R} = \frac{1}{2}||Ax -b||_2^2$
- the [[derivative]] $DF(A)[H]: \mathbb{R}^{n \times m} \to L( \mathbb{R}^{n \times m},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{n \times m}$ to $\mathbb{R}$ with $H \in \mathbb{R}^{n \times m}$
- from the definition we know the following:
$$
F(A + H) = f(X) + DF(A)[H] + \varphi(H) \quad \text{with} \quad \lim_{H \to 0} \frac{||\varphi(H)||}{||H||} = 0 
$$


$$
\begin{split}
F (X + H) 
&= \frac{1}{2}||(A+H)x -b||_2^2 \\
&= \frac{1}{2}\langle (Ax -b) + Hx, (Ax -b) + Hx\rangle \\
&= \frac{1}{2}\langle Ax -b, Ax -b\rangle + \frac{1}{2}\langle Hx, Hx\rangle + \langle Ax -b, Hx\rangle \\
&= \underbrace{\frac{1}{2}||Ax-b||_2^2}_{f(X)} + \underbrace{\frac{1}{2}||Hx||_2^2}_{\varphi(H)} +  \underbrace{\langle Ax -b, Hx \rangle}_{Df(X)[H]}  \\
\end{split}
$$

- show that $\varphi(H)$ is converging fast enough

$$
\begin{split}
\frac{\varphi(H)}{||H||} 
&= \frac{1}{2} \frac{||Hx||^2}{||H||} \\
&= \frac{1}{2} \frac{1}{||H||}  \frac{||Hx||^2 ||x||^2}{||x||^2} \\
&= \frac{1}{2}  \frac{||x||^2}{||H||} \frac{||Hx||^2 }{||x||^2} \\
&\leq \frac{1}{2}  \frac{||x||^2}{||H||} \sup_{||y|| \neq 0} \frac{||Hy||^2 }{||y||^2} \\
&= \frac{1}{2}  \frac{||x||^2}{||H||} ||H||^2 \\
&= \frac{1}{2} ||H|| \cdot ||x||^2 \xrightarrow{H \to 0} 0 \\
\end{split}
$$

- a [[scalar]] is its own [[trace]] and $\mathrm{trace}(AB) = \mathrm{trace}(BA)$


$$
\begin{split}
DF(A)[H] 
&= \langle Ax -b, Hx \rangle \\
&= \left(Ax -b\right)^\top Hx \\
&= trace\left(\left(Ax -b\right)^\top Hx\right) \\
&= trace\left(x\left(Ax -b\right)^\top H\right) \\
&= trace\left(x\left(x^\top A^\top  -b^\top\right) H\right) \\
&= trace\left(\left(xx^\top A^\top  -xb^\top\right) H\right) \\
&= \left\langle\left(xx^\top A^\top  -xb^\top\right)^\top, H \right\rangle_F \\
DF(A)
&= \left(xx^\top A^\top  -xb^\top\right)^\top\\
\nabla F(A)
&= xx^\top A^\top  -xb^\top\\
\end{split}
$$

_______________________

### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
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

### the [[operator norm]] is submultiplicative
- given two [[linear map|linear maps]] $A: X \to Y$ and $B: Y \to Z$ the following inequallity holds true
$$
||BA||_{X \to Z} \leq ||A||_{X \to Y} ||B||_{Y \to Z}
$$
 $$
 \begin{split}
||BA||_{X \to Z} 
&= \sup_{x\neq 0} \frac{||BAx||_Z}{||x||_X} \\
&= \sup_{x\neq 0, Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}}  \frac{||Ax||_Y}{||x||_X} \\
&\leq \sup_{Ax \neq 0} \frac{||BAx||_Z}{||Ax||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X} \\
&= \sup_{y \neq 0} \frac{||By||_Z}{||y||_{Y}} \cdot \sup_{x \neq 0} \frac{||Ax||_Y}{||x||_X}  \\
&= ||A||_{X \to Y} ||B||_{Y \to Z}
\end{split}
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


### jacobian
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[derivative]] $Df(x)[h]=Ah$ is a [[bounded linear map]] that can be represented by a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- for a general $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[matrix]] $A\in \mathbb{R}^{n \times m}$ called the [[jacobian]] $\nabla f = A \in \mathbb{R}^{n \times m}$ 
- if $f: \mathbb{R}^m \to \mathbb{R}$ is a scalar [[function]] [[transpose]] of [[matrix]] $A$ is a [[vector]]called the [[gradient]] $\nabla f = A^\top \in \mathbb{R}^m$ 


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


Tags: mathematics
<!--ID: 1716309337748-->
END


START
Basic
proof the following
$$
DF(A)[H] = \langle Ax -b, Hx \rangle 
\Leftrightarrow
\nabla F(A)= xx^\top A^\top  -xb^\top
$$

Back: 
- a [[scalar]] is its own [[trace]] and$\mathrm{trace}(AB) = \mathrm{trace}(BA)$
$$
\begin{split}
DF(A)[H] 
&= \langle Ax -b, Hx \rangle \\
&= \left(Ax -b\right)^\top Hx \\
&= trace\left(\left(Ax -b\right)^\top Hx\right) \\
&= trace\left(x\left(Ax -b\right)^\top H\right) \\
&= trace\left(x\left(x^\top A^\top  -b^\top\right) H\right) \\
&= trace\left(\left(xx^\top A^\top  -xb^\top\right) H\right) \\
&= \left\langle\left(xx^\top A^\top  -xb^\top\right)^\top, H \right\rangle_F \\
DF(A)
&= \left(xx^\top A^\top  -xb^\top\right)^\top\\
\nabla F(A)
&= xx^\top A^\top  -xb^\top\\
\end{split}
$$

_______________________

### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
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


### jacobian
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[derivative]] $Df(x)[h]=Ah$ is a [[bounded linear map]] that can be represented by a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- for a general $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[matrix]] $A\in \mathbb{R}^{n \times m}$ called the [[jacobian]] $\nabla f = A \in \mathbb{R}^{n \times m}$ 
- if $f: \mathbb{R}^m \to \mathbb{R}$ is a scalar [[function]] [[transpose]] of [[matrix]] $A$ is a [[vector]]called the [[gradient]] $\nabla f = A^\top \in \mathbb{R}^m$ 


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


Tags: mathematics
<!--ID: 1716309337752-->
END





START
Basic

given the [[function]] $f(x) = x^\top Ax$

calculate
- $Df(x)[h]$
- $Df(x)$
- $\nabla f(x)$

Back: 
#### $f(x) = x^\top Ax$

$$
\begin{split}
DF(A)[H] 
&= h^\top A x + x^\top A h \\
&= \left\langle h, Ax \right\rangle + \left\langle\left(x^\top A \right)^\top , h \right\rangle \\
&= \left\langle Ax, h  \right\rangle + \left\langle\left(x^\top A \right)^\top , h \right\rangle \\
DF(A)&= (Ax)^\top + x^\top A\\
\nabla F(A)
&= Ax + A^\top x \\
\end{split}
$$

_______________________

### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
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


### jacobian
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[derivative]] $Df(x)[h]=Ah$ is a [[bounded linear map]] that can be represented by a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- for a general $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[matrix]] $A\in \mathbb{R}^{n \times m}$ called the [[jacobian]] $\nabla f = A \in \mathbb{R}^{n \times m}$ 
- if $f: \mathbb{R}^m \to \mathbb{R}$ is a scalar [[function]] [[transpose]] of [[matrix]] $A$ is a [[vector]]called the [[gradient]] $\nabla f = A^\top \in \mathbb{R}^m$ 


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


Tags: mathematics
<!--ID: 1723048766553-->
END



START
Basic

- given the following [[derivative]]
- calculate the [[gradient]] $\nabla F(A)$

$$
DF(A)[H] = \langle H, A \rangle
$$

Back: 
$$
DF(A)[H] = \langle H, A \rangle = \langle A, H \rangle = A^\top H
$$
$$
DF(A) = A^\top
$$

$$
\nabla F(A) = DF(A)^\top = A
$$

_______________________

### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
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


### jacobian
- given a [[function]] $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[derivative]] $Df(x)[h]=Ah$ is a [[bounded linear map]] that can be represented by a [[matrix]] $A \in \mathbb{R}^{n \times m}$ 
- for a general $f: \mathbb{R}^m \to \mathbb{R}^n$ the [[matrix]] $A\in \mathbb{R}^{n \times m}$ called the [[jacobian]] $\nabla f = A \in \mathbb{R}^{n \times m}$ 
- if $f: \mathbb{R}^m \to \mathbb{R}$ is a scalar [[function]] [[transpose]] of [[matrix]] $A$ is a [[vector]]called the [[gradient]] $\nabla f = A^\top \in \mathbb{R}^m$ 


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


Tags: mathematics
<!--ID: 1723128193791-->
END