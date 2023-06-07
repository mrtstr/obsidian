![[derivative#Definition]]

![[inverse function#Definition Inverse Function]]

## [[inverse function|inverse]] rule for [[derivative]]
- [[derivative]] of a [[inverse function]]

$$
\frac{df^{-1(y)}}{dy} = \frac{1}{\frac{df\left(f^{-1}(y)\right)}{df^{-1}(y)}}
$$
## proof for [[inverse function|inverse]] rule for [[derivative]]


$$
\begin{split}
\frac{dy}{dy} 
&= 1 \\
&= \frac{df\left(f^{-1}(y)\right)}{dy}  \qquad &\text{definition inverse} \\
&= \frac{df\left(f^{-1}(y)\right)}{df^{-1}(y)} \cdot \frac{df^{-1(y)}}{dy} \qquad &\text{chain rule} \\
\Rightarrow \frac{df^{-1(y)}}{dy} &= \frac{1}{\frac{df\left(f^{-1}(y)\right)}{df^{-1}(y)}}
\end{split}
$$

# anki
START
Basic
[[inverse rule of derivative]] with proof

Back: 
### definition derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
### definition inverse function
Given a [[function]] $f:X \rightarrow Y$ then $f^{-1}:Y \rightarrow X$ is the [[inverse function]] of $f$ if

$$
\forall x \in X: f^{-1}\left(f(x)\right) = x
$$
$$
\forall y \in Y: f\left(f^{-1}(y)\right) = y
$$
### [[inverse function|inverse]] rule

$$
\frac{df^{-1(y)}}{dy} = \frac{1}{\frac{df\left(f^{-1}(y)\right)}{df^{-1}(y)}}
$$
#### proof


$$
\begin{split}
\frac{dy}{dy} 
&= 1 \\
&= \frac{df\left(f^{-1}(y)\right)}{dy}  \qquad &\text{definition inverse} \\
&= \frac{df\left(f^{-1}(y)\right)}{df^{-1}(y)} \cdot \frac{df^{-1(y)}}{dy} \qquad &\text{chain rule} \\
\Rightarrow \frac{df^{-1(y)}}{dy} &= \frac{1}{\frac{df\left(f^{-1}(y)\right)}{df^{-1}(y)}}
\end{split}
$$

Tags: mathematics
<!--ID: 1686036924120-->
END