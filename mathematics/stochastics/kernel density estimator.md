### kernel density estimator
- given $n$ i.i.d. observations $X_1, ..., X_n$ from a [[distribution]] $f_X$ 
- the [[probability density function (PDF)]] $f_X$ can be estimated with the [[kernel density estimator]] $\hat f(x)$ 
- with the [[kernel function (statistics)]] $K\left(u\right): \mathbb{R} \to [0, \infty)$ (often $K\left(u\right): [-1,1] \to [0, \infty)$) and the bandwidth $h>0$

$$
\hat f(t)=\frac{1}{nh} \sum_{i=1}^n K\left(\frac{t-X_i}{h}\right)
$$
- that means when we have $n$ samples the estimated [[probability density function (PDF)]] would be a sum of $n$ [[probability density function (PDF)|PDFs]] $\frac{1}{h}K\left(\frac{t-X_i}{h}\right)$ divided by $n$


![[Comparison_of_1D_histogram_and_KDE.png]]

# ------------

![[kernel function (statistics)#kernel function (statistics)]]


# Anki

START
Basic
how to estimate a [[probability density function (PDF)]] from observations using the [[kernel density estimator]]
Back: 

### kernel density estimators
- given $n$ i.i.d. observations $X_1, ..., X_n$ from a [[distribution]] $f_X$ 
- the [[probability density function (PDF)]] $f_X$ can be estimated with the [[kernel density estimator]] $\hat f(x)$ 
- with the [[kernel function (statistics)]] $K\left(u\right): \mathbb{R} \to [0, \infty)$ (often $K\left(u\right): [-1,1] \to [0, \infty)$) and the bandwidth $h>0$

$$
\hat f(t)=\frac{1}{nh} \sum_{i=1}^n K\left(\frac{t-X_i}{h}\right)
$$

- that means when we have $n$ samples the estimated [[probability density function (PDF)]] would be a sum of $n$ [[probability density function (PDF)|PDFs]] $\frac{1}{h}K\left(\frac{t-X_i}{h}\right)$ divided by $n$

![[Comparison_of_1D_histogram_and_KDE 1.png]]

____________________

### kernel function (statistics)
- symmetric [[probability density function (PDF)]] or [[probability mass function (PMF)]] $K$ that is centered around zero

$$
\begin{split}
\int_\infty^\infty K(u) du &= 1 \\
\sum_{u =\infty}^\infty K(u)  &= 1 \\
K(u)  &= K(-u) \\
\end{split}
$$

- the [[kernel function (statistics)]] is often used scaled with a bandwidth parameter $h$ but the resulting function $K_h(u)$ is still a [[kernel function (statistics)]]

$$
K_h(u) = \frac{1}{h}K\left(\frac{u}{h}\right)
$$

TODO add proof

Tags: mathematics time_series WS2425
<!--ID: 1736001837817-->
END