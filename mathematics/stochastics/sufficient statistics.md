### sufficient statistics
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- a [[statistics]] $T: \mathfrak{X} \to \mathfrak{Y}$ is a [[sufficient statistics]] if there exists the [[measurable function|measurable functions]] $g_\vartheta: \mathfrak{Y} \to \mathbb{R}$ and $h: \mathfrak{X} \to \mathbb{R}$ such that the following being true $\forall x \in \mathfrak{X}$

$$
f_\vartheta(x) = g_\vartheta(T(x)) h(x) 
$$

- without loss of generality wen can assume that  $g_\vartheta, h \geq 0$ 

#### interpretation
- in this case $T$ contains all the nesseary information for $\vartheta$ that is contained in $X$  

### example
- given the [[bernoulli distribution|bernoulli random variables]] $X_1, ..., X_n$ i.i.d. with $X_i \sim \mathcal{B}(p=\vartheta)$ 
- the sum of the [[random variable]] $T(X)$ is a [[sufficient statistics]]

$$
T(X) = \sum_{i \in [n]} X_i 
$$

- in this case $h(1)$ is the [[identity function]] and $g_\vartheta(X)= \vartheta^{T} (1- \vartheta)^{n-T}$

$$
f_\vartheta(x) 
= \prod \vartheta^X_i (1- \vartheta)^{1-X_i} 
= \vartheta^{\sum_{i \in [n]} X_i} (1- \vartheta)^{n-\sum_{i \in [n]} X_i} 
= \vartheta^{T} (1- \vartheta)^{n-T} 
$$


# anki


START
Basic
[[sufficient statistics]]
- definition
- interpretation

Back: 
### sufficient statistics
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- a [[statistics]] $T: \mathfrak{X} \to \mathfrak{Y}$ is a [[sufficient statistics]] if there exists the [[measurable function|measurable functions]] $g_\vartheta: \mathfrak{Y} \to \mathbb{R}$ and $h: \mathfrak{X} \to \mathbb{R}$ such that the following being true $\forall x \in \mathfrak{X}$

$$
f_\vartheta(x) = g_\vartheta(T(x)) h(x) 
$$

- without loss of generality wen can assume that  $g_\vartheta, h \geq 0$ 

#### interpretation
- in this case $T$ contains all the nesseary information for $\vartheta$ that is contained in $X$  

________________

### example
- given the [[bernoulli distribution|bernoulli random variables]] $X_1, ..., X_n$ i.i.d. with $X_i \sim \mathcal{B}(p=\vartheta)$ 
- the sum of the [[random variable]] $T(X)$ is a [[sufficient statistics]]

$$
T(X) = \sum_{i \in [n]} X_i 
$$

- in this case $h(1)$ is the [[identity function]] and $g_\vartheta(X)= \vartheta^{T} (1- \vartheta)^{n-T}$

$$
f_\vartheta(x) 
= \prod \vartheta^X_i (1- \vartheta)^{1-X_i} 
= \vartheta^{\sum_{i \in [n]} X_i} (1- \vartheta)^{n-\sum_{i \in [n]} X_i} 
= \vartheta^{T} (1- \vartheta)^{n-T} 
$$

Tags: mathematics statistics WS2425
<!--ID: 1731257650585-->
END


START
Basic
- given the [[bernoulli distribution|bernoulli random variables]] $X_1, ..., X_n$ i.i.d. with $X_i \sim \mathcal{B}(p=\vartheta)$ 
- name a [[sufficient statistics]] for $X$

Back: 
### sufficient statistics
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- a [[statistics]] $T: \mathfrak{X} \to \mathfrak{Y}$ is a [[sufficient statistics]] if there exists the [[measurable function|measurable functions]] $g_\vartheta: \mathfrak{Y} \to \mathbb{R}$ and $h: \mathfrak{X} \to \mathbb{R}$ such that the following being true $\forall x \in \mathfrak{X}$

$$
f_\vartheta(x) = g_\vartheta(T(x)) h(x) 
$$

- without loss of generality wen can assume that  $g_\vartheta, h \geq 0$ 

#### interpretation
- in this case $T$ contains all the nesseary information for $\vartheta$ that is contained in $X$  

### example
- given the [[bernoulli distribution|bernoulli random variables]] $X_1, ..., X_n$ i.i.d. with $X_i \sim \mathcal{B}(p=\vartheta)$ 
- the sum of the [[random variable]] $T(X)$ is a [[sufficient statistics]]

$$
T(X) = \sum_{i \in [n]} X_i 
$$

- in this case $h(1)$ is the [[identity function]] and $g_\vartheta(X)= \vartheta^{T} (1- \vartheta)^{n-T}$

$$
f_\vartheta(x) 
= \prod \vartheta^X_i (1- \vartheta)^{1-X_i} 
= \vartheta^{\sum_{i \in [n]} X_i} (1- \vartheta)^{n-\sum_{i \in [n]} X_i} 
= \vartheta^{T} (1- \vartheta)^{n-T} 
$$

Tags: mathematics statistics WS2425
<!--ID: 1731257650589-->
END