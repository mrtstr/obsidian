# Definition
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$


## Properties
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