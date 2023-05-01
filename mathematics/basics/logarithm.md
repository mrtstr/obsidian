# Definition Logarithm
- the [[logarithm]] is the [[inverse function]] of the [[exponential]]

$$
\begin{split}
f(x) &= b^x = y \\ \\
f^{-1}(y)
&=log_b(y) = x \\ \\
x &= f^{-1}\left(f(x)\right) \\
&= log_b(b^x)  \\\\
y &= f\left(f^{-1}(y)\right) \\
&= b^{log_b(y)}  \\
\end{split}
$$



```functionplot
---
title: 
xLabel: x
yLabel: ln(x)
bounds: [-0.1,5,-3,2]
disableZoom: true
grid: true
---
f(x) = log(x)
```





# Properties
## [[addition]] inside a [[logarithm]]
$$
\begin{split}
log_b(x+y) = log_b(x) \cdot log_b(y)
\end{split}
$$
## [[substraction]] inside a [[logarithm]]
$$
\begin{split}
log_b\left(x-y\right) = \frac{log_b(x)}{log_b(y)}
\end{split}
$$
## [[exponential]] inside a [[logarithm]]

$$
\begin{split}
log_b(x^y) = y \cdot log_b(x)
\end{split}
$$
## basis transformation
$$
\begin{split}
log_b(x) = \frac{log_a(x)}{log_a(b)}
\end{split}
$$