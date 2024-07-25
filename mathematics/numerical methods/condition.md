### condition
- given a [[function]] $F: X \subset \mathbb{R}^m \to Y \subset \mathbb{R}^n$ 
- given input data $x$ and perturbed input data $\tilde x = x + \Delta x$ 
- the [[condition]] of $F$ is the smallest number $\kappa\left(F\right)$ such that the following is true

$$
\frac{||F(x) - F(\tilde x)||}{||F(x)||} \leq \kappa\left(F\right) \cdot \frac{||x - \tilde x||}{||x||}
$$

### upper bound for the condition
- if the [[function]] $F$ is [[differentiabe]] then a $C$ that satsifies the following is an upper bound for the [[condition]] $\kappa\left(F\right) \leq C$

$$
\frac{\left|\left|\nabla F(x)\right|\right| \cdot ||x||}{||F(x)||} \leq C
$$
### example 
upper bound for [[condition]] of $f:\mathbb{R}^+ \times \mathbb{R}^+ \to \mathbb{R}^+$ regarding the [[norm|euclidian and infinity norm]]

$$
f(x, y) = xy
$$

$$
\begin{split}
C
&\geq \frac{\left|\left|\nabla F(x)\right|\right| \cdot ||x||}{||F(x)||} \\
&\geq \frac{\left|\left|\begin{matrix}y \\ x \end{matrix}\right|\right| \cdot \left|\left|\begin{matrix}x \\ y \end{matrix}\right|\right|}{|xy|} \\
\end{split}
$$
![[norm#euclidian norm ($l 2$)]]

$$
\begin{split}
\frac{\left|\left|\begin{matrix}y \\ x \end{matrix}\right|\right|_2 \cdot \left|\left|\begin{matrix}x \\ y \end{matrix}\right|\right|_2}{|xy|} 
&= \frac{  \left|\left|\begin{matrix}x \\ y \end{matrix}\right|\right|_2^2}{|xy|}  \\
&= \frac{ x^2+y^2}{xy}  \\
&= \frac{ x}{y} + \frac{y}{x}   \\
\end{split}
$$

![[norm#infinity norm ($l infty$)]]

$$
\begin{split}
\frac{\left|\left|\begin{matrix}y \\ x \end{matrix}\right|\right|_\infty \cdot \left|\left|\begin{matrix}x \\ y \end{matrix}\right|\right|_\infty}{|xy|} 
&= \frac{\max\{x, y\} \cdot \max\{x, y\}}{xy} \\
&= \frac{\max\{x, y\}}{\max\{x, y\} \cdot \min\{x, y\}} \\
&= \frac{\max\{x, y\}}{ \min\{x, y\}} \\
\end{split}
$$

START
Basic
[[condition]] of a [[function]]
- definition
- how to estimate the [[condition]] of a [[differentiabe]] [[function]]?
Back: 
### condition
- given a [[function]] $F: X \subset \mathbb{R}^m \to Y \subset \mathbb{R}^n$ 
- given input data $x$ and perturbed input data $\tilde x = x + \Delta x$ 
- the [[condition]] of $F$ is the smallest number $\kappa\left(F\right)$ such that the following is true

$$
\frac{||F(x) - F(\tilde x)||}{||F(x)||} \leq \kappa\left(F\right) \cdot \frac{||x - \tilde x||}{||x||}
$$

### upper bound for the condition
- if the [[function]] $F$ is [[differentiabe]] then a $C$ that satsifies the following is an upper bound for the [[condition]] $\kappa\left(F\right) \leq C$

$$
\frac{\left|\left|\nabla F(x)\right|\right| \cdot ||x||}{||F(x)||} \leq C
$$

Tags: mathematics
<!--ID: 1721830975431-->
END



START
Basic
calculate the upper bound for the [[condition]] of $f:\mathbb{R}^+ \times \mathbb{R}^+ \to \mathbb{R}^+$ regarding the [[norm|euclidian and infinity norm]]

$$
f(x, y) = xy
$$

Back: 
### example 
upper bound for [[condition]] of $f:\mathbb{R}^+ \times \mathbb{R}^+ \to \mathbb{R}^+$ regarding the [[norm|euclidian and infinity norm]]

$$
f(x, y) = xy
$$

$$
\begin{split}
C
&\geq \frac{\left|\left|\nabla F(x)\right|\right| \cdot ||x||}{||F(x)||} \\
&\geq \frac{\left|\left|\begin{matrix}y \\ x \end{matrix}\right|\right| \cdot \left|\left|\begin{matrix}x \\ y \end{matrix}\right|\right|}{|xy|} \\
\end{split}
$$
#### euclidian [[norm]] ($l^2$)
$$
||x||_2 = \left(\sum_{i \in [n]} |x_i|^2 \right)^{\frac{1}{2}}
$$



$$
\begin{split}
\frac{\left|\left|\begin{matrix}y \\ x \end{matrix}\right|\right|_2 \cdot \left|\left|\begin{matrix}x \\ y \end{matrix}\right|\right|_2}{|xy|} 
&= \frac{  \left|\left|\begin{matrix}x \\ y \end{matrix}\right|\right|_2^2}{|xy|}  \\
&= \frac{ x^2+y^2}{xy}  \\
&= \frac{ x}{y} + \frac{y}{x}   \\
\end{split}
$$

#### infinity [[norm]] ($l^\infty$)
$$
||x||_\infty = \left(\sum_{i \in [n]} |x_i|^\infty \right)^{\frac{1}{\infty}} = \max_{i \in [n]} |x_i|
$$


$$
\begin{split}
\frac{\left|\left|\begin{matrix}y \\ x \end{matrix}\right|\right|_\infty \cdot \left|\left|\begin{matrix}x \\ y \end{matrix}\right|\right|_\infty}{|xy|} 
&= \frac{\max\{x, y\} \cdot \max\{x, y\}}{xy} \\
&= \frac{\max\{x, y\}}{\max\{x, y\} \cdot \min\{x, y\}} \\
&= \frac{\max\{x, y\}}{ \min\{x, y\}} \\
\end{split}
$$

____________________

### condition
- given a [[function]] $F: X \subset \mathbb{R}^m \to Y \subset \mathbb{R}^n$ 
- given input data $x$ and perturbed input data $\tilde x = x + \Delta x$ 
- the [[condition]] of $F$ is the smallest number $\kappa\left(F\right)$ such that the following is true

$$
\frac{||F(x) - F(\tilde x)||}{||F(x)||} \leq \kappa\left(F\right) \cdot \frac{||x - \tilde x||}{||x||}
$$

### upper bound for the condition
- if the [[function]] $F$ is [[differentiabe]] then a $C$ that satsifies the following is an upper bound for the [[condition]] $\kappa\left(F\right) \leq C$

$$
\frac{\left|\left|\nabla F(x)\right|\right| \cdot ||x||}{||F(x)||} \leq C
$$

Tags: mathematics
<!--ID: 1721898211566-->
END