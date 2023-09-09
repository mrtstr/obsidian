## [[integration by parts]]

- the [[integration by parts]] rule for the [[integral]] is the equivalent of the [[product rule of derivative]]
- used to calculate the [[integral]] of [[function]] that is a [[sum]] of two [[function|functions]]

### theorem [[integration by parts]]

$$
\begin{split}
\int f(x) \frac{dg(x)}{x}dx = f(x)g(x)-\int g(x) \frac{df(x)}{dx} dx
\end{split}
$$
### given
![[derivative#definition derivative]]
![[integral#Infinite integral is an inverse function inverse derivative]]
![[product rule of derivative#multiplication product rule for derivative]]
### Proof
$$
\begin{split}
f(x) g(x) 
&= \int \frac{f(x) g(x)}{dx} dx \\
&= \int f(x) \frac{dg(x)}{x} + g(x) \frac{df(x)}{x}dx  \qquad \text{(product rule for the derivative)} \\
&= \int f(x) \frac{dg(x)}{x} dx + \int g(x) \frac{df(x)}{x}dx \\
\Rightarrow \int f(x) \frac{dg(x)}{x}dx &= f(x)g(x)-\int g(x) \frac{df(x)}{dx} dx
\end{split}
$$
### examples
$$
\begin{split}
\frac{dg(x)}{x} &= e^x \\
g(x) &= e^x \\
f(x) &= x^2 \\
\int x^2 e^x dx 
&=f(x)g(x)-\int g(x) \frac{df(x)}{dx} dx \\
&=x^2e^x-\int e^x \frac{dx^2}{dx} dx \\
&=x^2e^x-\int 2 e^x x dx \\
&=x^2e^x- \left(e^x 2x - 2\int e^x  \frac{dx}{dx} dx\right) \\
&=x^2e^x- \left(e^x 2x - 2\int e^x  dx\right) \\
&=x^2e^x- \left(e^x 2x - 2 e^x  \right) \\
&=e^x \left( x^2 - 2x + 2  \right) \\
\end{split}
$$

$$
\begin{split}
\frac{dg(x)}{x} &= x \\
g(x) &= \int x dx = \frac{x^2}{2}  \\
f(x) &= \ln(x) \\
\int x \ln(x) dx 
&=f(x)g(x)-\int g(x) \frac{df(x)}{dx} dx \\
&=\ln(x) \frac{x^2}{2} -\int \frac{x^2}{2}  \frac{d\ln(x)}{dx} dx \\
&=\ln(x) \frac{x^2}{2} -\int \frac{x^2}{2}  \frac{1}{x} dx \\
&=\ln(x) \frac{x^2}{2} -\int \frac{x}{2}  dx \\
&=\ln(x) \frac{x^2}{2} -\frac{x^2}{4}  \\
&= \frac{x^2}{2} \left(\ln(x) - \frac{1}{4}\right) \\
\end{split}
$$


# anki
START
Basic
[[integration by parts]]
- concept (2)
- theorem
- proof
Back: 

Tags: mathematics
- the [[integration by parts]] rule for the [[integral]] is the equivalent of the [[product rule of derivative]]
- used to calculate the [[integral]] of [[function]] that is a [[sum]] of two [[function|functions]]


### theorem

$$
\begin{split}
\int f(x) \frac{dg(x)}{x}dx = f(x)g(x)-\int g(x) \frac{df(x)}{dx} dx
\end{split}
$$
### given
#### Infinite [[integral]] is an [[inverse function|inverse]] [[derivative]]
Let $f(x)=\frac{dF(x)}{dx}$ be a [[continouse function]] defined for a [[function domain|domain]] $[a,b]$ that is the [[derivative]] of a [[function]] $F$. Since the **infinit [[integral]]** is the [[inverse function]] of the [[derivative]] it is defined as follows:

$$
\begin{split}
F(x) &= \int_a^x f(t) dt \\
\end{split}
$$
#### [[multiplication|product]] rule for [[derivative]]
- [[derivative]] of the [[multiplication]] of two [[function|functions]]
$$
\frac{d\left(f(x) \cdot g(x)\right)}{dx} 
= f(x)\frac{dg(x)}{dx} + g(x) \frac{df(x)}{dx}
$$

### Proof
$$
\begin{split}
f(x) g(x) 
&= \int \frac{f(x) g(x)}{dx} dx \\
&= \int f(x) \frac{dg(x)}{x} + g(x) \frac{df(x)}{x}dx  \qquad \text{(product rule for the derivative)} \\
&= \int f(x) \frac{dg(x)}{x} dx + \int g(x) \frac{df(x)}{x}dx \\
\Rightarrow \int f(x) \frac{dg(x)}{x}dx &= f(x)g(x)-\int g(x) \frac{df(x)}{dx} dx
\end{split}
$$

Tags: mathematics
<!--ID: 1693646460690-->
END

START
Basic
- examples
$$
\begin{split}

\int x^2 e^x dx  \\
\int x \ln(x) dx 

\end{split}
$$

Back: 
### theorem

$$
\begin{split}
\int f(x) \frac{dg(x)}{x}dx = f(x)g(x)-\int g(x) \frac{df(x)}{dx} dx
\end{split}
$$
### examples
$$
\begin{split}
\frac{dg(x)}{x} &= e^x \\
g(x) &= e^x \\
f(x) &= x^2 \\
\int x^2 e^x dx 
&=f(x)g(x)-\int g(x) \frac{df(x)}{dx} dx \\
&=x^2e^x-\int e^x \frac{dx^2}{dx} dx \\
&=x^2e^x-\int 2 e^x x dx \\
&=x^2e^x- \left(e^x 2x - 2\int e^x  \frac{dx}{dx} dx\right) \\
&=x^2e^x- \left(e^x 2x - 2\int e^x  dx\right) \\
&=x^2e^x- \left(e^x 2x - 2 e^x  \right) \\
&=e^x \left( x^2 - 2x + 2  \right) \\
\end{split}
$$

$$
\begin{split}
\frac{dg(x)}{x} &= x \\
g(x) &= \int x dx = \frac{x^2}{2}  \\
f(x) &= \ln(x) \\
\int x \ln(x) dx 
&=f(x)g(x)-\int g(x) \frac{df(x)}{dx} dx \\
&=\ln(x) \frac{x^2}{2} -\int \frac{x^2}{2}  \frac{d\ln(x)}{dx} dx \\
&=\ln(x) \frac{x^2}{2} -\int \frac{x^2}{2}  \frac{1}{x} dx \\
&=\ln(x) \frac{x^2}{2} -\int \frac{x}{2}  dx \\
&=\ln(x) \frac{x^2}{2} -\frac{x^2}{4}  \\
&= \frac{x^2}{2} \left(\ln(x) - \frac{1}{4}\right) \\
\end{split}
$$
Tags: mathematics
<!--ID: 1693646460694-->
END

