### maximum of uniform samples
- given a sample from a [[continous uniform distribution]]
$$
\begin{split}
X_1, ..., X_n \sim \mathcal{U}(0, b) \text{ i.i.d} \\
F_X(x) = \frac{x - a}{b -a} = \frac{x}{b} 
\end{split}
$$
- and a [[random variable]] $Y$ that is the [[maximum]] of the random sample
$$
Y = \max\{X_1, ..., X_n\}
$$
- the [[cumulative distribution function (CDF)]] and the [[probability density function (PDF)]]
$$
\begin{split}
F_Y(y) 
&= \mathbb{P}(Y \leq y) \\
&= \mathbb{P}\left(\max\{X_1, ..., X_n\} \leq y\right) \\
&= \mathbb{P}\left(X_1 \leq y\right)^n \\
&= F_X(y)^n \\
&= \frac{y^n}{b^n}  \\
f_Y(y)
&= \frac{dF_Y(y)}{dy}  \\
&= n \frac{y^{n-1}}{b^n} \\
\end{split}
$$
- the [[expectation]] of $Y$ is calculated as follows

$$
\begin{split}
\mathbb{E}[Y]  
&= \int_0^b y \cdot f_Y(y) dy \\
&= \int_0^b y \cdot n \frac{y^{n-1}}{b^n} dy \\
&= \frac{n}{b^n} \int_0^b  y^{n} dy \\
&= \frac{n}{b^n} b^{n+1} \frac{1}{n+1}  \\
&= b \frac{n}{n+1}  \\
\end{split}
$$

# ----------------

![[continous uniform distribution#continous uniform distribution]]


# anki
START
Basic

- given a sample from a [[continous uniform distribution]]
$$
\begin{split}
X_1, ..., X_n \sim \mathcal{U}(0, b) \text{ i.i.d} \\
\end{split}
$$
- and a [[random variable]] $Y$ that is the [[maximum]] of the random sample
$$
Y = \max\{X_1, ..., X_n\}
$$

calculate the 
- [[cumulative distribution function (CDF)]] of $Y$
- [[probability density function (PDF)]] of $Y$
- the [[expectation]] of $Y$

Back: 
### maximum of uniform samples
- given a sample from a [[continous uniform distribution]]
$$
\begin{split}
X_1, ..., X_n \sim \mathcal{U}(0, b) \text{ i.i.d} \\
F_X(x) = \frac{x - a}{b -a} = \frac{x}{b} 
\end{split}
$$
- and a [[random variable]] $Y$ that is the [[maximum]] of the random sample
$$
Y = \max\{X_1, ..., X_n\}
$$
- the [[cumulative distribution function (CDF)]] and the [[probability density function (PDF)]]
$$
\begin{split}
F_Y(y) 
&= \mathbb{P}(Y \leq y) \\
&= \mathbb{P}\left(\max\{X_1, ..., X_n\} \leq y\right) \\
&= \mathbb{P}\left(X_1 \leq y\right)^n \\
&= F_X(y)^n \\
&= \frac{y^n}{b^n}  \\
f_Y(y)
&= \frac{dF_Y(y)}{dy}  \\
&= n \frac{y^{n-1}}{b^n} \\
\end{split}
$$
- the [[expectation]] of $Y$ is calculated as follows

$$
\begin{split}
\mathbb{E}[Y]  
&= \int_0^b y \cdot f_Y(y) dy \\
&= \int_0^b y \cdot n \frac{y^{n-1}}{b^n} dy \\
&= \frac{n}{b^n} \int_0^b  y^{n} dy \\
&= \frac{n}{b^n} b^{n+1} \frac{1}{n+1}  \\
&= b \frac{n}{n+1}  \\
\end{split}
$$
_____________________________

### continous uniform distribution
[[probability density function (PDF)]] of a [[probability mass function (PMF)]] with the same probability of taking all values inside an interval $[a,b]$ and 0 for all other values.
#### [[probability density function (PDF)]]
$$
f_X(X = x)=
\begin{cases}
\frac{1}{b-a}
,& \text{if } x \in [a,b]\\
0
,& \text{otherwise}
\end{cases}
$$
#### [[cumulative distribution function (CDF)]]

$$
\begin{split}
F_X(x)&=
\begin{cases}
0 
,& \text{if } x<a \\
\int\limits_a^x\frac{1}{b-a}du
,& \text{if } x \in [a,b]\\
1
,& \text{if } x>b
\end{cases} \\
&= \begin{cases}
0 
,& \text{if } x<a \\
\frac{x-a}{b-a}
,& \text{if } x \in [a,b]\\
1
,& \text{if } x>b
\end{cases}
\end{split}
$$
<!--ID: 1719154404930-->
END