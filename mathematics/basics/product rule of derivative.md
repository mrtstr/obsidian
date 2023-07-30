![[derivative#definition derivative]]

## [[multiplication|product]] rule for [[derivative]]
- [[derivative]] of the [[multiplication]] of two [[function|functions]]
$$
\frac{d\left(f(x) \cdot g(x)\right)}{dx} 
= f(x)\frac{dg(x)}{dx} + g(x) \frac{df(x)}{dx}
$$
## proof for [[multiplication|product]] rule for [[derivative]]
$$
\begin{split}
\frac{d\left(f(x) \cdot g(x)\right)}{dx} 
&= \lim_{h \rightarrow 0} \frac{f(x+h) g(x+h) - f(x) g(x)}{h} \\
&= \lim_{h \rightarrow 0} \frac{
f(x+h) g(x+h) - f(x) g(x) + f(x+h)g(x) - f(x+h)g(x)
}{h} \\
&= \lim_{h \rightarrow 0} \frac{
f(x+h) \left(g(x+h) - g(x)\right) + g(x) \left(f(x+h) - g(x)\right)
}{h} \\
&= \frac{df(x)}{dx} \cdot g(x) + \frac{dg(x)}{dx} \cdot \lim_{h \rightarrow 0} f(x+h)  \\
&=  \frac{df(x)}{dx} g(x) + \frac{dg(x)}{dx}f(x) 
\end{split}
$$
##  Leibniz rule
generalizing the [[product rule of derivative]] for [[derivative]] of higher order

### theorem
$$
\begin{split}
\frac{d^n\left(f(x) \cdot g(x)\right)}{d^nx} 
&= \sum_{k=0}^n {n \choose k} \frac{d^{n-k}f(x)}{d^{n-k}x} \frac{d^{k}f(x)}{d^{k}x} \\

\end{split}
$$
# anki
START
Basic
[[product rule of derivative]] with proof

Back: 
### definition derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
### product rule
$$
\frac{d\left(f(x) \cdot g(x)\right)}{dx} 
= f(x)\frac{dg(x)}{dx} + g(x) \frac{df(x)}{dx}
$$
#### proof
$$
\begin{split}
\frac{d\left(f(x) \cdot g(x)\right)}{dx} 
&= \lim_{h \rightarrow 0} \frac{f(x+h) g(x+h) - f(x) g(x)}{h} \\
&= \lim_{h \rightarrow 0} \frac{
f(x+h) g(x+h) - f(x) g(x) + f(x+h)g(x) - f(x+h)g(x)
}{h} \\
&= \lim_{h \rightarrow 0} \frac{
f(x+h) \left(g(x+h) - g(x)\right) + g(x) \left(f(x+h) - g(x)\right)
}{h} \\
&= \frac{df(x)}{dx} \cdot g(x) + \frac{dg(x)}{dx} \cdot \lim_{h \rightarrow 0} f(x+h)  \\
&=  \frac{df(x)}{dx} g(x) + \frac{dg(x)}{dx}f(x) 
\end{split}
$$

Tags: mathematics
<!--ID: 1686036924127-->
END


START
Basic
[[product rule of derivative]] for [[derivative]] of higher order $\frac{d^n\left(f(x) \cdot g(x)\right)}{d^nx}$ 

Back: 
$$
\begin{split}
\frac{d^n\left(f(x) \cdot g(x)\right)}{d^nx} 
&= \sum_{k=0}^n {n \choose k} \frac{d^{n-k}f(x)}{d^{n-k}x} \frac{d^{k}f(x)}{d^{k}x} \\
\end{split}
$$
Tags: mathematics
<!--ID: 1690697790749-->
END