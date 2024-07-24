### forward analysis
- answers the question: given pertubed input data: how big can the resulting error be at most
- track the error step by step to calculate the absolute resulting error $\delta$
- given a [[function]] $F: X \subset \mathbb{R}^m \to Y \subset \mathbb{R}^n$ 
- given input data $x$ and perturbed input data $\tilde x_i = x_i + \Delta_{x_i}$ 

$$
\tilde F(x) = F(x) + \delta
$$
#### example $F(x_1, x_2)=x_1 + x_2$
$F(x_1, x_2)=x_1 + x_2$

$$
\begin{split}
\tilde F(x_1, x_2)
&=x_1 (1 + \epsilon) + x_2(1 + \epsilon) \\
&=x_1 + x_2 + \epsilon (x_1 + x_2) \\
\Rightarrow \delta &\leq  \epsilon (x_1 + x_2)
\end{split}
$$

#  anki
START
Basic
forward error analysis
- what question does it answer?
- methode
- example for $F(x_1, x_2)=x_1 + x_2$
Back: 
### forward analysis
- answers the question: given pertubed input data: how big can the resulting error be at most
- track the error step by step to calculate the absolute resulting error $\delta$
- given a [[function]] $F: X \subset \mathbb{R}^m \to Y \subset \mathbb{R}^n$ 
- given input data $x$ and perturbed input data $\tilde x_i = x_i + \Delta_{x_i}$ 

$$
\tilde F(x) = F(x) + \delta
$$
#### example $F(x_1, x_2)=x_1 + x_2$
$F(x_1, x_2)=x_1 + x_2$

$$
\begin{split}
\tilde F(x_1, x_2)
&=x_1 (1 + \epsilon) + x_2(1 + \epsilon) \\
&=x_1 + x_2 + \epsilon (x_1 + x_2) \\
\Rightarrow \delta &\leq  \epsilon (x_1 + x_2)
\end{split}
$$


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