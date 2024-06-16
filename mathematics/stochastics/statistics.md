### statistics
- mapping that helps to extract information about the underlaying randomness of an observation
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


### [[statistical model]] vs [[statistics]] vs [[statistical estimator]]
- a [[statistical model]] is the framework for 
	- describing a random experiment ([[sample space]] for the oberservations $\mathfrak{X}$ with [[sigma algebra]]) 
	- providing a familiy of [[distribution|distributions]] $\mathbb{P}_\theta$ to describe the observations bested on a parameter [[set]] $\vartheta \in \Theta$ from the [[parameter space]]

- a [[statistics]] is based on a [[statistical model]] and provides a mapping from the observations to a specific characteristis of the [[distribution]]




### example
- estimate the paramter $b$ of a [[continous uniform distribution]] $f_X(x|0, b)$ based on $n$ samples
$$
f_X(x|0, b) = \frac{1}{b} \qquad \text{for } x \in [0, b]
$$
- the situation can be described with an [[statistical model#n fold statistical model|n fold statistical model]] 
- the [[sample space]] $\mathfrak{X} = [0, \infty)^n$ is the space of all possible values
- the [[parameter space]] $\Theta = (0, \infty)$ is the [[set]] of all prossible values the parameter $b$ could take
- the [[probability measure]] $\mathbb{P}_\theta = \frac{1}{b^n}$ is the n fold product of the [[continous uniform distribution]]
# -----------------------

![[statistical model#statistical model]]

![[statistical model#n fold statistical model]]

![[measurable space#measurable space]]


# anki




START
Basic
statistics
- definition
- relationship to a [[statistical model]]

Back: 

### statistics
- mapping that helps to extract information about the underlaying randomness of an observation
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


______________


### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 
Tags: mathematics statistics
<!--ID: 1718476182002-->
END


START
Basic
[[statistical model]] vs [[statistics]] vs [[statistical estimator]]

Back: 
#### difference between statistic and [[statistical model]]
- a [[statistical model]] is the framework consisting for describing a random experiment ([[sample space]] for the oberservations with [[sigma algebra]]) and a family of [[distribution|distributions]]
- the statistics is the mapping from the observations to a specific characteristis of the [[distribution]]
- often the characteristic is the [[set]] of parameters to define a [[distribution]] from the family of [[distribution|distributions]]
- in this case the statistic would map from a specific observation to a specific [[distribution]]


### statistical model
- a [[statistical model]] is a triplet $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$  
- the [[sample space]] $\mathfrak{X}$ is a [[set]] of possible observations
- the [[sigma algebra]] $\mathcal{L}$ on  $\mathfrak{X}$
- a family of [[probability measure|probability measures]] $\mathbb{P}_\theta: \mathcal{L} \to [0,1]$ with one instance for each [[set]] of paraleters $\theta$ in the [[parameter space]] $\Theta$ 
- given a [[set]] of samples $C \in \mathcal{L}$ the [[probability measure]] $\mathbb{P}_\theta(C)$ discribes the probability that samples are from a [[distribution]] that is parameterized by the paramter [[set]] $\theta$ 
Tags: mathematics statistics

### statistics
- mapping that helps to extract information about the underlaying randomness
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$ and a [[measurable space]] $\left(\Omega,\mathcal{A} \right)$
- a [[random variable]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ is called a **statistics**

#### interpretation
- $\Omega$ can be interpreted is a space of characteristics of the [[probability measure]] $\mathbb{P}_\theta$ such that there exists a mapping $\tau: \Theta \to \Omega$ from the [[parameter space]] to the [[sample space]] of the **statistics**
- often the [[sample space]] of the **statistics** is equal to the [[parameter space]] $\Omega$ and thus the [[random variable]] $S: \mathfrak{X} \to \Omega$ is mapping directy to the [[parameter space]]
- in other words we are interested in a mapping from an observation $\in \mathfrak{X}$ to a parameter [[set]] $\theta \in \Theta$ that paramterizes the [[probability measure]] $\mathbb{P}_\theta$ in order to describe the oberservation best

<!--ID: 1718476182008-->
END