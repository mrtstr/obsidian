![[derivative#definition derivative]]

## [[derivative]] of the [[natural logarithm]]
### given
![[natural logarithm#properties]]
![[logarithm#theorem]]


### theorem
$$
\frac{d\ln(ax)}{dx} = \frac{1}{x}
$$
### proof
$$
\begin{split}
\frac{d\ln(ax)}{dx} 
&= \lim_{h \rightarrow 0} \frac{\ln\left(a(x+h)\right) - \ln(ax)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(\frac{a(x+h)}{ax}\right)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(\frac{x+h}{x}\right)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(1 + \frac{h}{x}\right)}{h} \\
&= \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax} \quad with \quad t=\frac{h}{x} \\
&= \frac{1}{x} \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot x}  \\
&= \frac{1}{x}  \\
\end{split}
$$
## [[derivative]] of the [[natural logarithm]] of a [[function]]
### given
![[derivative#chain rule of derivative]]

![[derivative logarithms#theorem]]

### theorem

$$
\begin{split}
\frac{d\ln\left(f(x)\right)}{dx} 
&= \frac{1}{f(x)} \frac{df(x)}{dx}  \\
\end{split}
$$
### proof
$$
\begin{split}
\frac{d\ln\left(f(x)\right)}{dx} 
&= \frac{d\ln\left(f(x)\right)}{df(x)} \frac{df(x)}{dx}  \\
&= \frac{1}{f(x)} \frac{df(x)}{dx}  \\
\end{split}
$$


# anki
START
Basic
[[derivative]] of the [[natural logarithm]] $\frac{d\ln(ax)}{dx}$ with [[proof]]

Back: 
### theorem
$$
\frac{d\ln(ax)}{dx} = \frac{1}{x}
$$
### given
$$
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} = 1
$$
$$
\begin{split}
log_b\left(\frac{x}{y}\right) = log_b(x) - log_b(y)
\end{split}
$$

### proof
$$
\begin{split}
\frac{d\ln(ax)}{dx} 
&= \lim_{h \rightarrow 0} \frac{\ln\left(a(x+h)\right) - \ln(ax)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(\frac{a(x+h)}{ax}\right)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(\frac{x+h}{x}\right)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(1 + \frac{h}{x}\right)}{h} \\
&= \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax} \quad with \quad t=\frac{h}{x} \\
&= \frac{1}{x} \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot x}  \\
&= \frac{1}{x}  \\
\end{split}
$$

Tags: mathematics
<!--ID: 1690611536702-->
END

START
Basic
[[derivative]] of the [[logarithm]] $\frac{d\log_b(ax)}{dx}$ with [[proof]]

Back: 
### theorem


$$
\frac{d\log_b(ax)}{dx} = \frac{1}{\ln(b)ax}
$$
### given
$$
\begin{split}
log_b(x) = \frac{log_a(x)}{log_a(b)}
\end{split}
$$
$$
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} = 1
$$
$$
\begin{split}
log_b\left(\frac{x}{y}\right) = log_b(x) - log_b(y)
\end{split}
$$

### proof
$$
\begin{split}
\frac{d\log_b(ax)}{dx} 
&= \frac{d\frac{\ln(ax)}{\ln(b)}}{dx}  \\
&= \frac{1}{\ln(b)} \frac{d\ln(ax)}{dx}  \\
&= \frac{1}{\ln(b)} \frac{1}{ax}  \\

\end{split}
$$

$$
\begin{split}
\frac{d\ln(ax)}{dx} 
&= \lim_{h \rightarrow 0} \frac{\ln(ax+h) - \ln(ax)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(\frac{ax+h}{ax}\right)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(1 + \frac{h}{ax}\right)}{h} \\
&= \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax} \quad with \quad t=\frac{h}{ax} \\
&= \frac{1}{ax} \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax}  \\
&= \frac{1}{ax}  \\
\end{split}
$$
Tags: mathematics
<!--ID: 1690611536708-->
END

START
Basic
[[derivative]] of the [[natural logarithm]] of a [[function]] $\frac{d\ln\left(f(x)\right)}{dx}$ with [[proof]]

Back: 
### theorem

$$
\begin{split}
\frac{d\ln\left(f(x)\right)}{dx} 
&= \frac{1}{f(x)} \frac{df(x)}{dx}  \\
\end{split}
$$



### given
$$
\lim_{h \rightarrow 0} \frac{\ln(1 + h)}{h} = 1
$$
$$
\begin{split}
log_b\left(\frac{x}{y}\right) = log_b(x) - log_b(y)
\end{split}
$$
$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$
### proof
$$
\begin{split}
\frac{d\ln\left(f(x)\right)}{dx} 
&= \frac{d\ln\left(f(x)\right)}{df(x)} \frac{df(x)}{dx}  \\
&= \frac{1}{f(x)} \frac{df(x)}{dx}  \\
\end{split}
$$
$$
\begin{split}
\frac{d\ln(ax)}{dx} 
&= \lim_{h \rightarrow 0} \frac{\ln(ax+h) - \ln(ax)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(\frac{ax+h}{ax}\right)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(1 + \frac{h}{ax}\right)}{h} \\
&= \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax} \quad with \quad t=\frac{h}{ax} \\
&= \frac{1}{ax} \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax}  \\
&= \frac{1}{ax}  \\
\end{split}
$$

Tags: mathematics
<!--ID: 1690697880369-->
END


START
Basic
How to calculate the [[derivative]] of a function $f(x)$ when it's easy to calculate the [[derivative]] of $\ln(f(x))$ but hard to calculate the [[derivative]] of $f(x)$ itself (proof given but not needed)

Back: 
$$
\begin{split}
\frac{df(x)}{dx}
&= \frac{1}{f(x)} \frac{d\ln\left(f(x)\right)}{dx}\\
\end{split}
$$
### proof
$$
\begin{split}
\frac{d\ln\left(f(x)\right)}{dx} 
&= \frac{d\ln\left(f(x)\right)}{df(x)} \frac{df(x)}{dx}  \\
&= \frac{1}{f(x)} \frac{df(x)}{dx}  \\
\end{split}
$$
$$
\begin{split}
\frac{d\ln(ax)}{dx} 
&= \lim_{h \rightarrow 0} \frac{\ln(ax+h) - \ln(ax)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(\frac{ax+h}{ax}\right)}{h} \\
&= \lim_{h \rightarrow 0} \frac{\ln\left(1 + \frac{h}{ax}\right)}{h} \\
&= \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax} \quad with \quad t=\frac{h}{ax} \\
&= \frac{1}{ax} \lim_{t \rightarrow 0} \frac{\ln\left(1 + t\right)}{t \cdot ax}  \\
&= \frac{1}{ax}  \\
\end{split}
$$
Tags: mathematics
<!--ID: 1690698714748-->
END