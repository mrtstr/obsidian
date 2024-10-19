### statistical estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and an [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ 
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is a [[function]] that approximates the [[statistics]] $S$ directly without nesserily approximation the parameters $\vartheta \in \Theta$ of the [[distribution]] $\mathbb{P}_\vartheta$ first
- thus $T: \mathfrak{X} \to \Omega$ estimates a property of the assumed [[distribution]] $\mathbb{P}_\vartheta$ based on an observation $X \in \mathfrak{X}$
- common examples for the property are the [[expectation]] $T(X)=\mathbb{E}_{Y \sim \mathbb{P}_\vartheta(X)}[Y]$ or the model parameters $T(X)=\vartheta \in \Theta$

### [[bias|unbiased]] [[statistical estimator]] for [[n fold statistical model]]
- given an [[n fold statistical model]] $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n), \mathbb{P}^{\otimes n}_{\vartheta \in \Theta}\right)$ with the following characteristics

$$
\begin{split}
m(\vartheta) &= \mathbb{E}_\vartheta[X_1] \\
v(\vartheta) &= \mathbb{VAR}_\vartheta[X_1] \\
\end{split}
$$

- the following are  [[statistical estimator|statistical estimators]] for $m$ and $v$

$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
V &= \frac{1}{n-1} \sum_{i=1}^n (X_i - M)^2 \\

\end{split}
$$

- note: for the [[statistical estimator]] of the [[variance]] we can not devide by the sample size $n$ because the mean of the samples is not independent of the samples $X_i$ because $M$ contains $X_i$, and thus we have to devide by $n-1$ instead
#### [[expectation]]

$$
\begin{split}
\mathbb{E}_\vartheta[M]  
&= \mathbb{E}_\vartheta\left[\frac{1}{n} \sum_{i=1}^n X_i\right]  \\
&= \frac{n}{n}  \mathbb{E}_\vartheta\left[  X_1\right]  \\
&= \mathbb{E}_\vartheta\left[  X_1\right]  \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}_\vartheta[M^2]
&= \mathbb{E}_\vartheta\left[\left(\frac{1}{n} \sum_{i=1}^n X_i \right)^2\right] \\
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\left( \sum_{i=1}^n X_i \right)^2\right] \\
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\sum_{i=1}^n\sum_{i=1}^n X_iX_j\right] \\
&= \frac{1}{n^2} \sum_{i=1}^n\sum_{i=1}^n \mathbb{E}_\vartheta\left[ X_iX_j\right] \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1^2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1\right]\mathbb{E}_\vartheta\left[ X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] - n\mathbb{E}_\vartheta\left[ X_1^2\right] + n^2 \mathbb{E}_\vartheta\left[ X_1\right]^2 \right) \\
&= \mathbb{E}_\vartheta\left[ X_1\right]^2 + \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right]
\end{split}
$$


$$
\begin{split}
&\mathbb{VAR}_\vartheta\left[X_1\right] = \mathbb{E}_\vartheta\left[X_1^2\right] - \mathbb{E}_\vartheta\left[X_1\right]^2 \\
\Rightarrow & \mathbb{E}_\vartheta\left[X_1^2\right] = \mathbb{VAR}_\vartheta\left[X_1\right] + \mathbb{E}_\vartheta\left[X_1\right]^2
\end{split}
$$


$$
\begin{split}
\mathbb{E}_\vartheta[V] 
&= \mathbb{E}_\vartheta\left[\frac{1}{n-1} \sum_{i=1}^n \left(X_i - M\right)^2\right]  \\
&= \frac{1}{n-1}  \sum_{i=1}^n \mathbb{E}_\vartheta\left[  X_i^2 + M^2 - 2 X_iM\right]    \\

&= \frac{1}{n-1} \left( n \mathbb{E}_\vartheta\left[  X_1^2\right] + n\mathbb{E}_\vartheta\left[M^2\right] - \mathbb{E}_\vartheta\left[2M \sum_{i=1}^n X_i\right] \right)  \\
&= \frac{1}{n-1} \left( \mathbb{E}_\vartheta\left[ n X_1^2\right] + n\mathbb{E}_\vartheta\left[M^2\right] - \mathbb{E}_\vartheta\left[2 \cdot n \cdot M^2\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{E}_\vartheta\left[  X_1^2\right] - \mathbb{E}_\vartheta\left[M^2\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{VAR}_\vartheta\left[X_1\right] + \mathbb{E}_\vartheta\left[X_1\right]^2 - \mathbb{E}_\vartheta\left[ X_1\right]^2 - \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{VAR}_\vartheta\left[X_1\right] - \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] \right)  \\
&= \frac{n}{n-1}\mathbb{VAR}_\vartheta\left[X_1\right] \left( 1- \frac{1}{n}  \right)  \\
&= \frac{n}{n-1} \frac{n-1}{n} \mathbb{VAR}_\vartheta\left[X_1\right]   \\
&= \mathbb{VAR}_\vartheta\left[ X_1\right]  \\
\end{split}
$$

#### [[bias]]


$$
\begin{split}
\mathbb{B}[M] 
&= \mathbb{E}_\vartheta[M] - m(\vartheta) \\
&= \mathbb{E}_\vartheta\left[\frac{1}{n} \sum_{i=1}^n X_i\right] -  \mathbb{E}_\vartheta[X_1] \\
&= \frac{n}{n}  \mathbb{E}_\vartheta\left[  X_1\right] -  \mathbb{E}_\vartheta[X_1] = 0 \\
\end{split}
$$
$$
\begin{split}
\mathbb{B}[V] 
&= \mathbb{E}_\vartheta[V] - v(\vartheta) \\
&=  \mathbb{VAR}_\vartheta\left[ X_1\right]  -  \mathbb{VAR}_\vartheta[X_1] \\
&=  0 \\

\end{split}
$$

#### [[variance]]

$$
\begin{split}
\mathbb{VAR}_\vartheta[M] 
&= \mathbb{E}_\vartheta\left[M^2\right] -\mathbb{E}_\vartheta\left[M\right]^2   \\
&= \mathbb{E}_\vartheta\left[ X_1\right]^2 + \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] -\mathbb{E}_\vartheta\left[X_1\right]^2   \\
&= \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right]  \\
\end{split}
$$




# ------------------
![[statistics#statistics]]

![[statistical model#statistical model]]


# anki


START
Basic
[[statistical estimator]]
- definition
- difference to a [[statistics]]
Back: 

### statistical estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and an [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ 
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is a [[function]] that approximates the [[statistics]] $S$ directly without nesserily approximation the parameters $\vartheta \in \Theta$ of the [[distribution]] $\mathbb{P}_\vartheta$ first
- thus $T: \mathfrak{X} \to \Omega$ estimates a property of the assumed [[distribution]] $\mathbb{P}_\vartheta$ based on an observation $X \in \mathfrak{X}$
- common examples for the property are the [[expectation]] $T(X)=\mathbb{E}_{Y \sim \mathbb{P}_\vartheta(X)}[Y]$ or the model parameters $T(X)=\vartheta \in \Theta$



### [[statistics]] vs [[statistical estimator]]
- a [[statistics]] is based on a [[statistical model]] and defines an (unknown) mapping from the observation to a specific property of the [[distribution]] $\mathbb{P}_\theta$ with the assumed parameter [[set]] $\theta \in \Theta$ derrived from the observation

- a [[statistical estimator]] is a [[function]] that estimates the [[statistics]] direclty without nessesary estimating the parameters $\theta \in \Theta$ of the [[distribution]] $\mathbb{P}_\theta$ 


### statistics
- (unknown) mapping from the observation to a property of the assumed underlaying [[distribution]] that helps to extract information about the underlaying randomness
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$ and a [[measurable space]] $\left(\Omega,\mathcal{A} \right)$
- a [[random variable]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ is called a [[statistics]]
- $\Omega$ can be interpreted is a space of characteristics of the [[probability measure]] $\mathbb{P}_\theta$
- $S$ consits of two components: a deterministic [[function]] $\tau: \Theta \to \Omega$ that extracts a property from the paramterized [[distribution]] $\mathbb{P}_\vartheta$ and the paramter approximation from the observation $\mathfrak{X} \to \Theta$ such that the [[distribution]] $\mathbb{P}_\vartheta$ describes an observation $X \in \mathfrak{X}$ best

$$
S(X \in \mathfrak{X}) = \tau\left(\vartheta(X)\right)
$$

#### deterministic [[function]] $\tau: \Theta \to \Omega$
- extracts a property from the parameterized [[distribution]] $\mathbb{P}_\vartheta$ (given the paramter [[set]] $\vartheta$)
- this can for example be the [[expectation]]
$$
\tau(\vartheta) = \mathbb{E}_\vartheta[X] = \sum_{\text{all }x} x \cdot \mathbb{P}_\vartheta (X = x)
$$
- or this can be the paramters themselfs: in this case  $\tau: \Theta \to \Theta$ is the [[identity function]]
$$
\tau(\vartheta) = \vartheta
$$

#### mapping from the obervations $\mathfrak{X}$ to the [[parameter space]] $\Theta$
- derrive the parameter [[set]] $\vartheta \in \Theta$ from an observation $X \in \mathfrak{X}$ such that the [[distribution]] $\mathbb{P}_\vartheta$ describes the observation $X$ best
- $\vartheta \in \Theta$ is a [[random variable]] because its is calculated based on the observation $X$ which is a random sample and this subject to randomness
$$
\vartheta(X) \in \Theta
$$

________________________

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 


Tags: mathematics statistics
<!--ID: 1718536601459-->
END




START
Basic
- given $n$ [[stochastic independent]] samples from the same [[distribution]] $X_1, ..., X_n$ 
- proof the following
$$
\begin{split}
\mathbb{E}\left[\left(\frac{1}{n} \sum_{i=1}^n X_i \right)^2\right] 
&= \mathbb{E}_\vartheta\left[X_1^2\right] +  \frac{1-n}{n} \mathbb{VAR}_\vartheta\left[ X\right]
\end{split}
$$
Back: 

$$
\begin{split}
&\mathbb{VAR}_\vartheta\left[X_1\right] = \mathbb{E}_\vartheta\left[X_1^2\right] - \mathbb{E}_\vartheta\left[X_1\right]^2 \\
\Rightarrow & \mathbb{E}_\vartheta\left[X_1\right]^2 = \mathbb{E}_\vartheta\left[X_1^2\right] -\mathbb{VAR}_\vartheta\left[X_1\right] 
\end{split}
$$


$$
\begin{split}
\mathbb{E}_\vartheta\left[\left(\frac{1}{n} \sum_{i=1}^n X_i \right)^2\right] 
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\left( \sum_{i=1}^n X_i \right)^2\right] \\
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\sum_{i=1}^n\sum_{i=1}^n X_iX_j\right] \\
&= \frac{1}{n^2} \sum_{i=1}^n\sum_{i=1}^n \mathbb{E}_\vartheta\left[ X_iX_j\right] \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1^2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1\right]\mathbb{E}_\vartheta\left[ X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] - n\mathbb{E}_\vartheta\left[ X_1^2\right] + n^2 \mathbb{E}_\vartheta\left[ X_1\right]^2 \right) \\
&= \mathbb{E}_\vartheta\left[ X_1\right]^2 + \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] \\
&= \mathbb{E}_\vartheta\left[X_1^2\right] +  \frac{1-n}{n} \mathbb{VAR}_\vartheta\left[ X\right]
\end{split}
$$



Tags: mathematics statistics
<!--ID: 1719243097791-->
END


START
Basic
### [[bias|unbiased]] [[statistical estimator]] for [[n fold statistical model]]

- given an [[n fold statistical model]] $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n), \mathbb{P}^{\otimes n}_{\vartheta \in \Theta}\right)$ with the following characteristics
$$
\begin{split}
m(\vartheta) &= \mathbb{E}_\vartheta[X_1] \\
v(\vartheta) &= \mathbb{VAR}_\vartheta[X_1] \\
\end{split}
$$


- [[bias|unbiased]] [[statistical estimator|statistical estimators]] for $m$ and $v$ (without proof)
Back: 

- the following are  [[statistical estimator|statistical estimators]] for $m$ and $v$
$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
V &= \frac{1}{n-1} \sum_{i=1}^n (X_i - M)^2 \\

\end{split}
$$

#### [[expectation]]
$$
\begin{split}
\mathbb{E}_\vartheta[M]  
&= \mathbb{E}_\vartheta\left[\frac{1}{n} \sum_{i=1}^n X_i\right]  \\
&= \frac{n}{n}  \mathbb{E}_\vartheta\left[  X_1\right]  \\
&= \mathbb{E}_\vartheta\left[  X_1\right]  \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}_\vartheta[M^2]
&= \mathbb{E}_\vartheta\left[\left(\frac{1}{n} \sum_{i=1}^n X_i \right)^2\right] \\
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\left( \sum_{i=1}^n X_i \right)^2\right] \\
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\sum_{i=1}^n\sum_{i=1}^n X_iX_j\right] \\
&= \frac{1}{n^2} \sum_{i=1}^n\sum_{i=1}^n \mathbb{E}_\vartheta\left[ X_iX_j\right] \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1^2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1\right]\mathbb{E}_\vartheta\left[ X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] - n\mathbb{E}_\vartheta\left[ X_1^2\right] + n^2 \mathbb{E}_\vartheta\left[ X_1\right]^2 \right) \\
&= \mathbb{E}_\vartheta\left[ X_1\right]^2 + \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right]
\end{split}
$$


$$
\begin{split}
&\mathbb{VAR}_\vartheta\left[X_1\right] = \mathbb{E}_\vartheta\left[X_1^2\right] - \mathbb{E}_\vartheta\left[X_1\right]^2 \\
\Rightarrow & \mathbb{E}_\vartheta\left[X_1^2\right] = \mathbb{VAR}_\vartheta\left[X_1\right] + \mathbb{E}_\vartheta\left[X_1\right]^2
\end{split}
$$


$$
\begin{split}
\mathbb{E}_\vartheta[V] 
&= \mathbb{E}_\vartheta\left[\frac{1}{n-1} \sum_{i=1}^n \left(X_i - M\right)^2\right]  \\
&= \frac{1}{n-1}  \sum_{i=1}^n \mathbb{E}_\vartheta\left[  X_i^2 + M^2 - 2 X_iM\right]    \\

&= \frac{1}{n-1} \left( n \mathbb{E}_\vartheta\left[  X_1^2\right] + n\mathbb{E}_\vartheta\left[M^2\right] - \mathbb{E}_\vartheta\left[2M \sum_{i=1}^n X_i\right] \right)  \\
&= \frac{1}{n-1} \left( \mathbb{E}_\vartheta\left[ n X_1^2\right] + n\mathbb{E}_\vartheta\left[M^2\right] - \mathbb{E}_\vartheta\left[2 \cdot n \cdot M^2\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{E}_\vartheta\left[  X_1^2\right] - \mathbb{E}_\vartheta\left[M^2\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{VAR}_\vartheta\left[X_1\right] + \mathbb{E}_\vartheta\left[X_1\right]^2 - \mathbb{E}_\vartheta\left[ X_1\right]^2 - \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{VAR}_\vartheta\left[X_1\right] - \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] \right)  \\
&= \frac{n}{n-1}\mathbb{VAR}_\vartheta\left[X_1\right] \left( 1- \frac{1}{n}  \right)  \\
&= \frac{n}{n-1} \frac{n-1}{n} \mathbb{VAR}_\vartheta\left[X_1\right]   \\
&= \mathbb{VAR}_\vartheta\left[ X_1\right]  \\
\end{split}
$$

#### [[bias]]


$$
\begin{split}
\mathbb{B}[M] 
&= \mathbb{E}_\vartheta[M] - m(\vartheta) \\
&= \mathbb{E}_\vartheta\left[\frac{1}{n} \sum_{i=1}^n X_i\right] -  \mathbb{E}_\vartheta[X_1] \\
&= \frac{n}{n}  \mathbb{E}_\vartheta\left[  X_1\right] -  \mathbb{E}_\vartheta[X_1] = 0 \\
\end{split}
$$
$$
\begin{split}
\mathbb{B}[V] 
&= \mathbb{E}_\vartheta[V] - v(\vartheta) \\
&=  \mathbb{VAR}_\vartheta\left[ X_1\right]  -  \mathbb{VAR}_\vartheta[X_1] \\
&=  0 \\

\end{split}
$$

#### [[variance]]

$$
\begin{split}
\mathbb{VAR}_\vartheta[M] 
&= \mathbb{E}_\vartheta\left[M^2\right] -\mathbb{E}_\vartheta\left[M\right]^2   \\
&= \mathbb{E}_\vartheta\left[ X_1\right]^2 + \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] -\mathbb{E}_\vartheta\left[X_1\right]^2   \\
&= \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right]  \\
\end{split}
$$



_____________

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself

$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$


### product probability space
- given the [[probability space|probability spaces]] $(\Omega_1, \mathcal{A}_1, \mathbb{P}_1)$ and $(\Omega_2, \mathcal{A}_2, \mathbb{P}_2)$
- we can construct a [[product probability space]] $(\Omega_1 \times \Omega_2, \mathcal{A}_1  \otimes \mathcal{A}_2 , \mathbb{P}_1 \otimes \mathbb{P}_2)$

$$
\mathcal{A}_1  \otimes \mathcal{A}_2 = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\}
$$

$$
\begin{split}
\mathbb{P}_1 \otimes \mathbb{P}_2=\mathbb{P}(A_1 \times A_2) = \mathbb{P}(A_1)\mathbb{P}(A_2)
\end{split}
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 



### statistics
- (unknown) mapping from the observation to a property of the assumed underlaying [[distribution]] that helps to extract information about the underlaying randomness
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$ and a [[measurable space]] $\left(\Omega,\mathcal{A} \right)$
- a [[random variable]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ is called a [[statistics]]
- $\Omega$ can be interpreted is a space of characteristics of the [[probability measure]] $\mathbb{P}_\theta$
- $S$ consits of two components: a deterministic [[function]] $\tau: \Theta \to \Omega$ that extracts a property from the paramterized [[distribution]] $\mathbb{P}_\vartheta$ and the paramter approximation from the observation $\mathfrak{X} \to \Theta$ such that the [[distribution]] $\mathbb{P}_\vartheta$ describes an observation $X \in \mathfrak{X}$ best

$$
S(X \in \mathfrak{X}) = \tau\left(\vartheta(X)\right)
$$

#### deterministic [[function]] $\tau: \Theta \to \Omega$
- extracts a characteristics from the parameterized [[distribution]] $\mathbb{P}_\vartheta$ (given the paramter [[set]] $\vartheta$)
- this can for example be the [[expectation]]
$$
\tau(\vartheta) = \mathbb{E}_\vartheta[X] = \sum_{\text{all }x} x \cdot \mathbb{P}_\vartheta (X = x)
$$
- or this can be the paramters themselfs: in this case  $\tau: \Theta \to \Theta$ is the [[identity function]]
$$
\tau(\vartheta) = \vartheta
$$

#### mapping from the obervations $\mathfrak{X}$ to the [[parameter space]] $\Theta$
- derrive the parameter [[set]] $\vartheta \in \Theta$ from an observation $X \in \mathfrak{X}$ such that the [[distribution]] $\mathbb{P}_\vartheta$ describes the observation $X$ best
- $\vartheta \in \Theta$ is a [[random variable]] because its is calculated based on the observation $X$ which is a random sample and this subject to randomness
$$
\vartheta(X) \in \Theta
$$
### statistical estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and an [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ 
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is a [[function]] that approximates the [[statistics]] $S$ directly without nesserily approximation the parameters $\vartheta \in \Theta$ of the [[distribution]] $\mathbb{P}_\vartheta$ first
- thus $T: \mathfrak{X} \to \Omega$ estimates a property of the assumed [[distribution]] $\mathbb{P}_\vartheta$ based on an observation $X \in \mathfrak{X}$
- common examples for the property are the [[expectation]] $T(X)=\mathbb{E}_{Y \sim \mathbb{P}_\vartheta(X)}[Y]$ or the model parameters $T(X)=\vartheta \in \Theta$


Tags: mathematics statistics
<!--ID: 1719243097797-->
END



START
Basic

- given an [[n fold statistical model]] $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n), \mathbb{P}^{\otimes n}_{\vartheta \in \Theta}\right)$ with the following characteristics
$$
\begin{split}
m(\vartheta) &= \mathbb{E}_\vartheta[X_1] \\
\end{split}
$$

- given the following are [[bias|unbiased]] [[statistical estimator|statistical estimators]] for $m$
$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
\end{split}
$$
calculate the following
- [[expectation]] $\mathbb{E}_\vartheta[M]$
- [[bias]] $\mathbb{B}_\vartheta[M]$
- [[variance]] $\mathbb{VAR}_\vartheta[M^2]$
Back: 
#### [[expectation]]
$$
\begin{split}
\mathbb{E}_\vartheta[M]  
&= \mathbb{E}_\vartheta\left[\frac{1}{n} \sum_{i=1}^n X_i\right]  \\
&= \frac{n}{n}  \mathbb{E}_\vartheta\left[  X_1\right]  \\
&= \mathbb{E}_\vartheta\left[  X_1\right]  \\
\end{split}
$$
#### [[bias]]


$$
\begin{split}
\mathbb{B}[M] 
&= \mathbb{E}_\vartheta[M] - m(\vartheta) \\
&= \mathbb{E}_\vartheta\left[\frac{1}{n} \sum_{i=1}^n X_i\right] -  \mathbb{E}_\vartheta[X_1] \\
&= \frac{n}{n}  \mathbb{E}_\vartheta\left[  X_1\right] -  \mathbb{E}_\vartheta[X_1] = 0 \\
\end{split}
$$

#### [[variance]]

$$
\begin{split}
\mathbb{VAR}_\vartheta[M] 
&= \mathbb{E}_\vartheta\left[M^2\right] -\mathbb{E}_\vartheta\left[M\right]^2   \\
&= \mathbb{E}_\vartheta\left[ X_1\right]^2 + \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] -\mathbb{E}_\vartheta\left[X_1\right]^2   \\
&= \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right]  \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}_\vartheta[M^2]
&= \mathbb{E}_\vartheta\left[\left(\frac{1}{n} \sum_{i=1}^n X_i \right)^2\right] \\
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\left( \sum_{i=1}^n X_i \right)^2\right] \\
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\sum_{i=1}^n\sum_{i=1}^n X_iX_j\right] \\
&= \frac{1}{n^2} \sum_{i=1}^n\sum_{i=1}^n \mathbb{E}_\vartheta\left[ X_iX_j\right] \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1^2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1\right]\mathbb{E}_\vartheta\left[ X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] - n\mathbb{E}_\vartheta\left[ X_1^2\right] + n^2 \mathbb{E}_\vartheta\left[ X_1\right]^2 \right) \\
&= \mathbb{E}_\vartheta\left[ X_1\right]^2 + \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right]
\end{split}
$$


_____________

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself

$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$


### product probability space
- given the [[probability space|probability spaces]] $(\Omega_1, \mathcal{A}_1, \mathbb{P}_1)$ and $(\Omega_2, \mathcal{A}_2, \mathbb{P}_2)$
- we can construct a [[product probability space]] $(\Omega_1 \times \Omega_2, \mathcal{A}_1  \otimes \mathcal{A}_2 , \mathbb{P}_1 \otimes \mathbb{P}_2)$

$$
\mathcal{A}_1  \otimes \mathcal{A}_2 = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\}
$$

$$
\begin{split}
\mathbb{P}_1 \otimes \mathbb{P}_2=\mathbb{P}(A_1 \times A_2) = \mathbb{P}(A_1)\mathbb{P}(A_2)
\end{split}
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 



### statistics
- (unknown) mapping from the observation to a property of the assumed underlaying [[distribution]] that helps to extract information about the underlaying randomness
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$ and a [[measurable space]] $\left(\Omega,\mathcal{A} \right)$
- a [[random variable]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ is called a [[statistics]]
- $\Omega$ can be interpreted is a space of characteristics of the [[probability measure]] $\mathbb{P}_\theta$
- $S$ consits of two components: a deterministic [[function]] $\tau: \Theta \to \Omega$ that extracts a property from the paramterized [[distribution]] $\mathbb{P}_\vartheta$ and the paramter approximation from the observation $\mathfrak{X} \to \Theta$ such that the [[distribution]] $\mathbb{P}_\vartheta$ describes an observation $X \in \mathfrak{X}$ best

$$
S(X \in \mathfrak{X}) = \tau\left(\vartheta(X)\right)
$$

#### deterministic [[function]] $\tau: \Theta \to \Omega$
- extracts a characteristics from the parameterized [[distribution]] $\mathbb{P}_\vartheta$ (given the paramter [[set]] $\vartheta$)
- this can for example be the [[expectation]]
$$
\tau(\vartheta) = \mathbb{E}_\vartheta[X] = \sum_{\text{all }x} x \cdot \mathbb{P}_\vartheta (X = x)
$$
- or this can be the paramters themselfs: in this case  $\tau: \Theta \to \Theta$ is the [[identity function]]
$$
\tau(\vartheta) = \vartheta
$$

#### mapping from the obervations $\mathfrak{X}$ to the [[parameter space]] $\Theta$
- derrive the parameter [[set]] $\vartheta \in \Theta$ from an observation $X \in \mathfrak{X}$ such that the [[distribution]] $\mathbb{P}_\vartheta$ describes the observation $X$ best
- $\vartheta \in \Theta$ is a [[random variable]] because its is calculated based on the observation $X$ which is a random sample and this subject to randomness
$$
\vartheta(X) \in \Theta
$$
### statistical estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and an [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ 
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is a [[function]] that approximates the [[statistics]] $S$ directly without nesserily approximation the parameters $\vartheta \in \Theta$ of the [[distribution]] $\mathbb{P}_\vartheta$ first
- thus $T: \mathfrak{X} \to \Omega$ estimates a property of the assumed [[distribution]] $\mathbb{P}_\vartheta$ based on an observation $X \in \mathfrak{X}$
- common examples for the property are the [[expectation]] $T(X)=\mathbb{E}_{Y \sim \mathbb{P}_\vartheta(X)}[Y]$ or the model parameters $T(X)=\vartheta \in \Theta$


Tags: mathematics statistics
<!--ID: 1719243097800-->
END


START
Basic
### [[bias|unbiased]] [[statistical estimator]] for [[n fold statistical model]]

- given an [[n fold statistical model]] $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n), \mathbb{P}^{\otimes n}_{\vartheta \in \Theta}\right)$ with the following characteristics
$$
\begin{split}
m(\vartheta) &= \mathbb{E}_\vartheta[X_1] \\
v(\vartheta) &= \mathbb{VAR}_\vartheta[X_1] \\
\end{split}
$$
- the following are  [[statistical estimator|statistical estimators]] for $m$ and $v$
$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
V &= \frac{1}{n-1} \sum_{i=1}^n (X_i - M)^2 \\

\end{split}
$$

-  proof that $V$ is an [[bias|unbiased]] [[statistical estimator|statistical estimators]] for $v$
Back: 
#### [[bias]]

$$
\begin{split}
\mathbb{B}[V] 
&= \mathbb{E}_\vartheta[V] - v(\vartheta) \\
&=  \mathbb{VAR}_\vartheta\left[ X_1\right]  -  \mathbb{VAR}_\vartheta[X_1] \\
&=  0 \\

\end{split}
$$

#### [[expectation]]
$$
\begin{split}
\mathbb{E}_\vartheta[M]  
&= \mathbb{E}_\vartheta\left[\frac{1}{n} \sum_{i=1}^n X_i\right]  \\
&= \frac{n}{n}  \mathbb{E}_\vartheta\left[  X_1\right]  \\
&= \mathbb{E}_\vartheta\left[  X_1\right]  \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}_\vartheta[M^2]
&= \mathbb{E}_\vartheta\left[\left(\frac{1}{n} \sum_{i=1}^n X_i \right)^2\right] \\
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\left( \sum_{i=1}^n X_i \right)^2\right] \\
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\sum_{i=1}^n\sum_{i=1}^n X_iX_j\right] \\
&= \frac{1}{n^2} \sum_{i=1}^n\sum_{i=1}^n \mathbb{E}_\vartheta\left[ X_iX_j\right] \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1^2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1\right]\mathbb{E}_\vartheta\left[ X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] - n\mathbb{E}_\vartheta\left[ X_1^2\right] + n^2 \mathbb{E}_\vartheta\left[ X_1\right]^2 \right) \\
&= \mathbb{E}_\vartheta\left[ X_1\right]^2 + \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right]
\end{split}
$$


$$
\begin{split}
&\mathbb{VAR}_\vartheta\left[X_1\right] = \mathbb{E}_\vartheta\left[X_1^2\right] - \mathbb{E}_\vartheta\left[X_1\right]^2 \\
\Rightarrow & \mathbb{E}_\vartheta\left[X_1^2\right] = \mathbb{VAR}_\vartheta\left[X_1\right] + \mathbb{E}_\vartheta\left[X_1\right]^2
\end{split}
$$


$$
\begin{split}
\mathbb{E}_\vartheta[V] 
&= \mathbb{E}_\vartheta\left[\frac{1}{n-1} \sum_{i=1}^n \left(X_i - M\right)^2\right]  \\
&= \frac{1}{n-1}  \sum_{i=1}^n \mathbb{E}_\vartheta\left[  X_i^2 + M^2 - 2 X_iM\right]    \\

&= \frac{1}{n-1} \left( n \mathbb{E}_\vartheta\left[  X_1^2\right] + n\mathbb{E}_\vartheta\left[M^2\right] - \mathbb{E}_\vartheta\left[2M \sum_{i=1}^n X_i\right] \right)  \\
&= \frac{1}{n-1} \left( \mathbb{E}_\vartheta\left[ n X_1^2\right] + n\mathbb{E}_\vartheta\left[M^2\right] - \mathbb{E}_\vartheta\left[2 \cdot n \cdot M^2\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{E}_\vartheta\left[  X_1^2\right] - \mathbb{E}_\vartheta\left[M^2\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{VAR}_\vartheta\left[X_1\right] + \mathbb{E}_\vartheta\left[X_1\right]^2 - \mathbb{E}_\vartheta\left[ X_1\right]^2 - \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{VAR}_\vartheta\left[X_1\right] - \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] \right)  \\
&= \frac{n}{n-1}\mathbb{VAR}_\vartheta\left[X_1\right] \left( 1- \frac{1}{n}  \right)  \\
&= \frac{n}{n-1} \frac{n-1}{n} \mathbb{VAR}_\vartheta\left[X_1\right]   \\
&= \mathbb{VAR}_\vartheta\left[ X_1\right]  \\
\end{split}
$$


_____________

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself

$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$


### product probability space
- given the [[probability space|probability spaces]] $(\Omega_1, \mathcal{A}_1, \mathbb{P}_1)$ and $(\Omega_2, \mathcal{A}_2, \mathbb{P}_2)$
- we can construct a [[product probability space]] $(\Omega_1 \times \Omega_2, \mathcal{A}_1  \otimes \mathcal{A}_2 , \mathbb{P}_1 \otimes \mathbb{P}_2)$

$$
\mathcal{A}_1  \otimes \mathcal{A}_2 = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\}
$$

$$
\begin{split}
\mathbb{P}_1 \otimes \mathbb{P}_2=\mathbb{P}(A_1 \times A_2) = \mathbb{P}(A_1)\mathbb{P}(A_2)
\end{split}
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 



### statistics
- (unknown) mapping from the observation to a property of the assumed underlaying [[distribution]] that helps to extract information about the underlaying randomness
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$ and a [[measurable space]] $\left(\Omega,\mathcal{A} \right)$
- a [[random variable]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ is called a [[statistics]]
- $\Omega$ can be interpreted is a space of characteristics of the [[probability measure]] $\mathbb{P}_\theta$
- $S$ consits of two components: a deterministic [[function]] $\tau: \Theta \to \Omega$ that extracts a property from the paramterized [[distribution]] $\mathbb{P}_\vartheta$ and the paramter approximation from the observation $\mathfrak{X} \to \Theta$ such that the [[distribution]] $\mathbb{P}_\vartheta$ describes an observation $X \in \mathfrak{X}$ best

$$
S(X \in \mathfrak{X}) = \tau\left(\vartheta(X)\right)
$$

#### deterministic [[function]] $\tau: \Theta \to \Omega$
- extracts a characteristics from the parameterized [[distribution]] $\mathbb{P}_\vartheta$ (given the paramter [[set]] $\vartheta$)
- this can for example be the [[expectation]]
$$
\tau(\vartheta) = \mathbb{E}_\vartheta[X] = \sum_{\text{all }x} x \cdot \mathbb{P}_\vartheta (X = x)
$$
- or this can be the paramters themselfs: in this case  $\tau: \Theta \to \Theta$ is the [[identity function]]
$$
\tau(\vartheta) = \vartheta
$$

#### mapping from the obervations $\mathfrak{X}$ to the [[parameter space]] $\Theta$
- derrive the parameter [[set]] $\vartheta \in \Theta$ from an observation $X \in \mathfrak{X}$ such that the [[distribution]] $\mathbb{P}_\vartheta$ describes the observation $X$ best
- $\vartheta \in \Theta$ is a [[random variable]] because its is calculated based on the observation $X$ which is a random sample and this subject to randomness
$$
\vartheta(X) \in \Theta
$$
### statistical estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and an [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ 
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is a [[function]] that approximates the [[statistics]] $S$ directly without nesserily approximation the parameters $\vartheta \in \Theta$ of the [[distribution]] $\mathbb{P}_\vartheta$ first
- thus $T: \mathfrak{X} \to \Omega$ estimates a property of the assumed [[distribution]] $\mathbb{P}_\vartheta$ based on an observation $X \in \mathfrak{X}$
- common examples for the property are the [[expectation]] $T(X)=\mathbb{E}_{Y \sim \mathbb{P}_\vartheta(X)}[Y]$ or the model parameters $T(X)=\vartheta \in \Theta$

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

Tags: mathematics statistics
<!--ID: 1719243097804-->
END



START
Basic
### [[bias|unbiased]] [[statistical estimator]] for [[n fold statistical model]]

- given an [[n fold statistical model]] $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n), \mathbb{P}^{\otimes n}_{\vartheta \in \Theta}\right)$ with the following characteristics
$$
\begin{split}
m(\vartheta) &= \mathbb{E}_\vartheta[X_1] \\
v(\vartheta) &= \mathbb{VAR}_\vartheta[X_1] \\
\end{split}
$$
- the following are  [[statistical estimator|statistical estimators]] for $m$ and $v$
$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
V &= \frac{1}{n} \sum_{i=1}^n (X_i - M)^2 \\
\end{split}
$$

-  explain why $V$ is not an [[bias|unbiased]] [[statistical estimator|statistical estimators]] for $v$
- how to change it to make it unbiased
Back: 
for the [[statistical estimator]] of the [[variance]] we can not devide by the sample size $n$ because the mean of the samples is not independent of the samples $X_i$ because $M$ contains $X_i$, and thus we have to devide by $n-1$ instead

$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
V &= \frac{1}{n-1} \sum_{i=1}^n (X_i - M)^2 \\
\end{split}
$$

#### [[expectation]]
$$
\begin{split}
\mathbb{E}_\vartheta[M]  
&= \mathbb{E}_\vartheta\left[\frac{1}{n} \sum_{i=1}^n X_i\right]  \\
&= \frac{n}{n}  \mathbb{E}_\vartheta\left[  X_1\right]  \\
&= \mathbb{E}_\vartheta\left[  X_1\right]  \\
\end{split}
$$

$$
\begin{split}
\mathbb{E}_\vartheta[M^2]
&= \mathbb{E}_\vartheta\left[\left(\frac{1}{n} \sum_{i=1}^n X_i \right)^2\right] \\
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\left( \sum_{i=1}^n X_i \right)^2\right] \\
&= \frac{1}{n^2} \mathbb{E}_\vartheta\left[\sum_{i=1}^n\sum_{i=1}^n X_iX_j\right] \\
&= \frac{1}{n^2} \sum_{i=1}^n\sum_{i=1}^n \mathbb{E}_\vartheta\left[ X_iX_j\right] \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1^2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] + n(n-1) \mathbb{E}_\vartheta\left[ X_1\right]\mathbb{E}_\vartheta\left[ X_2\right] \right) \\
&= \frac{1}{n^2} \left(n \mathbb{E}_\vartheta\left[ X_1^2\right] - n\mathbb{E}_\vartheta\left[ X_1^2\right] + n^2 \mathbb{E}_\vartheta\left[ X_1\right]^2 \right) \\
&= \mathbb{E}_\vartheta\left[ X_1\right]^2 + \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right]
\end{split}
$$


$$
\begin{split}
&\mathbb{VAR}_\vartheta\left[X_1\right] = \mathbb{E}_\vartheta\left[X_1^2\right] - \mathbb{E}_\vartheta\left[X_1\right]^2 \\
\Rightarrow & \mathbb{E}_\vartheta\left[X_1^2\right] = \mathbb{VAR}_\vartheta\left[X_1\right] + \mathbb{E}_\vartheta\left[X_1\right]^2
\end{split}
$$


$$
\begin{split}
\mathbb{E}_\vartheta[V] 
&= \mathbb{E}_\vartheta\left[\frac{1}{n-1} \sum_{i=1}^n \left(X_i - M\right)^2\right]  \\
&= \frac{1}{n-1}  \sum_{i=1}^n \mathbb{E}_\vartheta\left[  X_i^2 + M^2 - 2 X_iM\right]    \\

&= \frac{1}{n-1} \left( n \mathbb{E}_\vartheta\left[  X_1^2\right] + n\mathbb{E}_\vartheta\left[M^2\right] - \mathbb{E}_\vartheta\left[2M \sum_{i=1}^n X_i\right] \right)  \\
&= \frac{1}{n-1} \left( \mathbb{E}_\vartheta\left[ n X_1^2\right] + n\mathbb{E}_\vartheta\left[M^2\right] - \mathbb{E}_\vartheta\left[2 \cdot n \cdot M^2\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{E}_\vartheta\left[  X_1^2\right] - \mathbb{E}_\vartheta\left[M^2\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{VAR}_\vartheta\left[X_1\right] + \mathbb{E}_\vartheta\left[X_1\right]^2 - \mathbb{E}_\vartheta\left[ X_1\right]^2 - \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] \right)  \\
&= \frac{n}{n-1} \left(\mathbb{VAR}_\vartheta\left[X_1\right] - \frac{1}{n} \mathbb{VAR}_\vartheta\left[ X\right] \right)  \\
&= \frac{n}{n-1}\mathbb{VAR}_\vartheta\left[X_1\right] \left( 1- \frac{1}{n}  \right)  \\
&= \frac{n}{n-1} \frac{n-1}{n} \mathbb{VAR}_\vartheta\left[X_1\right]   \\
&= \mathbb{VAR}_\vartheta\left[ X_1\right]  \\
\end{split}
$$

#### [[bias]]


$$
\begin{split}
\mathbb{B}[M] 
&= \mathbb{E}_\vartheta[M] - m(\vartheta) \\
&= \mathbb{E}_\vartheta\left[\frac{1}{n} \sum_{i=1}^n X_i\right] -  \mathbb{E}_\vartheta[X_1] \\
&= \frac{n}{n}  \mathbb{E}_\vartheta\left[  X_1\right] -  \mathbb{E}_\vartheta[X_1] = 0 \\
\end{split}
$$
$$
\begin{split}
\mathbb{B}[V] 
&= \mathbb{E}_\vartheta[V] - v(\vartheta) \\
&=  \mathbb{VAR}_\vartheta\left[ X_1\right]  -  \mathbb{VAR}_\vartheta[X_1] \\
&=  0 \\

\end{split}
$$


_____________

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself

$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$


### product probability space
- given the [[probability space|probability spaces]] $(\Omega_1, \mathcal{A}_1, \mathbb{P}_1)$ and $(\Omega_2, \mathcal{A}_2, \mathbb{P}_2)$
- we can construct a [[product probability space]] $(\Omega_1 \times \Omega_2, \mathcal{A}_1  \otimes \mathcal{A}_2 , \mathbb{P}_1 \otimes \mathbb{P}_2)$

$$
\mathcal{A}_1  \otimes \mathcal{A}_2 = \{A_1 \times A_2 : A_1 \in \mathcal{A}_1, A_2 \in \mathcal{A}_2\}
$$

$$
\begin{split}
\mathbb{P}_1 \otimes \mathbb{P}_2=\mathbb{P}(A_1 \times A_2) = \mathbb{P}(A_1)\mathbb{P}(A_2)
\end{split}
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 



### statistics
- (unknown) mapping from the observation to a property of the assumed underlaying [[distribution]] that helps to extract information about the underlaying randomness
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$ and a [[measurable space]] $\left(\Omega,\mathcal{A} \right)$
- a [[random variable]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ is called a [[statistics]]
- $\Omega$ can be interpreted is a space of characteristics of the [[probability measure]] $\mathbb{P}_\theta$
- $S$ consits of two components: a deterministic [[function]] $\tau: \Theta \to \Omega$ that extracts a property from the paramterized [[distribution]] $\mathbb{P}_\vartheta$ and the paramter approximation from the observation $\mathfrak{X} \to \Theta$ such that the [[distribution]] $\mathbb{P}_\vartheta$ describes an observation $X \in \mathfrak{X}$ best

$$
S(X \in \mathfrak{X}) = \tau\left(\vartheta(X)\right)
$$

#### deterministic [[function]] $\tau: \Theta \to \Omega$
- extracts a characteristics from the parameterized [[distribution]] $\mathbb{P}_\vartheta$ (given the paramter [[set]] $\vartheta$)
- this can for example be the [[expectation]]
$$
\tau(\vartheta) = \mathbb{E}_\vartheta[X] = \sum_{\text{all }x} x \cdot \mathbb{P}_\vartheta (X = x)
$$
- or this can be the paramters themselfs: in this case  $\tau: \Theta \to \Theta$ is the [[identity function]]
$$
\tau(\vartheta) = \vartheta
$$

#### mapping from the obervations $\mathfrak{X}$ to the [[parameter space]] $\Theta$
- derrive the parameter [[set]] $\vartheta \in \Theta$ from an observation $X \in \mathfrak{X}$ such that the [[distribution]] $\mathbb{P}_\vartheta$ describes the observation $X$ best
- $\vartheta \in \Theta$ is a [[random variable]] because its is calculated based on the observation $X$ which is a random sample and this subject to randomness
$$
\vartheta(X) \in \Theta
$$
### statistical estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and an [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ 
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is a [[function]] that approximates the [[statistics]] $S$ directly without nesserily approximation the parameters $\vartheta \in \Theta$ of the [[distribution]] $\mathbb{P}_\vartheta$ first
- thus $T: \mathfrak{X} \to \Omega$ estimates a property of the assumed [[distribution]] $\mathbb{P}_\vartheta$ based on an observation $X \in \mathfrak{X}$
- common examples for the property are the [[expectation]] $T(X)=\mathbb{E}_{Y \sim \mathbb{P}_\vartheta(X)}[Y]$ or the model parameters $T(X)=\vartheta \in \Theta$

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

Tags: mathematics statistics
<!--ID: 1719305080446-->
END