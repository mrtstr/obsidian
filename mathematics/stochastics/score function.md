### score function
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- the [[score function]] $Q_n(\vartheta)$ is the [[gradient]] with respect to the paramter vector $\vartheta$ of the [[logarithm|log]] [[likelihood function]] evaluated at a particular position $X$ (observation)


one parameter case:
$$
Q_n(\vartheta) 
= \frac{d}{d \vartheta} \ln{f_\vartheta}(X) 
= \frac{\frac{d}{d \vartheta} f_\vartheta(X)}{f_\vartheta(X)} 
= 0
$$

multi parameter case:
$$
Q_n(\vartheta) = \nabla \ln{f_\vartheta}(X) = 0
$$

#### interpretation
- $Q_n(\vartheta)$ indicates the steepness of the [[logarithm|log]] [[likelihood function]]
- how much would a parameter change impact the [[probability density function (PDF)|PDF]] ${f_\vartheta}(X)$ → how sensitive  is the model to the data
- if their multiple observations the impact of each oberservation is scaled by $\frac{1}{f_\vartheta(X)}$
- at a [[local minimum]] $Q_n(\vartheta)$ will become zero 



# ----------------

![[fisher information#fisher information]]


![[likelihood function#likelihood function]]


# anki


START
Basic
[[score function]]
- definition
- interpretation
- what does ot mean when its zero?

Back: 
### score function
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- the [[score function]] $Q_n(\vartheta)$ is the [[gradient]] with respect to the paramter vector $\vartheta$ of the [[logarithm|log]] [[likelihood function]] evaluated at a particular position $X$ (observation)


one parameter case:
$$
Q_n(\vartheta) 
= \frac{d}{d \vartheta} \ln{f_\vartheta}(X) 
= \frac{\frac{d}{d \vartheta} f_\vartheta(X)}{f_\vartheta(X)} 
= 0
$$

multi parameter case:
$$
Q_n(\vartheta) = \nabla \ln{f_\vartheta}(X) = 0
$$

#### interpretation
- $Q_n(\vartheta)$ indicates the steepness of the [[logarithm|log]] [[likelihood function]]
- how much would a parameter change impact the [[probability density function (PDF)|PDF]] ${f_\vartheta}(X)$ → how sensitive  is the model to the data
- if their multiple observations the impact of each oberservation is scaled by $\frac{1}{f_\vartheta(X)}$
- at a [[local minimum]] $Q_n(\vartheta)$ will become zero 

________________


### likelihood function
- the [[likelihood function]] is the [[probability density function (PDF)|density]] of the observed data as a function of the parameter $\vartheta \in \Theta$
- given a [[statistical model]] $(\mathfrak{X}, \mathcal{L}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ where the [[distribution]] $\mathbb{P}_\vartheta: \mathcal{L} \to [0,1]$ has a [[probability density function (PDF)]] $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$  
- for a given observation $x \in \mathfrak{X}$ the function $\varrho(x, \: \cdot \:): \Theta \to (0, \infty)$ is called the [[likelihood function]]
- the [[likelihood function]] can be interpreted as a measurment for how well a parameter [[set]] $\vartheta \in \Theta$ discribes a given observation $x \in \mathfrak{X}$

#### the [[likelihood function]] is not a [[probability density function (PDF)]]
- note that the density $\varrho: \mathfrak{X} \times \Theta \to (0,\infty)$ is normalzed when integrated over all possible observations
$$
\int_\mathfrak{X} \varrho(x, \vartheta) dx = 1
$$
- but the [[likelihood function]] is a function of the parameters and because $\int_\Theta \varrho(x, \vartheta) d\vartheta$ does not have to be $1$ the [[likelihood function]] is not a [[probability density function (PDF)]]

Tags: mathematics statistics WS2425
<!--ID: 1730182230095-->
END