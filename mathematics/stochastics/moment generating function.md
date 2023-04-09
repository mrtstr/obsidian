# moment generating function
- The [[moment generating function]] $\psi_X(t)$ provides a method for calculating the [[moments|raw moments]] $\mathbb{E}\left[X^k\right]$ of [[distribution|distributions]] 
- for some [[distribution|distributions]] is easies than solving the integral 

## definition
$$
\psi_X(t) = \mathbb{E}\left[e^{tx}\right] = \int\limits_{-\infty}^\infty e^{tx} f_X(x) dx
$$

## Calculating the [[moments|raw moments]] $\mathbb{E}\left[X^k\right]$
![[eulers number]]

$$
\begin{split}
\psi_X(t) 
&= \mathbb{E}\left[e^{tx}\right] \\
&= \mathbb{E}\left[\sum_{n=0}^\infty \frac{X^n t^n}{n!}\right] \\
&= 1 + t \mathbb{E}\left[X\right] 
+ \frac{t^2}{2!} \mathbb{E}\left[X^2\right]  
+ \frac{t^3}{3!} \mathbb{E}\left[X^3\right] + ... \\ \\

\mathbb{E}\left[X^k\right] &= 
\left.\frac{d^n\psi_X(t)}{dt^n} \right|_{t=0}


\end{split}
$$



# anki

START
Basic
[[moment generating function]]
- definition
- how to calculate moments
Back: 
- The [[moment generating function]] $\psi_X(t)$ provides a method for calculating the [[moments|raw moments]] $\mathbb{E}\left[X^k\right]$ of [[distribution|distributions]] 
- for some [[distribution|distributions]] is easies than solving the integral 

$$
\psi_X(t) = \mathbb{E}\left[e^{tx}\right] = \int\limits_{-\infty}^\infty e^{tx} f_X(x) dx
$$
with the following formulat for [[eulers number]]
$$
e^\lambda = \sum\limits_{k=1}^\infty \frac{\lambda^k}{k!}
$$

$$
\begin{split}
\psi_X(t) 
&= \mathbb{E}\left[e^{tx}\right] \\
&= \mathbb{E}\left[\sum_{n=0}^\infty \frac{X^n t^n}{n!}\right] \\
&= 1 + t \mathbb{E}\left[X\right] 
+ \frac{t^2}{2!} \mathbb{E}\left[X^2\right]  
+ \frac{t^3}{3!} \mathbb{E}\left[X^3\right] + ... \\ \\

\mathbb{E}\left[X^k\right] &= 
\left.\frac{d^n\psi_X(t)}{dt^n} \right|_{t=0}


\end{split}
$$

Tags: mathematics statistics
<!--ID: 1680159610620-->
END