# [[linear function|Linear Transformation]] of a [[random variable]]
## Definition
$$
\begin{split}
X &\sim f_X(x) \\
Y &= aX + b \\
\end{split}
$$
## [[probability density function]]
![[functions of random variables#linear function of a probability density function]]

## [[expectation]] and [[variance]]
$$
\begin{split}
\mathbb{E}\left[Y\right] &= \mathbb{E}\left[aX + b\right] = a\mathbb{E}\left[X\right] + b  \\
\mathbb{VAR}\left[Y\right] &= \mathbb{VAR}\left[aX + b\right] = a^2\mathbb{VAR}\left[X\right]   \\
\end{split}
$$



# [[linear function|Linear Transformation]] of a [[random vector]]
$$
\begin{split}
\boldsymbol{X} &\sim f_\boldsymbol{X}(\boldsymbol{x}) \\
\mathbb{E}\left[\boldsymbol{X}\right] &= \left(\mathbb{E}\left[X_i\right]\right)_{i} \\
\mathbb{COVAR}\left[\boldsymbol{X}\right] &= \left(\mathbb{COVAR}\left[X_i,X_j\right]\right)_{i,j} \\
\boldsymbol{Y} &= A\boldsymbol{X} + b \\ \\

\Rightarrow \mathbb{E}\left[\boldsymbol{Y}\right] &=  A\mathbb{E}\left[\boldsymbol{X}\right] + b\\
\Rightarrow\mathbb{COVAR}\left[\boldsymbol{Y}\right] &=  A\mathbb{COVAR}\left[\boldsymbol{X}\right] A^T\\
\end{split}
$$

# [[linear function|Linear Transformation]] of a [[stochastic independent|i.i.d.]] [[random vector]]

$$
\begin{split}
\boldsymbol{X} &=\begin{pmatrix}X_1 \\ ... \\ X_n\end{pmatrix} , \:X_1 \sim f_\boldsymbol{X}(\boldsymbol{x}) \\
\mathbb{E}\left[\boldsymbol{X}\right] &= \left(\mathbb{E}\left[X_i\right]\right)_{i} \\
\mathbb{COVAR}\left[\boldsymbol{X}\right] &= \left(\mathbb{COVAR}\left[X_i,X_j\right]\right)_{i,j} = diag
\left(\mathbb{VAR}\left[X_i\right]\right) \\
\boldsymbol{Y} &= A\boldsymbol{X} + b \\ \\

\Rightarrow \mathbb{E}\left[\boldsymbol{Y}\right] &=  A\mathbb{E}\left[\boldsymbol{X}\right] + b\\
\Rightarrow\mathbb{COVAR}\left[\boldsymbol{Y}\right] &=  A\mathbb{COVAR}\left[\boldsymbol{X}\right] A^T
 = A A^T \begin{pmatrix}\mathbb{VAR}\left[X_1\right]\\ ... \\ \mathbb{VAR}\left[X_n\right]\end{pmatrix}\\
\end{split}
$$


# anki

START
Basic
[[linear function|Linear Transformation]] of a [[random variable]]
$$
\begin{split}
X &\sim f_X(x) \\
Y &= g(X) = aX + b \\
\end{split}
$$
- [[probability density function]]
- [[expectation]]
- [[variance]]
Back: 
[[probability density function]]

$$
f_Y(y)=\underbrace{\frac{1}{|a|}}_{\frac{dg^{-1}(y)}{dy}} f_{X}
\underbrace{
\left(\frac{y-b}{a}\right)
}_{g^{-1}(y)}
$$
proof:

$$
\begin{split}
F_{Y}(y)
&=P(Y \leq y) \\
&=P(g(X) \leq y) = P(aX=b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P(aX+b \leq y) \\
&=P\left(X \leq g^{-1}(y)\right) = P\left( X \leq \frac{y-b}{a} \right) \\
&= F_X\left(g^{-1}(y)\right) = F_X\left(\frac{y-b}{a}\right) \\


f_{Y}(y) &= \frac{dF_{Y}(y)}{dy} = \frac{dF_{Y}(y)}{dy} f_{X}\left(\frac{y-b}{a}\right) \\
&= \frac{dg^{-1}(y)}{dy} f_{X}\left(\frac{y-b}{a}\right)
= \frac{1}{|a|} f_{X}\left(\frac{y-b}{a}\right)
\end{split}
$$
### [[expectation]] and [[variance]]
$$
\begin{split}
\mathbb{E}\left[Y\right] &= \mathbb{E}\left[aX + b\right] = a\mathbb{E}\left[X\right] + b  \\
\mathbb{VAR}\left[Y\right] &= \mathbb{VAR}\left[aX + b\right] = a^2\mathbb{VAR}\left[X\right]   \\
\end{split}
$$

Tags: mathematics, statistics
<!--ID: 1680849735924-->
END


START
Basic
[[linear function|Linear Transformation]] of a [[random vector]]
- [[expectation]]
- [[variance]]
Back: 
$$
\begin{split}
\boldsymbol{X} &\sim f_\boldsymbol{X}(\boldsymbol{x}) \\
\mathbb{E}\left[\boldsymbol{X}\right] &= \left(\mathbb{E}\left[X_i\right]\right)_{i} \\
\mathbb{COVAR}\left[\boldsymbol{X}\right] &= \left(\mathbb{COVAR}\left[X_i,X_j\right]\right)_{i,j} \\
\boldsymbol{Y} &= A\boldsymbol{X} + b \\ \\

\Rightarrow \mathbb{E}\left[\boldsymbol{Y}\right] &=  A\mathbb{E}\left[\boldsymbol{X}\right] + b\\
\Rightarrow\mathbb{COVAR}\left[\boldsymbol{Y}\right] &=  A\mathbb{COVAR}\left[\boldsymbol{X}\right] A^T\\
\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1680849735929-->
END


START
Basic
[[linear function|Linear Transformation]] of a [[stochastic independent|i.i.d.]] [[random vector]]
- [[expectation]]
- [[variance]]
Back: 
$$
\begin{split}
\boldsymbol{X} &=\begin{pmatrix}X_1 \\ ... \\ X_n\end{pmatrix} , \:X_1 \sim f_\boldsymbol{X}(\boldsymbol{x}) \\
\mathbb{E}\left[\boldsymbol{X}\right] &= \left(\mathbb{E}\left[X_i\right]\right)_{i} \\
\mathbb{COVAR}\left[\boldsymbol{X}\right] &= \left(\mathbb{COVAR}\left[X_i,X_j\right]\right)_{i,j} = diag
\left(\mathbb{VAR}\left[X_i\right]\right) \\
\boldsymbol{Y} &= A\boldsymbol{X} + b \\ \\

\Rightarrow \mathbb{E}\left[\boldsymbol{Y}\right] &=  A\mathbb{E}\left[\boldsymbol{X}\right] + b\\
\Rightarrow\mathbb{COVAR}\left[\boldsymbol{Y}\right] &=  A\mathbb{COVAR}\left[\boldsymbol{X}\right] A^T
 = A A^T \begin{pmatrix}\mathbb{VAR}\left[X_1\right]\\ ... \\ \mathbb{VAR}\left[X_n\right]\end{pmatrix}\\
\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1680849735935-->
END