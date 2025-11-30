## chain rule
### single variable case
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$

#### intuition chain rule
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$


### multi variable case
#### single dimension case
- $x \in \mathbb{R}$ 
- $g: \mathbb{R} \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}$ 

$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= \lim_{h \to 0} \frac{ f\left(g(x + e h)\right) - f\left(g(x )\right) }{h}  \\
&= \sum_{j=1}^m   \frac{\partial f\left(g(x)\right)}{\partial g(x)_j} \frac{\partial g(x)_j}{\partial x} \\
\end{split}
$$


#### general case
let 
- $x \in \mathbb{R}^{n}$ 
- $g: \mathbb{R}^n \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}^k$ 


$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= D{g \circ f}(x) \\
&= \left.Df\left(u\right)\right|_{u=g(x)} Dg(x) \in \mathbb{R}^{k \times n} \\
\end{split}
$$

- with the [[jacobian]] $Df\left(g(x)\right) \in \mathbb{R}^{k\times m}$ and $Dg(x) \in \mathbb{R}^{m \times n}$ 

#### dimensions
- let $F = f\left(g(x)\right)$
- the rule for the decomposing the [[derivative]] with the [[chain rule]] is outer times inner and the dimensions are as follows

$$
\begin{split}
DF(x) = 
\underbrace{\left.Df(u)\right|_{u=g(x)}}_{
\mathbb{R}^{\mathrm{dim}(f) \times \mathrm{dim}(g)}} 
\quad
\underbrace{Dg(x)}_{\mathbb{R}^{\mathrm{dim}(g) \times \mathrm{dim}(x)}} 
\in \mathbb{R}^{\mathrm{dim}(F) \times \mathrm{dim}(x)} \\
\end{split}
$$
#### proof

- $g$ and $f$ are [[differentiable]] so that the following exists

$$
\begin{split}
g(x+h) 
=& g(x) + Dg(x)h + \varphi_g(h), \quad &\frac{||\varphi_g(h)||}{||h||} \to_{h \to 0} 0 \\
f\left(u+v(h)\right) =& f(u) + Df(u)v(h) + \varphi_f\left(v(h)\right) , \qquad &\frac{||\varphi_f(v)||}{||v||} \to_{v \to 0} 0  \\
\end{split}
$$
- now define

$$
\begin{split}
u :=& g(x)  \\
v(h) :=& Dg(x)h + \varphi_g(h)  \\
g(x+h) =& u + v(h)
\end{split}
$$
- now insert

$$
\begin{split}
f(g(x+h))
&= f(u + v(h)) \\
&= f(u) + Df(u)[v(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u)[Dg(x)[h] + \varphi_g(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u) Dg(x)[h] + \underbrace{ Df(u)\varphi_g(h) + \varphi_f(v(h))}_{r(h)} \\
r(h) &= Df(u)\varphi_g(h) + \varphi_f(v(h)), \quad  \frac{||r(h)||}{||h||} \to_{h \to 0} 0
\end{split}
$$

- it follows that

$$
\begin{split}
D f\left(g(x)\right) 
&= \underbrace{\left. Df\left(u\right) \right |_{u=g(x)}}_{\in \mathbb{R}^{1\times m}}\underbrace{ Dg(x)}_{\in \mathbb{R}^{m\times n}} \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

#### intuition
- if the ith dimension of $x$ changes by a delta, this can lead to a change of all dimensions of $g(x)$ and each change of a $g(x)_j$ can lead to a change of $f\left(g(x)\right)$ 
- by summing up the effects we have the [[partial derivative]]

$$
\lim_{h \to 0} \sum_{j=1}^m  \frac{ g(x+e_ih)_j -  g(x)_j}{h}  \cdot \frac{ f\left(g(x) + e_j h\right)-f\left(g(x)\right)}{h}   $$

# -----------------


![[derivative#general derivative]]
# anki

START
Basic
[[chain rule]] for the multi variable case
- theorem for the following cases with $f\left(g(x)\right)$
- intuition
- dimensions

- $x \in \mathbb{R}$ 
- $g: \mathbb{R} \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}$ 

- $x \in \mathbb{R}^{n}$ 
- $g: \mathbb{R}^n \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}^k$ 


Back: 
## chain rule
### single variable case
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$

#### intuition chain rule
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$


### multi variable case
#### single dimension case
- $x \in \mathbb{R}$ 
- $g: \mathbb{R} \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}$ 

$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= \lim_{h \to 0} \frac{ f\left(g(x + e h)\right) - f\left(g(x )\right) }{h}  \\
&= \sum_{j=1}^m   \frac{\partial f\left(g(x)\right)}{\partial g(x)_j} \frac{\partial g(x)_j}{\partial x} \\
\end{split}
$$


#### general case
let 
- $x \in \mathbb{R}^{n}$ 
- $g: \mathbb{R}^n \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}^k$ 


$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= D{g \circ f}(x) \\
&= \left.Df\left(u\right)\right|_{u=g(x)} Dg(x) \in \mathbb{R}^{k \times n} \\
\end{split}
$$

- with the [[jacobian]] $Df\left(g(x)\right) \in \mathbb{R}^{k\times m}$ and $Dg(x) \in \mathbb{R}^{m \times n}$ 

#### dimensions
- let $F = f\left(g(x)\right)$
- the rule for the decomposing the [[derivative]] with the [[chain rule]] is outer times inner and the dimensions are as follows

$$
\begin{split}
DF(x) = 
\underbrace{\left.Df(u)\right|_{u=g(x)}}_{
\mathbb{R}^{\mathrm{dim}(f) \times \mathrm{dim}(g)}} 
\quad
\underbrace{Dg(x)}_{\mathbb{R}^{\mathrm{dim}(g) \times \mathrm{dim}(x)}} 
\in \mathbb{R}^{\mathrm{dim}(F) \times \mathrm{dim}(x)} \\
\end{split}
$$
#### proof

- $g$ and $f$ are [[differentiable]] so that the following exists

$$
\begin{split}
g(x+h) 
=& g(x) + Dg(x)h + \varphi_g(h), \quad &\frac{||\varphi_g(h)||}{||h||} \to_{h \to 0} 0 \\
f\left(u+v(h)\right) =& f(u) + Df(u)v(h) + \varphi_f\left(v(h)\right) , \qquad &\frac{||\varphi_f(v)||}{||v||} \to_{v \to 0} 0  \\
\end{split}
$$
- now define

$$
\begin{split}
u :=& g(x)  \\
v(h) :=& Dg(x)h + \varphi_g(h)  \\
g(x+h) =& u + v(h)
\end{split}
$$
- now insert

$$
\begin{split}
f(g(x+h))
&= f(u + v(h)) \\
&= f(u) + Df(u)[v(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u)[Dg(x)[h] + \varphi_g(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u) Dg(x)[h] + \underbrace{ Df(u)\varphi_g(h) + \varphi_f(v(h))}_{r(h)} \\
r(h) &= Df(u)\varphi_g(h) + \varphi_f(v(h)), \quad  \frac{||r(h)||}{||h||} \to_{h \to 0} 0
\end{split}
$$

- it follows that

$$
\begin{split}
D f\left(g(x)\right) 
&= \underbrace{\left. Df\left(u\right) \right |_{u=g(x)}}_{\in \mathbb{R}^{1\times m}}\underbrace{ Dg(x)}_{\in \mathbb{R}^{m\times n}} \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

#### intuition
- if the ith dimension of $x$ changes by a delta, this can lead to a change of all dimensions of $g(x)$ and each change of a $g(x)_j$ can lead to a change of $f\left(g(x)\right)$ 
- by summing up the effects we have the [[partial derivative]]

$$
\lim_{h \to 0} \sum_{j=1}^m  \frac{ g(x+e_ih)_j -  g(x)_j}{h}  \cdot \frac{ f\left(g(x) + e_j h\right)-f\left(g(x)\right)}{h}   $$

___________

### general derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[derivative]] operator $Df: X \to L(X,Y)$ is a [[function]] that maps elements of $X$ to a [[bounded linear map]] $Df(x)[h]: X \to Y$
- the [[bounded linear map]] $Df(x)[h]: X \to Y$ is the [[derivative]] of $f$ in point $x \in X$ and can be interpreted as a linear approximation of $f$ in point $x$
- in the case of $f: \mathbb{R}^{m} \to \mathbb{R}^{n}$ the [[derivative]] $Df(x)[h] = Ah$ can be expressed as a [[matrix]] $A \in \mathbb{R}^{n \times m}$ which is called the [[jacobian]] $J_f(x)$

$$
\lim_{||h||_X \to 0} \frac{||f(x+h) - f(x) - Df(x)[h]||_Y}{||h||_X} = 0
$$

- this equivalent definition is often easier to work with:

$$
f(x + h) = f(x) + Df(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||_Y}{||h||_X} = 0
$$


### definition derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
### chain rule

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$
#### intuition:
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$

Tags: mathematics
<!--ID: 1764180973286-->
END


START
Basic
proof for the following
- $x \in \mathbb{R}^{n}$ 
- $g: \mathbb{R}^n \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}^k$ 

$$
\begin{split}
D f\left(g(x)\right) 
&= \left. Df\left(u\right) \right |_{u=g(x)} Dg(x) \\
\end{split}
$$

- how are the dimensions?

Back: 


#### general case
let 
- $x \in \mathbb{R}^{n}$ 
- $g: \mathbb{R}^n \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}^k$ 


$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= D{g \circ f}(x) \\
&= Df\left(g(x)\right) Dg(x) \in \mathbb{R}^{k \times n} \\
\end{split}
$$

- with the [[jacobian]] $Df\left(g(x)\right) \in \mathbb{R}^{k\times m}$ and $Dg(x) \in \mathbb{R}^{m \times n}$ 

#### dimensions
- let $F = f\left(g(x)\right)$
- the rule for the decomposing the [[derivative]] with the [[chain rule]] is outer times inner and the dimensions are as follows

$$
\begin{split}
DF(x) = 
\underbrace{\left.Df(u)\right|_{u=g(x)}}_{
\mathbb{R}^{\mathrm{dim}(f) \times \mathrm{dim}(g)}} 
\quad
\underbrace{Dg(x)}_{\mathbb{R}^{\mathrm{dim}(g) \times \mathrm{dim}(x)}} 
\in \mathbb{R}^{\mathrm{dim}(F) \times \mathrm{dim}(x)} \\
\end{split}
$$
#### proof

- $g$ and $f$ are [[differentiable]] so that the following exists

$$
\begin{split}
g(x+h) 
=& g(x) + Dg(x)h + \varphi_g(h), \quad &\frac{||\varphi_g(h)||}{||h||} \to_{h \to 0} 0 \\
f\left(u+v(h)\right) =& f(u) + Df(u)v(h) + \varphi_f\left(v(h)\right) , \qquad &\frac{||\varphi_f(v)||}{||v||} \to_{v \to 0} 0  \\
\end{split}
$$
- now define

$$
\begin{split}
u :=& g(x)  \\
v(h) :=& Dg(x)h + \varphi_g(h)  \\
g(x+h) =& u + v(h)
\end{split}
$$
- now insert

$$
\begin{split}
f(g(x+h))
&= f(u + v(h)) \\
&= f(u) + Df(u)[v(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u)[Dg(x)[h] + \varphi_g(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u) Dg(x)[h] + \underbrace{ Df(u)\varphi_g(h) + \varphi_f(v(h))}_{r(h)} \\
r(h) &= Df(u)\varphi_g(h) + \varphi_f(v(h)), \quad  \frac{||r(h)||}{||h||} \to_{h \to 0} 0
\end{split}
$$

- it follows that

$$
\begin{split}
D f\left(g(x)\right) 
&= \underbrace{\left. Df\left(u\right) \right |_{u=g(x)}}_{\in \mathbb{R}^{1\times m}}\underbrace{ Dg(x)}_{\in \mathbb{R}^{m\times n}} \in \mathbb{R}^{1 \times n} \\
\end{split}
$$


## chain rule
### single variable case
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$

#### intuition chain rule
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$


### multi variable case
#### single dimension case
- $x \in \mathbb{R}$ 
- $g: \mathbb{R} \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}$ 

$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= \lim_{h \to 0} \frac{ f\left(g(x + e h)\right) - f\left(g(x )\right) }{h}  \\
&= \sum_{j=1}^m   \frac{\partial f\left(g(x)\right)}{\partial g(x)_j} \frac{\partial g(x)_j}{\partial x} \\
\end{split}
$$


#### general case
let 
- $x \in \mathbb{R}^{n}$ 
- $g: \mathbb{R}^n \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}^k$ 


$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= D{g \circ f}(x) \\
&= \left.Df\left(u\right)\right|_{u=g(x)} Dg(x) \in \mathbb{R}^{k \times n} \\
\end{split}
$$

- with the [[jacobian]] $Df\left(g(x)\right) \in \mathbb{R}^{k\times m}$ and $Dg(x) \in \mathbb{R}^{m \times n}$ 

#### dimensions
- let $F = f\left(g(x)\right)$
- the rule for the decomposing the [[derivative]] with the [[chain rule]] is outer times inner and the dimensions are as follows

$$
\begin{split}
DF(x) = 
\underbrace{\left.Df(u)\right|_{u=g(x)}}_{
\mathbb{R}^{\mathrm{dim}(f) \times \mathrm{dim}(g)}} 
\quad
\underbrace{Dg(x)}_{\mathbb{R}^{\mathrm{dim}(g) \times \mathrm{dim}(x)}} 
\in \mathbb{R}^{\mathrm{dim}(F) \times \mathrm{dim}(x)} \\
\end{split}
$$
#### proof

- $g$ and $f$ are [[differentiable]] so that the following exists

$$
\begin{split}
g(x+h) 
=& g(x) + Dg(x)h + \varphi_g(h), \quad &\frac{||\varphi_g(h)||}{||h||} \to_{h \to 0} 0 \\
f\left(u+v(h)\right) =& f(u) + Df(u)v(h) + \varphi_f\left(v(h)\right) , \qquad &\frac{||\varphi_f(v)||}{||v||} \to_{v \to 0} 0  \\
\end{split}
$$
- now define

$$
\begin{split}
u :=& g(x)  \\
v(h) :=& Dg(x)h + \varphi_g(h)  \\
g(x+h) =& u + v(h)
\end{split}
$$
- now insert

$$
\begin{split}
f(g(x+h))
&= f(u + v(h)) \\
&= f(u) + Df(u)[v(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u)[Dg(x)[h] + \varphi_g(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u) Dg(x)[h] + \underbrace{ Df(u)\varphi_g(h) + \varphi_f(v(h))}_{r(h)} \\
r(h) &= Df(u)\varphi_g(h) + \varphi_f(v(h)), \quad  \frac{||r(h)||}{||h||} \to_{h \to 0} 0
\end{split}
$$

- it follows that

$$
\begin{split}
D f\left(g(x)\right) 
&= \underbrace{\left. Df\left(u\right) \right |_{u=g(x)}}_{\in \mathbb{R}^{1\times m}}\underbrace{ Dg(x)}_{\in \mathbb{R}^{m\times n}} \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

#### intuition
- if the ith dimension of $x$ changes by a delta, this can lead to a change of all dimensions of $g(x)$ and each change of a $g(x)_j$ can lead to a change of $f\left(g(x)\right)$ 
- by summing up the effects we have the [[partial derivative]]

$$
\lim_{h \to 0} \sum_{j=1}^m  \frac{ g(x+e_ih)_j -  g(x)_j}{h}  \cdot \frac{ f\left(g(x) + e_j h\right)-f\left(g(x)\right)}{h}   $$


___________

### general derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[derivative]] operator $Df: X \to L(X,Y)$ is a [[function]] that maps elements of $X$ to a [[bounded linear map]] $Df(x)[h]: X \to Y$
- the [[bounded linear map]] $Df(x)[h]: X \to Y$ is the [[derivative]] of $f$ in point $x \in X$ and can be interpreted as a linear approximation of $f$ in point $x$
- in the case of $f: \mathbb{R}^{m} \to \mathbb{R}^{n}$ the [[derivative]] $Df(x)[h] = Ah$ can be expressed as a [[matrix]] $A \in \mathbb{R}^{n \times m}$ which is called the [[jacobian]] $J_f(x)$

$$
\lim_{||h||_X \to 0} \frac{||f(x+h) - f(x) - Df(x)[h]||_Y}{||h||_X} = 0
$$

- this equivalent definition is often easier to work with:

$$
f(x + h) = f(x) + Df(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||_Y}{||h||_X} = 0
$$

### definition derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
### chain rule

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$
#### intuition:
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$

Tags: mathematics
<!--ID: 1764180973290-->
END


START
Basic
[[chain rule]] 
- definition
- intuition
- example


Back: 
### definition derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
### chain rule

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$
#### intuition:
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$

Tags: mathematics
<!--ID: 1686036924124-->
END


START
Basic
- let $F = f\left(g(x)\right)$ with all 3 functions mapping between high dimensional spaces
- how to apply the[[chain rule]] in this case, and how are the dimensions?

Back: 
## chain rule
### single variable case
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$

#### intuition chain rule
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$


### multi variable case
#### single dimension case
- $x \in \mathbb{R}$ 
- $g: \mathbb{R} \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}$ 

$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= \lim_{h \to 0} \frac{ f\left(g(x + e h)\right) - f\left(g(x )\right) }{h}  \\
&= \sum_{j=1}^m   \frac{\partial f\left(g(x)\right)}{\partial g(x)_j} \frac{\partial g(x)_j}{\partial x} \\
\end{split}
$$


#### general case
let 
- $x \in \mathbb{R}^{n}$ 
- $g: \mathbb{R}^n \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}^k$ 


$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= D{g \circ f}(x) \\
&= \left.Df\left(u\right)\right|_{u=g(x)} Dg(x) \in \mathbb{R}^{k \times n} \\
\end{split}
$$

- with the [[jacobian]] $Df\left(g(x)\right) \in \mathbb{R}^{k\times m}$ and $Dg(x) \in \mathbb{R}^{m \times n}$ 

#### dimensions
- let $F = f\left(g(x)\right)$
- the rule for the decomposing the [[derivative]] with the [[chain rule]] is outer times inner and the dimensions are as follows

$$
\begin{split}
DF(x) = 
\underbrace{\left.Df(u)\right|_{u=g(x)}}_{
\mathbb{R}^{\mathrm{dim}(f) \times \mathrm{dim}(g)}} 
\quad
\underbrace{Dg(x)}_{\mathbb{R}^{\mathrm{dim}(g) \times \mathrm{dim}(x)}} 
\in \mathbb{R}^{\mathrm{dim}(F) \times \mathrm{dim}(x)} \\
\end{split}
$$
#### proof

- $g$ and $f$ are [[differentiable]] so that the following exists

$$
\begin{split}
g(x+h) 
=& g(x) + Dg(x)h + \varphi_g(h), \quad &\frac{||\varphi_g(h)||}{||h||} \to_{h \to 0} 0 \\
f\left(u+v(h)\right) =& f(u) + Df(u)v(h) + \varphi_f\left(v(h)\right) , \qquad &\frac{||\varphi_f(v)||}{||v||} \to_{v \to 0} 0  \\
\end{split}
$$
- now define

$$
\begin{split}
u :=& g(x)  \\
v(h) :=& Dg(x)h + \varphi_g(h)  \\
g(x+h) =& u + v(h)
\end{split}
$$
- now insert

$$
\begin{split}
f(g(x+h))
&= f(u + v(h)) \\
&= f(u) + Df(u)[v(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u)[Dg(x)[h] + \varphi_g(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u) Dg(x)[h] + \underbrace{ Df(u)\varphi_g(h) + \varphi_f(v(h))}_{r(h)} \\
r(h) &= Df(u)\varphi_g(h) + \varphi_f(v(h)), \quad  \frac{||r(h)||}{||h||} \to_{h \to 0} 0
\end{split}
$$

- it follows that

$$
\begin{split}
D f\left(g(x)\right) 
&= \underbrace{\left. Df\left(u\right) \right |_{u=g(x)}}_{\in \mathbb{R}^{1\times m}}\underbrace{ Dg(x)}_{\in \mathbb{R}^{m\times n}} \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

#### intuition
- if the ith dimension of $x$ changes by a delta, this can lead to a change of all dimensions of $g(x)$ and each change of a $g(x)_j$ can lead to a change of $f\left(g(x)\right)$ 
- by summing up the effects we have the [[partial derivative]]

$$
\lim_{h \to 0} \sum_{j=1}^m  \frac{ g(x+e_ih)_j -  g(x)_j}{h}  \cdot \frac{ f\left(g(x) + e_j h\right)-f\left(g(x)\right)}{h}   $$


___________

### general derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[derivative]] operator $Df: X \to L(X,Y)$ is a [[function]] that maps elements of $X$ to a [[bounded linear map]] $Df(x)[h]: X \to Y$
- the [[bounded linear map]] $Df(x)[h]: X \to Y$ is the [[derivative]] of $f$ in point $x \in X$ and can be interpreted as a linear approximation of $f$ in point $x$
- in the case of $f: \mathbb{R}^{m} \to \mathbb{R}^{n}$ the [[derivative]] $Df(x)[h] = Ah$ can be expressed as a [[matrix]] $A \in \mathbb{R}^{n \times m}$ which is called the [[jacobian]] $J_f(x)$

$$
\lim_{||h||_X \to 0} \frac{||f(x+h) - f(x) - Df(x)[h]||_Y}{||h||_X} = 0
$$

- this equivalent definition is often easier to work with:

$$
f(x + h) = f(x) + Df(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||_Y}{||h||_X} = 0
$$

### definition derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
### chain rule

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$
#### intuition:
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$

Tags: mathematics
<!--ID: 1764243748866-->
END