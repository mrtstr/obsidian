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


# -----------------

![[statistical model#statistical model]]

![[statistical estimator#statistical estimator]]


# anki


START
Basic
[[estimator variance]]
- definition
- interpretation

Back: 
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

_______________________

### statistical estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and an [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ 
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is a [[function]] that approximates the [[statistics]] $S$ directly without nesserily approximation the parameters $\vartheta \in \Theta$ of the [[distribution]] $\mathbb{P}_\vartheta$ first
- thus $T: \mathfrak{X} \to \Omega$ estimates a property of the assumed [[distribution]] $\mathbb{P}_\vartheta$ based on an observation $X \in \mathfrak{X}$
- common examples for the property are the [[expectation]] $T(X)=\mathbb{E}_{Y \sim \mathbb{P}_\vartheta(X)}[Y]$ or the model parameters $T(X)=\vartheta \in \Theta$

### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of parameters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 



Tags: mathematics statistics
<!--ID: 1719154404914-->
END