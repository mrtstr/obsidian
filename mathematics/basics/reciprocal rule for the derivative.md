
![[chain rule#composition chain rule for derivative]]

![[power rule for derivative#elementary power rulelinearity of the derivative]]

## reciprocal rule for [[derivative]]
- [[derivative]] of [[division]] of two [[function|functions]]
- special case of the [[qutient rule for derivative]]
$$
\begin{split}
\frac{d \frac{1}{f(x)}}{dx}
= -\frac{
\frac{df(x)}{dx}
}{
f(x)^2
}
\end{split}
$$

## proof for reciprocal rule for [[derivative]]

$$
\begin{split}
\frac{d \frac{1}{f(x)}}{dx}
&= \frac{d f(x)^{-1}}{dx} \\
&= \frac{d   f(x)^{-1}}{df(x)} \cdot \frac{d   f(x)}{dx} \qquad& \text{chain rule}\\
&= f(x)^{-2} \cdot(-1) \cdot \frac{d   f(x)}{dx} \qquad& \text{power rule}\\
&= -\frac{
\frac{df(x)}{dx}
}{
f(x)^2
}
\end{split}
$$

# anki
START
Basic
[[reciprocal rule for the derivative]]
- with proof


Back: 
[[derivative]] of [[division]] of two [[function|functions]]

### reciprocal rule for [[derivative]]
- [[derivative]] of [[division]] of two [[function|functions]]
- special case of the [[qutient rule for derivative]]
$$
\begin{split}
\frac{d \frac{1}{f(x)}}{dx}
= -\frac{
\frac{df(x)}{dx}
}{
f(x)^2
}
\end{split}
$$

### proof for reciprocal rule for [[derivative]]

$$
\begin{split}
\frac{d \frac{1}{f(x)}}{dx}
&= \frac{d f(x)^{-1}}{dx} \\
&= \frac{d   f(x)^{-1}}{df(x)} \cdot \frac{d   f(x)}{dx} \qquad& \text{chain rule}\\
&= f(x)^{-2} \cdot(-1) \cdot \frac{d   f(x)}{dx} \qquad& \text{power rule}\\
&= -\frac{
\frac{df(x)}{dx}
}{
f(x)^2
}
\end{split}
$$

### [[composition|chain]] rule for [[derivative]]
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$
### elementary power rulelinearity of the [[derivative]]
- [[derivative]] of a [[polynomial]] with respect to the base
$$
\frac{dx^n}{dx} = n x^{n-1}
$$

Tags: mathematics
<!--ID: 1686116180662-->
END