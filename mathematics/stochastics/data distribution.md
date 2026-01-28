### data distribution
- the [[data distribution]] is the [[joint distribution]] of the [[input and output space]] of a model
- given the [[probability space]] 
	- input $(\mathcal{X}, \mathcal{A}_X, \mathcal{P}_X)$  
	- output  $(\mathcal{Y}, \mathcal{A_Y}, \mathcal{P}_Y)$ 
- the [[data distribution]] $\mathcal{P}_{XY}$ is the joint [[probability measure]] over the [[product measure space|product measurable space]] $(\mathcal{X} \times \mathcal{Y}, \mathcal{A_X} \otimes \mathcal{A_Y})$
- given a dataset $\mathcal{D}_0 \subset \mathcal{X} \times \mathcal{Y}$ its [[empirical distribution of a dataset|empirical distribution]] $\mathcal{\hat{P}}_{XY}$ is defined as follows with the [[dirac measure]] $\delta$ 

$$
\mathcal{\hat P}_{XY}(A) = \frac{1}{n} \sum_{i=1}^n \delta_{(x_i, y_i)}(A)
$$

# ---------


![[input and output space#input and output space]]

![[empirical distribution of a dataset#empirical distribution of a dataset]]

![[dirac measure#dirac measure]]
# anki

START
Basic
[[data distribution]]
- mathematical definition
- how can it be defined for a given data set $\mathcal{D}_0$

Back: 
### data distribution
- the [[data distribution]] is the [[joint distribution]] of the [[input and output space]] of a model
- given the [[probability space]] 
	- input $(\mathcal{X}, \mathcal{A}_X, \mathcal{P}_X)$  
	- output $(\mathcal{Y}, \mathcal{A_Y}, \mathcal{P}_Y)$ 
- the [[data distribution]] $\mathcal{P}_{XY}$ is the joint [[probability measure]] over the [[product measure space|product measurable space]] $(\mathcal{X} \times \mathcal{Y}, \mathcal{A_X} \otimes \mathcal{A_Y})$
- given a dataset $\mathcal{D}_0 \subset \mathcal{X} \times \mathcal{Y}$ its [[empirical distribution of a dataset|empirical distribution]] $\mathcal{\hat{P}}_{XY}$ is defined as follows with the [[dirac measure]] $\delta$ 

$$
\mathcal{\hat P}_{XY}(A) = \frac{1}{n} \sum_{i=1}^n \delta_{(x_i, y_i)}(A)
$$

______________

### input and output space
- the [[input and output space]] $(\mathcal{X}, \mathcal{A}_X, \mathcal{P}_X)$ and $(\mathcal{Y}, \mathcal{A_Y}, \mathcal{P}_Y)$ are [[probability space]] of the inputs and outputs of a model $f_\theta: \mathcal{X} \to \mathcal{Y}$ 
- given a dataset $\mathcal{D}_X \subset \mathcal{X}$ or $\mathcal{D}_Y \subset \mathcal{Y}$ its [[probability measure]] can be approximated using the [[empirical distribution of a dataset]]

### empirical distribution of a dataset
- given a dataset $\mathcal{D} \subset \mathbb{R}^d=\{x_1, ..., x_n\}$
- the [[empirical distribution of a dataset]] $\mathbb{\hat P}_n$ is a [[probability measure]] that puts equal weight on each data point and can be formalized with the [[dirac measure]]  

$$
\mathbb{\hat P}_n = \frac{1}{n} \sum_{i=1}^n \delta_{x_i}
$$
- thus any $A \subset \mathbb{R}^d$ can be measured with respect to $\mathbb{\hat P}_n$

$$
\mathbb{\hat P}_n(A) = \frac{1}{n} \sum_{i=1}^n \delta_{x_i}(A) = \frac{|A \cap \mathcal{D}|}{n}
$$


### dirac measure
- given a point $x$ in a [[measurable space]] $(\Omega, \mathcal{A})$ the [[dirac measure]] $\delta_x(A): \mathcal{A} \to \{0,1\}$ is defined as follows

$$
\delta_x(A)=\left\{
\begin{matrix} 
1& \text{if } x \in A  \\
0& \text{if } x \notin A  \\
\end{matrix}\right.
$$

- is a [[probability measure]] because $\delta_x(\Omega)=\int_\Omega d\delta_x = 1$
- is not [[absolutely continuous]] to the [[lebesgue measure]] because $\lambda(\{x\})=0$ but $\delta_x(\{x\})=1$
- if $f$ is a [[measurable function]] on $(\Omega, \mathcal{A})$ then integrating $f$ against $\delta_x$ is equivalent to evaluating $f$ at $x$

$$
\int_\Omega f(\omega) d\delta_x = f(x)
$$

- similar to the indicator function $\mathbb{I}[x \in A]=\delta_x(A)$ 


Tags: mathematics statistics SS25
<!--ID: 1746870898941-->
END