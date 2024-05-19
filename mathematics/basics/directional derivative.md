### directional derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[directional derivative]] $D_hf(x): X \to L(X,Y)$ in point $x \in X$ in the direction of $h \in X$ is defined as follows
- like the [[derivative]] the [[function]] $D_hf(x): X \to L(X,Y)$ maps every point $x \in X$ to a [[bounded linear map]] $\in L(X, Y)$ 
- the [[directional derivative]] measures the rate at which a [[function]] changes in a particular direction at a given point

$$
D_hf(x) = \lim_{t\to0}  \frac{f(x+th) - f(x)}{t}
$$

### [[directional derivative]] and the [[gradient]]
- the [[directional derivative]] in all directions can be constucted from the [[gradient]] 

$$
D_hf(x) =  \nabla f(x) h
$$

![[gradient#gradient]]


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
# -----------------

![[partial derivative#partial derivative]]

![[gradient#gradient]]

![[derivative#derivative in a banach space]]

![[differentiabe#differentiabe]]

# anki

START
Basic
[[directional derivative]]
- definition
- what kind of function is it?
- Geometric interpretation


Back: 
### directional derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[directional derivative]] $D_hf(x): X \to L(X,Y)$ in point $x \in X$ in the direction of $h \in X$ is defined as follows
- like the [[derivative]] the [[function]] $D_hf(x): X \to L(X,Y)$ maps every point $x \in X$ to a [[bounded linear map]] $\in L(X, Y)$ 
- the [[directional derivative]] measures the rate at which a [[function]] changes in a particular direction at a given point

$$
D_hf(x) = \lim_{t\to0}  \frac{f(x+th) - f(x)}{t}
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

### partial derivative
- given a [[function]] $f: \mathbb{R}^n \to Y$
- the [[partial derivative]] $\frac{\partial f}{\partial x_i}$ is defined as follows and mesures the rate of change of $f$ regarding the direction of die coordinate $x_i$ 

$$
\frac{\partial f}{\partial x_i}(x) = \lim_{h \to 0} \frac{f(x+h e_i) - f(x) }{h} 
$$


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
<!--ID: 1715629635958-->
END



START
Basic
[[directional derivative]]
- relationship to the [[gradient]]
- relationship to the [[partial derivative]]

Back: 
### directional derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[directional derivative]] $D_hf(x): X \to L(X,Y)$ in point $x \in X$ in the direction of $h \in X$ is defined as follows
- like the [[derivative]] the [[function]] $D_hf(x): X \to L(X,Y)$ maps every point $x \in X$ to a [[bounded linear map]] $\in L(X, Y)$ 
- the [[directional derivative]] measures the rate at which a [[function]] changes in a particular direction at a given point

$$
D_hf(x) = \lim_{t\to0}  \frac{f(x+th) - f(x)}{t}
$$

### [[directional derivative]] and the [[gradient]]
- the [[directional derivative]] in all directions can be constucted from the [[gradient]] 

$$
D_hf(x) =  \nabla f(x) h
$$


### [[directional derivative]] and [[partial derivative]]
- the [[directional derivative]] generalizes the [[partial derivative]] for an arbitrary direction $h$
	→ the [[partial derivative]] $\frac{\partial f}{\partial x_i}(x)$ is a [[directional derivative]] $D_hf(x)$ with the direction being the cordinate $i$ $h=e_i$ 
- while the [[partial derivative]] $\frac{\partial f}{\partial x_i}$ only gives the rate of change of a [[function]] $f$ in the direction of the coordinate its coodrinates the [[partial derivative]] does the same for an arbitrary direction

### partial derivative
- given a [[function]] $f: \mathbb{R}^n \to Y$
- the [[partial derivative]] $\frac{\partial f}{\partial x_i}$ is defined as follows and mesures the rate of change of $f$ regarding the direction of die coordinate $x_i$ 

$$
\frac{\partial f}{\partial x_i}(x) = \lim_{h \to 0} \frac{f(x+h e_i) - f(x) }{h} 
$$


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

Tags: mathematics
<!--ID: 1716128307662-->
END


START
Basic
given a [[function]] $f$ with the [[gradient]] $\nabla f$ what is the [[directional derivative]] is the direction $h$?

$$
\nabla f = \left(\begin{matrix} a \\ b \\ c \end{matrix}\right)
$$
$$
h = \left(\begin{matrix} 1 \\ 1 \\ 0 \end{matrix}\right)
$$

Back: 

$$
D_hf(x) = h \nabla f  = \left(\begin{matrix} a \\ b \\ 0 \end{matrix}\right)
$$

### [[directional derivative]] and the [[gradient]]
- the [[directional derivative]] in all directions can be constucted from the [[gradient]] 

$$
D_hf(x) =  \nabla f(x) h
$$

### directional derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[directional derivative]] $D_hf(x): X \to L(X,Y)$ in point $x \in X$ in the direction of $h \in X$ is defined as follows
- like the [[derivative]] the [[function]] $D_hf(x): X \to L(X,Y)$ maps every point $x \in X$ to a [[bounded linear map]] $\in L(X, Y)$ 
- the [[directional derivative]] measures the rate at which a [[function]] changes in a particular direction at a given point

$$
D_hf(x) = \lim_{t\to0}  \frac{f(x+th) - f(x)}{t}
$$

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


___________________



### [[directional derivative]] and [[partial derivative]]
- the [[directional derivative]] generalizes the [[partial derivative]] for an arbitrary direction $h$
	→ the [[partial derivative]] $\frac{\partial f}{\partial x_i}(x)$ is a [[directional derivative]] $D_hf(x)$ with the direction being the cordinate $i$ $h=e_i$ 
- while the [[partial derivative]] $\frac{\partial f}{\partial x_i}$ only gives the rate of change of a [[function]] $f$ in the direction of the coordinate its coodrinates the [[partial derivative]] does the same for an arbitrary direction

### partial derivative
- given a [[function]] $f: \mathbb{R}^n \to Y$
- the [[partial derivative]] $\frac{\partial f}{\partial x_i}$ is defined as follows and mesures the rate of change of $f$ regarding the direction of die coordinate $x_i$ 

$$
\frac{\partial f}{\partial x_i}(x) = \lim_{h \to 0} \frac{f(x+h e_i) - f(x) }{h} 
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

Tags: mathematics
<!--ID: 1716128307666-->
END