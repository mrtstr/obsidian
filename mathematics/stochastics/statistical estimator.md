### statistics
- mapping that helps to extract information about the underlaying randomness
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$ and a [[measurable space]] $\left(\Omega,\mathcal{A} \right)$
- a [[random variable]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ is called a **statistics**

#### interpretation
- $\Omega$ can be interpreted is a space of characteristics of the [[probability measure]] $\mathbb{P}_\theta$ such that there exists a mapping $\tau: \Theta \to \Omega$ from the [[parameter space]] to the [[sample space]] of the **statistics**
- often the [[sample space]] of the **statistics** is equal to the [[parameter space]] $\Omega$ and thus the [[random variable]] $S: \mathfrak{X} \to \Omega$ is mapping directy to the [[parameter space]]
- in other words we are interested in a mapping from an observation $\in \mathfrak{X}$ to a parameter [[set]] $\theta \in \Theta$ that paramterizes the [[probability measure]] $\mathbb{P}_\theta$ in order to describe the oberservation best

#### difference to a [[statistical model]]
- a [[statistical model]] is the framework consisting for describing a random experiment ([[sample space]] for the oberservations with [[sigma algebra]]) and a family of [[distribution|distributions]]
- the statistics is the mapping from the observations to a specific characteristis of the [[distribution]]
- often the characteristic is the [[set]] of parameters to define a [[distribution]] from the family of [[distribution|distributions]]
- in this case the statistic would map from a specific observation to a specific [[distribution]]

### estimator
- a [[function]] $T: \mathfrak{X} \to \Omega$ that approximates the [[random variable]] $S$ is called an **estimator** of $S$
- if the case of $\Omega = \Theta$ the estimator mapps directly from the [[sample space]] of the [[statistical model]] to theits [[parameter space]]

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
- interpretation

Back: 

### statistics
- mapping that helps to extract information about the underlaying randomness
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\theta: \theta \in \Theta)$ and a [[measurable space]] $\left(\Omega,\mathcal{A} \right)$
- a [[random variable]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ is called a **statistics**

#### interpretation
- $\Omega$ can be interpreted is a space of characteristics of the [[probability measure]] $\mathbb{P}_\theta$ such that there exists a mapping $\tau: \Theta \to \Omega$ from the [[parameter space]] to the [[sample space]] of the **statistics**
- often the [[sample space]] of the **statistics** is equal to the [[parameter space]] $\Omega$ and thus the [[random variable]] $S: \mathfrak{X} \to \Omega$ is mapping directy to the [[parameter space]]
- in other words we are interested in a mapping from an observation $\in \mathfrak{X}$ to a parameter [[set]] $\theta \in \Theta$ that paramterizes the [[probability measure]] $\mathbb{P}_\theta$ in order to describe the oberservation best

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
statistics
difference between a [[statistical model]] and a statistics

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