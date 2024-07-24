### floating point representation
- let $fl(x)$ be the flowting point representation of $x \in \mathbb{R}$ with the base $p$ (e.g. decimal: $10$ or binary $2$) and the **mantisse** $a$ with $m$ digits end the **exponent** $t$ with $e$ digits
$$
fl(x) = a \cdot p^t  
$$
- when using a computer the number of bits of a number are shared between the mantissa and the exponent $n = m + e$

### round off error
- the following is the **absolut error** of the floting point representation
$$
|fl(x) - x| \leq \frac{p^{-m}}{2} \cdot p^t
$$
- the **relative error** $\epsilon$ is defined as follows und is used as roundoff unit
$$
\frac{|fl(x) - x|}{|x|} \leq \frac{p^{-m}}{2} \cdot p = \epsilon
$$
$$
fl(x) = x(1+\delta) \text{ with } |\delta| \leq \epsilon
$$
### floating point arithmetic
- for computer based numbers only the [[commutative]] law applies while [[associative]] and [[distributive]] laws do not apply

![[commutative#commutative]]

![[associative#associative]]

![[distributive#distributive]]

### error propagation
#### addition
- absolute error is small because $x+y$ is bigger than before
$$
\begin{split}
\tilde x + \tilde y 
&= x(1 + \delta_x)+y(1 + \delta_y) \\
&= x+y + x\delta_x + y\delta_y \\
&= x+y + (x+y) \frac{x\delta_x + y\delta_y}{x+y} \\
&= (x+y)  \left(1 + \frac{x\delta_x + y\delta_y}{x+y}\right) \\
\end{split}
$$

#### subtraction
- can lead to very big erros when $x\approx y$ → cancellation 
 $$
\begin{split}
\tilde x - \tilde y 
&= x(1 + \delta_x)-y(1 + \delta_y) \\
&= x-y + x\delta_x - y\delta_y \\
&= x-y + (x-y) \frac{x\delta_x - y\delta_y}{x-y} \\
&= (x-y)  \left(1 - \frac{x\delta_x - y\delta_y}{x-y}\right) \\
\end{split}
$$
#### multiplication
- absolute error is small because $\delta_x\delta_y \approx 0$ 
$$
\begin{split}
\tilde x \cdot \tilde y 
&= x(1 + \delta_x)\cdot y(1 + \delta_y) \\
&= xy \cdot (1 + \delta_x + \delta_y + \delta_x\delta_y) \\
\end{split}
$$

#### division
- small not problem
$$
\begin{split}
\tilde x / \tilde y 
&= x(1 + \delta_x)/ y(1 + \delta_y) \\
&= \frac{x}{y} \cdot \frac{1 + \delta_x}{1 + \delta_y} \\
&= \frac{x}{y} \cdot \left(1 + \frac{1 + \delta_x}{1 + \delta_y} -1\right) \\
&= \frac{x}{y} \cdot \left(1 + \frac{1 + \delta_x - 1 - \delta_y}{1 + \delta_y} \right) \\
&= \frac{x}{y} \cdot \left(1 + \frac{\delta_x - \delta_y}{1 + \delta_y} \right) \\
\end{split}
$$


### cancellation
- subtracting good approximations can lead to significant error when $x\approx y$

$$
\begin{split}
\tilde x - \tilde y 
&= x(1 + \delta_x)-y(1 + \delta_y) \\
&= x-y + x\delta_x - y\delta_y \\
&= x-y + (x-y) \frac{x\delta_x - y\delta_y}{x-y} \\
&= (x-y)  \left(1 - \frac{x\delta_x - y\delta_y}{x-y}\right) \\
\end{split}
$$

- how to transform to prevent cancellation
1) bruch auf einen nenner bringen
2) $a - b = \frac{a^2-b^2}{a+b}$

# anki

START
Basic
- how are floating point number represented?
- how large is the **relative error** and **absolute error**?
Back: 
### floating point representation
- let $fl(x)$ be the flowting point representation of $x \in \mathbb{R}$ with the base $p$ (e.g. decimal: $10$ or binary $2$) and the **mantisse** $a$ with $m$ digits end the **exponent** $t$ with $e$ digits
$$
fl(x) = a \cdot p^t  
$$
- when using a computer the number of bits of a number are shared between the mantissa and the exponent $n = m + e$

### round off error
- the following is the **absolut error** of the floting point representation
$$
|fl(x) - x| \leq \frac{p^{-m}}{2} \cdot p^t
$$
- the **relative error** $\epsilon$ is defined as follows und is used as roundoff unit
$$
\frac{|fl(x) - x|}{|x|} \leq \frac{p^{-m}}{2} \cdot p = \epsilon
$$
$$
fl(x) = x(1+\delta) \text{ with } |\delta| \leq \epsilon
$$


Tags: mathematics

END


START
Basic
which of the arithmetic are still true for floating point arithmetic?
Back: 
### floating point arithmetic
- for computer based numbers only the [[commutative]] law applies while [[associative]] and [[distributive]] laws do not apply

#### commutative
a operation is commutative if the following is true in general
$$
a \circ b = b \circ a
$$

#### associative
$$
a \circ (b \circ c) = (a \circ b) \circ c
$$

#### distributive
two operations $\circ$ and $\times$ are distributive if the following is true in general
$$
(a \times b) \circ b = (a \circ c) \times (b \circ c)
$$

_________________
### floating point representation
- let $fl(x)$ be the flowting point representation of $x \in \mathbb{R}$ with the base $p$ (e.g. decimal: $10$ or binary $2$) and the **mantisse** $a$ with $m$ digits end the **exponent** $t$ with $e$ digits
$$
fl(x) = a \cdot p^t  
$$
- when using a computer the number of bits of a number are shared between the mantissa and the exponent $n = m + e$

### round off error
- the following is the **absolut error** of the floting point representation
$$
|fl(x) - x| \leq \frac{p^{-m}}{2} \cdot p^t
$$
- the **relative error** $\epsilon$ is defined as follows und is used as roundoff unit
$$
\frac{|fl(x) - x|}{|x|} \leq \frac{p^{-m}}{2} \cdot p = \epsilon
$$
$$
fl(x) = x(1+\delta) \text{ with } |\delta| \leq \epsilon
$$

Tags: mathematics

END



START
Basic
- how is the rounding error propagated for addition and subtaction?
- can this lead to problems?
Back: 
### error propagation
#### addition
- absolute error is small because $x+y$ is bigger than before
$$
\begin{split}
\tilde x + \tilde y 
&= x(1 + \delta_x)+y(1 + \delta_y) \\
&= x+y + x\delta_x + y\delta_y \\
&= x+y + (x+y) \frac{x\delta_x + y\delta_y}{x+y} \\
&= (x+y)  \left(1 + \frac{x\delta_x + y\delta_y}{x+y}\right) \\
\end{split}
$$

#### subtraction
- can lead to very big erros when $x\approx y$ → cancellation 
 $$
\begin{split}
\tilde x - \tilde y 
&= x(1 + \delta_x)-y(1 + \delta_y) \\
&= x-y + x\delta_x - y\delta_y \\
&= x-y + (x-y) \frac{x\delta_x - y\delta_y}{x-y} \\
&= (x-y)  \left(1 - \frac{x\delta_x - y\delta_y}{x-y}\right) \\
\end{split}
$$
#### multiplication
- absolute error is small because $\delta_x\delta_y \approx 0$ 
$$
\begin{split}
\tilde x \cdot \tilde y 
&= x(1 + \delta_x)\cdot y(1 + \delta_y) \\
&= xy \cdot (1 + \delta_x + \delta_y + \delta_x\delta_y) \\
\end{split}
$$

#### division
- small not problem
$$
\begin{split}
\tilde x / \tilde y 
&= x(1 + \delta_x)/ y(1 + \delta_y) \\
&= \frac{x}{y} \cdot \frac{1 + \delta_x}{1 + \delta_y} \\
&= \frac{x}{y} \cdot \left(1 + \frac{1 + \delta_x}{1 + \delta_y} -1\right) \\
&= \frac{x}{y} \cdot \left(1 + \frac{1 + \delta_x - 1 - \delta_y}{1 + \delta_y} \right) \\
&= \frac{x}{y} \cdot \left(1 + \frac{\delta_x - \delta_y}{1 + \delta_y} \right) \\
\end{split}
$$


_________________
### floating point representation
- let $fl(x)$ be the flowting point representation of $x \in \mathbb{R}$ with the base $p$ (e.g. decimal: $10$ or binary $2$) and the **mantisse** $a$ with $m$ digits end the **exponent** $t$ with $e$ digits
$$
fl(x) = a \cdot p^t  
$$
- when using a computer the number of bits of a number are shared between the mantissa and the exponent $n = m + e$

### round off error
- the following is the **absolut error** of the floting point representation
$$
|fl(x) - x| \leq \frac{p^{-m}}{2} \cdot p^t
$$
- the **relative error** $\epsilon$ is defined as follows und is used as roundoff unit
$$
\frac{|fl(x) - x|}{|x|} \leq \frac{p^{-m}}{2} \cdot p = \epsilon
$$
$$
fl(x) = x(1+\delta) \text{ with } |\delta| \leq \epsilon
$$

Tags: mathematics

END


START
Basic
- how is the rounding error propagated for multiplication and division?
- can this lead to problems?
Back: 
### error propagation
#### addition
- absolute error is small because $x+y$ is bigger than before
$$
\begin{split}
\tilde x + \tilde y 
&= x(1 + \delta_x)+y(1 + \delta_y) \\
&= x+y + x\delta_x + y\delta_y \\
&= x+y + (x+y) \frac{x\delta_x + y\delta_y}{x+y} \\
&= (x+y)  \left(1 + \frac{x\delta_x + y\delta_y}{x+y}\right) \\
\end{split}
$$

#### subtraction
- can lead to very big erros when $x\approx y$ → cancellation 
 $$
\begin{split}
\tilde x - \tilde y 
&= x(1 + \delta_x)-y(1 + \delta_y) \\
&= x-y + x\delta_x - y\delta_y \\
&= x-y + (x-y) \frac{x\delta_x - y\delta_y}{x-y} \\
&= (x-y)  \left(1 - \frac{x\delta_x - y\delta_y}{x-y}\right) \\
\end{split}
$$
#### multiplication
- absolute error is small because $\delta_x\delta_y \approx 0$ 
$$
\begin{split}
\tilde x \cdot \tilde y 
&= x(1 + \delta_x)\cdot y(1 + \delta_y) \\
&= xy \cdot (1 + \delta_x + \delta_y + \delta_x\delta_y) \\
\end{split}
$$

#### division
- small not problem
$$
\begin{split}
\tilde x / \tilde y 
&= x(1 + \delta_x)/ y(1 + \delta_y) \\
&= \frac{x}{y} \cdot \frac{1 + \delta_x}{1 + \delta_y} \\
&= \frac{x}{y} \cdot \left(1 + \frac{1 + \delta_x}{1 + \delta_y} -1\right) \\
&= \frac{x}{y} \cdot \left(1 + \frac{1 + \delta_x - 1 - \delta_y}{1 + \delta_y} \right) \\
&= \frac{x}{y} \cdot \left(1 + \frac{\delta_x - \delta_y}{1 + \delta_y} \right) \\
\end{split}
$$


_________________
### floating point representation
- let $fl(x)$ be the flowting point representation of $x \in \mathbb{R}$ with the base $p$ (e.g. decimal: $10$ or binary $2$) and the **mantisse** $a$ with $m$ digits end the **exponent** $t$ with $e$ digits
$$
fl(x) = a \cdot p^t  
$$
- when using a computer the number of bits of a number are shared between the mantissa and the exponent $n = m + e$

### round off error
- the following is the **absolut error** of the floting point representation
$$
|fl(x) - x| \leq \frac{p^{-m}}{2} \cdot p^t
$$
- the **relative error** $\epsilon$ is defined as follows und is used as roundoff unit
$$
\frac{|fl(x) - x|}{|x|} \leq \frac{p^{-m}}{2} \cdot p = \epsilon
$$
$$
fl(x) = x(1+\delta) \text{ with } |\delta| \leq \epsilon
$$

Tags: mathematics

END

START
Basic
- explain the numeric effect **cancellation**
- when does it happen
- 2 measures to prevent it
Back: 
### cancellation
- subtracting good approximations can lead to significant error when $x\approx y$

$$
\begin{split}
\tilde x - \tilde y 
&= x(1 + \delta_x)-y(1 + \delta_y) \\
&= x-y + x\delta_x - y\delta_y \\
&= x-y + (x-y) \frac{x\delta_x - y\delta_y}{x-y} \\
&= (x-y)  \left(1 - \frac{x\delta_x - y\delta_y}{x-y}\right) \\
\end{split}
$$

- how to transform to prevent cancellation
1) bruch auf einen nenner bringen
2) $a - b = \frac{a^2-b^2}{a+b}$

_________________

### error propagation
#### addition
- absolute error is small because $x+y$ is bigger than before
$$
\begin{split}
\tilde x + \tilde y 
&= x(1 + \delta_x)+y(1 + \delta_y) \\
&= x+y + x\delta_x + y\delta_y \\
&= x+y + (x+y) \frac{x\delta_x + y\delta_y}{x+y} \\
&= (x+y)  \left(1 + \frac{x\delta_x + y\delta_y}{x+y}\right) \\
\end{split}
$$

#### subtraction
- can lead to very big erros when $x\approx y$ → cancellation 
 $$
\begin{split}
\tilde x - \tilde y 
&= x(1 + \delta_x)-y(1 + \delta_y) \\
&= x-y + x\delta_x - y\delta_y \\
&= x-y + (x-y) \frac{x\delta_x - y\delta_y}{x-y} \\
&= (x-y)  \left(1 - \frac{x\delta_x - y\delta_y}{x-y}\right) \\
\end{split}
$$
#### multiplication
- absolute error is small because $\delta_x\delta_y \approx 0$ 
$$
\begin{split}
\tilde x \cdot \tilde y 
&= x(1 + \delta_x)\cdot y(1 + \delta_y) \\
&= xy \cdot (1 + \delta_x + \delta_y + \delta_x\delta_y) \\
\end{split}
$$

#### division
- small not problem
$$
\begin{split}
\tilde x / \tilde y 
&= x(1 + \delta_x)/ y(1 + \delta_y) \\
&= \frac{x}{y} \cdot \frac{1 + \delta_x}{1 + \delta_y} \\
&= \frac{x}{y} \cdot \left(1 + \frac{1 + \delta_x}{1 + \delta_y} -1\right) \\
&= \frac{x}{y} \cdot \left(1 + \frac{1 + \delta_x - 1 - \delta_y}{1 + \delta_y} \right) \\
&= \frac{x}{y} \cdot \left(1 + \frac{\delta_x - \delta_y}{1 + \delta_y} \right) \\
\end{split}
$$



### floating point representation
- let $fl(x)$ be the flowting point representation of $x \in \mathbb{R}$ with the base $p$ (e.g. decimal: $10$ or binary $2$) and the **mantisse** $a$ with $m$ digits end the **exponent** $t$ with $e$ digits
$$
fl(x) = a \cdot p^t  
$$
- when using a computer the number of bits of a number are shared between the mantissa and the exponent $n = m + e$

### round off error
- the following is the **absolut error** of the floting point representation
$$
|fl(x) - x| \leq \frac{p^{-m}}{2} \cdot p^t
$$
- the **relative error** $\epsilon$ is defined as follows und is used as roundoff unit
$$
\frac{|fl(x) - x|}{|x|} \leq \frac{p^{-m}}{2} \cdot p = \epsilon
$$
$$
fl(x) = x(1+\delta) \text{ with } |\delta| \leq \epsilon
$$

Tags: mathematics

END