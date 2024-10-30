## consistency criteria
### $n \cdot MSE_\vartheta(\hat \vartheta)$ is bounded $\Rightarrow$ $\hat \vartheta$ is $\sqrt{n}$ consitent

$$
n \cdot MSE_\vartheta(\hat \vartheta) = \mathcal{O}_p(1) \Rightarrow \sqrt{n} (\hat \vartheta - \vartheta) = \mathcal{O}_p(1)
$$
#### proof

$$
\begin{split}
\mathbb{P}\left(\hat\vartheta - \vartheta \geq \epsilon\right) 
&\leq \frac{1}{\epsilon^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
\mathbb{P}\left(\hat\vartheta - \vartheta \geq \frac{C}{\sqrt{n}}\right) 
&\leq \frac{1}{\left(\frac{C}{\sqrt{n}}\right)^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
\mathbb{P}\left(\sqrt{n}(\hat\vartheta - \vartheta) \geq C\right) 
&\leq \frac{n}{C^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
\mathbb{P}\left(\sqrt{n}(\hat\vartheta - \vartheta) \geq C\right) 
&\leq \frac{n \cdot MSE_\vartheta(\hat \vartheta)}{C^2}  \\
\end{split}
$$

- for since $n \cdot MSE_\vartheta(\hat \vartheta)$ is bounded by a constant for every $\epsilon$ we can make $C$ big enough for $\frac{n \cdot MSE_\vartheta(\hat \vartheta)}{C^2}$ to be smaller


### $n \cdot \mathbb{VAR}_\vartheta(\hat \vartheta))$ and $\sqrt{n} \cdot \mathbb{B}_\vartheta(\hat \vartheta)$ are bounded $\Rightarrow$ $\hat \vartheta$ is $\sqrt{n}$ consitent

$$
\begin{split}
&n \cdot \mathbb{VAR}_\vartheta(\hat \vartheta)= \mathcal{O}_p(1) \land \sqrt{n} \cdot \mathbb{B}_\vartheta(\hat \vartheta)= \mathcal{O}_p(1) \\
\Rightarrow &\sqrt{n} (\hat \vartheta - \vartheta) = \mathcal{O}_p(1)
\end{split}
$$

#### proof

$$
\begin{split}
\sqrt{n} (\hat \vartheta - \vartheta) 
&= \sqrt{n} \left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) - \sqrt{n}\left(\mathbb{E}_\vartheta\left[\hat  \vartheta\right] - \vartheta \right) \\
&= \sqrt{n} \left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) - \sqrt{n}\mathbb{B}_\vartheta\left[\hat  \vartheta\right]  \\
&= \sqrt{n} \left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) - \mathcal{O}(1) \\
\end{split}
$$

$$
\begin{split}
\mathbb{P}\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right] \geq \epsilon\right) 
&\leq \frac{1}{\epsilon^2}\mathbb{E}_\vartheta\left[\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right)^2\right] \\
&\leq \frac{\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{\epsilon^2}\\
\mathbb{P}\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right] \geq \frac{C}{\sqrt{n}}\right) 
&\leq \frac{\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{\frac{C^2}{\sqrt{n}^2}}\\
\mathbb{P}\left(\sqrt{n}\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) \geq C\right) 
&\leq \frac{n\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{C^2}\\
\end{split}
$$

- for since $n\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]$ is bounded by a constant for every $\epsilon$ we can make $C$ big enough for $\frac{n\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{C^2}$ to be smaller


### $MSE_\vartheta(\hat \vartheta) \to 0$ $\Rightarrow$ $\hat \vartheta$ is consitent

$$
MSE_\vartheta(\hat \vartheta) = \mathcal{o}(1) \Rightarrow \hat \vartheta - \vartheta = \mathcal{o}_p(1)
$$

#### proof

$$
\begin{split}
\mathbb{P}\left(\hat\vartheta - \vartheta \geq \epsilon\right) 
&\leq \frac{1}{\epsilon^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
&\leq \frac{1}{\epsilon^2} MSE(\hat\vartheta) \\
\end{split}
$$
- since $MSE(\hat\vartheta)$ goes to zero $\frac{1}{\epsilon^2} MSE(\hat\vartheta)$ also goes to zero for every epsilon


### $\mathbb{VAR}_\vartheta(\hat \vartheta) + |\mathbb{B}_\vartheta(\hat \vartheta)| \to 0$ $\Rightarrow$ $\hat \vartheta$ is consitent


$$
\mathbb{VAR}_\vartheta(\hat \vartheta) + |\mathbb{B}_\vartheta(\hat \vartheta)| = \mathcal{o}_p(1) \Rightarrow \hat \vartheta - \vartheta = \mathcal{o}_p(1)
$$


# --------------------
![[chebyshev markov inequality#markov inequality]]

![[estimator consitency#estimator consitency]]

![[estimator consitency#$ sqrt{n}$ consitency]]


![[stochasic landau notation#stochasic landau notation]]
# anki

START
Basic
4 [[estimator consitency]] criteria (without proof)

Back: 

## consistency criteria
### $n \cdot MSE_\vartheta(\hat \vartheta)$ is bounded $\Rightarrow$ $\hat \vartheta$ is $\sqrt{n}$ consitent

$$
n \cdot MSE_\vartheta(\hat \vartheta) = \mathcal{O}_p(1) \Rightarrow \sqrt{n} (\hat \vartheta - \vartheta) = \mathcal{O}_p(1)
$$
#### proof

$$
\begin{split}
\mathbb{P}\left(\hat\vartheta - \vartheta \geq \epsilon\right) 
&\leq \frac{1}{\epsilon^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
\mathbb{P}\left(\hat\vartheta - \vartheta \geq \frac{C}{\sqrt{n}}\right) 
&\leq \frac{1}{\left(\frac{C}{\sqrt{n}}\right)^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
\mathbb{P}\left(\sqrt{n}(\hat\vartheta - \vartheta) \geq C\right) 
&\leq \frac{n}{C^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
\mathbb{P}\left(\sqrt{n}(\hat\vartheta - \vartheta) \geq C\right) 
&\leq \frac{n \cdot MSE_\vartheta(\hat \vartheta)}{C^2}  \\
\end{split}
$$

- for since $n \cdot MSE_\vartheta(\hat \vartheta)$ is bounded by a constant for every $\epsilon$ we can make $C$ big enough for $\frac{n \cdot MSE_\vartheta(\hat \vartheta)}{C^2}$ to be smaller


### $n \cdot \mathbb{VAR}_\vartheta(\hat \vartheta))$ and $\sqrt{n} \cdot \mathbb{B}_\vartheta(\hat \vartheta)$ are bounded $\Rightarrow$ $\hat \vartheta$ is $\sqrt{n}$ consitent

$$
\begin{split}
&n \cdot \mathbb{VAR}_\vartheta(\hat \vartheta)= \mathcal{O}_p(1) \land \sqrt{n} \cdot \mathbb{B}_\vartheta(\hat \vartheta)= \mathcal{O}_p(1) \\
\Rightarrow &\sqrt{n} (\hat \vartheta - \vartheta) = \mathcal{O}_p(1)
\end{split}
$$

#### proof

$$
\begin{split}
\sqrt{n} (\hat \vartheta - \vartheta) 
&= \sqrt{n} \left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) - \sqrt{n}\left(\mathbb{E}_\vartheta\left[\hat  \vartheta\right] - \vartheta \right) \\
&= \sqrt{n} \left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) - \sqrt{n}\mathbb{B}_\vartheta\left[\hat  \vartheta\right]  \\
&= \sqrt{n} \left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) - \mathcal{O}(1) \\
\end{split}
$$

$$
\begin{split}
\mathbb{P}\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right] \geq \epsilon\right) 
&\leq \frac{1}{\epsilon^2}\mathbb{E}_\vartheta\left[\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right)^2\right] \\
&\leq \frac{\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{\epsilon^2}\\
\mathbb{P}\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right] \geq \frac{C}{\sqrt{n}}\right) 
&\leq \frac{\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{\frac{C^2}{\sqrt{n}^2}}\\
\mathbb{P}\left(\sqrt{n}\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) \geq C\right) 
&\leq \frac{n\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{C^2}\\
\end{split}
$$

- for since $n\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]$ is bounded by a constant for every $\epsilon$ we can make $C$ big enough for $\frac{n\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{C^2}$ to be smaller


### $MSE_\vartheta(\hat \vartheta) \to 0$ $\Rightarrow$ $\hat \vartheta$ is consitent

$$
MSE_\vartheta(\hat \vartheta) = \mathcal{o}(1) \Rightarrow \hat \vartheta - \vartheta = \mathcal{o}_p(1)
$$

#### proof

$$
\begin{split}
\mathbb{P}\left(\hat\vartheta - \vartheta \geq \epsilon\right) 
&\leq \frac{1}{\epsilon^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
&\leq \frac{1}{\epsilon^2} MSE(\hat\vartheta) \\
\end{split}
$$
- since $MSE(\hat\vartheta)$ goes to zero $\frac{1}{\epsilon^2} MSE(\hat\vartheta)$ also goes to zero for every epsilon


### $\mathbb{VAR}_\vartheta(\hat \vartheta) + |\mathbb{B}_\vartheta(\hat \vartheta)| \to 0$ $\Rightarrow$ $\hat \vartheta$ is consitent


$$
\mathbb{VAR}_\vartheta(\hat \vartheta) + |\mathbb{B}_\vartheta(\hat \vartheta)| = \mathcal{o}_p(1) \Rightarrow \hat \vartheta - \vartheta = \mathcal{o}_p(1)
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
<!--ID: 1729346313390-->
END


START
Basic
proof for the following
- $n \cdot MSE_\vartheta(\hat \vartheta)$ is bounded $\Rightarrow$ $\hat \vartheta$ is $\sqrt{n}$ consitent

Back: 


### $n \cdot MSE_\vartheta(\hat \vartheta)$ is bounded $\Rightarrow$ $\hat \vartheta$ is $\sqrt{n}$ consitent

$$
n \cdot MSE_\vartheta(\hat \vartheta) = \mathcal{O}_p(1) \Rightarrow \sqrt{n} (\hat \vartheta - \vartheta) = \mathcal{O}_p(1)
$$
#### proof

$$
\begin{split}
\mathbb{P}\left(\hat\vartheta - \vartheta \geq \epsilon\right) 
&\leq \frac{1}{\epsilon^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
\mathbb{P}\left(\hat\vartheta - \vartheta \geq \frac{C}{\sqrt{n}}\right) 
&\leq \frac{1}{\left(\frac{C}{\sqrt{n}}\right)^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
\mathbb{P}\left(\sqrt{n}(\hat\vartheta - \vartheta) \geq C\right) 
&\leq \frac{n}{C^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
\mathbb{P}\left(\sqrt{n}(\hat\vartheta - \vartheta) \geq C\right) 
&\leq \frac{n \cdot MSE_\vartheta(\hat \vartheta)}{C^2}  \\
\end{split}
$$

- for since $n \cdot MSE_\vartheta(\hat \vartheta)$ is bounded by a constant for every $\epsilon$ we can make $C$ big enough for $\frac{n \cdot MSE_\vartheta(\hat \vartheta)}{C^2}$ to be smaller


__________________

### markov inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{E}\left[|X|^r\right] \geq \epsilon^r \cdot \mathbb{P}\left(|X| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[|X|^r\right] 
&= \int_{-\infty}^{0} (-x)^r f_X(x) \mathrm{d} x^r + \int_{0}^{\infty} x f_X(x) \mathrm{d} x \\
&= \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{-\epsilon}^{0} (-x)^r f_X(x) \mathrm{d} x 
+ \int_{0}^{\epsilon} x^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} \epsilon^r f_X(x) \mathrm{d} x + \int_{\epsilon}^{\infty} \epsilon^r f_X(x) \mathrm{d} x \\
&\geq \epsilon^r \cdot \mathbb{P}(|X| \geq \epsilon)\\
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
<!--ID: 1730014111658-->
END


START
Basic
proof for the following
- $n \cdot \mathbb{VAR}_\vartheta(\hat \vartheta))$ and $\sqrt{n} \cdot \mathbb{B}_\vartheta(\hat \vartheta)$ are bounded $\Rightarrow$ $\hat \vartheta$ is $\sqrt{n}$ consitent

Back: 


### $n \cdot \mathbb{VAR}_\vartheta(\hat \vartheta))$ and $\sqrt{n} \cdot \mathbb{B}_\vartheta(\hat \vartheta)$ are bounded $\Rightarrow$ $\hat \vartheta$ is $\sqrt{n}$ consitent

$$
\begin{split}
&n \cdot \mathbb{VAR}_\vartheta(\hat \vartheta)= \mathcal{O}_p(1) \land \sqrt{n} \cdot \mathbb{B}_\vartheta(\hat \vartheta)= \mathcal{O}_p(1) \\
\Rightarrow &\sqrt{n} (\hat \vartheta - \vartheta) = \mathcal{O}_p(1)
\end{split}
$$

#### proof

$$
\begin{split}
\sqrt{n} (\hat \vartheta - \vartheta) 
&= \sqrt{n} \left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) - \sqrt{n}\left(\mathbb{E}_\vartheta\left[\hat  \vartheta\right] - \vartheta \right) \\
&= \sqrt{n} \left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) - \sqrt{n}\mathbb{B}_\vartheta\left[\hat  \vartheta\right]  \\
&= \sqrt{n} \left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) - \mathcal{O}(1) \\
\end{split}
$$

$$
\begin{split}
\mathbb{P}\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right] \geq \epsilon\right) 
&\leq \frac{1}{\epsilon^2}\mathbb{E}_\vartheta\left[\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right)^2\right] \\
&\leq \frac{\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{\epsilon^2}\\
\mathbb{P}\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right] \geq \frac{C}{\sqrt{n}}\right) 
&\leq \frac{\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{\frac{C^2}{\sqrt{n}^2}}\\
\mathbb{P}\left(\sqrt{n}\left(\hat  \vartheta - \mathbb{E}_\vartheta\left[\hat  \vartheta\right]\right) \geq C\right) 
&\leq \frac{n\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{C^2}\\
\end{split}
$$

- for since $n\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]$ is bounded by a constant for every $\epsilon$ we can make $C$ big enough for $\frac{n\mathbb{VAR}_\vartheta\left[\hat  \vartheta\right]}{C^2}$ to be smaller



__________________

### markov inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{E}\left[|X|^r\right] \geq \epsilon^r \cdot \mathbb{P}\left(|X| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[|X|^r\right] 
&= \int_{-\infty}^{0} (-x)^r f_X(x) \mathrm{d} x^r + \int_{0}^{\infty} x f_X(x) \mathrm{d} x \\
&= \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{-\epsilon}^{0} (-x)^r f_X(x) \mathrm{d} x 
+ \int_{0}^{\epsilon} x^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} \epsilon^r f_X(x) \mathrm{d} x + \int_{\epsilon}^{\infty} \epsilon^r f_X(x) \mathrm{d} x \\
&\geq \epsilon^r \cdot \mathbb{P}(|X| \geq \epsilon)\\
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
<!--ID: 1730014111663-->
END


START
Basic
proof for the following
- $\mathbb{VAR}_\vartheta(\hat \vartheta) + |\mathbb{B}_\vartheta(\hat \vartheta)| \to 0$ $\Rightarrow$ $\hat \vartheta$ is consitent

Back: 


### $MSE_\vartheta(\hat \vartheta) \to 0$ $\Rightarrow$ $\hat \vartheta$ is consitent

$$
MSE_\vartheta(\hat \vartheta) = \mathcal{o}(1) \Rightarrow \hat \vartheta - \vartheta = \mathcal{o}_p(1)
$$

#### proof

$$
\begin{split}
\mathbb{P}\left(\hat\vartheta - \vartheta \geq \epsilon\right) 
&\leq \frac{1}{\epsilon^2}\mathbb{E}_\vartheta\left[(\hat\vartheta - \vartheta)^2\right] \\
&\leq \frac{1}{\epsilon^2} MSE(\hat\vartheta) \\
\end{split}
$$
- since $MSE(\hat\vartheta)$ goes to zero $\frac{1}{\epsilon^2} MSE(\hat\vartheta)$ also goes to zero for every epsilon


### $\mathbb{VAR}_\vartheta(\hat \vartheta) + |\mathbb{B}_\vartheta(\hat \vartheta)| \to 0$ $\Rightarrow$ $\hat \vartheta$ is consitent
- follows from [[variance bias trade-off]]

$$
\mathbb{VAR}_\vartheta(\hat \vartheta) + |\mathbb{B}_\vartheta(\hat \vartheta)| = \mathcal{o}_p(1) \Rightarrow \hat \vartheta - \vartheta = \mathcal{o}_p(1)
$$


__________________

### markov inequality
- given a [[random variable]] $X$ in a [[probability space]] $(\Omega, \mathcal{A}, \mathbb{P})$

$$
\forall \epsilon > 0, r>0:\mathbb{E}\left[|X|^r\right] \geq \epsilon^r \cdot \mathbb{P}\left(|X| \geq \epsilon\right)
$$
#### proof
$$
\begin{split}
\mathbb{E}\left[|X|^r\right] 
&= \int_{-\infty}^{0} (-x)^r f_X(x) \mathrm{d} x^r + \int_{0}^{\infty} x f_X(x) \mathrm{d} x \\
&= \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{-\epsilon}^{0} (-x)^r f_X(x) \mathrm{d} x 
+ \int_{0}^{\epsilon} x^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} (-x)^r f_X(x) \mathrm{d} x^r + \int_{\epsilon}^{\infty} x^r f_X(x) \mathrm{d} x \\
&\geq \int_{-\infty}^{-\epsilon} \epsilon^r f_X(x) \mathrm{d} x + \int_{\epsilon}^{\infty} \epsilon^r f_X(x) \mathrm{d} x \\
&\geq \epsilon^r \cdot \mathbb{P}(|X| \geq \epsilon)\\
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
<!--ID: 1730014111668-->
END