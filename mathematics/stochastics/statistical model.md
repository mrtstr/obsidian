### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of parameters $\theta$ in the [[parameter space]] $\Theta$ 



### different kinds of [[statistical model|statistical models]]
- if the [[parameter space]] $\Theta \subseteq \mathbb{R}$ the [[statistical model]] is a **one parameter model**
- if the [[sample space]] $\mathfrak{X}$ is [[discrete probability space|discrete]] the [[statistical model]] is a **discrete model**


### a statistical model of a random variable
unfinished
- given a [[random variable]] $X: \Omega \to \mathfrak{X}$ from a [[probability space]] $\left(\Omega, \mathcal{A} , \mathbb{P}\right)$ to a [[probability space]] $\left(\mathfrak{X}, \mathcal{L}, \mathcal{P}^X \right)$
- the [[statistical model]] of $X$ is the triplet $\left(\mathfrak{X}, \mathcal{L}, \mathcal{P}^X_\theta: \vartheta \in \Theta \right)$
- the true [[distribution]] $\mathcal{P}^X$ might or might not be in the [[set]] $\left\{\mathcal{P}^X_\vartheta: \vartheta \in \Theta \right\}$ 
- $\vartheta$ is a constant property of the [[distribution]] $\mathcal{P}^X$ and can be erstimated by a [[statistical estimator]] $\hat \vartheta: \mathfrak{X} \to \Theta$ 
- before we were intersted in estimating a [[statistics]] that is based on a property $\tau(\vartheta)$ of the
- in this approach  $\vartheta = \tau(\vartheta)$

#### example 
- $\Omega \subset \mathbb{R}$ with $X_1, ..., X_n \sim f_X$ i.i.d. from a [[probability density function (PDF)]] that is based on a [[probability measure]] $\mathbb{P}$ 
- the following [[random variable]] $X \in \left(\mathfrak{X} \subset \mathbb{R}, \mathcal{L}, \mathcal{P}^X \right)$ with a [[distribution]] $\mathcal{P}^X$ is modeled with the [[statistical model]] $\left(\mathfrak{X}, \mathcal{L}, \mathcal{P}^X_\theta: \theta \in \Theta = \mathbb{R} \right)$

$$
\theta = \mathbb{E}[X]
$$

- the following is a [[statistical estimator]] $\hat X_n: \mathfrak{X}^{\otimes n} \to \Theta$ estimates $\theta$ based on the $n$ observations

$$
\hat{\theta} = \hat X_n = \frac{1}{n} \sum X_i
$$

$$
\mathbb{E}_\theta\left[\hat \theta\left(X_1, ..., X_n\right)\right] = \theta
$$

$$
\begin{split}
\mathbb{B}_T[\vartheta] 
&= \mathbb{E}_\vartheta[T] - \tau(\vartheta) \\
&= \mathbb{E}_{X \sim \mathbb{P}_\vartheta}\left[T(X)\right] - \tau(\vartheta) \\
\end{split}
$$

$$
S(X \in \mathfrak{X}) = \tau\left(\vartheta(X)\right)
$$

# -----------------
![[random variable#random variable]]

![[statistics#statistics]]

![[product probability space#product probability space]]




START
Basic
[[statistical model]]
- defintion
- how can the [[probability measure]] be interpreted
Back: 
### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 

Tags: mathematics statistics
<!--ID: 1718476182014-->
END


START
Basic
when to use an n fold [[statistical model]] and when to use a normal [[statistical model]]?
Back: 
the n fold model is needed when there are multiple samples to estimate the parameters from

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself

$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 

_____________

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



Tags: mathematics statistics
<!--ID: 1718476182017-->
END

