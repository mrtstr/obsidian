### multinomial logistic regresssion

- In [[logistic regression]], a [[linear model]] maps an input $\varphi(x) \in \mathbb{R}^n$ and parameters $\theta \in \mathbb{R}^n$ to a scalar [[logit]]:  

$$
  z = \varphi(x)^\top \theta \in \mathbb{R}
$$

  This scalar is passed through the [[sigmoid function]] to model binary classification.

- In [[multinomial logistic regresssion]], we generalize to $C$ classes by learning a separate parameter vector $\beta_c \in \mathbb{R}^n$ for each class.

- Collecting all class-specific weights into a [[matrix]] $B \in \mathbb{R}^{C \times n}$, the input is mapped to a [[logit|vector of logits]]:  
$$
  z = B \varphi(x) \in \mathbb{R}^C
$$

  where each component $z_c = \beta_c^\top \varphi(x$ corresponds to class $c$.

- Applying the [[softmax function]] converts the [[logit|logits]] into a valid probability distribution over the classes:
  
$$
  \begin{split}
  \mathbb{P}(Y = c \mid X = x) 
  &= \mathrm{softmax}(B \varphi(x))_c \\
  &= \frac{\exp(\beta_c^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}
  \end{split}
$$

This model is commonly used in multiclass [[classification]] tasks and serves as the final layer in many [[mathematics/stochastics/statistical learning/models/neural networks/neural networks]].

### decision boundary's

- when two classes $k$ and $l$ are compared we have the following because the [[exponential]] function is [[monotonic function|monotonic increasing]]

$$
  \begin{split}
\frac{\exp(\beta_k^\top \varphi(x))}{Const)} &> \frac{\exp(\beta_l^\top \varphi(x))}{Const} \\
&\Leftrightarrow\\
\beta_k^\top \varphi(x)) &> \beta_l^\top \varphi(x))
  \end{split}
$$

- thus the decision boundary is where $\beta_k^\top \varphi(x))=\beta_l^\top \varphi(x))$

##### example


$$
\varphi : 
\begin{bmatrix}
x_1 \\
x_2
\end{bmatrix}
\rightarrow
\begin{bmatrix}
1 \\
x_1 \\
x_2 \\
x_1^2 \\
x_2
\end{bmatrix}
$$


- $\beta_k = [-1, 0, 0, 1, 0]^\top$ and $\beta_l = [0, 0, 1, 0, 0]^\top$

- bring the equation in the form $x_2 = f(x_1)$ and draw the function
- above the curve its $l$ and below the curve its $k$

$$
-1 + x_1^2 = x_2
$$


```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-3,3,-2,2]
disableZoom: true
grid: true
---
f(x) = -1 + x^2
```

#### maximum likeliehood with gradient descent

- there is no closed form solution, but the [[log likelihood]] function can be maximized using [[gradient descent|gradient ascent]] 
- using the following update rule

$$
\beta_k^{(t+1)} \leftarrow \beta_k^{(t)} + \gamma \nabla_{\beta_k} \mathcal{L}\left(\beta^{(t)}\right)
$$

- [[log likelihood]] of a class $c$

$$
\begin{split}
\log p\left(Y=c|X=x \right) 
&= \log \left( \frac{\exp(\beta_c^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))} \right) \\
&= \beta_c^\top \varphi(x) - \log \left( \sum_{j=1}^C \exp(\beta_j^\top \varphi(x)) \right)
\end{split}
$$

- with the [[log likelihood]] function being regarding the true label $y$

$$
\begin{split}
\mathcal{L}(\beta) 
&= \log p\left(Y=y|X=x \right) \\
&= \beta_y^\top \varphi(x) - \log \left( \sum_{j=1}^C \exp(\beta_j^\top \varphi(x)) \right)
\end{split}
$$

- for the case $y=k$ we have the following [[gradient]]

$$
\begin{split}
\nabla_{\beta_k} \mathcal{L} 
&= \nabla_{\beta_y} \beta_y^\top \varphi(x) - \nabla_{\beta_y} \log \left( \sum_{j=1}^C \exp(\beta_j^\top \varphi(x)) \right) \\
&= \varphi(x) - \frac{1}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}   \sum_{j=1}^C \nabla_{\beta_y} \exp(\beta_j^\top \varphi(x))  \\
&= \varphi(x) - \frac{1}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}   \nabla_{\beta_y} \exp(\beta_y^\top \varphi(x))  \\
&= \varphi(x) - \frac{\exp(\beta_y^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}   \varphi(x)   \\
&= \varphi(x) \left(1 - \frac{\exp(\beta_y^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}  \right)  \\
&= \varphi(x) \left(1 - p(Y=y|X=x) \right)  \\
\end{split}
$$

- for the case $y\neq k$ we have the following [[gradient]]

$$
\begin{split}
\nabla_{\beta_k} \mathcal{L} 
&= \nabla_{\beta_k} \beta_y^\top \varphi(x) - \nabla_{\beta_k} \log \left( \sum_{j=1}^C \exp(\beta_j^\top \varphi(x)) \right) \\
&= 0 - \frac{\sum_{j=1}^C \nabla_{\beta_y} \exp(\beta_j^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))} \varphi(x)    \\
&= - \frac{\nabla_{\beta_k} \exp(\beta_k^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}  \varphi(x)   \\

&= - \varphi(x) \left(p(Y=y|X=x) \right) \varphi(x) \\
\end{split}
$$

- resulting in the following [[gradient]]

$$
\begin{split}
\nabla_{\beta_k} \mathcal{L} = 
\begin{cases}
(1 - p(y = k \mid x)) \cdot \varphi(x), & \text{if } k = y \\
- p(y = k \mid x) \cdot \varphi(x), & \text{if } k \neq y
\end{cases}
\end{split}
$$

# -------------

![[softmax function#softmax function]]

![[logistic regression#logistic regression]]


# anki

START
Basic
[[multinomial logistic regresssion]]
- how to calculate the max [[log likelihood]] solution using [[gradient descent|gradient ascent]] 
- calculate the [[gradient]] and provide the update rule
Back: 
#### maximum likeliehood with gradient descent

- there is no closed form solution, but the [[log likelihood]] function can be maximized using [[gradient descent|gradient ascent]] 
- using the following update rule

$$
\beta_k^{(t+1)} \leftarrow \beta_k^{(t)} + \gamma \nabla_{\beta_k} \mathcal{L}\left(\beta^{(t)}\right)
$$

- [[log likelihood]] of a class $c$

$$
\begin{split}
\log p\left(Y=c|X=x \right) 
&= \log \left( \frac{\exp(\beta_c^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))} \right) \\
&= \beta_c^\top \varphi(x) - \log \left( \sum_{j=1}^C \exp(\beta_j^\top \varphi(x)) \right)
\end{split}
$$

- with the [[log likelihood]] function being regarding the true label $y$

$$
\begin{split}
\mathcal{L}(\beta) 
&= \log p\left(Y=y|X=x \right) \\
&= \beta_y^\top \varphi(x) - \log \left( \sum_{j=1}^C \exp(\beta_j^\top \varphi(x)) \right)
\end{split}
$$

- for the case $y=k$ we have the following [[gradient]]

$$
\begin{split}
\nabla_{\beta_k} \mathcal{L} 
&= \nabla_{\beta_y} \beta_y^\top \varphi(x) - \nabla_{\beta_y} \log \left( \sum_{j=1}^C \exp(\beta_j^\top \varphi(x)) \right) \\
&= \varphi(x) - \frac{1}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}   \sum_{j=1}^C \nabla_{\beta_y} \exp(\beta_j^\top \varphi(x))  \\
&= \varphi(x) - \frac{1}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}   \nabla_{\beta_y} \exp(\beta_y^\top \varphi(x))  \\
&= \varphi(x) - \frac{\exp(\beta_y^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}   \varphi(x)   \\
&= \varphi(x) \left(1 - \frac{\exp(\beta_y^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}  \right)  \\
&= \varphi(x) \left(1 - p(Y=y|X=x) \right)  \\
\end{split}
$$

- for the case $y\neq k$ we have the following [[gradient]]

$$
\begin{split}
\nabla_{\beta_k} \mathcal{L} 
&= \nabla_{\beta_k} \beta_y^\top \varphi(x) - \nabla_{\beta_k} \log \left( \sum_{j=1}^C \exp(\beta_j^\top \varphi(x)) \right) \\
&= 0 - \frac{\sum_{j=1}^C \nabla_{\beta_y} \exp(\beta_j^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))} \varphi(x)    \\
&= - \frac{\nabla_{\beta_k} \exp(\beta_k^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}  \varphi(x)   \\

&= - \varphi(x) \left(p(Y=y|X=x) \right) \varphi(x) \\
\end{split}
$$

- resulting in the following [[gradient]]

$$
\begin{split}
\nabla_{\beta_k} \mathcal{L} = 
\begin{cases}
(1 - p(y = k \mid x)) \cdot \varphi(x), & \text{if } k = y \\
- p(y = k \mid x) \cdot \varphi(x), & \text{if } k \neq y
\end{cases}
\end{split}
$$


### multinomial logistic regresssion

- In [[logistic regression]], a [[linear model]] maps an input $\varphi(x) \in \mathbb{R}^n$ and parameters $\theta \in \mathbb{R}^n$ to a scalar [[logit]]:  

$$
  z = \varphi(x)^\top \theta \in \mathbb{R}
$$

  This scalar is passed through the [[sigmoid function]] to model binary classification.

- In [[multinomial logistic regresssion]], we generalize to $C$ classes by learning a separate parameter vector $\beta_c \in \mathbb{R}^n$ for each class.

- Collecting all class-specific weights into a [[matrix]] $B \in \mathbb{R}^{C \times n}$, the input is mapped to a [[logit|vector of logits]]:  
$$
  z = B \varphi(x) \in \mathbb{R}^C
$$

  where each component $z_c = \beta_c^\top \varphi(x$ corresponds to class $c$.

- Applying the [[softmax function]] converts the [[logit|logits]] into a valid probability distribution over the classes:
  
$$
  \begin{split}
  \mathbb{P}(Y = c \mid X = x) 
  &= \mathrm{softmax}(B \varphi(x))_c \\
  &= \frac{\exp(\beta_c^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}
  \end{split}
$$

This model is commonly used in multiclass [[classification]] tasks and serves as the final layer in many [[mathematics/stochastics/statistical learning/models/neural networks/neural networks]].


___________

### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z) = \frac{1}{\sum_{i=1}^n \exp(y_i)} \exp(X)
\end{split}
$$
- used as output function in [[classification]] problems for example with [[mathematics/stochastics/statistical learning/models/neural networks/neural networks]] and [[multinomial logistic regresssion]]



Tags: mathematics SS25
<!--ID: 1753092525198-->
END


START
Basic
[[multinomial logistic regresssion]]
- decision boundary's
- how to draw them and why does this work
- do it for the following example


$$
\varphi : 
\begin{bmatrix}
x_1 \\
x_2
\end{bmatrix}
\rightarrow
\begin{bmatrix}
1 \\
x_1 \\
x_2 \\
x_1^2 \\
x_2
\end{bmatrix}
$$


- $\beta_k = [-1, 0, 0, 1, 0]^\top$ and $\beta_l = [0, 0, 1, 0, 0]^\top$

Back: 

### decision boundary's

- when two classes $k$ and $l$ are compared we have the following because the [[exponential]] function is [[monotonic function|monotonic increasing]]

$$
  \begin{split}
\frac{\exp(\beta_k^\top \varphi(x))}{Const)} &> \frac{\exp(\beta_l^\top \varphi(x))}{Const} \\
&\Leftrightarrow\\
\beta_k^\top \varphi(x)) &> \beta_l^\top \varphi(x))
  \end{split}
$$

- thus the decision boundary is where $\beta_k^\top \varphi(x))=\beta_l^\top \varphi(x))$

##### example


$$
\varphi : 
\begin{bmatrix}
x_1 \\
x_2
\end{bmatrix}
\rightarrow
\begin{bmatrix}
1 \\
x_1 \\
x_2 \\
x_1^2 \\
x_2
\end{bmatrix}
$$


- $\beta_k = [-1, 0, 0, 1, 0]^\top$ and $\beta_l = [0, 0, 1, 0, 0]^\top$

- bring the equation in the form $x_2 = f(x_1)$ and draw the function
- above the curve its $l$ and below the curve its $k$

$$
-1 + x_1^2 = x_2
$$

![[Pasted image 20250721103039.png]]

### multinomial logistic regresssion

- In [[logistic regression]], a [[linear model]] maps an input $\varphi(x) \in \mathbb{R}^n$ and parameters $\theta \in \mathbb{R}^n$ to a scalar [[logit]]:  

$$
  z = \varphi(x)^\top \theta \in \mathbb{R}
$$

  This scalar is passed through the [[sigmoid function]] to model binary classification.

- In [[multinomial logistic regresssion]], we generalize to $C$ classes by learning a separate parameter vector $\beta_c \in \mathbb{R}^n$ for each class.

- Collecting all class-specific weights into a [[matrix]] $B \in \mathbb{R}^{C \times n}$, the input is mapped to a [[logit|vector of logits]]:  
$$
  z = B \varphi(x) \in \mathbb{R}^C
$$

  where each component $z_c = \beta_c^\top \varphi(x$ corresponds to class $c$.

- Applying the [[softmax function]] converts the [[logit|logits]] into a valid probability distribution over the classes:
  
$$
  \begin{split}
  \mathbb{P}(Y = c \mid X = x) 
  &= \mathrm{softmax}(B \varphi(x))_c \\
  &= \frac{\exp(\beta_c^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}
  \end{split}
$$

This model is commonly used in multiclass [[classification]] tasks and serves as the final layer in many [[mathematics/stochastics/statistical learning/models/neural networks/neural networks]].


___________

### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z) = \frac{1}{\sum_{i=1}^n \exp(y_i)} \exp(X)
\end{split}
$$
- used as output function in [[classification]] problems for example with [[mathematics/stochastics/statistical learning/models/neural networks/neural networks]] and [[multinomial logistic regresssion]]

### logistic regression
- for solving binary [[classification]] problems
- [[linear model]] with a [[sigmoid function]] around the output
- does not have a closed form solution but can be trained iterative using [[gradient descent]]
#### standard (0, 1) label convention
- standard version of the [[logistic regression]] for binary classification problems with labels $y \in \{0,1\}$
$$
\begin{split}
\mathbb{P}(Y=1|X=x) 
&= \sigma(\varphi(x)^\top\theta) \\
&= \frac{1}{1+e^{-{\varphi}(x)^\top\theta}} \\
\mathbb{P}(Y=0|X=x) 
&= 1- \sigma(\varphi(x)^\top\theta) \\
&= \sigma(-\varphi(x)^\top\theta) \\
&= \frac{1}{1+e^{{\varphi}(x)^\top\theta}} \\
\end{split}
$$

#### (−1, +1) label convention
- for labels $y \in \{-1,1\}$ the following version of the [[logistic regression]] can be used
- this makes calculating the [[gradient]] easier

$$
\begin{split}
\mathbb{P}(Y=y|X=x) 
&= \sigma(y \cdot \varphi(x)^\top\theta) \\
&= \frac{1}{1+e^{-y \cdot{\varphi}(x)^\top\theta}} \\
\mathbb{P}(Y=1|X=x) 
&= \frac{1}{1+e^{-{\varphi}(x)^\top\theta}} \\
\mathbb{P}(Y=-1|X=x) 
&= \frac{1}{1+e^{{\varphi}(x)^\top\theta}} \\
\end{split}
$$

#### log likelihood solution for the logistic regression
- using the (−1, +1) label convention we have the following [[log likelihood]]

$$
\begin{split}
\mathcal{L}(\theta) 
&= \sum_{i=1}^n \log \mathbb{P}(Y=y_i|X=x_i) \\
&= \sum_{i=1}^n \log \frac{1}{1+e^{-y \cdot{\varphi}(x)^\top\theta}} \\
\end{split}
$$

- since there is no analytical solution the [[log likelihood]] is maximized with [[gradient descent|gradient ascent]] with the following update rule

$$
\begin{split}
\theta_t \leftarrow \theta_{t-1} + \gamma_t \nabla F(\theta_{t-1})
\end{split}
$$

#### overfitting and the generalization gap
- to prevent [[overfitting]] the [[logistic regression]] can also be trained with regularization terms like with [[ridge regression]] and [[lasso regression]]
- apart from that training with [[gradient descent]] also leads to implicit regularization

Tags: mathematics SS25
<!--ID: 1753092525203-->
END

START
Basic
[[multinomial logistic regresssion]]
- general setup
- difference to [[logistic regression]]
Back: 

### multinomial logistic regresssion

- In [[logistic regression]], a [[linear model]] maps an input $\varphi(x) \in \mathbb{R}^n$ and parameters $\theta \in \mathbb{R}^n$ to a scalar [[logit]]:  

$$
  z = \varphi(x)^\top \theta \in \mathbb{R}
$$

  This scalar is passed through the [[sigmoid function]] to model binary classification.

- In [[multinomial logistic regresssion]], we generalize to $C$ classes by learning a separate parameter vector $\beta_c \in \mathbb{R}^n$ for each class.

- Collecting all class-specific weights into a [[matrix]] $B \in \mathbb{R}^{C \times n}$, the input is mapped to a [[logit|vector of logits]]:  
$$
  z = B \varphi(x) \in \mathbb{R}^C
$$

  where each component $z_c = \beta_c^\top \varphi(x$ corresponds to class $c$.

- Applying the [[softmax function]] converts the [[logit|logits]] into a valid probability distribution over the classes:
  
$$
  \begin{split}
  \mathbb{P}(Y = c \mid X = x) 
  &= \mathrm{softmax}(B \varphi(x))_c \\
  &= \frac{\exp(\beta_c^\top \varphi(x))}{\sum_{j=1}^C \exp(\beta_j^\top \varphi(x))}
  \end{split}
$$

This model is commonly used in multiclass [[classification]] tasks and serves as the final layer in many [[mathematics/stochastics/statistical learning/models/neural networks/neural networks]].


___________

### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z) = \frac{1}{\sum_{i=1}^n \exp(y_i)} \exp(X)
\end{split}
$$
- used as output function in [[classification]] problems for example with [[mathematics/stochastics/statistical learning/models/neural networks/neural networks]] and [[multinomial logistic regresssion]]

### logistic regression
- for solving binary [[classification]] problems
- [[linear model]] with a [[sigmoid function]] around the output
- does not have a closed form solution but can be trained iterative using [[gradient descent]]
#### standard (0, 1) label convention
- standard version of the [[logistic regression]] for binary classification problems with labels $y \in \{0,1\}$
$$
\begin{split}
\mathbb{P}(Y=1|X=x) 
&= \sigma(\varphi(x)^\top\theta) \\
&= \frac{1}{1+e^{-{\varphi}(x)^\top\theta}} \\
\mathbb{P}(Y=0|X=x) 
&= 1- \sigma(\varphi(x)^\top\theta) \\
&= \sigma(-\varphi(x)^\top\theta) \\
&= \frac{1}{1+e^{{\varphi}(x)^\top\theta}} \\
\end{split}
$$

#### (−1, +1) label convention
- for labels $y \in \{-1,1\}$ the following version of the [[logistic regression]] can be used
- this makes calculating the [[gradient]] easier

$$
\begin{split}
\mathbb{P}(Y=y|X=x) 
&= \sigma(y \cdot \varphi(x)^\top\theta) \\
&= \frac{1}{1+e^{-y \cdot{\varphi}(x)^\top\theta}} \\
\mathbb{P}(Y=1|X=x) 
&= \frac{1}{1+e^{-{\varphi}(x)^\top\theta}} \\
\mathbb{P}(Y=-1|X=x) 
&= \frac{1}{1+e^{{\varphi}(x)^\top\theta}} \\
\end{split}
$$

#### log likelihood solution for the logistic regression
- using the (−1, +1) label convention we have the following [[log likelihood]]

$$
\begin{split}
\mathcal{L}(\theta) 
&= \sum_{i=1}^n \log \mathbb{P}(Y=y_i|X=x_i) \\
&= \sum_{i=1}^n \log \frac{1}{1+e^{-y \cdot{\varphi}(x)^\top\theta}} \\
\end{split}
$$

- since there is no analytical solution the [[log likelihood]] is maximized with [[gradient descent|gradient ascent]] with the following update rule

$$
\begin{split}
\theta_t \leftarrow \theta_{t-1} + \gamma_t \nabla F(\theta_{t-1})
\end{split}
$$

#### overfitting and the generalization gap
- to prevent [[overfitting]] the [[logistic regression]] can also be trained with regularization terms like with [[ridge regression]] and [[lasso regression]]
- apart from that training with [[gradient descent]] also leads to implicit regularization

Tags: mathematics SS25
<!--ID: 1752949761739-->
END