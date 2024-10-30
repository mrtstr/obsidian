### estimator consitency
- given a [[statistical estimator]] $T_n$ for a chracateristics $\tau(\vartheta)$
- $T_n$ is consistence if it [[convergence in probability|converges in probability]] against $\tau(\vartheta)$

$$
\begin{split}
&\forall \vartheta \in \Theta: T_n \to_\mathbb{P} \tau(\vartheta) \\
&\Leftrightarrow \\
&\forall \vartheta \in \Theta: 
\forall \epsilon > 0:  
\forall \delta > 0: 
\exists N: \forall n > N:
\mathbb{P}_\vartheta\left(|T_n - \tau(\vartheta) | \geq \delta\right) < \epsilon 
\end{split}
$$

- the [[estimator consitency]] is about how the [[statistical estimator]] behaves with infinite sample size

#### landau notation
- the following definition is equivalent to the definition of [[estimator consitency]] in [[stochasic landau notation]]
- it means that the difference between the [[statistical estimator]] and the true value [[convergence in probability|converges in probability]] against zero

$$
\begin{split}
T_n - \tau(\vartheta) =  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
\hat \vartheta - \vartheta =  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
\end{split}
$$

### $\sqrt{n}$ consitency
- given a [[statistical estimator]] $T_n$ for a chracateristics $\tau(\vartheta)$
- $T_n$ is consistence if it [[convergence in probability|converges in probability]] against $\tau(\vartheta)$

$$
\forall \vartheta \in \Theta: 
\forall \epsilon > 0:  
\exists \delta > 0: 
\exists N: \forall n > N:
\exists C > 0:  
\mathbb{P}_\vartheta\left(\sqrt{n}||T_n - \tau(\vartheta)||
 \geq C \right) \leq \epsilon
$$

- or in [[stochasic landau notation]]:

$$
\begin{split}
\sqrt{n}\left(T_n  - \tau(\vartheta) \right)=  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
T_n = \tau(\vartheta) + \mathcal{o}_{\mathbb{P}_\vartheta}\left(n^{-\frac{1}{2}}\right) \\
\end{split}
$$




### relationship to bias
- both are not equivalent: [[statistical estimator|estimators]] can be [[bias|biased]] and [[estimator consitency|consitent]] and [[bias|unbiased]] and [[estimator consitency|inconsitent]] 
- the [[estimator consitency]] is about infinite sample size while the [[bias]] is about the average result when doing the experiment infinite times

#### [[bias|unbiased]] and [[estimator consitency|inconsitent]] 
- $X_1, ..., X_n$ i.i.d with $\tau(\vartheta) = \mathbb{E_\vartheta}[X_i]$

$$
\begin{split}
T_n &=  X_n\\
\mathbb{B}[T_n] 
&=  \mathbb{E}[T_n] - \tau(\vartheta) \\
&=  \mathbb{E}[X_n] - \mathbb{E_\vartheta}[X_i] = 0 \\
\lim_{n \to \infty}\mathbb{P}_\vartheta\left(|T_n - \tau(\vartheta) | \geq \epsilon\right) &= \mathbb{P}_\vartheta\left(|X_n - \mathbb{E_\vartheta}[X_i] | \geq \epsilon\right) > 0
\end{split}
$$

#### [[bias|biased]] and [[estimator consitency|consitent]] 

$$
\begin{split}
T_n
&= \frac{1}{n} + \frac{1}{n} \sum_{i \in [n]} X_i\\
\end{split}
$$

![[bias#bias]]


### relationship to bias
![[bias#asymptotically bias]]

# -------------

![[stochasic landau notation#stochasic landau notation]]

![[convergence in probability#convergence in probability]]

![[statistical estimator#statistical estimator]]

![[statistics#statistics]]

# anki

START
Basic
[[estimator consitency]]
- definition
- definition in [[stochasic landau notation]] (why is it equivalent?)
- interpretation

Back: 
### estimator consitency
- given a [[statistical estimator]] $T_n$ for a chracateristics $\tau(\vartheta)$
- $T_n$ is consistence if it [[convergence in probability|converges in probability]] against $\tau(\vartheta)$

$$
\begin{split}
&\forall \vartheta \in \Theta: T_n \to_\mathbb{P} \tau(\vartheta) \\
&\Leftrightarrow \\
&\forall \vartheta \in \Theta: 
\forall \epsilon > 0:  
\forall \delta > 0: 
\exists N: \forall n > N:
\mathbb{P}_\vartheta\left(|T_n - \tau(\vartheta) | \geq \delta\right) < \epsilon 
\end{split}
$$

- the [[estimator consitency]] is about how the [[statistical estimator]] behaves with infinite sample size

#### landau notation
- the following definition is equivalent to the definition of [[estimator consitency]] in [[stochasic landau notation]]
- it means that the difference between the [[statistical estimator]] and the true value [[convergence in probability|converges in probability]] against zero

$$
\begin{split}
T_n - \tau(\vartheta) =  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
\hat \vartheta - \vartheta =  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
\end{split}
$$

__________________

### convergence in probability
- given a sequence of [[random variable]] $\{X_n\}$
- $X_n$ is converging against a [[random variable]] $X$ is the following is true

$$
\forall \epsilon > 0: \lim_{n \to \infty}\mathbb{P}\left(|T_n - \tau(\vartheta) | \geq \epsilon\right)
$$

#### equivalent statements

$$
\mathbb{P}(X_n \leq x) \to \mathbb{P}(X \leq x)
$$

$$
\mathbb{E}[X_n] \to \mathbb{E}[X_n]
$$

### stochasic landau notation

#### big O: stochstic bounded
- means that the term $\left|\frac{X_n}{a_n}\right|$ is bounded thus there is a constant value $M$ that is lager alomst surely

$$
\begin{split}
&X_n = \mathcal{O}_p(a_n) \\
&\Leftrightarrow  \exists M > 0 : \lim_{n \to \infty} \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > M\right) =0\\
&\Leftrightarrow  \exists M > 0: \forall \varepsilon > 0: N > 0: \forall n > N: \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > M\right) \leq \varepsilon \\
\end{split}
$$

- case $X_n = \mathcal{O}_p(1)$ means that $X_n$ is bounded by a constant alomst surely

#### small o
- means that the probability of $\left|\frac{X_n}{a_n}\right|$ [[convergence in probability|converges in probability]] to zero 

$$
\begin{split}
&X_n = \mathcal{o}_p(a_n) \\
&\Leftrightarrow \forall \delta > 0: \lim_{n \to \infty} \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > \delta \right) = 0 \\
&\Leftrightarrow \forall \delta > 0: \forall \epsilon > 0: \exists N \in \mathbb{N} : \forall n > N: \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > \delta\right) \leq \varepsilon \\
\end{split}
$$



Tags: mathematics statistics WS2425
<!--ID: 1729346313385-->
END


START
Basic
$\sqrt{n}$  [[estimator consitency]]
- definition + definition in [[estimator consitency]]

Back: 
### $\sqrt{n}$ consitency
- given a [[statistical estimator]] $T_n$ for a chracateristics $\tau(\vartheta)$
- $T_n$ is consistence if it [[convergence in probability|converges in probability]] against $\tau(\vartheta)$

$$
\forall \vartheta \in \Theta: 
\forall \epsilon > 0:  
\exists \delta > 0: 
\exists N: \forall n > N:
\exists C > 0:  
\mathbb{P}_\vartheta\left(\sqrt{n}||T_n - \tau(\vartheta)||
 \geq C \right) \leq \epsilon
$$

- or in [[stochasic landau notation]]:

$$
\begin{split}
\sqrt{n}\left(T_n  - \tau(\vartheta) \right)=  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
T_n = \tau(\vartheta) + \mathcal{o}_{\mathbb{P}_\vartheta}\left(n^{-\frac{1}{2}}\right) \\
\end{split}
$$



### estimator consitency
- given a [[statistical estimator]] $T_n$ for a chracateristics $\tau(\vartheta)$
- $T_n$ is consistence if it [[convergence in probability|converges in probability]] against $\tau(\vartheta)$

$$
\begin{split}
&\forall \vartheta \in \Theta: T_n \to_\mathbb{P} \tau(\vartheta) \\
&\Leftrightarrow \\
&\forall \vartheta \in \Theta: 
\forall \epsilon > 0:  
\forall \delta > 0: 
\exists N: \forall n > N:
\mathbb{P}_\vartheta\left(|T_n - \tau(\vartheta) | \geq \delta\right) < \epsilon 
\end{split}
$$

- the [[estimator consitency]] is about how the [[statistical estimator]] behaves with infinite sample size

#### landau notation
- the following definition is equivalent to the definition of [[estimator consitency]] in [[stochasic landau notation]]
- it means that the difference between the [[statistical estimator]] and the true value [[convergence in probability|converges in probability]] against zero

$$
\begin{split}
T_n - \tau(\vartheta) =  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
\hat \vartheta - \vartheta =  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
\end{split}
$$

__________________

### convergence in probability
- given a sequence of [[random variable]] $\{X_n\}$
- $X_n$ is converging against a [[random variable]] $X$ is the following is true

$$
\forall \epsilon > 0: \lim_{n \to \infty}\mathbb{P}\left(|T_n - \tau(\vartheta) | \geq \epsilon\right)
$$

#### equivalent statements

$$
\mathbb{P}(X_n \leq x) \to \mathbb{P}(X \leq x)
$$

$$
\mathbb{E}[X_n] \to \mathbb{E}[X_n]
$$

### stochasic landau notation

#### big O: stochstic bounded
- means that the term $\left|\frac{X_n}{a_n}\right|$ is bounded thus there is a constant value $M$ that is lager alomst surely

$$
\begin{split}
&X_n = \mathcal{O}_p(a_n) \\
&\Leftrightarrow  \exists M > 0 : \lim_{n \to \infty} \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > M\right) =0\\
&\Leftrightarrow  \exists M > 0: \forall \varepsilon > 0: N > 0: \forall n > N: \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > M\right) \leq \varepsilon \\
\end{split}
$$

- case $X_n = \mathcal{O}_p(1)$ means that $X_n$ is bounded by a constant alomst surely

#### small o
- means that the probability of $\left|\frac{X_n}{a_n}\right|$ [[convergence in probability|converges in probability]] to zero 

$$
\begin{split}
&X_n = \mathcal{o}_p(a_n) \\
&\Leftrightarrow \forall \delta > 0: \lim_{n \to \infty} \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > \delta \right) = 0 \\
&\Leftrightarrow \forall \delta > 0: \forall \epsilon > 0: \exists N \in \mathbb{N} : \forall n > N: \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > \delta\right) \leq \varepsilon \\
\end{split}
$$


Tags: mathematics statistics WS2425
<!--ID: 1729346313388-->
END




START
Basic
[[estimator consitency]] and [[bias]] relationship
- interpretation
- with proof

Back: 
### relationship to bias
- both are not equivalent: [[statistical estimator|estimators]] can be [[bias|biased]] and [[estimator consitency|consitent]] and [[bias|unbiased]] and [[estimator consitency|inconsitent]] 
- the [[estimator consitency]] is about infinite sample size while the [[bias]] is about the average result when doing the experiment infinite times

#### [[bias|unbiased]] and [[estimator consitency|inconsitent]] 
- $X_1, ..., X_n$ i.i.d with $\tau(\vartheta) = \mathbb{E_\vartheta}[X_i]$

$$
\begin{split}
T_n &=  X_n\\
\mathbb{B}[T_n] 
&=  \mathbb{E}[T_n] - \tau(\vartheta) \\
&=  \mathbb{E}[X_n] - \mathbb{E_\vartheta}[X_i] = 0 \\
\lim_{n \to \infty}\mathbb{P}_\vartheta\left(|T_n - \tau(\vartheta) | \geq \epsilon\right) &= \mathbb{P}_\vartheta\left(|X_n - \mathbb{E_\vartheta}[X_i] | \geq \epsilon\right) > 0
\end{split}
$$

#### [[bias|biased]] and [[estimator consitency|consitent]] 

$$
\begin{split}
T_n
&= \frac{1}{n} + \frac{1}{n} \sum_{i \in [n]} X_i\\
\end{split}
$$

### estimator consitency
- given a [[statistical estimator]] $T_n$ for a chracateristics $\tau(\vartheta)$
- $T_n$ is consistence if it [[convergence in probability|converges in probability]] against $\tau(\vartheta)$

$$
\begin{split}
&\forall \vartheta \in \Theta: T_n \to_\mathbb{P} \tau(\vartheta) \\
&\Leftrightarrow \\
&\forall \vartheta \in \Theta: 
\forall \epsilon > 0:  
\forall \delta > 0: 
\exists N: \forall n > N:
\mathbb{P}_\vartheta\left(|T_n - \tau(\vartheta) | \geq \delta\right) < \epsilon 
\end{split}
$$

- the [[estimator consitency]] is about how the [[statistical estimator]] behaves with infinite sample size

#### landau notation
- the following definition is equivalent to the definition of [[estimator consitency]] in [[stochasic landau notation]]
- it means that the difference between the [[statistical estimator]] and the true value [[convergence in probability|converges in probability]] against zero

$$
\begin{split}
T_n - \tau(\vartheta) =  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
\hat \vartheta - \vartheta =  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
\end{split}
$$

__________________

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
- the [[expectation]] of the [[statistical estimator]] $\mathbb{E}_\vartheta[T]$ is the approximation of the [[statistics]] $\tau(\vartheta)$ is the mean approximation when calculating over an infinite amount of sample sets (not eqaul to an infinitely large sample let)
→ the [[bias]] the mean error when doing the process infinite times


### estimator consitency
- given a [[statistical estimator]] $T_n$ for a chracateristics $\tau(\vartheta)$
- $T_n$ is consistence if it [[convergence in probability|converges in probability]] against $\tau(\vartheta)$

$$
\begin{split}
&\forall \vartheta \in \Theta: T_n \to_\mathbb{P} \tau(\vartheta) \\
&\Leftrightarrow \\
&\forall \vartheta \in \Theta: 
\forall \epsilon > 0:  
\forall \delta > 0: 
\exists N: \forall n > N:
\mathbb{P}_\vartheta\left(|T_n - \tau(\vartheta) | \geq \delta\right) < \epsilon 
\end{split}
$$

- the [[estimator consitency]] is about how the [[statistical estimator]] behaves with infinite sample size

#### landau notation
- the following definition is equivalent to the definition of [[estimator consitency]] in [[stochasic landau notation]]
- it means that the difference between the [[statistical estimator]] and the true value [[convergence in probability|converges in probability]] against zero

$$
\begin{split}
T_n - \tau(\vartheta) =  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
\hat \vartheta - \vartheta =  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
\end{split}
$$


### convergence in probability
- given a sequence of [[random variable]] $\{X_n\}$
- $X_n$ is converging against a [[random variable]] $X$ is the following is true

$$
\forall \epsilon > 0: \lim_{n \to \infty}\mathbb{P}\left(|T_n - \tau(\vartheta) | \geq \epsilon\right)
$$

#### equivalent statements

$$
\mathbb{P}(X_n \leq x) \to \mathbb{P}(X \leq x)
$$

$$
\mathbb{E}[X_n] \to \mathbb{E}[X_n]
$$

### stochasic landau notation

#### big O: stochstic bounded
- means that the term $\left|\frac{X_n}{a_n}\right|$ is bounded thus there is a constant value $M$ that is lager alomst surely

$$
\begin{split}
&X_n = \mathcal{O}_p(a_n) \\
&\Leftrightarrow  \exists M > 0 : \lim_{n \to \infty} \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > M\right) =0\\
&\Leftrightarrow  \exists M > 0: \forall \varepsilon > 0: N > 0: \forall n > N: \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > M\right) \leq \varepsilon \\
\end{split}
$$

- case $X_n = \mathcal{O}_p(1)$ means that $X_n$ is bounded by a constant alomst surely

#### small o
- means that the probability of $\left|\frac{X_n}{a_n}\right|$ [[convergence in probability|converges in probability]] to zero 

$$
\begin{split}
&X_n = \mathcal{o}_p(a_n) \\
&\Leftrightarrow \forall \delta > 0: \lim_{n \to \infty} \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > \delta \right) = 0 \\
&\Leftrightarrow \forall \delta > 0: \forall \epsilon > 0: \exists N \in \mathbb{N} : \forall n > N: \mathbb{P}\left(\left|\frac{X_n}{a_n}\right| > \delta\right) \leq \varepsilon \\
\end{split}
$$


Tags: mathematics statistics WS2425
<!--ID: 1729346313393-->
END