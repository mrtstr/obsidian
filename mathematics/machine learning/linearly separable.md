## linearly separable (binary case)
- given two [[set]] of samples $A = \{a_1, ..., a_n\}, B = \{b_1, ..., b_k\} \subset \mathbb{R}^n$
- $A$ and $B$ are called [[linearly separable]] if there exists a [[vector]] $\mathrm{w}$ and a [[scalar]] $w_0$ such that the following is true

$$
\begin{split}
\mathrm{w}^\top a_i + w_0 > 0 \ \forall a_i \in A \\
\mathrm{w}^\top b_i + w_0 < 0 \ \forall b_i \in B \\
\end{split}
$$
### linearly separable and the [[convex hull]]
- $A$ and $B$ are [[linearly separable]] exactly when their [[convex hull]] are [[intersection]] free $\mathrm{conv}(A) \cap \mathrm{conv}(B) = \emptyset$ 

#### proof
- let $a^* \in \mathrm{conv}(A)$ and $b^* \in \mathrm{conv}(B)$ the closest points of $\mathrm{conv}(A)$ and $\mathrm{conv}(B)$
- since $\mathrm{conv}(A)$ and $\mathrm{conv}(B)$ are [[intersection]] free the distance between $a^*$ and $b^*$ has to be greater $0$

$$
||a^* - b^*|| = \min \{||a - b||: a \in \mathrm{conv}(A), b \in \mathrm{conv}(B)\} > 0
$$

- the following hyperplane $H$ is separating $A$ and $B$

$$
\begin{split}
H &= \{x : w^\top x + w_0 = 0\} \\
\mathrm{w} &= a^* - b^* \\
w_0 
&= \frac{\left(b^* - a^*\right)^\top \left(a^* +b^* \right)}{2} \\
&= -\frac{w^\top (a^* +b^*)}{2} \\
&= \frac{||b^*||^2-||a^*||^2}{2}
\end{split}
$$

- first to show that $\forall a \in A: \mathrm{w}^\top a > \mathrm{w}^\top a^*$
- because of the [[convex|convexity]] the point $x_t = a_i t + (1-t) a^* \in \mathrm{conv}(A)$ for an arbitrary $a_i \in A$ has to be in $\mathrm{conv}(A)$ for $t \in [0,1]$
- since $||a_t - b^*||^2$ is minimal at the point $t=0$ (over $t \in [0,1]$) $t=0$  is also minimizing $f(t)$ and thus $f'(0) \geq 0$
- the derivative of the function $f$ has to be greater than $0$ for all $t>0$

$$
\begin{split}
f(t) &= ||a_t - b^*||^2 \\
&= ||\mathrm{w} +  t (a_i - a^*)||^2 \\
&= ||\mathrm{w}||^2 +  t^2 ||(a_i - a^*)||^2 + 2 t \mathrm{w}^\top (a_i - a^*) \\
f'(0) &= 2 \mathrm{w}^\top (a_i - a^*) \geq 0 \\
\Rightarrow & \forall a_i \in A: \mathrm{w}^\top a_i \geq \mathrm{w}^\top a^*\\
\end{split}
$$

- equivalently, we have $\forall b_i \in B: \mathrm{w}^\top b_i \leq \mathrm{w}^\top b^*$

$$
\begin{split}
\mathrm{w}^\top \left(a_i - \frac{a^* - b^*}{2} \right) 
&= \mathrm{w}^\top a_i - \frac{1}{2} \left(\mathrm{w}^\top a^* + \mathrm{w}^\top a^* \right)\\
&\geq \mathrm{w}^\top a^* - \frac{1}{2} \left(\mathrm{w}^\top a^* + \mathrm{w}^\top a^* \right)\\
&= \frac{1}{2}\mathrm{w}^\top \left(a^* -  b^* \right)\\
&= \frac{1}{2}||\mathrm{w}||^2\\
&\geq 0 \ \forall a_i \in A \\
\end{split}
$$

- similar for the $B$

$$
\mathrm{w}^\top \left(b_i - \frac{a^* - b^*}{2} \right) \leq 0 \ \forall b_i \in B
$$

- reverse direction is trivial: if there is a separating hyperplane such that the one set is completely on one side and the other set is completely on the other, side the sets cannot intersect
# ------------

![[convex hull#convex hull]]



START
Basic
[[linearly separable]]
- two equivalent definitions

Back: 
## linearly separable (binary case)
- given two [[set]] of samples $A = \{a_1, ..., a_n\}, B = \{b_1, ..., b_k\} \subset \mathbb{R}^n$
- $A$ and $B$ are called [[linearly separable]] if there exists a [[vector]] $\mathrm{w}$ and a [[scalar]] $w_0$ such that the following is true

$$
\begin{split}
\mathrm{w}^\top a_i + w_0 > 0 \ \forall a_i \in A \\
\mathrm{w}^\top b_i + w_0 < 0 \ \forall b_i \in B \\
\end{split}
$$
### linearly separable and the [[convex hull]]
- $A$ and $B$ are [[linearly separable]] exactly when their [[convex hull]] are [[intersection]] free $\mathrm{conv}(A) \cap \mathrm{conv}(B) = \emptyset$ 

#### convex hull
- given a [[set]] of [[vector]] $A=a_1, ..., a_n$ 
- the [[convex hull]] of $A$ is defined as follows

$$
\begin{split}
\mathrm{conv}(A) = \left\{\sum_{i=1}^n \alpha_i a_i : \sum_{i=1}^n \alpha_i = 1 \right\}
\end{split}
$$

#### proof
- let $a^* \in \mathrm{conv}(A)$ and $b^* \in \mathrm{conv}(B)$ the closest points of $\mathrm{conv}(A)$ and $\mathrm{conv}(B)$
- since $\mathrm{conv}(A)$ and $\mathrm{conv}(B)$ are [[intersection]] free the distance between $a^*$ and $b^*$ has to be greater $0$

$$
||a^* - b^*|| = \min \{||a - b||: a \in \mathrm{conv}(A), b \in \mathrm{conv}(B)\} > 0
$$

- the following hyperplane $H$ is separating $A$ and $B$

$$
\begin{split}
H &= \{x : w^\top x + w_0 = 0\} \\
\mathrm{w} &= a^* - b^* \\
w_0 
&= \frac{\left(b^* - a^*\right)^\top \left(a^* +b^* \right)}{2} \\
&= -\frac{w^\top (a^* +b^*)}{2} \\
&= \frac{||b^*||^2-||a^*||^2}{2}
\end{split}
$$

- first to show that $\forall a \in A: \mathrm{w}^\top a > \mathrm{w}^\top a^*$
- because of the [[convex|convexity]] the point $x_t = a_i t + (1-t) a^* \in \mathrm{conv}(A)$ for an arbitrary $a_i \in A$ has to be in $\mathrm{conv}(A)$ for $t \in [0,1]$
- since $||a_t - b^*||^2$ is minimal at the point $t=0$ (over $t \in [0,1]$) $t=0$ is also minimizing $f(t)$ and thus $f'(0) \geq 0$
- the derivative of the function $f$ has to be greater than $0$ for all $t>0$

$$
\begin{split}
f(t) &= ||a_t - b^*||^2 \\
&= ||\mathrm{w} +  t (a_i - a^*)||^2 \\
&= ||\mathrm{w}||^2 +  t^2 ||(a_i - a^*)||^2 + 2 t \mathrm{w}^\top (a_i - a^*) \\
f'(0) &= 2 \mathrm{w}^\top (a_i - a^*) \geq 0 \\
\Rightarrow & \forall a_i \in A: \mathrm{w}^\top a_i \geq \mathrm{w}^\top a^*\\
\end{split}
$$

- equivalently, we have $\forall b_i \in B: \mathrm{w}^\top b_i \leq \mathrm{w}^\top b^*$

$$
\begin{split}
\mathrm{w}^\top \left(a_i - \frac{a^* - b^*}{2} \right) 
&= \mathrm{w}^\top a_i - \frac{1}{2} \left(\mathrm{w}^\top a^* + \mathrm{w}^\top a^* \right)\\
&\geq \mathrm{w}^\top a^* - \frac{1}{2} \left(\mathrm{w}^\top a^* + \mathrm{w}^\top a^* \right)\\
&= \frac{1}{2}\mathrm{w}^\top \left(a^* -  b^* \right)\\
&= \frac{1}{2}||\mathrm{w}||^2\\
&\geq 0 \ \forall a_i \in A \\
\end{split}
$$

- similar for the $B$

$$
\mathrm{w}^\top \left(b_i - \frac{a^* - b^*}{2} \right) \leq 0 \ \forall b_i \in B
$$

- reverse direction is trivial: if there is a separating hyperplane such that the one set is completely on one side and the other set is completely on the other, side the sets cannot intersect



Tags: mathematics WS2526 ml
END
