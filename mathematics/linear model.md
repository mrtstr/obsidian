### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon_i]=\sigma^2$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
Y 
&= X \theta + \epsilon \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$
#### feature map
- can be generalized by introducing a function $\varphi: \mathcal{X} \to \mathbb{R}^d$ that transforms the input features
- in this way the model can lean non-linear relationships between input and output

$$
\begin{split}
Y = f_\theta(X) + \epsilon = \varphi(X)^\top\theta  + \epsilon
\end{split}
$$

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependent variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown properties $X$ based on the known characteristics $X_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[Y\right]=X\theta$ and the [[variance]] $\mathbb{VAR}\left[Y\right]=v$

#### design [[matrix]] $X$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $X \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $X \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\theta$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\theta_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
- since the [[variance]] of the error is normalized ($\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$) the parameter $v$ refelcts the variance that is not explained by the linear relationship between chracteristics $A$ and dependent variable $X$


### [[expectation]] and [[variance]] of a [[linear model]]
$$
\begin{split}
\mathbb{E}\left[Y\right]
&= \mathbb{E}\left[X \theta + \sqrt{v} \xi\right]  \\
&= X\theta  + \sqrt{v}\mathbb{E}\left[   \xi\right]  \\
&= X\theta   \\
\mathbb{E}\left[Y\right]
&= v\mathbb{VAR}\left[\xi\right]  \\
&= v  \\
\end{split}
$$


### example [[linear model]]
##### model the weight of a person based on hight
$$
X=
\left(\begin{matrix}
1 & t_1 \\
... & ...\\
1 & t_n \\
\end{matrix}\right) \in \mathbb{R}^{n \times 2}
$$
$$
Y=
\left(\begin{matrix}
w_1 \\
 ...\\
w_n \\
\end{matrix}\right) \in \mathbb{R}^{n }
$$

$$
\theta=
\left(\begin{matrix}
\theta_1 \\
\theta_n \\
\end{matrix}\right) \in \mathbb{R}^{2 }
$$

$$
\begin{split}
Y 
&= A \theta + \sqrt{v} \xi \\
\end{split}
$$

$$
\begin{split}
\theta
&= arg \min_\theta || Y - X\theta||^2 \\
&= arg \min_\theta \sum_{i\in [n]} (Y_i - \theta_0 - \theta_1 \cdot t_i)^2 \\
\end{split}
$$


$$
\begin{split}
&\frac{\partial}{\partial \theta_0} \sum_{i\in [n]} \left(Y_i - \theta_0 - \theta_1 \cdot t_i\right)^2 = 0 \\
\Rightarrow& \sum_{i\in [n]} -2 \cdot \left(X_i - \theta_0 - \theta_1 \cdot t_i\right) = 0 \\
\Rightarrow& \left(\sum_{i\in [n]}  Y_i\right) - n \cdot \theta_0 - \theta_1 \cdot \left(\sum_{i\in [n]}  t_i\right) = 0 \\
\Rightarrow& \left(\frac{1}{n}\sum_{i\in [n]}  Y_i\right) - \theta_0 - \theta_1 \cdot \left(\frac{1}{n}\sum_{i\in [n]}  t_i\right) = 0 \\
\Rightarrow& M(Y) - \theta_0 - \theta_1 \cdot M(t) = 0 \\
\Rightarrow& \theta_0 = M(Y)  - \theta_1 \cdot M(t) \\
\end{split}
$$

$$
\begin{split}
&\frac{\partial}{\partial \theta_1} \sum_{i\in [n]} \left(Y_i - \theta_0 - \theta_1 \cdot t_i\right)^2 = 0 \\
\Rightarrow& \sum_{i\in [n]} -2t_i \cdot \left(Y_i - \theta_0 - \theta_1 \cdot t_i\right) = 0 \\

\Rightarrow& \sum_{i\in [n]} t_i X_i - t_i \theta_0 - t_i^2 \theta_1  = 0 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i - \theta_0 \frac{1}{n} \sum_{i\in [n]} t_i  - \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2   = 0 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i - \theta_0 M(t)  - \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2   = 0 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i = \theta_0 M(t)  + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\end{split}
$$


$$
\begin{split}
& \frac{1}{n} \sum_{i\in [n]} t_i X_i = \theta_0 M(t)  + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i = \left( M(X)  - \theta_1 \cdot M(t)\right) M(t)  + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i =  M(X)M(t)  - \theta_1 \cdot M(t)^2   + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i =  M(X)M(t)  - \theta_1 V(t)\\
\Rightarrow& \theta_1 V(t)  =  M(X)M(t)  - \frac{1}{n} \sum_{i\in [n]} t_i X_i \\
\Rightarrow& \theta_1 V(t)  =  C(X, t)\\
\Rightarrow& \theta_1   =   \frac{C(X, t)}{V(t)}\\
\end{split}
$$

$$
\begin{split}
\theta_0 &= M(X)  - \theta_1 \cdot M(t) \\
&= M(X)  - \frac{C(X, t)}{V(t)} \cdot M(t) \\
\end{split}
$$


### training of a [[linear model]]
$$
\begin{split}
\hat\theta 
&= arg \min_\theta ||Y - X\theta||^2 \\
&= \left(X^\top X\right)^{-1}X^\top Y \\
\end{split}
$$

#### proof

$$
\begin{split}
&D||Y - X\theta||^2(\theta)^\top 
= A^\top\left(X\theta -Y\right) = 0 \\
\Rightarrow&\theta= \left(X^\top X\right)^{-1}X^\top Y
\end{split}
$$
#### proof that $\hat\theta$ is [[bias|unbiased]]
$$
\begin{split}
\mathbb{E}[\hat\theta] 
&= \left(X^\top X\right)^{-1}X^\top \mathbb{E}[Y] \\
&= \left(X^\top X\right)^{-1}X^\top Y\theta \\
&= \theta \\
\end{split}
$$

# --------------------------
![[empirical variance#empirical variance]]

![[empirical covariance#empirical covariance]]

![[derivative#$F(x): mathbb{R} {m} to mathbb{R} = frac{1}{2} Ax -b _2 2$]]


# anki


START
Basic
[[linear model]]
- definition
- interpretation
Back: 
### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, v}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \theta_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \theta_j + \sqrt{v} \xi_i \\
\end{split}
$$

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\theta$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\theta$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\theta_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
- since the [[variance]] of the error is normalized ($\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$) the parameter $v$ refelcts the variance that is not explained by the linear relationship between chracteristics $A$ and dependent variable $X$

Tags: mathematics statistics
<!--ID: 1719759188721-->
END



START
Basic
[[linear model]]
- definition
- [[expectation]]
- [[variance]]
Back: 
### [[expectation]] and [[variance]] of a [[linear model]]
$$
\begin{split}
\mathbb{E}\left[X\right]
&= \mathbb{E}\left[A \theta + \sqrt{v} \xi\right]  \\
&= A\theta  + \sqrt{v}\mathbb{E}\left[   \xi\right]  \\
&= A\theta   \\
\mathbb{E}\left[X\right]
&= v\mathbb{VAR}\left[\xi\right]  \\
&= v  \\
\end{split}
$$

_______________________


### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, v}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \theta_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \theta_j + \sqrt{v} \xi_i \\
\end{split}
$$

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\theta$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\theta$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\theta_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
- since the [[variance]] of the error is normalized ($\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$) the parameter $v$ refelcts the variance that is not explained by the linear relationship between chracteristics $A$ and dependent variable $X$

Tags: mathematics statistics
<!--ID: 1719759188726-->
END



START
Basic
[[linear model]]
- definition
- training with proof
Back: 

$$
\begin{split}
&D||X - A\theta||^2(\theta)^\top 
= A^\top\left(A\theta -X\right) = 0 \\
\Rightarrow&\theta= \left(A^\top A\right)^{-1}A^\top X
\end{split}
$$

#### $F(x): \mathbb{R}^{m} \to \mathbb{R} = \frac{1}{2}||Ax -b||_2^2$
- the [[derivative]] $DF(x)[h]: \mathbb{R}^{m} \to L( \mathbb{R}^{m},  \mathbb{R})$ has to be [[bounded linear map]] mapping from the $\mathbb{R}^{m}$ to $\mathbb{R}$ with $h \in \mathbb{R}^{m}$
- from the definition we know the following:
$$
F(x + h) = F(x) + DF(x)[h] + \varphi(h) \quad \text{with} \quad \lim_{h \to 0} \frac{||\varphi(h)||}{||h||} = 0 
$$


$$
\begin{split}
F (x + h) 
&= \frac{1}{2}||A(x+h) -b||_2^2 \\
&= \frac{1}{2}\langle (Ax -b) + Ah, (Ax -b) + Ah\rangle \\
&= \frac{1}{2}\langle Ax -b, Ax -b\rangle + \frac{1}{2}\langle Ah, Ah\rangle + \langle Ax -b, Ah\rangle \\
&= \underbrace{\frac{1}{2}||Ax-b||_2^2}_{f(X)} + \underbrace{\frac{1}{2}||Ah||_2^2}_{\varphi(H)} +  \underbrace{\langle Ax -b, Ah \rangle}_{Df(x)[h]}  \\
\end{split}
$$

- show that $\varphi(h)$ is converging fast enough

$$
\begin{split}
\frac{\varphi(h)}{||h||} 
&= \frac{1}{2} \frac{||Ah||^2}{||h||} \\
&= \frac{1}{2} ||h|| \frac{||Ah||^2}{||h||^2} \\
&= \frac{1}{2} ||h|| \left(\frac{||Ah||}{||h||}\right)^2 \\
&\leq \frac{1}{2} ||h|| \left(\sup_{||y|| \neq 0}\frac{||Ay||}{||y||}\right)^2 \\
&= \frac{1}{2} ||h|| \cdot ||A||^2 \xrightarrow{h \to 0} 0 \\
\end{split}
$$


$$
\begin{split}
Df(x)[h] 
&= \langle Ax -b, Ah \rangle \\
&= \left(Ax -b\right)^\top Ah \\
Df(x)
&= \left(Ax -b\right)^\top A \\
\nabla f (x)
&= \left(\left(Ax -b\right)^\top A\right)^\top \\
&= A^\top\left(Ax -b\right)  \\
\end{split}
$$


_______________________


### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, v}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \theta_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \theta_j + \sqrt{v} \xi_i \\
\end{split}
$$

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\theta$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\theta$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\theta_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
- since the [[variance]] of the error is normalized ($\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$) the parameter $v$ refelcts the variance that is not explained by the linear relationship between chracteristics $A$ and dependent variable $X$

Tags: mathematics statistics
<!--ID: 1719759188731-->
END



START
Basic
- given the following [[linear model]]
$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \theta_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \theta_j + \sqrt{v} \xi_i \\
\end{split}
$$
proof that the following [[statistical estimator]] is [[bias|unbiased]]
$$
\begin{split}
\theta= \left(A^\top A\right)^{-1}A^\top X
\end{split}
$$
Back: 

#### proof that $\hat\theta$ is [[bias|unbiased]]
$$
\begin{split}
\mathbb{E}[\hat\theta] 
&= \left(A^\top A\right)^{-1}A^\top \mathbb{E}[X] \\
&= \left(A^\top A\right)^{-1}A^\top A\theta \\
&= \theta \\
\end{split}
$$


#### [[expectation]] and [[variance]] of a [[linear model]]
$$
\begin{split}
\mathbb{E}\left[X\right]
&= \mathbb{E}\left[A \theta + \sqrt{v} \xi\right]  \\
&= A\theta  + \sqrt{v}\mathbb{E}\left[   \xi\right]  \\
&= A\theta   \\
\mathbb{E}\left[X\right]
&= v\mathbb{VAR}\left[\xi\right]  \\
&= v  \\
\end{split}
$$

_______________________
### bias
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and a [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ with an [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is for the caracteristics $\tau: \Theta \to \Omega$
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


### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, v}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \theta_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \theta_j + \sqrt{v} \xi_i \\
\end{split}
$$

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\theta$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\theta$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\theta_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
- since the [[variance]] of the error is normalized ($\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$) the parameter $v$ refelcts the variance that is not explained by the linear relationship between chracteristics $A$ and dependent variable $X$

Tags: mathematics statistics
<!--ID: 1719759188735-->
END


START
Basic
[[linear model]]
- how to estimate the weight of a person based on the hight
Back: 

### example [[linear model]]
- model the weight of a person based on hight
$$
A=
\left(\begin{matrix}
1 & h_1 \\
... & ...\\
1 & h_n \\
\end{matrix}\right) \in \mathbb{R}^{n \times 2}
$$
$$
X=
\left(\begin{matrix}
w_1 \\
 ...\\
w_n \\
\end{matrix}\right) \in \mathbb{R}^{n }
$$


### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, v}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \theta_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \theta_j + \sqrt{v} \xi_i \\
\end{split}
$$
________________________

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\theta$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\theta$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\theta_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
- since the [[variance]] of the error is normalized ($\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$) the parameter $v$ refelcts the variance that is not explained by the linear relationship between chracteristics $A$ and dependent variable $X$

Tags: mathematics statistics
<!--ID: 1719759188740-->
END


START
Basic
- given the following [[linear model]]

$$
A=
\left(\begin{matrix}
1 & t_1 \\
... & ...\\
1 & t_n \\
\end{matrix}\right) \in \mathbb{R}^{n \times 2}
$$
$$
X=
\left(\begin{matrix}
w_1 \\
 ...\\
w_n \\
\end{matrix}\right) \in \mathbb{R}^{n }
$$

$$
\theta=
\left(\begin{matrix}
\theta_1 \\
\theta_n \\
\end{matrix}\right) \in \mathbb{R}^{2 }
$$

$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
\end{split}
$$

- proof the following:
$$
\begin{split}
\theta_0 &= M(X)  - \frac{C(X, t)}{V(t)} \cdot M(t) \\
\theta_1   &=   \frac{C(X, t)}{V(t)}\\
\end{split}
$$

Back: 

##### model the weight of a person based on hight
$$
A=
\left(\begin{matrix}
1 & t_1 \\
... & ...\\
1 & t_n \\
\end{matrix}\right) \in \mathbb{R}^{n \times 2}
$$
$$
X=
\left(\begin{matrix}
w_1 \\
 ...\\
w_n \\
\end{matrix}\right) \in \mathbb{R}^{n }
$$

$$
\theta=
\left(\begin{matrix}
\theta_1 \\
\theta_n \\
\end{matrix}\right) \in \mathbb{R}^{2 }
$$

$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
\end{split}
$$

$$
\begin{split}
\theta
&= arg \min_\theta || X - A\theta||^2 \\
&= arg \min_\theta \sum_{i\in [n]} (X_i - \theta_0 - \theta_1 \cdot t_i)^2 \\
\end{split}
$$


$$
\begin{split}
&\frac{\partial}{\partial \theta_0} \sum_{i\in [n]} \left(X_i - \theta_0 - \theta_1 \cdot t_i\right)^2 = 0 \\
\Rightarrow& \sum_{i\in [n]} -2 \cdot \left(X_i - \theta_0 - \theta_1 \cdot t_i\right) = 0 \\
\Rightarrow& \left(\sum_{i\in [n]}  X_i\right) - n \cdot \theta_0 - \theta_1 \cdot \left(\sum_{i\in [n]}  t_i\right) = 0 \\
\Rightarrow& \left(\frac{1}{n}\sum_{i\in [n]}  X_i\right) - \theta_0 - \theta_1 \cdot \left(\frac{1}{n}\sum_{i\in [n]}  t_i\right) = 0 \\
\Rightarrow& M(X) - \theta_0 - \theta_1 \cdot M(t) = 0 \\
\Rightarrow& \theta_0 = M(X)  - \theta_1 \cdot M(t) \\
\end{split}
$$

$$
\begin{split}
&\frac{\partial}{\partial \theta_1} \sum_{i\in [n]} \left(X_i - \theta_0 - \theta_1 \cdot t_i\right)^2 = 0 \\
\Rightarrow& \sum_{i\in [n]} -2t_i \cdot \left(X_i - \theta_0 - \theta_1 \cdot t_i\right) = 0 \\

\Rightarrow& \sum_{i\in [n]} t_i X_i - t_i \theta_0 - t_i^2 \theta_1  = 0 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i - \theta_0 \frac{1}{n} \sum_{i\in [n]} t_i  - \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2   = 0 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i - \theta_0 M(t)  - \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2   = 0 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i = \theta_0 M(t)  + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\end{split}
$$


$$
\begin{split}
& \frac{1}{n} \sum_{i\in [n]} t_i X_i = \theta_0 M(t)  + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i = \left( M(X)  - \theta_1 \cdot M(t)\right) M(t)  + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i =  M(X)M(t)  - \theta_1 \cdot M(t)^2   + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i =  M(X)M(t)  - \theta_1 V(t)\\
\Rightarrow& \theta_1 V(t)  =  M(X)M(t)  - \frac{1}{n} \sum_{i\in [n]} t_i X_i \\
\Rightarrow& \theta_1 V(t)  =  C(X, t)\\
\Rightarrow& \theta_1   =   \frac{C(X, t)}{V(t)}\\
\end{split}
$$

$$
\begin{split}
\theta_0 &= M(X)  - \theta_1 \cdot M(t) \\
&= M(X)  - \frac{C(X, t)}{V(t)} \cdot M(t) \\
\end{split}
$$

### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, v}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \theta_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \theta_j + \sqrt{v} \xi_i \\
\end{split}
$$

### empirical variance
- given $n$ [[stochastic independent]] samples from the same [[distribution]] the $V$ is appoximating the [[variance]] of the [[distribution]] (but has a [[bias]])

$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
V &= \frac{1}{n} \sum_{i=1}^n (X_i - M)^2 \\
\end{split}
$$

$$
\begin{split}
V(X) 
&= \frac{1}{n}\sum_{i\in [n]}  \left(X_i - M(X)\right)^2 \\
&= \frac{1}{n}\sum_{i\in [n]}  X_i^2 + M(X)^2 - 2X_i M(X) \\
&= \left(\frac{1}{n}\sum_{i\in [n]}  X_i^2 \right)+ \frac{n}{n}M(X)^2 - 2M(X) \frac{1}{n} \sum_{i\in [n]}X_i  \\
&= \left(\frac{1}{n}\sum_{i\in [n]}  X_i^2 \right)- M(X)^2  \\
\end{split}
$$

### empirical covariance
- given $n$ [[stochastic independent]] samples from the two [[distribution]] of the [[random variable]] $X$ and $V$
- the [[function]] $C$ is appoximating the [[covariance]] of the [[distribution]] (but has a [[bias]])

$$
\begin{split}
M(X) &= \frac{1}{n} \sum_{i=1}^n X_i \\
C(X, Y) &= \frac{1}{n} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\
\end{split}
$$

$$
\begin{split}
C(X, Y) 
&= \frac{1}{n} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) + M(X)M(Y) - M(X)\frac{1}{n} \sum_{i=1}^n Y_i - M(Y)\frac{1}{n} \sum_{i=1}^n X_i \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) + M(X)M(Y) - M(X)M(Y) - M(Y)M(X) \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) - M(X)M(Y)\\
\end{split}
$$


________________________

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\theta$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\theta$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\theta_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
- since the [[variance]] of the error is normalized ($\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$) the parameter $v$ refelcts the variance that is not explained by the linear relationship between chracteristics $A$ and dependent variable $X$

Tags: mathematics statistics
<!--ID: 1720372857682-->
END



START
Basic
- given the following [[linear model]]

$$
A=
\left(\begin{matrix}
1 & t_1 \\
... & ...\\
1 & t_n \\
\end{matrix}\right) \in \mathbb{R}^{n \times 2}
$$
$$
X=
\left(\begin{matrix}
w_1 \\
 ...\\
w_n \\
\end{matrix}\right) \in \mathbb{R}^{n }
$$

$$
\theta=
\left(\begin{matrix}
\theta_1 \\
\theta_n \\
\end{matrix}\right) \in \mathbb{R}^{2 }
$$

$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
\end{split}
$$

what are the [[linear least squares]] minimizing paramters $\theta^*$ (as a function of the [[empirical variance]] and [[empirical covariance]])
(no proof)
Back: 

##### model the weight of a person based on hight
$$
A=
\left(\begin{matrix}
1 & t_1 \\
... & ...\\
1 & t_n \\
\end{matrix}\right) \in \mathbb{R}^{n \times 2}
$$
$$
X=
\left(\begin{matrix}
w_1 \\
 ...\\
w_n \\
\end{matrix}\right) \in \mathbb{R}^{n }
$$

$$
\theta=
\left(\begin{matrix}
\theta_1 \\
\theta_n \\
\end{matrix}\right) \in \mathbb{R}^{2 }
$$

$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
\end{split}
$$

$$
\begin{split}
\theta
&= arg \min_\theta || X - A\theta||^2 \\
&= arg \min_\theta \sum_{i\in [n]} (X_i - \theta_0 - \theta_1 \cdot t_i)^2 \\
\end{split}
$$


$$
\begin{split}
&\frac{\partial}{\partial \theta_0} \sum_{i\in [n]} \left(X_i - \theta_0 - \theta_1 \cdot t_i\right)^2 = 0 \\
\Rightarrow& \sum_{i\in [n]} -2 \cdot \left(X_i - \theta_0 - \theta_1 \cdot t_i\right) = 0 \\
\Rightarrow& \left(\sum_{i\in [n]}  X_i\right) - n \cdot \theta_0 - \theta_1 \cdot \left(\sum_{i\in [n]}  t_i\right) = 0 \\
\Rightarrow& \left(\frac{1}{n}\sum_{i\in [n]}  X_i\right) - \theta_0 - \theta_1 \cdot \left(\frac{1}{n}\sum_{i\in [n]}  t_i\right) = 0 \\
\Rightarrow& M(X) - \theta_0 - \theta_1 \cdot M(t) = 0 \\
\Rightarrow& \theta_0 = M(X)  - \theta_1 \cdot M(t) \\
\end{split}
$$

$$
\begin{split}
&\frac{\partial}{\partial \theta_1} \sum_{i\in [n]} \left(X_i - \theta_0 - \theta_1 \cdot t_i\right)^2 = 0 \\
\Rightarrow& \sum_{i\in [n]} -2t_i \cdot \left(X_i - \theta_0 - \theta_1 \cdot t_i\right) = 0 \\

\Rightarrow& \sum_{i\in [n]} t_i X_i - t_i \theta_0 - t_i^2 \theta_1  = 0 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i - \theta_0 \frac{1}{n} \sum_{i\in [n]} t_i  - \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2   = 0 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i - \theta_0 M(t)  - \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2   = 0 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i = \theta_0 M(t)  + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\end{split}
$$


$$
\begin{split}
& \frac{1}{n} \sum_{i\in [n]} t_i X_i = \theta_0 M(t)  + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i = \left( M(X)  - \theta_1 \cdot M(t)\right) M(t)  + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i =  M(X)M(t)  - \theta_1 \cdot M(t)^2   + \theta_1 \frac{1}{n} \sum_{i\in [n]} t_i^2 \\
\Rightarrow& \frac{1}{n} \sum_{i\in [n]} t_i X_i =  M(X)M(t)  - \theta_1 V(t)\\
\Rightarrow& \theta_1 V(t)  =  M(X)M(t)  - \frac{1}{n} \sum_{i\in [n]} t_i X_i \\
\Rightarrow& \theta_1 V(t)  =  C(X, t)\\
\Rightarrow& \theta_1   =   \frac{C(X, t)}{V(t)}\\
\end{split}
$$

$$
\begin{split}
\theta_0 &= M(X)  - \theta_1 \cdot M(t) \\
&= M(X)  - \frac{C(X, t)}{V(t)} \cdot M(t) \\
\end{split}
$$

### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, v}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \theta + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \theta_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \theta_j + \sqrt{v} \xi_i \\
\end{split}
$$

### empirical variance
- given $n$ [[stochastic independent]] samples from the same [[distribution]] the $V$ is appoximating the [[variance]] of the [[distribution]] (but has a [[bias]])

$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
V &= \frac{1}{n} \sum_{i=1}^n (X_i - M)^2 \\
\end{split}
$$

$$
\begin{split}
V(X) 
&= \frac{1}{n}\sum_{i\in [n]}  \left(X_i - M(X)\right)^2 \\
&= \frac{1}{n}\sum_{i\in [n]}  X_i^2 + M(X)^2 - 2X_i M(X) \\
&= \left(\frac{1}{n}\sum_{i\in [n]}  X_i^2 \right)+ \frac{n}{n}M(X)^2 - 2M(X) \frac{1}{n} \sum_{i\in [n]}X_i  \\
&= \left(\frac{1}{n}\sum_{i\in [n]}  X_i^2 \right)- M(X)^2  \\
\end{split}
$$

### empirical covariance
- given $n$ [[stochastic independent]] samples from the two [[distribution]] of the [[random variable]] $X$ and $V$
- the [[function]] $C$ is appoximating the [[covariance]] of the [[distribution]] (but has a [[bias]])

$$
\begin{split}
M(X) &= \frac{1}{n} \sum_{i=1}^n X_i \\
C(X, Y) &= \frac{1}{n} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\
\end{split}
$$

$$
\begin{split}
C(X, Y) 
&= \frac{1}{n} \sum_{i=1}^n \left(X_i - M(X)\right)\left(Y_i - M(Y)\right) \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) + M(X)M(Y) - M(X)\frac{1}{n} \sum_{i=1}^n Y_i - M(Y)\frac{1}{n} \sum_{i=1}^n X_i \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) + M(X)M(Y) - M(X)M(Y) - M(Y)M(X) \\
&= \left(\frac{1}{n} \sum_{i=1}^n X_iY_i \right) - M(X)M(Y)\\
\end{split}
$$


________________________

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\theta$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\theta$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\theta_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
- since the [[variance]] of the error is normalized ($\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$) the parameter $v$ refelcts the variance that is not explained by the linear relationship between chracteristics $A$ and dependent variable $X$

Tags: mathematics statistics
<!--ID: 1720372857686-->
END



START
Basic
can a [[linear model]] learn non learn relationships?

Back: 
### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\theta, \sigma^2}: \theta \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(X)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\epsilon=(\epsilon_1, ..., \epsilon_n)^\top$ with $\mathbb{E}[\epsilon_i]=0$ and $\mathbb{VAR}[\epsilon_i]=\sigma^2$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\theta \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\theta, v}$ is the [[distribution]] of $X$

$$
\begin{split}
Y 
&= X \theta + \epsilon \\
&= \sum_{j \in [S]} X_{(*, j)} \theta_j + \epsilon \\
Y_i
&= \sum_{j \in [S]} X_{(i, j)} \theta_j + \epsilon_i \\
\end{split}
$$
#### feature map
- can be generalized by introducing a function $\varphi: \mathcal{X} \to \mathbb{R}^d$ that transforms the input features
- in this way the model can lean non-linear relationships between input and output

$$
\begin{split}
Y = f_\theta(X) + \epsilon = \varphi(X)^\top\theta  + \epsilon
\end{split}
$$

Tags: mathematics statistics SS25
<!--ID: 1748424598842-->
END