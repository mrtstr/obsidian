![[derivative#definition derivative]]

## [[exponential]] rule for [[derivative]]

$$
\frac{dc^{ax}}{dx} = c^{ax} a \ln(c)
$$
### special case: basis $c$ is [[eulers number]] $c=e$

$$
\frac{de^{ax}}{dx} = e^{ax} a \ln(e)= e^{ax} a \cdot 1
$$

## proof for [[derivative of exponential function]]
- the [[derivative of exponential function]] can be calculated by first applying the [[chain rule]] and using the [[limit]] identity of the [[natural logarithm]]

![[chain rule#composition chain rule for derivative]]

![[natural logarithm#limit identity of natural logarithm]]

$$
\begin{split}
\frac{dc^{x}}{dx} 
&= \lim_{h \rightarrow 0} \frac{c^{x + h} - c^x}{h} \\
&= \lim_{h \rightarrow 0} \frac{c^{x}c^{h} - c^x}{h} \\
&= \lim_{h \rightarrow 0} \frac{c^{x}\left(c^{h} - 1\right)}{h} \\
&= c^x \lim_{h \rightarrow 0} \frac{c^{h} - 1}{h} \\
&= c^x \ln(c)  \quad \quad \text{ln limit identity} \\ 
\\ \\
\frac{dc^{ax}}{dx} 
&= \frac{d(c^{x})^a}{dx} \\
&= \frac{d(c^{x})^a}{dc^{x}} \cdot \frac{dc^{x}}{dx} \quad \quad \text{chain rule} \\
&= a c^{x(a-1)}  \cdot  \frac{dc^{x}}{dx} \quad \quad \text{exponent rule} \\ 
&= a c^{x(a-1)}  \cdot  c^x \ln(c)  \\ 
&= a c^{xa} \ln(c)  \\ 

\end{split}
$$


# anki
START
Basic
[[derivative]] of a [[exponential]] [[function]] $dc^{ax}$ with proof
Back: 


$$
\frac{dc^{ax}}{dx} = c^{ax} a \ln(c)
$$

## requierments
- the [[derivative of exponential function]] can be calculated by first applying the [[chain rule]] and using the [[limit]] identity of the [[natural logarithm]]
#### definition derivative
$$
\frac{df(x)}{dx} = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h}
$$
#### [[composition|chain]] rule for [[derivative]]
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$





#### [[limit]] identity of [[natural logarithm]]
$$
\ln(a) = \lim_{h \rightarrow 0} \frac{a^h - 1}{h}
$$

## proof
$$
\begin{split}
\frac{dc^{x}}{dx} 
&= \lim_{h \rightarrow 0} \frac{c^{x + h} - c^x}{h} \\
&= \lim_{h \rightarrow 0} \frac{c^{x}c^{h} - c^x}{h} \\
&= \lim_{h \rightarrow 0} \frac{c^{x}\left(c^{h} - 1\right)}{h} \\
&= c^x \lim_{h \rightarrow 0} \frac{c^{h} - 1}{h} \\
&= c^x \ln(c)  \quad \quad \text{ln limit identity} \\ 
\\ \\
\frac{dc^{ax}}{dx} 
&= \frac{d(c^{x})^a}{dx} \\
&= \frac{d(c^{x})^a}{dc^{x}} \cdot \frac{dc^{x}}{dx} \quad \quad \text{chain rule} \\
&= a c^{x(a-1)}  \cdot  \frac{dc^{x}}{dx} \quad \quad \text{exponent rule} \\ 
&= a c^{x(a-1)}  \cdot  c^x \ln(c)  \\ 
&= a c^{xa} \ln(c)  \\ 

\end{split}
$$
Tags: mathematics
<!--ID: 1689407672466-->
END


START
Basic
[[derivative]] of a [[exponential]] [[function]] $de^{ax}$ with [[eulers number]] as basis (given the gerneral [[derivative of exponential function]])
Back: 


$$
\frac{dc^{ax}}{dx} = c^{ax} a \ln(c)
$$


### special case: basis $c$ is [[eulers number]] $c=e$

$$
\frac{de^{ax}}{dx} = e^{ax} a \ln(e)= e^{ax} a \cdot 1
$$

## proof
$$
\begin{split}
\frac{dc^{x}}{dx} 
&= \lim_{h \rightarrow 0} \frac{c^{x + h} - c^x}{h} \\
&= \lim_{h \rightarrow 0} \frac{c^{x}c^{h} - c^x}{h} \\
&= \lim_{h \rightarrow 0} \frac{c^{x}\left(c^{h} - 1\right)}{h} \\
&= c^x \lim_{h \rightarrow 0} \frac{c^{h} - 1}{h} \\
&= c^x \ln(c)  \quad \quad \text{ln limit identity} \\ 
\\ \\
\frac{dc^{ax}}{dx} 
&= \frac{d(c^{x})^a}{dx} \\
&= \frac{d(c^{x})^a}{dc^{x}} \cdot \frac{dc^{x}}{dx} \quad \quad \text{chain rule} \\
&= a c^{x(a-1)}  \cdot  \frac{dc^{x}}{dx} \quad \quad \text{exponent rule} \\ 
&= a c^{x(a-1)}  \cdot  c^x \ln(c)  \\ 
&= a c^{xa} \ln(c)  \\ 

\end{split}
$$
Tags: mathematics
<!--ID: 1689408245037-->
END