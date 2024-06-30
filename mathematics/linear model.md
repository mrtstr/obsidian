### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\gamma, v}: \gamma \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\gamma \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\gamma, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \gamma + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \gamma_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \gamma_j + \sqrt{v} \xi_i \\
\end{split}
$$

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\gamma$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\gamma$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\gamma_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
- since the [[variance]] of the error is normalized ($\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$) the parameter $v$ refelcts the variance that is not explained by the linear relationship between chracteristics $A$ and dependent variable $X$


### [[expectation]] and [[variance]] of a [[linear model]]
$$
\begin{split}
\mathbb{E}\left[X\right]
&= \mathbb{E}\left[A \gamma + \sqrt{v} \xi\right]  \\
&= A\gamma  + \sqrt{v}\mathbb{E}\left[   \xi\right]  \\
&= A\gamma   \\
\mathbb{E}\left[X\right]
&= v\mathbb{VAR}\left[\xi\right]  \\
&= v  \\
\end{split}
$$


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

### training of a [[linear model]]
$$
\begin{split}
\hat\gamma 
&= arg \min_\gamma ||X - A\gamma||^2 \\
&= \left(A^\top A\right)^{-1}A^\top X \\
\end{split}
$$

#### proof

$$
\begin{split}
&D||X - A\gamma||^2(\gamma)^\top 
= A^\top\left(A\gamma -X\right) = 0 \\
\Rightarrow&\gamma= \left(A^\top A\right)^{-1}A^\top X
\end{split}
$$
#### proof that $\hat\gamma$ is [[bias|unbiased]]
$$
\begin{split}
\mathbb{E}[\hat\gamma] 
&= \left(A^\top A\right)^{-1}A^\top \mathbb{E}[X] \\
&= \left(A^\top A\right)^{-1}A^\top A\gamma \\
&= \gamma \\
\end{split}
$$

![[derivative#$F(x): mathbb{R} {m} to mathbb{R} = frac{1}{2} Ax -b _2 2$]]


# anki


START
Basic
[[linear model]]
- definition
- interpretation
Back: 
### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\gamma, v}: \gamma \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\gamma \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\gamma, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \gamma + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \gamma_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \gamma_j + \sqrt{v} \xi_i \\
\end{split}
$$

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\gamma$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\gamma$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\gamma_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
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
&= \mathbb{E}\left[A \gamma + \sqrt{v} \xi\right]  \\
&= A\gamma  + \sqrt{v}\mathbb{E}\left[   \xi\right]  \\
&= A\gamma   \\
\mathbb{E}\left[X\right]
&= v\mathbb{VAR}\left[\xi\right]  \\
&= v  \\
\end{split}
$$

_______________________


### linear model
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\gamma, v}: \gamma \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\gamma \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\gamma, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \gamma + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \gamma_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \gamma_j + \sqrt{v} \xi_i \\
\end{split}
$$

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\gamma$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\gamma$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\gamma_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
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
&D||X - A\gamma||^2(\gamma)^\top 
= A^\top\left(A\gamma -X\right) = 0 \\
\Rightarrow&\gamma= \left(A^\top A\right)^{-1}A^\top X
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
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\gamma, v}: \gamma \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\gamma \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\gamma, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \gamma + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \gamma_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \gamma_j + \sqrt{v} \xi_i \\
\end{split}
$$

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\gamma$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\gamma$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\gamma_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
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
&= A \gamma + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \gamma_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \gamma_j + \sqrt{v} \xi_i \\
\end{split}
$$
proof that the following [[statistical estimator]] is [[bias|unbiased]]
$$
\begin{split}
\gamma= \left(A^\top A\right)^{-1}A^\top X
\end{split}
$$
Back: 

#### proof that $\hat\gamma$ is [[bias|unbiased]]
$$
\begin{split}
\mathbb{E}[\hat\gamma] 
&= \left(A^\top A\right)^{-1}A^\top \mathbb{E}[X] \\
&= \left(A^\top A\right)^{-1}A^\top A\gamma \\
&= \gamma \\
\end{split}
$$


#### [[expectation]] and [[variance]] of a [[linear model]]
$$
\begin{split}
\mathbb{E}\left[X\right]
&= \mathbb{E}\left[A \gamma + \sqrt{v} \xi\right]  \\
&= A\gamma  + \sqrt{v}\mathbb{E}\left[   \xi\right]  \\
&= A\gamma   \\
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
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\gamma, v}: \gamma \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\gamma \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\gamma, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \gamma + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \gamma_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \gamma_j + \sqrt{v} \xi_i \\
\end{split}
$$

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\gamma$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\gamma$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\gamma_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
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
- a [[linear model]] $\left(\mathbb{R}^n, \mathcal{B}\left(\mathbb{R}^n\right), \mathbb{P}_{\gamma, v}: \gamma \in \mathbb{R}^{s}, v \in (0, \infty)\right)$ 
- is defined by a design [[matrix]] $A \in \mathbb{R}^{n \times s}$ with $s<n$ and a full [[rank]] $\mathrm{rank}(A)=s$ 
- the error is model my a [[stochastic independent]] normalized [[random variable|random vector]] $\xi=(\xi_1, ..., \xi_n)^\top$ with $\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$
- the model parameters are a positive [[scalar]] values $v$ that is a weight for the error term and real valued [[vector]] $\gamma \in \mathbb{R}^s$ 
- the $\mathbb{P}_{\gamma, v}$ is the [[distribution]] of $X$

$$
\begin{split}
X 
&= A \gamma + \sqrt{v} \xi \\
&= \sum_{j \in [S]} A_{(*, j)} \gamma_j + \sqrt{v} \xi \\
X_i
&= \sum_{j \in [S]} A_{(i, j)} \gamma_j + \sqrt{v} \xi_i \\
\end{split}
$$
________________________

### interpretation of a [[linear model]]
- during the training the parameters are fitted to explain the relationship between the dependen variable $X_i$ and its characteristics (features) $A_{(i, *)} \in \mathbb{R}^s$ for all training samples $i \in [n]$ 
- for an unknown sample we can model unknown propertie $X$ based on the known characterists $A_{(1, *)} \in \mathbb{R}^1$ as a [[random variable]] with the [[expectation]] $\mathbb{E}\left[X\right]=A\gamma$ and th [[variance]] $\mathbb{VAR}\left[X\right]=v$

#### design [[matrix]] $A$
- the design [[matrix]] contains the training data
- $s$ is the number of characteristics and $n$ is the number of observations
- e.g. $A \in \mathbb{R}^{n \times 2}$ containing the hight and weight of $n$ different people
- e.g. $A \in \mathbb{R}^{n \times 3}$ containing the GDP of $n$ different countries in 3 consecutive year's
#### parameter $\gamma$ and $v$
- for each characteristic of the observation (features of the training samples) the model has a paramter $\gamma_i: i \in [s]$ that reflects the impact the feature $i$ has on the dependen variable $X_i$
- since the [[variance]] of the error is normalized ($\mathbb{E}[\xi_i]=0$ and $\mathbb{VAR}[\xi_i]=1$) the parameter $v$ refelcts the variance that is not explained by the linear relationship between chracteristics $A$ and dependent variable $X$

Tags: mathematics statistics
<!--ID: 1719759188740-->
END