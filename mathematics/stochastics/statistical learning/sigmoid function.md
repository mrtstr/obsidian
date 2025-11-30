### sigmoid function
- the [[sigmoid function]] $\sigma: \mathbb{R} \to (0,1)$ is defined as follows:
- its the inverse of the [[logit function]]

$$
\sigma(u) = \frac{1}{1+e^{-u}}
$$

#### properties
$$
\sigma(0) = \frac{1}{2}
$$

$$
\begin{split}
\lim_{u\to\infty}\sigma(u) &= 1 \\
\lim_{u\to-\infty}\sigma(u) &= 0 \\
\end{split}
$$

$$
1-\sigma(u) = \frac{1}{1+e^{+u}} = \sigma(-u)
$$

###### proof


$$
\begin{split}
1-\sigma(u) 
&= 1-\frac{1}{1+e^{-u}} \\
&= \frac{1+e^{-u}}{1+e^{-u}}-\frac{1}{1+e^{-u}} \\
&= \frac{e^{-u}}{1+e^{-u}} \\
&= \frac{1}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \\
&= \frac{1}{e^{--u}+1} \\
&= \sigma(-u) \\
\end{split}
$$

#### derivative of the sigmoid function

$$
\begin{split}
\frac{d}{du}\sigma(u) 
&= \frac{d}{du} \frac{1}{1+e^{-u}} \\
&=  \frac{-1}{(1+e^{-u})^2} \cdot e^{-u} \cdot -1 \\
&=  \frac{e^{-u}}{1+e^{-u}} \frac{1}{1+e^{-u}}\\
&=  \frac{e^{-u}}{1+e^{-u}} \sigma(u)\\
&=  \frac{\frac{e^{-u}}{e^{-u}}}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \sigma(u)\\
&=  \frac{1}{e^{u}+1} \sigma(u)\\
&=  \sigma(-u) \sigma(u)\\
&=  (1-\sigma(u)) \sigma(u)\\
\end{split}
$$
#### application
- often used to predict probabilities in binary [[classification]] problems, e.g. [[logistic regression]]

#### inverse of the sigmoid function
- the [[inverse function]] on the [[sigmoid function]] is the [[logit function]]

$$
\begin{split}
\sigma(\mathrm{logit}(p) ) 
&= \frac{1}{1+e^{-\log\left(\frac{p}{1-p}\right)}} \\
&= \frac{1}{1+\left(e^{\log\left(\frac{p}{1-p}\right)}\right)^{-1}} \\
&= \frac{1}{1+\frac{1-p}{p}} \\
&= \frac{1}{1+\frac{1}{p}-1} \\
&= p \\
\end{split}
$$

# -----------

![[logit function#logit function]]

# anki

START
Basic
[[sigmoid function]]
- definition
- application
- properties (3)
- [[inverse function]] with proof
- [[derivative]]
Back: 
### sigmoid function
- the [[sigmoid function]] $\sigma: \mathbb{R} \to (0,1)$ is defined as follows:
- its the inverse of the [[logit function]]

$$
\sigma(u) = \frac{1}{1+e^{-u}}
$$

#### properties
$$
\sigma(0) = \frac{1}{2}
$$

$$
\begin{split}
\lim_{u\to\infty}\sigma(u) &= 1 \\
\lim_{u\to-\infty}\sigma(u) &= 0 \\
\end{split}
$$

$$
1-\sigma(u) = \frac{1}{1+e^{+u}} = \sigma(-u)
$$

###### proof


$$
\begin{split}
1-\sigma(u) 
&= 1-\frac{1}{1+e^{-u}} \\
&= \frac{1+e^{-u}}{1+e^{-u}}-\frac{1}{1+e^{-u}} \\
&= \frac{e^{-u}}{1+e^{-u}} \\
&= \frac{1}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \\
&= \frac{1}{e^{--u}+1} \\
&= \sigma(-u) \\
\end{split}
$$

#### derivative

$$
\begin{split}
\frac{d}{du}\sigma(u) 
&= \frac{d}{du} \frac{1}{1+e^{-u}} \\
&=  \frac{-1}{(1+e^{-u})^2} \cdot e^{-u} \cdot -1 \\
&=  \frac{e^{-u}}{1+e^{-u}} \frac{1}{1+e^{-u}}\\
&=  \frac{e^{-u}}{1+e^{-u}} \sigma(u)\\
&=  \frac{\frac{e^{-u}}{e^{-u}}}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \sigma(u)\\
&=  \frac{1}{e^{u}+1} \sigma(u)\\
&=  \sigma(-u) \sigma(u)\\
&=  (1-\sigma(u)) \sigma(u)\\
\end{split}
$$
#### application
- often used to predict probabilities in binary [[classification]] problems, e.g. [[logistic regression]]

#### inverse of the sigmoid function
- the [[inverse function]] on the [[sigmoid function]] is the [[logit function]]

$$
\begin{split}
\sigma(\mathrm{logit}(p) ) 
&= \frac{1}{1+e^{-\log\left(\frac{p}{1-p}\right)}} \\
&= \frac{1}{1+\left(e^{\log\left(\frac{p}{1-p}\right)}\right)^{-1}} \\
&= \frac{1}{1+\frac{1-p}{p}} \\
&= \frac{1}{1+\frac{1}{p}-1} \\
&= p \\
\end{split}
$$

_____________

### logit function
- the [[logit function]] $\mathrm{logit}: (0,1)\to\mathbb{R}$ is defined as follows and is the [[inverse function]] of the [[sigmoid function]] 

$$
\mathrm{logit}(p) = \log\left(\frac{p}{1-p}\right)
$$
Tags: mathematics basics SS25
<!--ID: 1752944639524-->
END



START
Basic
proof the following property of the [[sigmoid function]]

$$
1-\sigma(u) = \sigma(-u)
$$

Back: 
### sigmoid function
- the [[sigmoid function]] $\sigma: \mathbb{R} \to (0,1)$ is defined as follows:
- its the inverse of the [[logit function]]

$$
\sigma(u) = \frac{1}{1+e^{-u}}
$$

$$
1-\sigma(u) = \frac{1}{1+e^{+u}} = \sigma(-u)
$$
###### proof


$$
\begin{split}
1-\sigma(u) 
&= 1-\frac{1}{1+e^{-u}} \\
&= \frac{1+e^{-u}}{1+e^{-u}}-\frac{1}{1+e^{-u}} \\
&= \frac{e^{-u}}{1+e^{-u}} \\
&= \frac{1}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \\
&= \frac{1}{e^{--u}+1} \\
&= \sigma(-u) \\
\end{split}
$$



Tags: mathematics basics SS25
<!--ID: 1752944639527-->
END


START
Basic
[[derivative]] of the [[sigmoid function]] with calculation

Back: 

$$
\begin{split}
\frac{d}{du}\sigma(u) 
&= \frac{d}{du} \frac{1}{1+e^{-u}} \\
&=  \frac{-1}{(1+e^{-u})^2} \cdot e^{-u} \cdot -1 \\
&=  \frac{e^{-u}}{1+e^{-u}} \frac{1}{1+e^{-u}}\\
&=  \frac{e^{-u}}{1+e^{-u}} \sigma(u)\\
&=  \frac{\frac{e^{-u}}{e^{-u}}}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \sigma(u)\\
&=  \frac{1}{e^{u}+1} \sigma(u)\\
&=  \sigma(-u) \sigma(u)\\
&=  (1-\sigma(u)) \sigma(u)\\
\end{split}
$$

$$
\begin{split}
1-\sigma(u) 
&= 1-\frac{1}{1+e^{-u}} \\
&= \frac{1+e^{-u}}{1+e^{-u}}-\frac{1}{1+e^{-u}} \\
&= \frac{e^{-u}}{1+e^{-u}} \\
&= \frac{1}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \\
&= \frac{1}{e^{--u}+1} \\
&= \sigma(-u) \\
\end{split}
$$

### sigmoid function
- the [[sigmoid function]] $\sigma: \mathbb{R} \to (0,1)$ is defined as follows:
- its the inverse of the [[logit function]]

$$
\sigma(u) = \frac{1}{1+e^{-u}}
$$

#### properties
$$
\sigma(0) = \frac{1}{2}
$$

$$
\begin{split}
\lim_{u\to\infty}\sigma(u) &= 1 \\
\lim_{u\to-\infty}\sigma(u) &= 0 \\
\end{split}
$$

$$
1-\sigma(u) = \frac{1}{1+e^{+u}} = \sigma(-u)
$$

###### proof


$$
\begin{split}
1-\sigma(u) 
&= 1-\frac{1}{1+e^{-u}} \\
&= \frac{1+e^{-u}}{1+e^{-u}}-\frac{1}{1+e^{-u}} \\
&= \frac{e^{-u}}{1+e^{-u}} \\
&= \frac{1}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \\
&= \frac{1}{e^{--u}+1} \\
&= \sigma(-u) \\
\end{split}
$$

#### derivative

$$
\begin{split}
\frac{d}{du}\sigma(u) 
&= \frac{d}{du} \frac{1}{1+e^{-u}} \\
&=  \frac{-1}{(1+e^{-u})^2} \cdot e^{-u} \cdot -1 \\
&=  \frac{e^{-u}}{1+e^{-u}} \frac{1}{1+e^{-u}}\\
&=  \frac{e^{-u}}{1+e^{-u}} \sigma(u)\\
&=  \frac{\frac{e^{-u}}{e^{-u}}}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \sigma(u)\\
&=  \frac{1}{e^{u}+1} \sigma(u)\\
&=  \sigma(-u) \sigma(u)\\
&=  (1-\sigma(u)) \sigma(u)\\
\end{split}
$$
#### application
- often used to predict probabilities in binary [[classification]] problems, e.g. [[logistic regression]]

#### inverse of the sigmoid function
- the [[inverse function]] on the [[sigmoid function]] is the [[logit function]]

$$
\begin{split}
\sigma(\mathrm{logit}(p) ) 
&= \frac{1}{1+e^{-\log\left(\frac{p}{1-p}\right)}} \\
&= \frac{1}{1+\left(e^{\log\left(\frac{p}{1-p}\right)}\right)^{-1}} \\
&= \frac{1}{1+\frac{1-p}{p}} \\
&= \frac{1}{1+\frac{1}{p}-1} \\
&= p \\
\end{split}
$$

_____________

### logit function
- the [[logit function]] $\mathrm{logit}: (0,1)\to\mathbb{R}$ is defined as follows and is the [[inverse function]] of the [[sigmoid function]] 

$$
\mathrm{logit}(p) = \log\left(\frac{p}{1-p}\right)
$$
Tags: mathematics basics SS25
<!--ID: 1764496843807-->
END