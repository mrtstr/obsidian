### score function
- given a [[random variable]] $X$ with a [[statistical model]] $(\mathfrak{X}, \mathcal{A}, \mathbb{P}_\vartheta: \vartheta \in \Theta)$ with a [[probability density function (PDF)]] $f_\vartheta(x)$ 
- the [[score function]] $Q_n(\vartheta)$ is the [[gradient]] with respect to the paramter vector $\vartheta$ of the [[logarithm|log]] [[likelihood function]] evaluated at a particular position $X$ (observation)

one parameter case:
$$
Q_n(\vartheta) = \frac{d}{d \vartheta} \ln{f_\vartheta}(X) = 0
$$

multi parameter case:
$$
Q_n(\vartheta) = \nabla \ln{f_\vartheta}(X) = 0
$$

### interpretation
- $Q_n(\vartheta)$ indicates the steepness of the [[logarithm|log]] [[likelihood function]]
- at a [[local minimum]] $Q_n(\vartheta)$ will become zero 

![[fisher information#fisher information]]


![[likelihood function#likelihood function]]