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


# ---------------

![[statistical estimator#statistical estimator]]

![[statistical model#statistical model]]

![[statistics#statistics]]

# anki

START
Basic
[[bias]]
- definition
- interpretation

Back: 
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

_________________


### statistical estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and an [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ 
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is a [[function]] that approximates the [[statistics]] $S$ directly without nesserily approximation the parameters $\vartheta \in \Theta$ of the [[distribution]] $\mathbb{P}_\vartheta$ first
- thus $T: \mathfrak{X} \to \Omega$ estimates a property of the assumed [[distribution]] $\mathbb{P}_\vartheta$ based on an observation $X \in \mathfrak{X}$
- common examples for the property are the [[expectation]] $T(X)=\mathbb{E}_{Y \sim \mathbb{P}_\vartheta(X)}[Y]$ or the model parameters $T(X)=\vartheta \in \Theta$



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


### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 


Tags: mathematics statistics
<!--ID: 1718542005161-->
END