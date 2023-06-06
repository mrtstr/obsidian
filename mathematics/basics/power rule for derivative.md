![[derivative#definition derivative]]

## elementary power rule
$$
\frac{dx^n}{dx} = n x^{n-1}
$$
### proof for [[exponential|exponents]] from the [[natural numbers]] ([[induction proof]])
$$
\begin{split}
n=1: \\
\frac{dx}{dx} 
&= \lim_{h \rightarrow 0} \frac{x + h - x}{h} = 1 = x^0 \cdot 1 \\
n+1: \\
\frac{dx^{n+1}}{dx} 
&= \lim_{h \rightarrow 0} \frac{(x + h)^{n+1} - x^{n+1}}{h} \\
&= \lim_{h \rightarrow 0} \frac{(x + h)(x + h)^{n} - xx^{n}}{h}  \\
&= \lim_{h \rightarrow 0} \frac{ h(x + h)^{n} + x (x + h)^{n} - xx^{n}}{h}  \\
&= \lim_{h \rightarrow 0} \frac{ h(x + h)^{n} + x \left((x + h)^{n} - x^{n}\right)}{h}  \\
&= \lim_{h \rightarrow 0}\frac{ h(x + h)^{n}}{h} + \lim_{h \rightarrow 0} \frac{  x \left((x + h)^{n} - x^{n}\right)}{h}  \\
&= x^n + x  \frac{dx^n}{x}  \\
&= x^n + x \cdot n x^{n-1}  \\
&= x^n +  n x^{n}  \\
&= (n + 1) x^{n}  \\
&= \left(n + 1\right) x^{\left(n + 1\right) - 1}  \\
\end{split}
$$
### proof for [[exponential|exponent]] $\frac{1}{n}$ using the [[chain rule of derivative]]
$$
\begin{split}
f(x) &= x^{\frac{1}{n}} = y \\
f^{-1}\left(y\right) &= y^{n} = x \\
1 = \frac{dy}{dy} 
&= \frac{df\left(f^{-1}\left(y\right)\right)}{dy} &\text{definition of inverse}\\
&= \frac{df\left(f^{-1}\left(y\right)\right)}{df^{-1}\left(y\right)} \frac{df^{-1}\left(y\right)}{dy} &\text{chain rule}\\
&= \frac{df\left(x\right)}{dx} \cdot \frac{dy^{n}}{dy}\\
&= \frac{dx^{\frac{1}{n}}}{dx} \cdot n  y^{n-1}\\
\Rightarrow  \frac{df(x)}{dx} &= \frac{dx^{\frac{1}{n}}}{dx} \\
&= \frac{1}{ n  y^{n-1}} \\
&= \frac{1}{ n  \left({x^{\frac{1}{n}}}\right)^{n-1}} \\
&= \frac{1}{ n  x^{\frac{n-1}{n}}} \\
&= \frac{1}{ n} x^{\frac{1}{n} - 1} \\
\end{split}
$$

### proof for [[exponential|exponents]] from the [[rational number]] $q = \frac{n}{m}$ using the [[chain rule of derivative|chain rule]]
$$
\begin{split}
\frac{dx^{\frac{n}{m}}}{dx} 
&= \frac{d\left(x^{\frac{1}{m}}\right)^n}{d\frac{1}{m}} \cdot \frac{dx^{\frac{1}{m}}}{dx} &\text{chain rule}  \\
&= n\left(x^{\frac{1}{m}}\right)^{n-1} \cdot \frac{1}{m} x^{\frac{1}{m}-1}  \\
&= \frac{n}{m}x^{\frac{n}{m} -1}  \\
\end{split}
$$


# anki
START
Basic
[[power rule for derivative|elementary power rule]]
- proof for [[exponential|exponents]] from the [[natural numbers]]

Back: 
### definition derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$

### elementary power rule
$$
\frac{dx^n}{dx} = n x^{n-1}
$$
#### proof for [[exponential|exponents]] from the [[natural numbers]] ([[induction proof]])
$$
\begin{split}
n=1: \\
\frac{dx}{dx} 
&= \lim_{h \rightarrow 0} \frac{x + h - x}{h} = 1 = x^0 \cdot 1 \\
n+1: \\
\frac{dx^{n+1}}{dx} 
&= \lim_{h \rightarrow 0} \frac{(x + h)^{n+1} - x^{n+1}}{h} \\
&= \lim_{h \rightarrow 0} \frac{(x + h)(x + h)^{n} - xx^{n}}{h}  \\
&= \lim_{h \rightarrow 0} \frac{ h(x + h)^{n} + x (x + h)^{n} - xx^{n}}{h}  \\
&= \lim_{h \rightarrow 0} \frac{ h(x + h)^{n} + x \left((x + h)^{n} - x^{n}\right)}{h}  \\
&= \lim_{h \rightarrow 0}\frac{ h(x + h)^{n}}{h} + \lim_{h \rightarrow 0} \frac{  x \left((x + h)^{n} - x^{n}\right)}{h}  \\
&= x^n + x  \frac{dx^n}{x}  \\
&= x^n + x \cdot n x^{n-1}  \\
&= x^n +  n x^{n}  \\
&= (n + 1) x^{n}  \\
&= \left(n + 1\right) x^{\left(n + 1\right) - 1}  \\
\end{split}
$$
Tags: mathematics
<!--ID: 1686068039038-->
END


START
Basic
[[power rule for derivative|elementary power rule]]
- proof for [[exponential|exponents]] from the [[rational number]] given the [[power rule for derivative|elementary power rule]] for [[exponential|exponents]] from the [[natural numbers]]

Back: 
### definition derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$

### elementary power rule
$$
\frac{dx^n}{dx} = n x^{n-1}
$$
#### proof for [[exponential|exponents]] from the [[natural numbers]] ([[induction proof]])
$$
\begin{split}
n=1: \\
\frac{dx}{dx} 
&= \lim_{h \rightarrow 0} \frac{x + h - x}{h} = 1 = x^0 \cdot 1 \\
n+1: \\
\frac{dx^{n+1}}{dx} 
&= \lim_{h \rightarrow 0} \frac{(x + h)^{n+1} - x^{n+1}}{h} \\
&= \lim_{h \rightarrow 0} \frac{(x + h)(x + h)^{n} - xx^{n}}{h}  \\
&= \lim_{h \rightarrow 0} \frac{ h(x + h)^{n} + x (x + h)^{n} - xx^{n}}{h}  \\
&= \lim_{h \rightarrow 0} \frac{ h(x + h)^{n} + x \left((x + h)^{n} - x^{n}\right)}{h}  \\
&= \lim_{h \rightarrow 0}\frac{ h(x + h)^{n}}{h} + \lim_{h \rightarrow 0} \frac{  x \left((x + h)^{n} - x^{n}\right)}{h}  \\
&= x^n + x  \frac{dx^n}{x}  \\
&= x^n + x \cdot n x^{n-1}  \\
&= x^n +  n x^{n}  \\
&= (n + 1) x^{n}  \\
&= \left(n + 1\right) x^{\left(n + 1\right) - 1}  \\
\end{split}
$$

#### proof for [[exponential|exponent]] $\frac{1}{n}$ using the [[chain rule of derivative]]
$$
\begin{split}
f(x) &= x^{\frac{1}{n}} = y \\
f^{-1}\left(y\right) &= y^{n} = x \\
1 = \frac{dy}{dy} 
&= \frac{df\left(f^{-1}\left(y\right)\right)}{dy} &\text{definition of inverse}\\
&= \frac{df\left(f^{-1}\left(y\right)\right)}{df^{-1}\left(y\right)} \frac{df^{-1}\left(y\right)}{dy} &\text{chain rule}\\
&= \frac{df\left(x\right)}{dx} \cdot \frac{dy^{n}}{dy}\\
&= \frac{dx^{\frac{1}{n}}}{dx} \cdot n  y^{n-1}\\
\Rightarrow  \frac{df(x)}{dx} &= \frac{dx^{\frac{1}{n}}}{dx} \\
&= \frac{1}{ n  y^{n-1}} \\
&= \frac{1}{ n  \left({x^{\frac{1}{n}}}\right)^{n-1}} \\
&= \frac{1}{ n  x^{\frac{n-1}{n}}} \\
&= \frac{1}{ n} x^{\frac{1}{n} - 1} \\
\end{split}
$$

#### proof for [[exponential|exponents]] from the [[rational number]] $q = \frac{n}{m}$ using the [[chain rule of derivative|chain rule]]
$$
\begin{split}
\frac{dx^{\frac{n}{m}}}{dx} 
&= \frac{d\left(x^{\frac{1}{m}}\right)^n}{d\frac{1}{m}} \cdot \frac{dx^{\frac{1}{m}}}{dx} &\text{chain rule}  \\
&= n\left(x^{\frac{1}{m}}\right)^{n-1} \cdot \frac{1}{m} x^{\frac{1}{m}-1}  \\
&= \frac{n}{m}x^{\frac{n}{m} -1}  \\
\end{split}
$$


Tags: mathematics
<!--ID: 1686068039047-->
END