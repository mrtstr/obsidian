### mutual information
- given two random variables $X$ and $Y$ with a joint [[distribution]] $f_{XY}$
- the [[mutual information]] is defined as the following with the joint [[entropy]] $H(X,Y)$ and the [[entropy]] $H(X)$ and $H(Y)$

$$
\begin{split}
I[X, Y] 
&= D_{KL}(f_{XY} \parallel f_{X}f_{Y}) \\
&= H(X) + H(Y) - H(X,Y) \\
&= H(Y) - H(Y|X) \\
&= H(X) - H(X|Y) \\
\end{split}
$$

- the [[mutual information]] is positive because the [[kl divergence]] is positive 

- proof first equality
$$
\begin{split}
D_{KL}(f_{XY} \parallel f_{X}f_{Y})
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( \frac{f_{XY}(x, y)}{f_{X}(x)f_{Y}(y)} \right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \left(\log \left( f_{XY}(x, y)\right) - \log \left( f_{X}(x)f_{Y}(y)\right)\right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{XY}(x, y)\right)  dxdy  \\
&-\int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{X}(x)\right)  dxdy \\
&-\int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{Y}(y)\right)  dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{XY}(x, y)\right)  dxdy  \\
&-\int_{\mathbb{R}} f_{X}(x) \log \left( f_{X}(x)\right)  dx \\
&-\int_{\mathbb{R}} f_{Y}(y) \log \left( f_{Y}(y)\right)  dy \\
&= H(X) + H(Y) - H(X,Y) \\
\end{split}
$$

- proof second equality
$$
\begin{split}
D_{KL}(f_{XY} \parallel f_{X}f_{Y})
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( \frac{f_{XY}(x, y)}{f_{X}(x)f_{Y}(y)} \right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \left(\log \left( f_{XY}(x, y)\right) - \log \left( f_{X}(x)f_{Y}(y)\right)\right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{XY}(x, y)\right)  dxdy  +H(X)+H(Y)  \\
&= \int_{\mathbb{R}} f_{X|Y}(x, y) f_Y(y) \log \left( f_{X|Y}(x, y) f_Y(y)\right)  dxdy  +H(X)+H(Y)  \\
&= \int_{\mathbb{R}} f_{X|Y}(x, y) f_Y(y) (\log \left( f_{X|Y}(x, y) \right) + \log \left(f_Y(y)\right))  dxdy  +H(X)+H(Y)  \\
&= -H(X|Y) - H(Y)  +H(X)+H(Y)  \\
&=  - H(X)   -H(X|Y)  \\
\end{split}
$$


# --------

![[cross entropy#cross entropy]]

![[entropy#differential entropy]]

# anki

START
Basic
[[mutual information]]
- definition + two qualities without proof

Back: 

### mutual information
- given two random variables $X$ and $Y$ with a joint [[distribution]] $f_{XY}$
- the [[mutual information]] is defined as the following with the joint [[entropy]] $H(X,Y)$ and the [[entropy]] $H(X)$ and $H(Y)$

$$
\begin{split}
I[X, Y] 
&= D_{KL}(f_{XY} \parallel f_{X}f_{Y}) \\
&= H(X) + H(Y) - H(X,Y) \\
&= H(Y) - H(Y|X) \\
&= H(X) - H(X|Y) \\
\end{split}
$$

- the [[mutual information]] is positive because the [[kl divergence]] is positive 

- proof first equality
$$
\begin{split}
D_{KL}(f_{XY} \parallel f_{X}f_{Y})
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( \frac{f_{XY}(x, y)}{f_{X}(x)f_{Y}(y)} \right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \left(\log \left( f_{XY}(x, y)\right) - \log \left( f_{X}(x)f_{Y}(y)\right)\right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{XY}(x, y)\right)  dxdy  \\
&-\int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{X}(x)\right)  dxdy \\
&-\int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{Y}(y)\right)  dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{XY}(x, y)\right)  dxdy  \\
&-\int_{\mathbb{R}} f_{X}(x) \log \left( f_{X}(x)\right)  dx \\
&-\int_{\mathbb{R}} f_{Y}(y) \log \left( f_{Y}(y)\right)  dy \\
&= H(X) + H(Y) - H(X,Y) \\
\end{split}
$$

- proof second equality
$$
\begin{split}
D_{KL}(f_{XY} \parallel f_{X}f_{Y})
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( \frac{f_{XY}(x, y)}{f_{X}(x)f_{Y}(y)} \right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \left(\log \left( f_{XY}(x, y)\right) - \log \left( f_{X}(x)f_{Y}(y)\right)\right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{XY}(x, y)\right)  dxdy  +H(X)+H(Y)  \\
&= \int_{\mathbb{R}} f_{X|Y}(x, y) f_Y(y) \log \left( f_{X|Y}(x, y) f_Y(y)\right)  dxdy  +H(X)+H(Y)  \\
&= \int_{\mathbb{R}} f_{X|Y}(x, y) f_Y(y) (\log \left( f_{X|Y}(x, y) \right) + \log \left(f_Y(y)\right))  dxdy  +H(X)+H(Y)  \\
&= -H(X|Y) - H(Y)  +H(X)+H(Y)  \\
&=  - H(X)   -H(X|Y)  \\
\end{split}
$$



### prove that the kl divergence is positive
- using the fact that for all $u>0$ the following is true

$$
-\log(u) \geq 1-u
$$

$$
\begin{split}
D_{KL}(P \parallel Q) 
&= \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx \\
&= - \int_{\mathbb{R}} p(x) \log \left( \frac{q(x)}{p(x)} \right) dx \\
&\leq  \int_{\mathbb{R}} p(x) \left( 1 - \frac{q(x)}{p(x)} \right) dx \\
&=  \int_{\mathbb{R}} p(x) dx - \int_{\mathbb{R}} p(x)  \frac{q(x)}{p(x)}  dx \\
&=  1 - \int_{\mathbb{R}}q(x)  dx \\
&= 0 \\
\end{split}
$$


_______________

### kl divergence
- KL divergence is a measure of how much the **assumed distribution $Q$**
  diverges from the **true distribution $P$**.
#### Continuous Case

$$
D_{KL}(P \parallel Q) = \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx
$$

#### Discrete Case

$$
D_{KL}(P \parallel Q) = \sum_{x \in \mathcal{X}} p(x) \log \left( \frac{p(x)}{q(x)} \right)
$$

- $D_{KL}(P \parallel Q) \in [0, \infty]$
- $D_{KL}(P \parallel Q) = 0$ if and only if $P = Q$
- $D_{KL}(P \parallel Q) = \infty$ if there exists any $x$ such that $p(x) > 0$ and $q(x) = 0$ because this would make the [[cross entropy]] go to infinity

### cross entropy
- [[cross entropy]] is a measure of the dissimilarity between two probability distributions: a **true distribution** $P$ and an **estimated (or assumed) distribution** $Q$
- It quantifies the **expected number of bits** needed to encode samples from $P$
  using a code that is optimized for $Q$
- It is defined as the **expected negative log-likelihood** under $Q$
  when the data is actually drawn from $P$

#### Continuous Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### Discrete Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### range
- The **minimum** cross-entropy is reached when $P=Q$ in which case it reduces to the **entropy** of $P$:

$$
H(P, Q) = H(P) \quad \text{if and only if} \quad P = Q
$$

- can go to infinity if there are regions where  $p(x) > 0$ but $q(x) = 0$ because $\log \left(q(x)\right)=\log \left(0\right) = -\infty$, and thus the expectation $-\mathbb{E}_{x \sim P}[\log q(x)]$ becomes infinite.

$$
\text{supp}(P) \nsubseteq \text{supp}(Q)
$$




### entropy
- measure of the **average amount of information** contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(p_X(X)\right)\right] = - \sum p_X(x_i) \log\left(p_X(x_i)\right)
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$
##### example
- [[bernoulli distribution]] with $p=0.9$ and $p=0.5$
- We see that the entropy is **higher** when $p=0.5$, indicating that this outcome is **more uncertain** and thus contains **more information per observation**.

$$
\begin{split}
H(X) &= - 0.1 \cdot \log_2(0.1) - 0.9 \cdot \log_2(0.9) = 0.33 + 0.14 = 0.47 \\
H(X) &= - 0.5 \cdot \log_2(0.5) - 0.5 \cdot \log_2(0.5) = \frac{1}{2} + \frac{1}{2} = 1 \\
\end{split}
$$

### differential entropy
- for continuous random variables the concept of [[entropy]] can be extended
- does not have an intuitive interpretation other than **measurement for uncertainty or spread**
- other than the [[entropy]] the differential entropy can be negative and is sensitive to scaling

- for a continuous random variable with the [[probability density function (PDF)]] $f_X$ the differential entropy is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(f_X(X)\right)\right] = - \int_\mathbb{R} f_X(x) \log\left(f_X(x)\right) dx
$$
##### example
- [[exponential distribution]]

$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln\left(\lambda e^{-\lambda x})\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \left(\ln(\lambda)  -\lambda x\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln(\lambda) dx + \lambda \int_\mathbb{R} \lambda e^{-\lambda x}  x dx \\
&= - \ln(\lambda) + \lambda \int_\mathbb{R}  \mathbb{E}[X] \\
&= - \ln(\lambda) + \frac{\lambda}{\lambda} \\
&= 1 - \ln(\lambda) \\
\end{split}
$$

- the higher $\lambda$ is the less the PDF spreads thus $1-\ln(2)=0.3<1-\ln(1)=1$

Tags: mathematics statistics SS25
<!--ID: 1748337248590-->
END

START
Basic
[[mutual information]]
- prove for the following equalitys

$$
\begin{split}
I[X, Y] 
&= H(X) + H(Y) - H(X,Y) \\
&= H(Y) - H(Y|X) \\
\end{split}
$$

Back: 

### mutual information
- given two random variables $X$ and $Y$ with a joint [[distribution]] $f_{XY}$
- the [[mutual information]] is defined as the following with the joint [[entropy]] $H(X,Y)$ and the [[entropy]] $H(X)$ and $H(Y)$

$$
\begin{split}
I[X, Y] 
&= D_{KL}(f_{XY} \parallel f_{X}f_{Y}) \\
&= H(X) + H(Y) - H(X,Y) \\
&= H(Y) - H(Y|X) \\
&= H(X) - H(X|Y) \\
\end{split}
$$

- the [[mutual information]] is positive because the [[kl divergence]] is positive 

- proof first equality
$$
\begin{split}
D_{KL}(f_{XY} \parallel f_{X}f_{Y})
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( \frac{f_{XY}(x, y)}{f_{X}(x)f_{Y}(y)} \right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \left(\log \left( f_{XY}(x, y)\right) - \log \left( f_{X}(x)f_{Y}(y)\right)\right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{XY}(x, y)\right)  dxdy  \\
&-\int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{X}(x)\right)  dxdy \\
&-\int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{Y}(y)\right)  dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{XY}(x, y)\right)  dxdy  \\
&-\int_{\mathbb{R}} f_{X}(x) \log \left( f_{X}(x)\right)  dx \\
&-\int_{\mathbb{R}} f_{Y}(y) \log \left( f_{Y}(y)\right)  dy \\
&= H(X) + H(Y) - H(X,Y) \\
\end{split}
$$

- proof second equality
$$
\begin{split}
D_{KL}(f_{XY} \parallel f_{X}f_{Y})
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( \frac{f_{XY}(x, y)}{f_{X}(x)f_{Y}(y)} \right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \left(\log \left( f_{XY}(x, y)\right) - \log \left( f_{X}(x)f_{Y}(y)\right)\right) dxdy \\
&= \int_{\mathbb{R}} f_{XY}(x, y) \log \left( f_{XY}(x, y)\right)  dxdy  +H(X)+H(Y)  \\
&= \int_{\mathbb{R}} f_{X|Y}(x, y) f_Y(y) \log \left( f_{X|Y}(x, y) f_Y(y)\right)  dxdy  +H(X)+H(Y)  \\
&= \int_{\mathbb{R}} f_{X|Y}(x, y) f_Y(y) (\log \left( f_{X|Y}(x, y) \right) + \log \left(f_Y(y)\right))  dxdy  +H(X)+H(Y)  \\
&= -H(X|Y) - H(Y)  +H(X)+H(Y)  \\
&=  - H(X)   -H(X|Y)  \\
\end{split}
$$



### prove that the kl divergence is positive
- using the fact that for all $u>0$ the following is true

$$
-\log(u) \geq 1-u
$$

$$
\begin{split}
D_{KL}(P \parallel Q) 
&= \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx \\
&= - \int_{\mathbb{R}} p(x) \log \left( \frac{q(x)}{p(x)} \right) dx \\
&\leq  \int_{\mathbb{R}} p(x) \left( 1 - \frac{q(x)}{p(x)} \right) dx \\
&=  \int_{\mathbb{R}} p(x) dx - \int_{\mathbb{R}} p(x)  \frac{q(x)}{p(x)}  dx \\
&=  1 - \int_{\mathbb{R}}q(x)  dx \\
&= 0 \\
\end{split}
$$


_______________

### kl divergence
- KL divergence is a measure of how much the **assumed distribution $Q$**
  diverges from the **true distribution $P$**.
#### Continuous Case

$$
D_{KL}(P \parallel Q) = \int_{\mathbb{R}} p(x) \log \left( \frac{p(x)}{q(x)} \right) dx
$$

#### Discrete Case

$$
D_{KL}(P \parallel Q) = \sum_{x \in \mathcal{X}} p(x) \log \left( \frac{p(x)}{q(x)} \right)
$$

- $D_{KL}(P \parallel Q) \in [0, \infty]$
- $D_{KL}(P \parallel Q) = 0$ if and only if $P = Q$
- $D_{KL}(P \parallel Q) = \infty$ if there exists any $x$ such that $p(x) > 0$ and $q(x) = 0$ because this would make the [[cross entropy]] go to infinity

### cross entropy
- [[cross entropy]] is a measure of the dissimilarity between two probability distributions: a **true distribution** $P$ and an **estimated (or assumed) distribution** $Q$
- It quantifies the **expected number of bits** needed to encode samples from $P$
  using a code that is optimized for $Q$
- It is defined as the **expected negative log-likelihood** under $Q$
  when the data is actually drawn from $P$

#### Continuous Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### Discrete Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### range
- The **minimum** cross-entropy is reached when $P=Q$ in which case it reduces to the **entropy** of $P$:

$$
H(P, Q) = H(P) \quad \text{if and only if} \quad P = Q
$$

- can go to infinity if there are regions where  $p(x) > 0$ but $q(x) = 0$ because $\log \left(q(x)\right)=\log \left(0\right) = -\infty$, and thus the expectation $-\mathbb{E}_{x \sim P}[\log q(x)]$ becomes infinite.

$$
\text{supp}(P) \nsubseteq \text{supp}(Q)
$$




### entropy
- measure of the **average amount of information** contained in an observation of a [[random variable]] in bits (if the $\log_2$ is used)
- in other words the average amount of removed uncertainty by an observation 
- for a discrete random variable with the [[probability function]] $p_X$ the [[entropy]] is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(p_X(X)\right)\right] = - \sum p_X(x_i) \log\left(p_X(x_i)\right)
$$

- $H(X)$ is positive, and its maximum value depends on the [[distribution]] of $X$
##### example
- [[bernoulli distribution]] with $p=0.9$ and $p=0.5$
- We see that the entropy is **higher** when $p=0.5$, indicating that this outcome is **more uncertain** and thus contains **more information per observation**.

$$
\begin{split}
H(X) &= - 0.1 \cdot \log_2(0.1) - 0.9 \cdot \log_2(0.9) = 0.33 + 0.14 = 0.47 \\
H(X) &= - 0.5 \cdot \log_2(0.5) - 0.5 \cdot \log_2(0.5) = \frac{1}{2} + \frac{1}{2} = 1 \\
\end{split}
$$

### differential entropy
- for continuous random variables the concept of [[entropy]] can be extended
- does not have an intuitive interpretation other than **measurement for uncertainty or spread**
- other than the [[entropy]] the differential entropy can be negative and is sensitive to scaling

- for a continuous random variable with the [[probability density function (PDF)]] $f_X$ the differential entropy is defined as follows

$$
H(X) = \mathbb{E}\left[-\log\left(f_X(X)\right)\right] = - \int_\mathbb{R} f_X(x) \log\left(f_X(x)\right) dx
$$
##### example
- [[exponential distribution]]

$$
\begin{split}
H(X) 
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln\left(\lambda e^{-\lambda x})\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \left(\ln(\lambda)  -\lambda x\right) dx \\
&= - \int_\mathbb{R} \lambda e^{-\lambda x} \ln(\lambda) dx + \lambda \int_\mathbb{R} \lambda e^{-\lambda x}  x dx \\
&= - \ln(\lambda) + \lambda \int_\mathbb{R}  \mathbb{E}[X] \\
&= - \ln(\lambda) + \frac{\lambda}{\lambda} \\
&= 1 - \ln(\lambda) \\
\end{split}
$$

- the higher $\lambda$ is the less the PDF spreads thus $1-\ln(2)=0.3<1-\ln(1)=1$

Tags: mathematics statistics SS25
<!--ID: 1748337248594-->
END