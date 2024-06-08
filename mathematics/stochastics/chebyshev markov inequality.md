### markov inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{E}\left[|X|^r\right] \geq \epsilon^r \cdot \mathbb{P}\left(|X| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[|X|^r\right] 
&= \int_{-\infty}^{0} (-x)^r f_X(x) \mathrm{d} x^r + \int_{0}^{\infty} x f_X(x) \mathrm{d} x \\
&= \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{-\epsilon}^{0} (-x)^r f_X(x) \mathrm{d} x 
+ \int_{0}^{\epsilon} x^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} \epsilon^r f_X(x) \mathrm{d} x + \int_{\epsilon}^{\infty} \epsilon^r f_X(x) \mathrm{d} x \\
&\geq \epsilon^r \cdot \mathbb{P}(|X| \geq \epsilon)\\
\end{split}
$$

### chebyshev inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{VAR}\left[X\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
&\text{let } X' = X - \mathbb{E}[X] \text{ and } r = 2 \\
&\forall \epsilon > 0:\mathbb{E}\left[|X'|^2\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X'| \geq \epsilon\right) \\
\Rightarrow &\forall \epsilon > 0:\mathbb{E}\left[|X - \mathbb{E}[X]|^2\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right) \\

\Rightarrow & \forall \epsilon > 0:\mathbb{VAR}\left[X\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right) \\
\end{split}
$$


# anki


START
Basic
- markov inequality
- chebyshev inequality
(proof given but not requiered)
Back: 
### markov inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{E}\left[|X|^r\right] \geq \epsilon^r \cdot \mathbb{P}\left(|X| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[|X|^r\right] 
&= \int_{-\infty}^{0} (-x)^r f_X(x) \mathrm{d} x^r + \int_{0}^{\infty} x f_X(x) \mathrm{d} x \\
&= \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{-\epsilon}^{0} (-x)^r f_X(x) \mathrm{d} x 
+ \int_{0}^{\epsilon} x^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} \epsilon^r f_X(x) \mathrm{d} x + \int_{\epsilon}^{\infty} \epsilon^r f_X(x) \mathrm{d} x \\
&\geq \epsilon^r \cdot \mathbb{P}(|X| \geq \epsilon)\\
\end{split}
$$

### chebyshev inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{VAR}\left[X\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
&\text{let } X' = X - \mathbb{E}[X] \text{ and } r = 2 \\
&\forall \epsilon > 0:\mathbb{E}\left[|X'|^2\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X'| \geq \epsilon\right) \\
\Rightarrow &\forall \epsilon > 0:\mathbb{E}\left[|X - \mathbb{E}[X]|^2\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right) \\

\Rightarrow & \forall \epsilon > 0:\mathbb{VAR}\left[X\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right) \\
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1717740451569-->
END


START
Basic
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$
- prove the following
$$
\forall \epsilon > 0, r>0:\mathbb{E}\left[|X|^r\right] \geq \epsilon^r \cdot \mathbb{P}\left(|X| \geq \epsilon\right)
$$

Back: 
### markov inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{E}\left[|X|^r\right] \geq \epsilon^r \cdot \mathbb{P}\left(|X| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[|X|^r\right] 
&= \int_{-\infty}^{0} (-x)^r f_X(x) \mathrm{d} x^r + \int_{0}^{\infty} x f_X(x) \mathrm{d} x \\
&= \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{-\epsilon}^{0} (-x)^r f_X(x) \mathrm{d} x 
+ \int_{0}^{\epsilon} x^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} \epsilon^r f_X(x) \mathrm{d} x + \int_{\epsilon}^{\infty} \epsilon^r f_X(x) \mathrm{d} x \\
&\geq \epsilon^r \cdot \mathbb{P}(|X| \geq \epsilon)\\
\end{split}
$$

### chebyshev inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{VAR}\left[X\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
&\text{let } X' = X - \mathbb{E}[X] \text{ and } r = 2 \\
&\forall \epsilon > 0:\mathbb{E}\left[|X'|^2\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X'| \geq \epsilon\right) \\
\Rightarrow &\forall \epsilon > 0:\mathbb{E}\left[|X - \mathbb{E}[X]|^2\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right) \\

\Rightarrow & \forall \epsilon > 0:\mathbb{VAR}\left[X\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right) \\
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1717740451572-->
END

START
Basic
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$
- prove the following

$$
\forall \epsilon > 0, r>0:\mathbb{VAR}\left[|X|^r\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right)
$$

Back: 
### markov inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{E}\left[|X|^r\right] \geq \epsilon^r \cdot \mathbb{P}\left(|X| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[|X|^r\right] 
&= \int_{-\infty}^{0} (-x)^r f_X(x) \mathrm{d} x^r + \int_{0}^{\infty} x f_X(x) \mathrm{d} x \\
&= \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{-\epsilon}^{0} (-x)^r f_X(x) \mathrm{d} x 
+ \int_{0}^{\epsilon} x^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} \epsilon^r f_X(x) \mathrm{d} x + \int_{\epsilon}^{\infty} \epsilon^r f_X(x) \mathrm{d} x \\
&\geq \epsilon^r \cdot \mathbb{P}(|X| \geq \epsilon)\\
\end{split}
$$

### chebyshev inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{VAR}\left[X\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
&\text{let } X' = X - \mathbb{E}[X] \text{ and } r = 2 \\
&\forall \epsilon > 0:\mathbb{E}\left[|X'|^2\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X'| \geq \epsilon\right) \\
\Rightarrow &\forall \epsilon > 0:\mathbb{E}\left[|X - \mathbb{E}[X]|^2\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right) \\

\Rightarrow & \forall \epsilon > 0:\mathbb{VAR}\left[X\right] \geq \epsilon^2 \cdot \mathbb{P}\left(|X - \mathbb{E}[X]| \geq \epsilon\right) \\
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1717740451576-->
END