

![[product rule of derivative#multiplication product rule for derivative]]

![[chain rule of derivative#composition chain rule for derivative]]

![[power rule for derivative#elementary power rulelinearity of the derivative]]

## qutient rule for derivative
- [[derivative]] of [[division]] of two [[function|functions]]
$$
\begin{split}
\frac{d \frac{f(x)}{g(x)}}{dx}
= \frac{
\frac{df(x)}{dx} \cdot g(x) - \frac{dg(x)}{dx} \cdot f(x)
}{
g(x)^2
}
\end{split}
$$

## proof for qutient rule for derivative

$$
\begin{split}
\frac{d \frac{f(x)}{g(x)}}{dx}
&= \frac{d f(x) \cdot g(x)^{-1}}{dx} \\
&= f(x) \frac{d   g(x)^{-1}}{dx} + g(x)^{-1} \frac{d f(x) }{dx} \qquad& \text{product rule}\\
&= f(x) \left(\frac{d   g(x)^{-1}}{dg(x)} \cdot \frac{d   g(x)}{dx}\right) + g(x)^{-1} \frac{d f(x) }{dx} \qquad& \text{chain rule}\\
&= f(x) \left(g(x)^{-2} \cdot (-1) \cdot \frac{d   g(x)}{dx}\right) + g(x)^{-2} g(x) \frac{d f(x) }{dx} \qquad& \text{power rule}\\
&= \frac{d \frac{f(x)}{g(x)}}{dx}= \frac{
\frac{df(x)}{dx} \cdot g(x) - \frac{dg(x)}{dx} \cdot f(x)
}{
g(x)^2
}
\end{split}
$$

# anki
START
Basic
[[qutient rule for derivative]]
- with proof


Back: 
[[derivative]] of [[division]] of two [[function|functions]]

## qutient rule for derivative
$$
\begin{split}
\frac{d \frac{f(x)}{g(x)}}{dx}
= \frac{
\frac{df(x)}{dx} \cdot g(x) - \frac{dg(x)}{dx} \cdot f(x)
}{
g(x)^2
}
\end{split}
$$
## proof

$$
\begin{split}
\frac{d \frac{f(x)}{g(x)}}{dx}
&= \frac{d f(x) \cdot g(x)^{-1}}{dx} \\
&= f(x) \frac{d   g(x)^{-1}}{dx} + g(x)^{-1} \frac{d f(x) }{dx} \qquad& \text{product rule}\\
&= f(x) \left(\frac{d   g(x)^{-1}}{dg(x)} \cdot \frac{d   g(x)}{dx}\right) + g(x)^{-1} \frac{d f(x) }{dx} \qquad& \text{chain rule}\\
&= f(x) \left(g(x)^{-2} \cdot (-1) \cdot \frac{d   g(x)}{dx}\right) + g(x)^{-2} g(x) \frac{d f(x) }{dx} \qquad& \text{power rule}\\
&= \frac{d \frac{f(x)}{g(x)}}{dx}= \frac{
\frac{df(x)}{dx} \cdot g(x) - \frac{dg(x)}{dx} \cdot f(x)
}{
g(x)^2
}
\end{split}
$$

## [[multiplication|product]] rule for [[derivative]]
- [[derivative]] of the [[multiplication]] of two [[function|functions]]
$$
\frac{d\left(f(x) \cdot g(x)\right)}{dx} 
= f(x)\frac{dg(x)}{dx} + g(x) \frac{df(x)}{dx}
$$

## [[composition|chain]] rule for [[derivative]]
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$
## elementary power rulelinearity of the [[derivative]]
- [[derivative]] of a [[polynomial]] with respect to the base
$$
\frac{dx^n}{dx} = n x^{n-1}
$$

Tags: mathematics
<!--ID: 1686115234661-->
END