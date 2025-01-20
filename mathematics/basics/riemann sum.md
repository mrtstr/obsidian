### riemann sum
- $x_1, ..., x_{n+1}$ are points that are [[partition|partitioning]] $[a, b]$ in $n$ sub-intervals thus $a=x_1 < ...< x_n < x_{n+1} = b$
- $c_i \in [x_{i-1}, x_{i}]$ is an arbitrary point in each sub-interval 
- then the [[integral]] of $f$ can be approximated as follows

$$
\begin{split}
\int_a^b f(x) dx = \sum_{i=1}^n f(c_i) \left(x_{i+1} - x_i\right)+ \mathcal{O}\left(\frac{1}{n}\right)
\end{split}
$$

if the sub-intervals $x_i - x_{i-1}=\frac{a-b}{n}$ are equally sized then it simplifies as follows

$$
\begin{split}
\int_a^b f(x) dx = \frac{a-b}{n} \sum_{i=1}^n f(c_i) + \mathcal{O}\left(\frac{1}{n}\right)
\end{split}
$$

- the error is in $\mathcal{O}\left(\frac{1}{n}\right)$

# anki

START
Basic
[[riemann sum]] as approximation for the [[integral]]
- definition
- error
Back: 
### riemann sum
- $x_1, ..., x_{n+1}$ are points that are [[partition|partitioning]] $[a, b]$ in $n$ sub-intervals thus $a=x_1 < ...< x_n < x_{n+1} = b$
- $c_i \in [x_{i-1}, x_{i}]$ is an arbitrary point in each sub-interval 
- then the [[integral]] of $f$ can be approximated as follows

$$
\begin{split}
\int_a^b f(x) dx = \sum_{i=1}^n f(c_i) \left(x_{i+1} - x_i\right)+ \mathcal{O}\left(\frac{1}{n}\right)
\end{split}
$$

if the sub-intervals $x_i - x_{i-1}=\frac{a-b}{n}$ are equally sized then it simplifies as follows

$$
\begin{split}
\int_a^b f(x) dx = \frac{a-b}{n} \sum_{i=1}^n f(c_i) + \mathcal{O}\left(\frac{1}{n}\right)
\end{split}
$$

- the error is in $\mathcal{O}\left(\frac{1}{n}\right)$

Tags: mathematics WS2425
<!--ID: 1737394997654-->
END
