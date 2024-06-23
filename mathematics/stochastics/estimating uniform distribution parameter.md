### estimating uniform distribution parameter
- given a random sample from an [[continous uniform distribution]] $\mathcal{U}(0, b)$ of size $n$
- given a [[statistical model#n fold statistical model|n fold statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with $\mathbb{P}_\vartheta$ being the [[continous uniform distribution]] and $\vartheta = b$
$$
\begin{split}
\mathfrak{X} &= [0, \infty)^n \\
\Theta &= [0, \infty) \\
\mathbb{P}_\vartheta &= \frac{1}{\vartheta^n} \\
\end{split}
$$
- given a [[statistics]] $\tau(\vartheta) = \vartheta$ that describes the paramter itself

#### first [[statistical estimator]]

$$
T_n = \frac{2}{n} \sum_{i\in [n]} X_i
$$
##### [[bias]]
- the [[expectation]] of a [[random variable]] with a [[continous uniform distribution]] is $\frac{b-a}{2}$ thus the [[statistical estimator]] has no [[bias]]

$$
\begin{split}
\mathbb{B}_T[\vartheta] 
&= \mathbb{E}_\vartheta[T_n] - \tau(\vartheta) \\
&= 2 \cdot \mathbb{E}_\vartheta[X_1] - \vartheta = 0\\
\end{split}
$$

##### [[estimator variance]]

$$
\begin{split}
\mathbb{VAR}_\vartheta[T_n] 
&= \mathbb{VAR}_\vartheta\left[ \frac{2}{n} \sum_{i\in [n]} X_i\right]  \\
&= \frac{4}{n^2} n \mathbb{VAR}_\vartheta\left[ X_1\right]  \\
&= \frac{4}{n}  \frac{\vartheta^2}{12}  \\
&= \frac{\vartheta^2}{n}  \frac{1}{3}  \\
\end{split}
$$

#### second [[statistical estimator]]
$$
T_n = \max\{X_1, ..., X_n\}
$$
- the [[statistical estimator]] the following [[expectation]] (see [[maximum of uniform samples]])
$$
\begin{split}
\mathbb{E}[T_n]  
&= \int_0^b x \cdot f_\vartheta(x) dx \\
&= \int_0^\vartheta y \cdot n \frac{x^{n-1}}{\vartheta^n} dx \\
&= \frac{n}{\vartheta^n} \int_0^b  x^{n} dx \\
&= \frac{n}{\vartheta^n} b^{n+1} \frac{1}{n+1}  \\
&= \vartheta \frac{n}{n+1}  \\
\end{split}
$$
- thus the [[statistical estimator]] has a negative [[bias]] and tends to unterestimate the parameter

$$
\begin{split}
\mathbb{B}_T[\vartheta] 
&= \mathbb{E}_\vartheta[T_n] - \tau(\vartheta) \\
&= \vartheta \frac{n}{n+1} - \vartheta \\
&= \vartheta \left(\frac{n}{n+1} - 1\right) \\
&= \vartheta \left(\frac{-1}{n+1}\right) \\
\end{split}
$$
- but the [[bias]] can be compensated in the [[statistical estimator]] $\widetilde{T_n}$ which is unbiased
$$
\widetilde{T_n} = \frac{n+1}{n} \max\{X_1, ..., X_n\}
$$

# ------------------

![[estimator variance#estimator variance]]

![[bias#bias]]

![[statistical model#statistical model]]

![[statistical estimator#statistical estimator]]

![[maximum of uniform samples#maximum of uniform samples]]

![[continous uniform distribution#continous uniform distribution]]



# anki


START
Basic
### estimating uniform distribution parameter
- given a random sample from an [[continous uniform distribution]] $\mathcal{U}(0, b)$ of size $n$
- given a [[statistical model#n fold statistical model|n fold statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with $\mathbb{P}_\vartheta$ being the [[continous uniform distribution]] and $\vartheta = b$
$$
\begin{split}
\mathfrak{X} &= [0, \infty)^n \\
\Theta &= [0, \infty) \\
\mathbb{P}_\vartheta &= \frac{1}{\vartheta^n} \\
\end{split}
$$
- given a [[statistics]] $\tau(\vartheta) = \vartheta$ that describes the paramter itself


- give two different unbiased [[statistical estimator]] for the [[statistics]] (no proof)

Back: 

#### first [[statistical estimator]]

$$
T_n = \frac{2}{n} \sum_{i\in [n]} X_i
$$
##### [[bias]]
- the [[expectation]] of a [[random variable]] with a [[continous uniform distribution]] is $\frac{b-a}{2}$ thus the [[statistical estimator]] has no [[bias]]

$$
\begin{split}
\mathbb{B}_T[\vartheta] 
&= \mathbb{E}_\vartheta[T_n] - \tau(\vartheta) \\
&= 2 \cdot \mathbb{E}_\vartheta[X_1] - \vartheta = 0\\
\end{split}
$$


#### second [[statistical estimator]]
$$
T_n = \max\{X_1, ..., X_n\}
$$
- the [[statistical estimator]] the following [[expectation]] (see [[maximum of uniform samples]])
$$
\begin{split}
\mathbb{E}[T_n]  
&= \int_0^b x \cdot f_\vartheta(x) dx \\
&= \int_0^\vartheta y \cdot n \frac{x^{n-1}}{\vartheta^n} dx \\
&= \frac{n}{\vartheta^n} \int_0^b  x^{n} dx \\
&= \frac{n}{\vartheta^n} b^{n+1} \frac{1}{n+1}  \\
&= \vartheta \frac{n}{n+1}  \\
\end{split}
$$
- thus the [[statistical estimator]] has a negative [[bias]] and tends to unterestimate the parameter

$$
\begin{split}
\mathbb{B}_T[\vartheta] 
&= \mathbb{E}_\vartheta[T_n] - \tau(\vartheta) \\
&= \vartheta \frac{n}{n+1} - \vartheta \\
&= \vartheta \left(\frac{n}{n+1} - 1\right) \\
&= \vartheta \left(\frac{-1}{n+1}\right) \\
\end{split}
$$
- but the [[bias]] can be compensated in the [[statistical estimator]] $\widetilde{T_n}$ which is unbiased
$$
\widetilde{T_n} = \frac{n+1}{n} \max\{X_1, ..., X_n\}
$$
______________________

### bias
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and a [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ with an [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is
- the [[bias]] of $T$ is defined as follows
$$
\begin{split}
\mathbb{B}_T[\vartheta] 
&= \mathbb{E}_\vartheta[T] - \tau(\vartheta) \\
&= \mathbb{E}_{X \sim \mathbb{P}_\vartheta}\left[T(X)\right] - \tau(\vartheta) \\
\end{split}
$$
- given a [[set]] of parameters $\vartheta \in \Theta$ the [[function]] $\tau: \Theta \to \Omega$ gives the true characteristics of the [[distribution]] $\mathbb{P}_\vartheta$ defined by $\vartheta$
- the [[expectation]] of the [[statistical estimator]] $\mathbb{E}_\vartheta[T]$ is the approximation of the [[statistics]] $\tau(\vartheta)$ assuming an infinitely large sample to estimate from
→ the [[bias]] the remaining error when esimating based on an infinitely large sample

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
#### [[quantile function]]
Because [[cumulative distribution function (CDF)]] is continuous we can calculate $Q_X(p) = F^{-1}_X(p)$ by rearranging $p=\frac{x-a}{b-a}$:
$$
Q_X(p): [0,1] \mapsto \mathbb{R} = a+p(b-a)
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of parameters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself


$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$


Tags: mathematics statistics
<!--ID: 1719154404920-->
END


START
Basic
### estimating uniform distribution parameter
- given a random sample from an [[continous uniform distribution]] $\mathcal{U}(0, b)$ of size $n$
- given a [[statistical model#n fold statistical model|n fold statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with $\mathbb{P}_\vartheta$ being the [[continous uniform distribution]] and $\vartheta = b$
$$
\begin{split}
\mathfrak{X} &= [0, \infty)^n \\
\Theta &= [0, \infty) \\
\mathbb{P}_\vartheta &= \frac{1}{\vartheta^n} \\
\end{split}
$$
- given a [[statistics]] $\tau(\vartheta) = \vartheta$ that describes the paramter itself

- given the following [[statistical estimator]]
$$
T_n = \max\{X_1, ..., X_n\}
$$

- what is the [[bias]] of $T_n$
- can it be changed to be unbiased?

Back: 

$$
T_n = \max\{X_1, ..., X_n\}
$$
- the [[statistical estimator]] the following [[expectation]] (see [[maximum of uniform samples]])
$$
\begin{split}
\mathbb{E}[T_n]  
&= \int_0^b x \cdot f_\vartheta(x) dx \\
&= \int_0^\vartheta y \cdot n \frac{x^{n-1}}{\vartheta^n} dx \\
&= \frac{n}{\vartheta^n} \int_0^b  x^{n} dx \\
&= \frac{n}{\vartheta^n} b^{n+1} \frac{1}{n+1}  \\
&= \vartheta \frac{n}{n+1}  \\
\end{split}
$$
- thus the [[statistical estimator]] has a negative [[bias]] and tends to unterestimate the parameter

$$
\begin{split}
\mathbb{B}_T[\vartheta] 
&= \mathbb{E}_\vartheta[T_n] - \tau(\vartheta) \\
&= \vartheta \frac{n}{n+1} - \vartheta \\
&= \vartheta \left(\frac{n}{n+1} - 1\right) \\
&= \vartheta \left(\frac{-1}{n+1}\right) \\
\end{split}
$$
- but the [[bias]] can be compensated in the [[statistical estimator]] $\widetilde{T_n}$ which is unbiased
$$
\widetilde{T_n} = \frac{n+1}{n} \max\{X_1, ..., X_n\}
$$

______________________

### bias
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and a [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ with an [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is
- the [[bias]] of $T$ is defined as follows
$$
\begin{split}
\mathbb{B}_T[\vartheta] 
&= \mathbb{E}_\vartheta[T] - \tau(\vartheta) \\
&= \mathbb{E}_{X \sim \mathbb{P}_\vartheta}\left[T(X)\right] - \tau(\vartheta) \\
\end{split}
$$
- given a [[set]] of parameters $\vartheta \in \Theta$ the [[function]] $\tau: \Theta \to \Omega$ gives the true characteristics of the [[distribution]] $\mathbb{P}_\vartheta$ defined by $\vartheta$
- the [[expectation]] of the [[statistical estimator]] $\mathbb{E}_\vartheta[T]$ is the approximation of the [[statistics]] $\tau(\vartheta)$ assuming an infinitely large sample to estimate from
→ the [[bias]] the remaining error when esimating based on an infinitely large sample


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
#### [[quantile function]]
Because [[cumulative distribution function (CDF)]] is continuous we can calculate $Q_X(p) = F^{-1}_X(p)$ by rearranging $p=\frac{x-a}{b-a}$:
$$
Q_X(p): [0,1] \mapsto \mathbb{R} = a+p(b-a)
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of parameters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself


$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$


Tags: mathematics statistics
<!--ID: 1719154404925-->
END



START
Basic

### estimating uniform distribution parameter
- given a random sample from an [[continous uniform distribution]] $\mathcal{U}(0, b)$ of size $n$
- given a [[statistical model#n fold statistical model|n fold statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with $\mathbb{P}_\vartheta$ being the [[continous uniform distribution]] and $\vartheta = b$
$$
\begin{split}
\mathfrak{X} &= [0, \infty)^n \\
\Theta &= [0, \infty) \\
\mathbb{P}_\vartheta &= \frac{1}{\vartheta^n} \\
\end{split}
$$
- given a [[statistics]] $\tau(\vartheta) = \vartheta$ that describes the paramter itself


- given the [[statistical estimator]] $T_n$
$$
T_n = \frac{2}{n} \sum_{i\in [n]} X_i
$$
- calculate the [[variance]] of $T_n$
Back: 


##### [[bias]]
- the [[expectation]] of a [[random variable]] with a [[continous uniform distribution]] is $\frac{b-a}{2}$ thus the [[statistical estimator]] has no [[bias]]

$$
\begin{split}
\mathbb{B}_T[\vartheta] 
&= \mathbb{E}_\vartheta[T_n] - \tau(\vartheta) \\
&= 2 \cdot \mathbb{E}_\vartheta[X_1] - \vartheta = 0\\
\end{split}
$$

##### [[estimator variance]]

$$
\begin{split}
\mathbb{VAR}_\vartheta[T_n] 
&= \mathbb{VAR}_\vartheta\left[ \frac{2}{n} \sum_{i\in [n]} X_i\right]  \\
&= \frac{4}{n^2} n \mathbb{VAR}_\vartheta\left[ X_1\right]  \\
&= \frac{4}{n}  \frac{\vartheta^2}{12}  \\
&= \frac{\vartheta^2}{n}  \frac{1}{3}  \\
\end{split}
$$

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

#### [[expectation]]

$$
\begin{split}
\mathbb{E}[X] 
&= \int_a^b x \frac{1}{b-a} dx \\
&= \frac{b^2 - a^2}{b-a} \frac{1}{2}  \\
&= \frac{(b-a)(b+a)}{b-a} \frac{1}{2}  \\
&= \frac{b+a}{2}  \\
\end{split}
$$

#### [[variance]]

$$
\begin{split}
\mathbb{E}\left[X^2\right] 
&= \int_a^b x^2 \frac{1}{b-a} dx \\
&= \frac{b^3 - a^3}{b-a} \frac{1}{3}  \\
\mathbb{VAR}\left[X\right] 
&= \mathbb{E}\left[X^2\right]  - \mathbb{E}\left[X\right] ^2\\
&= \frac{b^3 - a^3}{b-a} \frac{1}{3} - \left(\frac{b+a}{2}\right)^2\\
\end{split}
$$
- for $a=0$
$$
\begin{split}
\mathbb{VAR}\left[X\right] 
&= \frac{b^3}{b} \frac{1}{3} - \left(\frac{b}{2}\right)^2\\
&= \frac{b^2}{3} - \frac{b^2}{4}\\
&= \frac{b^2}{12}\\
\end{split}
$$

______________________

### estimator variance
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and a [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ with an [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ 
- the [[estimator variance]] of $T$ is defined as follows
$$
\begin{split}
\mathbb{VAR}_\vartheta[T] &= \mathbb{E}_\vartheta\left[\left(T -\mathbb{E}_\vartheta\left[T\right]\right)^2 \right]  \\
&= \mathbb{E}_\vartheta\left[T^2\right] - \mathbb{E}_\vartheta\left[T\right]^2\\
\end{split}
$$

- the [[estimator variance]] can be interpreted as the amount of fluctuation of the [[statistical estimator]]

### bias
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and a [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ with an [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is
- the [[bias]] of $T$ is defined as follows
$$
\begin{split}
\mathbb{B}_T[\vartheta] 
&= \mathbb{E}_\vartheta[T] - \tau(\vartheta) \\
&= \mathbb{E}_{X \sim \mathbb{P}_\vartheta}\left[T(X)\right] - \tau(\vartheta) \\
\end{split}
$$
- given a [[set]] of parameters $\vartheta \in \Theta$ the [[function]] $\tau: \Theta \to \Omega$ gives the true characteristics of the [[distribution]] $\mathbb{P}_\vartheta$ defined by $\vartheta$
- the [[expectation]] of the [[statistical estimator]] $\mathbb{E}_\vartheta[T]$ is the approximation of the [[statistics]] $\tau(\vartheta)$ assuming an infinitely large sample to estimate from
→ the [[bias]] the remaining error when esimating based on an infinitely large sample


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



### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of parameters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself


$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$


Tags: mathematics statistics
<!--ID: 1719154404927-->
END