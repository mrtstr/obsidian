### conditional covariance matrix
- given three [[random variable]] $X \in \mathbb{R}^n$ and $Y_1 \in \mathbb{R}^m$ and $Y_2 \in \mathbb{R}^k$ 
- the [[conditional covariance matrix]] $\mathbb{COV}[Y_1, Y_2| X=x]: \mathbb{R}^n \to \mathbb{R}^{m\times k}$ of $Y_1$ and $Y_2$ given $X$ is defined as follows

$$
\begin{split}
\mathbb{COV}[Y_1, Y_2| X]
&= \mathbb{E}\left[\left( Y_1 -\mathbb{E}[Y_1|X]\right) \left( Y_2 -\mathbb{E}[Y_2|X]\right)^\top|X\right] \\
&= \mathbb{E}\left[Y_1 Y_2^\top|X\right] - \mathbb{E}\left[Y_1|X \right] \mathbb{E}\left[Y_2|X \right]^\top \\
&= \left( \mathbb{E}\left[\left( Y_{1(i)} -\mathbb{E}[Y_{1(i)} |X]\right) \left( Y_{2(j)} -\mathbb{E}[Y_{2(j)}|X]\right)^\top |X \right]\right)_{i \in [m], j \in [k]} \\
\end{split}
$$

### law of total covariance
- given three [[random variable]] $X \in \mathbb{R}^n$ and $Y_1 \in \mathbb{R}^m$ and $Y_2 \in \mathbb{R}^k$ 
- the following is the [[law of total probability]] for the [[conditional covariance matrix]]

$$
\begin{split}
\mathbb{COV}[Y_1, Y_2]
&= \mathbb{E}\left[\mathbb{COV}[Y_1, Y_2| X]\right] + \mathbb{COV}\left[\mathbb{E}\left[Y_1|X\right], \mathbb{E}\left[Y_2|X\right]\right] \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{E}\left[\mathbb{COV}[Y_1, Y_2| X]\right]
&= \mathbb{E}\left[\mathbb{E}\left[Y_1 Y_2^\top|X\right] - \mathbb{E}\left[Y_1|X \right] \mathbb{E}\left[Y_2|X \right]^\top\right] \\
&= \mathbb{E}\left[\mathbb{E}\left[Y_1 Y_2^\top|X\right]\right] - \mathbb{E}\left[\mathbb{E}\left[Y_1|X \right] \mathbb{E}\left[Y_2|X \right]^\top\right] \\
&= \mathbb{E}\left[Y_1 Y_2^\top\right] - \mathbb{E}\left[\mathbb{E}\left[Y_1|X \right] \mathbb{E}\left[Y_2|X \right]^\top\right] \\
\mathbb{COV}\left[\mathbb{E}\left[Y_1|X\right], \mathbb{E}\left[Y_2|X\right]\right]
&= \mathbb{E}\left[\mathbb{E}\left[Y_1|X\right] \mathbb{E}\left[Y_2|X\right]^\top\right] - \mathbb{E}\left[\mathbb{E}\left[Y_1|X\right] \right] \mathbb{E}\left[\mathbb{E}\left[Y_2|X \right]\right]^\top \\
&= \mathbb{E}\left[\mathbb{E}\left[Y_1|X\right] \mathbb{E}\left[Y_2|X\right]^\top\right] - \mathbb{E}\left[Y_1\right]\mathbb{E}\left[Y_2\right]^\top \\
\end{split}
$$


# anki

START
Basic
[[conditional covariance matrix]]
- definition
- [[law of total probability]] with proof

Back: 
### conditional covariance matrix
- given three [[random variable]] $X \in \mathbb{R}^n$ and $Y_1 \in \mathbb{R}^m$ and $Y_2 \in \mathbb{R}^k$ 
- the [[conditional covariance matrix]] $\mathbb{COV}[Y_1, Y_2| X=x]: \mathbb{R}^n \to \mathbb{R}^{m\times k}$ of $Y_1$ and $Y_2$ given $X$ is defined as follows

$$
\begin{split}
\mathbb{COV}[Y_1, Y_2| X]
&= \mathbb{E}\left[\left( Y_1 -\mathbb{E}[Y_1|X]\right) \left( Y_2 -\mathbb{E}[Y_2|X]\right)^\top|X\right] \\
&= \mathbb{E}\left[Y_1 Y_2^\top|X\right] - \mathbb{E}\left[Y_1|X \right] \mathbb{E}\left[Y_2|X \right]^\top \\
&= \left( \mathbb{E}\left[\left( Y_{1(i)} -\mathbb{E}[Y_{1(i)} |X]\right) \left( Y_{2(j)} -\mathbb{E}[Y_{2(j)}|X]\right)^\top |X \right]\right)_{i \in [m], j \in [k]} \\
\end{split}
$$

### law of total covariance
- given three [[random variable]] $X \in \mathbb{R}^n$ and $Y_1 \in \mathbb{R}^m$ and $Y_2 \in \mathbb{R}^k$ 
- the following is the [[law of total probability]] for the [[conditional covariance matrix]]

$$
\begin{split}
\mathbb{COV}[Y_1, Y_2]
&= \mathbb{E}\left[\mathbb{COV}[Y_1, Y_2| X]\right] + \mathbb{COV}\left[\mathbb{E}\left[Y_1|X\right], \mathbb{E}\left[Y_2|X\right]\right] \\
\end{split}
$$

#### proof

$$
\begin{split}
\mathbb{E}\left[\mathbb{COV}[Y_1, Y_2| X]\right]
&= \mathbb{E}\left[\mathbb{E}\left[Y_1 Y_2^\top|X\right] - \mathbb{E}\left[Y_1|X \right] \mathbb{E}\left[Y_2|X \right]^\top\right] \\
&= \mathbb{E}\left[\mathbb{E}\left[Y_1 Y_2^\top|X\right]\right] - \mathbb{E}\left[\mathbb{E}\left[Y_1|X \right] \mathbb{E}\left[Y_2|X \right]^\top\right] \\
&= \mathbb{E}\left[Y_1 Y_2^\top\right] - \mathbb{E}\left[\mathbb{E}\left[Y_1|X \right] \mathbb{E}\left[Y_2|X \right]^\top\right] \\
\mathbb{COV}\left[\mathbb{E}\left[Y_1|X\right], \mathbb{E}\left[Y_2|X\right]\right]
&= \mathbb{E}\left[\mathbb{E}\left[Y_1|X\right] \mathbb{E}\left[Y_2|X\right]^\top\right] - \mathbb{E}\left[\mathbb{E}\left[Y_1|X\right] \right] \mathbb{E}\left[\mathbb{E}\left[Y_2|X \right]\right]^\top \\
&= \mathbb{E}\left[\mathbb{E}\left[Y_1|X\right] \mathbb{E}\left[Y_2|X\right]^\top\right] - \mathbb{E}\left[Y_1\right]\mathbb{E}\left[Y_2\right]^\top \\
\end{split}
$$

____________________

### covariance matrix
- given two [[random variable]] $X \in \mathbb{R}^n$ and $Y \in \mathbb{R}^M$ with the [[expectation]] $\mathbb{E}[X] = \left(\mathbb{E}[X_i]\right)_{i \in [n]}$ and $\mathbb{E}[Y] = \left(\mathbb{E}[Y_i]\right)_{i \in [m]}$
- the cross [[covariance matrix]] $K_{XY} = \mathbb{COV}[X, Y] \in \mathbb{R}^{n\times m}$ of $X$ and $Y$ is defined as follows

$$
\begin{split}
K_{XY} 
&= \mathbb{COV}[X, Y]\\
&= \mathbb{E}\left[\left( X -\mathbb{E}[X]\right) \left( Y -\mathbb{E}[Y]\right)^\top\right] \\
&= \left( \mathbb{E}\left[\left( X -\mathbb{E}[X_i]\right) \left( Y -\mathbb{E}[Y_j]\right)^\top\right]\right)_{i,j \in [n]} \\
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$

- the [[covariance matrix]] of one [[random variable]] is the cross [[covariance matrix]] with itself

$$
\begin{split}
\mathbb{VAR}[X]
&= K_{XX}   \\
\end{split}
$$
#### base properties


- $K_{XX}$ is [[symmetric]]
- $K_{XX}$ is [[positive definite]]

$$
\begin{split}
\mathbb{VAR}[AX + b]
&= A\mathbb{VAR}[X]A^\top \\
\end{split}
$$

$$
\begin{split}
\mathbb{COV}[X, Y]
&= \mathbb{E}\left[X Y^\top\right] - \mathbb{E}\left[X \right] \mathbb{E}\left[Y \right]^\top \\
\end{split}
$$


$$
\begin{split}
\mathbb{VAR}[X + Y]
&= \mathbb{VAR}[X] + \mathbb{VAR}[Y] + \mathbb{COV}[X, Y] + \mathbb{COV}[Y, X] \\
\end{split}
$$

- if we combine two random vectors $X_1 \in \mathbb{R}^n$ and $X_2 \in \mathbb{R}^m$ to one random vector $X \in \mathbb{R}^{n+m}$ the [[covariance matrix]] of $K_{XX} \in  \in \mathbb{R}^{n\times m}$ can be constructed as follows

$$
\begin{split}
K_{XX} 
&= \mathbb{COV}[X, X] \\
&= \left[\begin{matrix}
K_{X_1X_1} & K_{X_1X_2} \\
K_{X_2X_1} & K_{X_2X_2} \\
\end{matrix}\right]

\end{split}
$$

Tags: mathematics statistics SS25
<!--ID: 1746944681995-->
END
