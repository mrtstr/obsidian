### statistical estimator
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \theta \in \Theta)$ and an [[statistics]] $S: \left(\mathfrak{X}, \mathcal{L}\right) \to \left(\Omega,\mathcal{A} \right)$ 
- a [[statistical estimator]] $T: \mathfrak{X} \to \Omega$ is a [[function]] that approximates the [[statistics]] $S$ directly without nesserily approximation the parameters $\vartheta \in \Theta$ of the [[distribution]] $\mathbb{P}_\vartheta$ first
- thus $T: \mathfrak{X} \to \Omega$ estimates a property of the assumed [[distribution]] $\mathbb{P}_\vartheta$ based on an observation $X \in \mathfrak{X}$
- common examples for the property are the [[expectation]] $T(X)=\mathbb{E}_{Y \sim \mathbb{P}_\vartheta(X)}[Y]$ or the model parameters $T(X)=\vartheta \in \Theta$



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





