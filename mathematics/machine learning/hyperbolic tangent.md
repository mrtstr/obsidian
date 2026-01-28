### hyperbolic tangent
- the [[hyperbolic tangent]] can be used as [[activation function]] for [[neural network]] and is defined a $\tanh: \mathbb{R} \to (-1, 1)$

$$
\tanh(z) = \frac{e^z - e^{-z}}{e^z + e^{-z}}
$$

- the [[hyperbolic tangent]] is a scaled and shifted version of the [[sigmoid function]] in a way that it's zero centered and is mapping to $(-1, 1)$

$$
\begin{split}
\tanh(z) &= 2\sigma(2z)-1 \\
\sigma(z) &= \frac{1+\tanh\left(\frac{z}{2}\right)}{2} \\
\end{split}
$$


$$
\begin{split}
\tanh(z) 
&= 2\sigma(2z)-1 \\
&= \frac{2}{1+e^{-2z}}-1 \\
&= \frac{1-e^{-2z}}{1+e^{-2z}} \\
&= \frac{e^{z}-e^{-z}}{e^{z}+e^{-z}} \\
\end{split}
$$

### derivative of the hyperbolic tangent

$$
\begin{split}
\frac{d}{dz}\tanh(z) 
&= \frac{d}{dz} \frac{e^z - e^{-z}}{e^z + e^{-z}} \\
&= \frac{e^z + e^{-z}}{e^z + e^{-z}} - \frac{e^z - e^{-z}}{(e^z + e^{-z})^2} (e^z - e^{-z}) \\
&= 1 - \tanh(z)^2 \\
\end{split}
$$

# ------------

![[sigmoid function#sigmoid function]]

# anki

START
Basic
[[hyperbolic tangent]]
- definition
- relationship to [[sigmoid function]] with proof
- derivative without proof
Back: 

### hyperbolic tangent
- the [[hyperbolic tangent]] can be used as [[activation function]] for [[neural network]] and is defined a $\tanh: \mathbb{R} \to (-1, 1)$

$$
\tanh(z) = \frac{e^z - e^{-z}}{e^z + e^{-z}}
$$

- the [[hyperbolic tangent]] is a scaled and shifted version of the [[sigmoid function]] in a way that it's zero centered and is mapping to $(-1, 1)$

$$
\begin{split}
\tanh(z) &= 2\sigma(2z)-1 \\
\sigma(z) &= \frac{1+\tanh\left(\frac{z}{2}\right)}{2} \\
\end{split}
$$


$$
\begin{split}
\tanh(z) 
&= 2\sigma(2z)-1 \\
&= \frac{2}{1+e^{-2z}}-1 \\
&= \frac{1-e^{-2z}}{1+e^{-2z}} \\
&= \frac{e^{z}-e^{-z}}{e^{z}+e^{-z}} \\
\end{split}
$$

### derivative of the hyperbolic tangent

$$
\begin{split}
\frac{d}{dz}\tanh(z) 
&= \frac{d}{dz} \frac{e^z - e^{-z}}{e^z + e^{-z}} \\
&= \frac{e^z + e^{-z}}{e^z + e^{-z}} - \frac{e^z - e^{-z}}{(e^z + e^{-z})^2} (e^z - e^{-z}) \\
&= 1 - \tanh(z)^2 \\
\end{split}
$$


_____________
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


###### proof

$$
1-\sigma(u) = \frac{1}{1+e^{+u}} = \sigma(-u)
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



### logit function
- the [[logit function]] $\mathrm{logit}: (0,1)\to\mathbb{R}$ is defined as follows and is the [[inverse function]] of the [[sigmoid function]] 

$$
\mathrm{logit}(p) = \log\left(\frac{p}{1-p}\right)
$$
Tags: mathematics basics WS2526
<!--ID: 1763312447271-->
END


START
Basic
[[derivative]] of the [[hyperbolic tangent]] with calculation

Back: 
### derivative of the hyperbolic tangent

$$
\begin{split}
\frac{d}{dz}\tanh(z) 
&= \frac{d}{dz} \frac{e^z - e^{-z}}{e^z + e^{-z}} \\
&= \frac{e^z + e^{-z}}{e^z + e^{-z}} - \frac{e^z - e^{-z}}{(e^z + e^{-z})^2} (e^z - e^{-z}) \\
&= 1 - \tanh(z)^2 \\
\end{split}
$$

### hyperbolic tangent
- the [[hyperbolic tangent]] can be used as [[activation function]] for [[neural network]] and is defined a $\tanh: \mathbb{R} \to (-1, 1)$

$$
\tanh(z) = \frac{e^z - e^{-z}}{e^z + e^{-z}}
$$

- the [[hyperbolic tangent]] is a scaled and shifted version of the [[sigmoid function]] in a way that it's zero centered and is mapping to $(-1, 1)$

$$
\begin{split}
\tanh(z) &= 2\sigma(2z)-1 \\
\sigma(z) &= \frac{1+\tanh\left(\frac{z}{2}\right)}{2} \\
\end{split}
$$


$$
\begin{split}
\tanh(z) 
&= 2\sigma(2z)-1 \\
&= \frac{2}{1+e^{-2z}}-1 \\
&= \frac{1-e^{-2z}}{1+e^{-2z}} \\
&= \frac{e^{z}-e^{-z}}{e^{z}+e^{-z}} \\
\end{split}
$$



Tags: mathematics basics WS2526
<!--ID: 1764519362367-->
END