### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself


$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$

### [[expectation]] of [[n fold statistical model]]
- given an [[n fold statistical model]] $\left(\mathbb{R}^n, \mathcal{B}(\mathbb{R}^n), \mathbb{P}^{\otimes n}_{\vartheta \in \Theta}\right)$ with the following characteristics
$$
\begin{split}
m(\vartheta) &= \mathbb{E}_\vartheta[X_1] \\
v(\vartheta) &= \mathbb{VAR}_\vartheta[X_1] \\
\end{split}
$$
- the following are [[bias|unbiased]] [[statistical estimator|statistical estimators]] for $m$ and $v$
$$
\begin{split}
M &= \frac{1}{n} \sum_{i=1}^n X_i \\
V &= \frac{1}{n-1} \sum_{i=1}^n (X_i - M)^2 \\

\end{split}
$$

#### proof
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
\mathbb{E}_\vartheta[V] 
&= \mathbb{E}_\vartheta\left[\frac{1}{n-1} \sum_{i=1}^n (X_i - M)^2\right]  \\
&= \frac{n}{n-1} \mathbb{E}_\vartheta\left[  (X_1 - M)^2\right]  \\
&= \frac{n}{n-1} \left(\mathbb{E}_\vartheta\left[  X_1^2\right] + M^2- 2 \mathbb{E}_\vartheta\left[  X_1\right]M\right) \\
&= \frac{n}{n-1} \left(\mathbb{E}_\vartheta\left[  X_1^2\right] + \mathbb{E}_\vartheta\left[  X_1\right]^2- 2 \mathbb{E}_\vartheta\left[  X_1\right]^2\right) \\
&= \frac{n}{n-1} \mathbb{VAR}_\vartheta[X_1] \\
\end{split}
$$

$$
\begin{split}
\mathbb{B}[V] 
&= \mathbb{E}_\vartheta[V] - v(\vartheta) \\
&= \frac{n}{n-1} \mathbb{VAR}_\vartheta[X_1] -  \mathbb{VAR}_\vartheta[X_1] \\
&= \frac{n}{n-1} \mathbb{E}_\vartheta\left[  (X_1 - M)^2\right] -  \mathbb{VAR}_\vartheta[X_1] \\
\end{split}
$$

# -----------------

![[bias#bias]]

![[statistical model#statistical model]]


# anki
START
Basic
n fold statistical model
- defintion
- releated concept
- when is it used
Back: 

### n fold statistical model
- given a [[statistical model]] $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with $n$ samples
- the result is a [[product probability space]] between $n$ times $(\mathfrak{X}', \mathcal{L}', \mathbb{P}'_\theta: \theta \in \Theta)$ with itself

$$
(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta) = ( \mathfrak{X} \times ... \times \mathfrak{X}, \mathcal{L}' \otimes ... \otimes \mathcal{L}', \mathbb{P}'_\theta \otimes ... \otimes \mathbb{P}'_\theta: \theta \in \Theta)
$$

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



### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 
Tags: mathematics statistics
<!--ID: 1718476182020-->
END