
### directional derivative
- let $(X, ||\cdot||_X)$ and $(Y, ||\cdot||_Y)$ be [[banach space|banach spaces]] and let $f: X\to Y$ a [[function]]
- the [[directional derivative]] $D_hf(x): X \to L(X,Y)$ in point $x \in X$ in the direction of $h \in X$ is defined as follows
- like the [[derivative]] the [[function]] $D_hf(x): X \to L(X,Y)$ maps every point $x \in X$ to a [[bounded linear map]] $\in L(X, Y)$ 
- the [[directional derivative]] measures the rate at which a [[function]] changes in a particular direction at a given point

$$
D_hf(x) = \lim_{t\to0}  \frac{f(x+th) - f(x)}{t}
$$



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
