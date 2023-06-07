![[derivative#definition]]

## [[linear function|linearity]] of the [[derivative]]
$$
\frac{d\left(af(x) + bg(x)\right)}{dx} = a \frac{df(x)}{dx} + b \frac{dg(x)}{dx}
$$
## proof for [[linear function|linearity]] of the [[derivative]]

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

# anki
START
Basic
[[linearity of the derivative]] with proof


Back: 
### definition derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
### linearity of the derivative
$$
\frac{d\left(af(x) + bg(x)\right)}{dx} = a \frac{df(x)}{dx} + b \frac{dg(x)}{dx}
$$
#### proof

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

Tags: mathematics
<!--ID: 1686036924114-->
END