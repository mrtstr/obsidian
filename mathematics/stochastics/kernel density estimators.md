### kernel density estimators
- given $n$ i.i.d. observations $X_1, ..., X_n$ from a [[distribution]] $f_X$ 
- the [[probability density function (PDF)]] $f_X$ can be estimated with the [[kernel density estimators]] $\hat f(x)$ 
- with the [[kernel function (statistics)]] $K\left(u\right): \mathbb{R} \to [0, \infty)$ (often $K\left(u\right): [-1,1] \to [0, \infty)$) and the bandwidth $h>0$

$$
\hat f(t)=\frac{1}{nh} \sum_{i=1}^n K\left(\frac{t-X_i}{h}\right)
$$
- that means when we have $n$ samples the estimated [[probability density function (PDF)]] would be a sum of $n$ [[probability density function (PDF)|PDFs]] $\frac{1}{h}K\left(\frac{t-X_i}{h}\right)$ divided by $n$




# ------------

![[kernel function (statistics)#kernel function (statistics)]]