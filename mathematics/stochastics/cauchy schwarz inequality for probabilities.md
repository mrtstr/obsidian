### cauchy schwarz inequality for probabilities

$$
\mathbb{COV}[X, Y]^2 \leq \mathbb{VAR}[X]  \mathbb{VAR}[Y]
$$

#### proof 

$$
\begin{split}
0 
&\leq \mathbb{E}\left[(X-\lambda Y)^2\right] \\
&\leq \mathbb{E}\left[X^2\right] + \lambda^2 \mathbb{E}\left[Y^2\right] - 2\lambda\mathbb{E}\left[XY\right] \quad \text{with } \lambda = \frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]} \\

&\leq \mathbb{E}\left[X^2\right] + \left(\frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]}\right)^2 \mathbb{E}\left[Y^2\right] -2 \frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]} \mathbb{E}\left[XY\right] \\
&\leq \mathbb{E}\left[X^2\right] + \frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  - 2\frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  \\
&\leq \mathbb{E}\left[X^2\right]  - \frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  \\
&\leq \mathbb{E}\left[X^2\right]\mathbb{E}\left[Y^2\right]  - \mathbb{E}\left[XY\right]^2  \\
\Rightarrow \mathbb{E}\left[XY\right]^2 &\leq \mathbb{E}\left[X^2\right]\mathbb{E}\left[Y^2\right]
\end{split}
$$

- let $X' = X - \mathbb{E}[X]$ and $Y' = Y - \mathbb{E}[Y]$

$$
\begin{split}
&\mathbb{E}\left[X'Y'\right]^2 \leq \mathbb{E}\left[^2\right]\mathbb{E}\left[Y'^2\right] \\
\Rightarrow &\mathbb{E}\left[\left( X - \mathbb{E}[X]\right)\left( Y - \mathbb{E}[Y]\right)\right]^2 \leq \mathbb{E}\left[\left( X - \mathbb{E}[X]\right)^2\right]\mathbb{E}\left[\left( Y - \mathbb{E}[Y]\right)^2\right] \\
\Rightarrow &\mathbb{COV}[X, Y]^2 \leq \mathbb{VAR}[X]  \mathbb{VAR}[Y]\\
\end{split}
$$
### example
- given $X$ with $\mathbb{E}\left[X\right]=0$ and $\mathbb{VAR}\left[X\right]=1$ prove that $1 \leq \mathbb{E}\left[X^4\right]$

$$
\begin{split}
&\mathbb{E}\left[ST\right]^2 \leq \mathbb{E}\left[S^2\right]\mathbb{E}\left[T^2\right] \\
\Rightarrow&\mathbb{E}\left[X^2\cdot 1\right]^2 \leq \mathbb{E}\left[X^4\right]\mathbb{E}\left[1^2\right] \\
\Rightarrow&\mathbb{E}\left[X^2\right]^2 \leq \mathbb{E}\left[X^4\right] \\
\Rightarrow&1^2 \leq \mathbb{E}\left[X^4\right] \\
\Rightarrow&1 \leq \mathbb{E}\left[X^4\right] \\

\end{split}
$$
# ------------------------
![[covariance#covariance]]

![[cauchy schwarz inequality#cauchy schwarz inequality]]

# anki


START
Basic
given $X$ with $\mathbb{E}\left[X\right]=0$ and $\mathbb{VAR}\left[X\right]=1$ prove that $1 \leq \mathbb{E}\left[X^4\right]$

Back: 
### example
- given $X$ with $\mathbb{E}\left[X\right]=0$ and $\mathbb{VAR}\left[X\right]=1$ prove that $1 \leq \mathbb{E}\left[X^4\right]$

$$
\begin{split}
&\mathbb{E}\left[ST\right]^2 \leq \mathbb{E}\left[S^2\right]\mathbb{E}\left[T^2\right] \\
\Rightarrow&\mathbb{E}\left[X^2\cdot 1\right]^2 \leq \mathbb{E}\left[X^4\right]\mathbb{E}\left[1^2\right] \\
\Rightarrow&\mathbb{E}\left[X^2\right]^2 \leq \mathbb{E}\left[X^4\right] \\
\Rightarrow&1^2 \leq \mathbb{E}\left[X^4\right] \\
\Rightarrow&1 \leq \mathbb{E}\left[X^4\right] \\

\end{split}
$$
### cauchy schwarz inequality for probabilities

$$
\mathbb{COV}[X, Y]^2 \leq \mathbb{VAR}[X]  \mathbb{VAR}[Y]
$$

#### proof 

$$
\begin{split}
0 
&\leq \mathbb{E}\left[(X-\lambda Y)^2\right] \\
&\leq \mathbb{E}\left[X^2\right] + \lambda^2 \mathbb{E}\left[Y^2\right] - 2\lambda\mathbb{E}\left[XY\right] \quad \text{with } \lambda = \frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]} \\

&\leq \mathbb{E}\left[X^2\right] + \left(\frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]}\right)^2 \mathbb{E}\left[Y^2\right] -2 \frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]} \mathbb{E}\left[XY\right] \\
&\leq \mathbb{E}\left[X^2\right] + \frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  - 2\frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  \\
&\leq \mathbb{E}\left[X^2\right]  - \frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  \\
&\leq \mathbb{E}\left[X^2\right]\mathbb{E}\left[Y^2\right]  - \mathbb{E}\left[XY\right]^2  \\
\Rightarrow \mathbb{E}\left[XY\right]^2 &\leq \mathbb{E}\left[X^2\right]\mathbb{E}\left[Y^2\right]
\end{split}
$$

- let $X' = X - \mathbb{E}[X]$ and $Y' = Y - \mathbb{E}[Y]$

$$
\begin{split}
&\mathbb{E}\left[X'Y'\right]^2 \leq \mathbb{E}\left[^2\right]\mathbb{E}\left[Y'^2\right] \\
\Rightarrow &\mathbb{E}\left[\left( X - \mathbb{E}[X]\right)\left( Y - \mathbb{E}[Y]\right)\right]^2 \leq \mathbb{E}\left[\left( X - \mathbb{E}[X]\right)^2\right]\mathbb{E}\left[\left( Y - \mathbb{E}[Y]\right)^2\right] \\
\Rightarrow &\mathbb{COV}[X, Y]^2 \leq \mathbb{VAR}[X]  \mathbb{VAR}[Y]\\
\end{split}
$$
______________________

### covariance
$$
\mathbb{COV}\left[X,Y\right] = \mathbb{E}\left[(X-\mathbb{E}\left[X\right])(Y-\mathbb{E}\left[Y\right])\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]
$$

### cauchy schwarz inequality
- let $V$ be a [[vector space]] with an [[inner product]] $\langle \cdot , \cdot \rangle$ 
- then the following is true for all $x, y \in V$

$$
|\langle x , y \rangle|^2 \leq \langle x , x \rangle \cdot \langle y , y \rangle
$$
$$
|\langle x , y \rangle| \leq || x || \cdot || y ||
$$

Tags: mathematics statistics WS2425
<!--ID: 1737021016313-->
END



START
Basic
[[cauchy schwarz inequality for probabilities]] with proof
Back: 
### cauchy schwarz inequality for probabilities

$$
\mathbb{COV}[X, Y]^2 \leq \mathbb{VAR}[X]  \mathbb{VAR}[Y]
$$

#### proof 

$$
\begin{split}
0 
&\leq \mathbb{E}\left[(X-\lambda Y)^2\right] \\
&\leq \mathbb{E}\left[X^2\right] + \lambda^2 \mathbb{E}\left[Y^2\right] - 2\lambda\mathbb{E}\left[XY\right] \quad \text{with } \lambda = \frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]} \\

&\leq \mathbb{E}\left[X^2\right] + \left(\frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]}\right)^2 \mathbb{E}\left[Y^2\right] -2 \frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]} \mathbb{E}\left[XY\right] \\
&\leq \mathbb{E}\left[X^2\right] + \frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  - 2\frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  \\
&\leq \mathbb{E}\left[X^2\right]  - \frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  \\
&\leq \mathbb{E}\left[X^2\right]\mathbb{E}\left[Y^2\right]  - \mathbb{E}\left[XY\right]^2  \\
\Rightarrow \mathbb{E}\left[XY\right]^2 &\leq \mathbb{E}\left[X^2\right]\mathbb{E}\left[Y^2\right]
\end{split}
$$

- let $X' = X - \mathbb{E}[X]$ and $Y' = Y - \mathbb{E}[Y]$

$$
\begin{split}
&\mathbb{E}\left[X'Y'\right]^2 \leq \mathbb{E}\left[^2\right]\mathbb{E}\left[Y'^2\right] \\
\Rightarrow &\mathbb{E}\left[\left( X - \mathbb{E}[X]\right)\left( Y - \mathbb{E}[Y]\right)\right]^2 \leq \mathbb{E}\left[\left( X - \mathbb{E}[X]\right)^2\right]\mathbb{E}\left[\left( Y - \mathbb{E}[Y]\right)^2\right] \\
\Rightarrow &\mathbb{COV}[X, Y]^2 \leq \mathbb{VAR}[X]  \mathbb{VAR}[Y]\\
\end{split}
$$
______________________

### covariance
$$
\mathbb{COV}\left[X,Y\right] = \mathbb{E}\left[(X-\mathbb{E}\left[X\right])(Y-\mathbb{E}\left[Y\right])\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]
$$

### cauchy schwarz inequality
- let $V$ be a [[vector space]] with an [[inner product]] $\langle \cdot , \cdot \rangle$ 
- then the following is true for all $x, y \in V$

$$
|\langle x , y \rangle|^2 \leq \langle x , x \rangle \cdot \langle y , y \rangle
$$
$$
|\langle x , y \rangle| \leq || x || \cdot || y ||
$$

Tags: mathematics statistics
<!--ID: 1717740451560-->
END


START
Basic
- proof for the following
- how is this equation called?

$$
\mathbb{E}\left[XY\right]^2 \leq \mathbb{E}\left[X^2\right]\mathbb{E}\left[Y^2\right]
$$

Back: 
### cauchy schwarz inequality for probabilities

$$
\mathbb{COV}[X, Y]^2 \leq \mathbb{VAR}[X]  \mathbb{VAR}[Y]
$$

#### proof 

$$
\begin{split}
0 
&\leq \mathbb{E}\left[(X-\lambda Y)^2\right] \\
&\leq \mathbb{E}\left[X^2\right] + \lambda^2 \mathbb{E}\left[Y^2\right] - 2\lambda\mathbb{E}\left[XY\right] \quad \text{with } \lambda = \frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]} \\

&\leq \mathbb{E}\left[X^2\right] + \left(\frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]}\right)^2 \mathbb{E}\left[Y^2\right] -2 \frac{\mathbb{E}\left[XY\right]}{\mathbb{E}\left[Y^2\right]} \mathbb{E}\left[XY\right] \\
&\leq \mathbb{E}\left[X^2\right] + \frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  - 2\frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  \\
&\leq \mathbb{E}\left[X^2\right]  - \frac{\mathbb{E}\left[XY\right]^2}{\mathbb{E}\left[Y^2\right]}  \\
&\leq \mathbb{E}\left[X^2\right]\mathbb{E}\left[Y^2\right]  - \mathbb{E}\left[XY\right]^2  \\
\Rightarrow \mathbb{E}\left[XY\right]^2 &\leq \mathbb{E}\left[X^2\right]\mathbb{E}\left[Y^2\right]
\end{split}
$$

- let $X' = X - \mathbb{E}[X]$ and $Y' = Y - \mathbb{E}[Y]$

$$
\begin{split}
&\mathbb{E}\left[X'Y'\right]^2 \leq \mathbb{E}\left[^2\right]\mathbb{E}\left[Y'^2\right] \\
\Rightarrow &\mathbb{E}\left[\left( X - \mathbb{E}[X]\right)\left( Y - \mathbb{E}[Y]\right)\right]^2 \leq \mathbb{E}\left[\left( X - \mathbb{E}[X]\right)^2\right]\mathbb{E}\left[\left( Y - \mathbb{E}[Y]\right)^2\right] \\
\Rightarrow &\mathbb{COV}[X, Y]^2 \leq \mathbb{VAR}[X]  \mathbb{VAR}[Y]\\
\end{split}
$$
______________________

### covariance
$$
\mathbb{COV}\left[X,Y\right] = \mathbb{E}\left[(X-\mathbb{E}\left[X\right])(Y-\mathbb{E}\left[Y\right])\right]
= 
\mathbb{E}\left[XY\right]-\mathbb{E}\left[X\right]\mathbb{E}\left[Y\right]
$$

### cauchy schwarz inequality
- let $V$ be a [[vector space]] with an [[inner product]] $\langle \cdot , \cdot \rangle$ 
- then the following is true for all $x, y \in V$

$$
|\langle x , y \rangle|^2 \leq \langle x , x \rangle \cdot \langle y , y \rangle
$$
$$
|\langle x , y \rangle| \leq || x || \cdot || y ||
$$

Tags: mathematics statistics
<!--ID: 1717740451565-->
END