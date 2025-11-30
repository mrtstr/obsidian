## cross entropy loss
### multi class classification
- let $y \in \mathbb{R}^n$ be true [[distribution]] and $\hat y  \in \mathbb{R}^n$ the model prediction in a multi class classification problem
- by minimizing the [[cross entropy]] between the label $y$ and the assumed [[distribution]] $\hat y$ we can train the model to match the true [[distribution]] 
- if $y$ is a one hot vector with the value with the index $c$ being the correct class the [[nn cross entropy loss]] simplifies

$$
\begin{split}
\ell(y, \hat y) 
&=  -\sum_i y_i \log(\hat y_i) \\
&=  -\log(\hat y_c) \\
\end{split}
$$

#### relationship to the softmax function
- when combining the [[nn cross entropy loss]] with a [[softmax function]] in the output layer, the [[gradient]] with respect to the [[logit]] $z$ with $\hat y=\mathrm{SOFTMAX}(z)$ simplifies to the following

$$
\nabla_z \ell(y, \hat y(z)) = \left(\frac{\partial \ell(y, \hat y(z)) }{\partial z}\right)^\top = \hat y -y
$$

$$
\begin{split}
\frac{\partial \ell(y, \hat y(z)) }{\partial z_j} 
&= \sum_i \frac{\partial \ell\left(y, \hat y\right) }{\partial \hat y_i} \frac{\partial \mathrm{SOFTMAX}(z)_i }{\partial z_j}  \\
&= \sum_i -  \frac{y_i}{\hat y_i} \hat y_j (\mathrm{I} \left[i=j\right]- \hat y_j)  \\
&= \sum_i   \frac{y_i \hat y_j \hat y_j - y_i \hat y_j \mathrm{I} \left[i=j\right]}{\hat y_i}   \\
&= \sum_i   \frac{y_i \hat y_j \hat y_j}{\hat y_i} - \sum_i   \frac{y_i \hat y_j \mathrm{I} \left[i=j\right]}{\hat y_i}   \\
&= \hat y_j - y_i  \\
\frac{\partial \mathrm{SOFTMAX}(z)_i }{\partial z_j}
&= \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]-\mathrm{SOFTMAX}(Z)_j\mathrm{SOFTMAX}(Z)_i\\
&=  \hat y_j (\mathrm{I} \left[i=j\right]- \hat y_j)  \\
\frac{\partial \ell\left(y, \hat y\right) }{\partial \hat y_i} 
&= -  \sum_i \frac{\partial  }{\partial \hat y_i}  y_i \log(\hat y_i) \\
&= -  \frac{y_i}{\hat y_i}   \\
\end{split}
$$


![[softmax function#derivative of the softmax]]

### binary classification
- in a multi class problem with $n$ classes the $y \in \mathbb{R}^n$ has $n$ dimensions
- in a binary problem we just need one dimension ($y \in \mathbb{R}$) because $\mathbb{P}(Y=1) = 1-\mathbb{P}(Y=0)$

$$
\begin{split}
\ell(y, \hat y) 
&=  -y \log(\hat y) -(1-y) \log(1-\hat y) \\
\end{split}
$$

#### relationship to the sigmoid function
- when combining the [[nn cross entropy loss]] with a [[sigmoid function]] in the output layer, the [[gradient]] with respect to the [[logit]] $z$ with $\hat y=\sigma(z)$ simplifies to the following


$$
\frac{d \ell(y, \hat y(z)) }{d z} = \hat y -y
$$

$$
\begin{split}
\frac{d \ell(y, \hat y(z)) }{d z}
=& \frac{d \ell(y, \hat y) }{d \hat y} \frac{d \sigma(z) }{d z} \\
=& \frac{\hat y -y)}{\hat y (1- \hat y)} \hat y(1-\hat y)  \\
=& \hat y -y  \\
\frac{d \ell(y, \hat y) }{d \hat y}
=& \frac{d }{d \hat y} \left(-y \log(\hat y) -(1-y) \log(1-\hat y)\right) \\
=& - \frac{y}{\hat y}  +\frac{1-y}{1- \hat y} \\
=&  \frac{\hat y(1-y)-y(1- \hat y) }{\hat y (1- \hat y)}  \\
=&  \frac{\hat y -y + y\hat y +  -y \hat y)}{\hat y (1- \hat y)}  \\
=&  \frac{\hat y -y)}{\hat y (1- \hat y)}  \\
\frac{d \sigma(z) }{d z}
=& \frac{d  }{d z} \frac{1}{1+e^{-z}} \\
=& \sigma(z)(1-\sigma(z)) \\
=& \hat y(1-\hat y) \\
\end{split}
$$



![[sigmoid function#derivative of the sigmoid function]]

# ------------

![[softmax function#softmax function]]


![[cross entropy#cross entropy]]


# anki

START
Basic
[[nn cross entropy loss]]
- definition: multi class case different from the binary case
- which [[loss function]] to use in each case

Back: 
## cross entropy loss
### multi class classification
- let $y \in \mathbb{R}^n$ be true [[distribution]] and $\hat y  \in \mathbb{R}^n$ the model prediction in a multi class classification problem
- by minimizing the [[cross entropy]] between the label $y$ and the assumed [[distribution]] $\hat y$ we can train the model to match the true [[distribution]] 
- if $y$ is a one hot vector with the value with the index $c$ being the correct class the [[nn cross entropy loss]] simplifies

$$
\begin{split}
\ell(y, \hat y) 
&=  -\sum_i y_i \log(\hat y_i) \\
&=  -\log(\hat y_c) \\
\end{split}
$$

#### relationship to the softmax function
- when combining the [[nn cross entropy loss]] with a [[softmax function]] in the output layer, the [[gradient]] with respect to the [[logit]] $z$ with $\hat y=\mathrm{SOFTMAX}(z)$ simplifies to the following

$$
\nabla_z \ell(y, \hat y(z)) = \left(\frac{\partial \ell(y, \hat y(z)) }{\partial z}\right)^\top = \hat y -y
$$

$$
\begin{split}
\frac{\partial \ell(y, \hat y(z)) }{\partial z_j} 
&= \sum_i \frac{\partial \ell\left(y, \hat y\right) }{\partial \hat y_i} \frac{\partial \mathrm{SOFTMAX}(z)_i }{\partial z_j}  \\
&= \sum_i -  \frac{y_i}{\hat y_i} \hat y_j (\mathrm{I} \left[i=j\right]- \hat y_j)  \\
&= \sum_i   \frac{y_i \hat y_j \hat y_j - y_i \hat y_j \mathrm{I} \left[i=j\right]}{\hat y_i}   \\
&= \sum_i   \frac{y_i \hat y_j \hat y_j}{\hat y_i} - \sum_i   \frac{y_i \hat y_j \mathrm{I} \left[i=j\right]}{\hat y_i}   \\
&= \hat y_j - y_i  \\
\frac{\partial \mathrm{SOFTMAX}(z)_i }{\partial z_j}
&= \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]-\mathrm{SOFTMAX}(Z)_j\mathrm{SOFTMAX}(Z)_i\\
&=  \hat y_j (\mathrm{I} \left[i=j\right]- \hat y_j)  \\
\frac{\partial \ell\left(y, \hat y\right) }{\partial \hat y_i} 
&= -  \sum_i \frac{\partial  }{\partial \hat y_i}  y_i \log(\hat y_i) \\
&= -  \frac{y_i}{\hat y_i}   \\
\end{split}
$$


#### derivative of the softmax

$$
\begin{split}
\frac{\partial \mathrm{SOFTMAX}(Z)_i }{\partial Z_j}
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial \exp{(Z_{i})}}{\partial Z_j} \frac{1}{\sum_{k} \exp{(Z_{k})}}+ \exp{(Z_{i})}\frac{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}}{\partial Z_j} \\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \frac{\sum_{k} \exp{(Z_{k})}}{\partial Z_j}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \exp{(Z_{j})}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]-\mathrm{SOFTMAX}(Z)_j\mathrm{SOFTMAX}(Z)_i\\
=& \begin{cases}
\mathrm{SOFTMAX}(Z)_j (1- \mathrm{SOFTMAX}(Z)_j) & ,for\ i=j \\
-\mathrm{SOFTMAX}(Z)_j \mathrm{SOFTMAX}(Z)_i  & ,for\ i\neq j  \\
\end{cases}
\end{split}
$$


### binary classification
- in a multi class problem with $n$ classes the $y \in \mathbb{R}^n$ has $n$ dimensions
- in a binary problem we just need one dimension ($y \in \mathbb{R}$) because $\mathbb{P}(Y=1) = 1-\mathbb{P}(Y=0)$

$$
\begin{split}
\ell(y, \hat y) 
&=  -y \log(\hat y) -(1-y) \log(1-\hat y) \\
\end{split}
$$

#### relationship to the sigmoid function
- when combining the [[nn cross entropy loss]] with a [[sigmoid function]] in the output layer, the [[gradient]] with respect to the [[logit]] $z$ with $\hat y=\sigma(z)$ simplifies to the following


$$
\frac{d \ell(y, \hat y(z)) }{d z} = \hat y -y
$$

$$
\begin{split}
\frac{d \ell(y, \hat y(z)) }{d z}
=& \frac{d \ell(y, \hat y) }{d \hat y} \frac{d \sigma(z) }{d z} \\
=& \frac{\hat y -y)}{\hat y (1- \hat y)} \hat y(1-\hat y)  \\
=& \hat y -y  \\
\frac{d \ell(y, \hat y) }{d \hat y}
=& \frac{d }{d \hat y} \left(-y \log(\hat y) -(1-y) \log(1-\hat y)\right) \\
=& - \frac{y}{\hat y}  +\frac{1-y}{1- \hat y} \\
=&  \frac{\hat y(1-y)-y(1- \hat y) }{\hat y (1- \hat y)}  \\
=&  \frac{\hat y -y + y\hat y +  -y \hat y)}{\hat y (1- \hat y)}  \\
=&  \frac{\hat y -y)}{\hat y (1- \hat y)}  \\
\frac{d \sigma(z) }{d z}
=& \frac{d  }{d z} \frac{1}{1+e^{-z}} \\
=& \sigma(z)(1-\sigma(z)) \\
=& \hat y(1-\hat y) \\
\end{split}
$$



#### derivative of the sigmoid function

$$
\begin{split}
\frac{d}{du}\sigma(u) 
&= \frac{d}{du} \frac{1}{1+e^{-u}} \\
&=  \frac{-1}{(1+e^{-u})^2} \cdot e^{-u} \cdot -1 \\
&=  \frac{e^{-u}}{1+e^{-u}} \frac{1}{1+e^{-u}}\\
&=  \frac{e^{-u}}{1+e^{-u}} \sigma(u)\\
&=  \frac{\frac{e^{-u}}{e^{-u}}}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \sigma(u)\\
&=  \frac{1}{e^{u}+1} \sigma(u)\\
&=  \sigma(-u) \sigma(u)\\
&=  (1-\sigma(u)) \sigma(u)\\
\end{split}
$$

___________
### cross entropy
- [[cross entropy]] is a measure of the dissimilarity between two probability distributions: a **true distribution** $P$ and an **estimated (or assumed) distribution** $Q$
- It quantifies the **expected number of bits** needed to encode samples from $P$
  using a code that is optimized for $Q$
- It is defined as the **expected negative log-likelihood** under $Q$
  when the data is actually drawn from $P$

#### Continuous Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### Discrete Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### range
- The **minimum** cross-entropy is reached when $P=Q$ in which case it reduces to the **entropy** of $P$:

$$
H(P, Q) = H(P) \quad \text{if and only if} \quad P = Q
$$

- can go to infinity if there are regions where  $p(x) > 0$ but $q(x) = 0$ because $\log \left(q(x)\right)=\log \left(0\right) = -\infty$, and thus the expectation $-\mathbb{E}_{x \sim P}[\log q(x)]$ becomes infinite.

$$
\text{supp}(P) \nsubseteq \text{supp}(Q)
$$
### cross entropy of independent random variables

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\

\end{split}
$$
### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z)_i 
&= \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}}
\end{split}
$$

- used as output function in [[classification]] problems, for example with [[neural network]] and [[multinomial logistic regresssion]]

### sigmoid function
- the [[sigmoid function]] $\sigma: \mathbb{R} \to (0,1)$ is defined as follows:
- its the inverse of the [[logit function]]

$$
\sigma(u) = \frac{1}{1+e^{-u}}
$$

#### properties
$$
\sigma(0) = \frac{1}{2}
$$

$$
\begin{split}
\lim_{u\to\infty}\sigma(u) &= 1 \\
\lim_{u\to-\infty}\sigma(u) &= 0 \\
\end{split}
$$

$$
1-\sigma(u) = \frac{1}{1+e^{+u}} = \sigma(-u)
$$

###### proof


$$
\begin{split}
1-\sigma(u) 
&= 1-\frac{1}{1+e^{-u}} \\
&= \frac{1+e^{-u}}{1+e^{-u}}-\frac{1}{1+e^{-u}} \\
&= \frac{e^{-u}}{1+e^{-u}} \\
&= \frac{1}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \\
&= \frac{1}{e^{--u}+1} \\
&= \sigma(-u) \\
\end{split}
$$


Tags: mathematics WS2526 ml
<!--ID: 1764519362354-->
END


START
Basic
calculate the [[gradient]] with respect to the [[logit]] $z$ with $\hat y=\sigma(z)$ for the [[nn cross entropy loss]] with a [[sigmoid function]] in the output layer in a binary classification problem


$$
\frac{d \ell(y, \hat y(z)) }{d z}
$$

Back: 
## cross entropy loss

### binary classification
- in a multi class problem with $n$ classes the $y \in \mathbb{R}^n$ has $n$ dimensions
- in a binary problem we just need one dimension ($y \in \mathbb{R}$) because $\mathbb{P}(Y=1) = 1-\mathbb{P}(Y=0)$

$$
\begin{split}
\ell(y, \hat y) 
&=  -y \log(\hat y) -(1-y) \log(1-\hat y) \\
\end{split}
$$

#### relationship to the sigmoid function
- when combining the [[nn cross entropy loss]] with a [[sigmoid function]] in the output layer, the [[gradient]] with respect to the [[logit]] $z$ with $\hat y=\sigma(z)$ simplifies to the following


$$
\frac{d \ell(y, \hat y(z)) }{d z} = \hat y -y
$$

$$
\begin{split}
\frac{d \ell(y, \hat y(z)) }{d z}
=& \frac{d \ell(y, \hat y) }{d \hat y} \frac{d \sigma(z) }{d z} \\
=& \frac{\hat y -y)}{\hat y (1- \hat y)} \hat y(1-\hat y)  \\
=& \hat y -y  \\
\frac{d \ell(y, \hat y) }{d \hat y}
=& \frac{d }{d \hat y} \left(-y \log(\hat y) -(1-y) \log(1-\hat y)\right) \\
=& - \frac{y}{\hat y}  +\frac{1-y}{1- \hat y} \\
=&  \frac{\hat y(1-y)-y(1- \hat y) }{\hat y (1- \hat y)}  \\
=&  \frac{\hat y -y + y\hat y +  -y \hat y)}{\hat y (1- \hat y)}  \\
=&  \frac{\hat y -y)}{\hat y (1- \hat y)}  \\
\frac{d \sigma(z) }{d z}
=& \frac{d  }{d z} \frac{1}{1+e^{-z}} \\
=& \sigma(z)(1-\sigma(z)) \\
=& \hat y(1-\hat y) \\
\end{split}
$$



#### derivative of the sigmoid function

$$
\begin{split}
\frac{d}{du}\sigma(u) 
&= \frac{d}{du} \frac{1}{1+e^{-u}} \\
&=  \frac{-1}{(1+e^{-u})^2} \cdot e^{-u} \cdot -1 \\
&=  \frac{e^{-u}}{1+e^{-u}} \frac{1}{1+e^{-u}}\\
&=  \frac{e^{-u}}{1+e^{-u}} \sigma(u)\\
&=  \frac{\frac{e^{-u}}{e^{-u}}}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \sigma(u)\\
&=  \frac{1}{e^{u}+1} \sigma(u)\\
&=  \sigma(-u) \sigma(u)\\
&=  (1-\sigma(u)) \sigma(u)\\
\end{split}
$$



### multi class classification
- let $y \in \mathbb{R}^n$ be true [[distribution]] and $\hat y  \in \mathbb{R}^n$ the model prediction in a multi class classification problem
- by minimizing the [[cross entropy]] between the label $y$ and the assumed [[distribution]] $\hat y$ we can train the model to match the true [[distribution]] 
- if $y$ is a one hot vector with the value with the index $c$ being the correct class the [[nn cross entropy loss]] simplifies

$$
\begin{split}
\ell(y, \hat y) 
&=  -\sum_i y_i \log(\hat y_i) \\
&=  -\log(\hat y_c) \\
\end{split}
$$

#### relationship to the softmax function
- when combining the [[nn cross entropy loss]] with a [[softmax function]] in the output layer, the [[gradient]] with respect to the [[logit]] $z$ with $\hat y=\mathrm{SOFTMAX}(z)$ simplifies to the following

$$
\nabla_z \ell(y, \hat y(z)) = \left(\frac{\partial \ell(y, \hat y(z)) }{\partial z}\right)^\top = \hat y -y
$$

$$
\begin{split}
\frac{\partial \ell(y, \hat y(z)) }{\partial z_j} 
&= \sum_i \frac{\partial \ell\left(y, \hat y\right) }{\partial \hat y_i} \frac{\partial \mathrm{SOFTMAX}(z)_i }{\partial z_j}  \\
&= \sum_i -  \frac{y_i}{\hat y_i} \hat y_j (\mathrm{I} \left[i=j\right]- \hat y_j)  \\
&= \sum_i   \frac{y_i \hat y_j \hat y_j - y_i \hat y_j \mathrm{I} \left[i=j\right]}{\hat y_i}   \\
&= \sum_i   \frac{y_i \hat y_j \hat y_j}{\hat y_i} - \sum_i   \frac{y_i \hat y_j \mathrm{I} \left[i=j\right]}{\hat y_i}   \\
&= \hat y_j - y_i  \\
\frac{\partial \mathrm{SOFTMAX}(z)_i }{\partial z_j}
&= \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]-\mathrm{SOFTMAX}(Z)_j\mathrm{SOFTMAX}(Z)_i\\
&=  \hat y_j (\mathrm{I} \left[i=j\right]- \hat y_j)  \\
\frac{\partial \ell\left(y, \hat y\right) }{\partial \hat y_i} 
&= -  \sum_i \frac{\partial  }{\partial \hat y_i}  y_i \log(\hat y_i) \\
&= -  \frac{y_i}{\hat y_i}   \\
\end{split}
$$


#### derivative of the softmax

$$
\begin{split}
\frac{\partial \mathrm{SOFTMAX}(Z)_i }{\partial Z_j}
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial \exp{(Z_{i})}}{\partial Z_j} \frac{1}{\sum_{k} \exp{(Z_{k})}}+ \exp{(Z_{i})}\frac{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}}{\partial Z_j} \\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \frac{\sum_{k} \exp{(Z_{k})}}{\partial Z_j}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \exp{(Z_{j})}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]-\mathrm{SOFTMAX}(Z)_j\mathrm{SOFTMAX}(Z)_i\\
=& \begin{cases}
\mathrm{SOFTMAX}(Z)_j (1- \mathrm{SOFTMAX}(Z)_j) & ,for\ i=j \\
-\mathrm{SOFTMAX}(Z)_j \mathrm{SOFTMAX}(Z)_i  & ,for\ i\neq j  \\
\end{cases}
\end{split}
$$



___________
### cross entropy
- [[cross entropy]] is a measure of the dissimilarity between two probability distributions: a **true distribution** $P$ and an **estimated (or assumed) distribution** $Q$
- It quantifies the **expected number of bits** needed to encode samples from $P$
  using a code that is optimized for $Q$
- It is defined as the **expected negative log-likelihood** under $Q$
  when the data is actually drawn from $P$

#### Continuous Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### Discrete Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### range
- The **minimum** cross-entropy is reached when $P=Q$ in which case it reduces to the **entropy** of $P$:

$$
H(P, Q) = H(P) \quad \text{if and only if} \quad P = Q
$$

- can go to infinity if there are regions where  $p(x) > 0$ but $q(x) = 0$ because $\log \left(q(x)\right)=\log \left(0\right) = -\infty$, and thus the expectation $-\mathbb{E}_{x \sim P}[\log q(x)]$ becomes infinite.

$$
\text{supp}(P) \nsubseteq \text{supp}(Q)
$$
### cross entropy of independent random variables

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\

\end{split}
$$
### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z)_i 
&= \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}}
\end{split}
$$

- used as output function in [[classification]] problems, for example with [[neural network]] and [[multinomial logistic regresssion]]

### sigmoid function
- the [[sigmoid function]] $\sigma: \mathbb{R} \to (0,1)$ is defined as follows:
- its the inverse of the [[logit function]]

$$
\sigma(u) = \frac{1}{1+e^{-u}}
$$

#### properties
$$
\sigma(0) = \frac{1}{2}
$$

$$
\begin{split}
\lim_{u\to\infty}\sigma(u) &= 1 \\
\lim_{u\to-\infty}\sigma(u) &= 0 \\
\end{split}
$$

$$
1-\sigma(u) = \frac{1}{1+e^{+u}} = \sigma(-u)
$$

###### proof


$$
\begin{split}
1-\sigma(u) 
&= 1-\frac{1}{1+e^{-u}} \\
&= \frac{1+e^{-u}}{1+e^{-u}}-\frac{1}{1+e^{-u}} \\
&= \frac{e^{-u}}{1+e^{-u}} \\
&= \frac{1}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \\
&= \frac{1}{e^{--u}+1} \\
&= \sigma(-u) \\
\end{split}
$$


Tags: mathematics WS2526 ml
<!--ID: 1764519362358-->
END



START
Basic
calculate the [[gradient]] with respect to the [[logit]] $z$ with $\hat y=\sigma(z)$ for the [[nn cross entropy loss]] with a [[softmax function]] in the output layer in a multi class classification


$$
\frac{d \ell(y, \hat y(z)) }{d z}
$$

Back: 
## cross entropy loss


### multi class classification
- let $y \in \mathbb{R}^n$ be true [[distribution]] and $\hat y  \in \mathbb{R}^n$ the model prediction in a multi class classification problem
- by minimizing the [[cross entropy]] between the label $y$ and the assumed [[distribution]] $\hat y$ we can train the model to match the true [[distribution]] 
- if $y$ is a one hot vector with the value with the index $c$ being the correct class the [[nn cross entropy loss]] simplifies

$$
\begin{split}
\ell(y, \hat y) 
&=  -\sum_i y_i \log(\hat y_i) \\
&=  -\log(\hat y_c) \\
\end{split}
$$

#### relationship to the softmax function
- when combining the [[nn cross entropy loss]] with a [[softmax function]] in the output layer, the [[gradient]] with respect to the [[logit]] $z$ with $\hat y=\mathrm{SOFTMAX}(z)$ simplifies to the following

$$
\nabla_z \ell(y, \hat y(z)) = \left(\frac{\partial \ell(y, \hat y(z)) }{\partial z}\right)^\top = \hat y -y
$$

$$
\begin{split}
\frac{\partial \ell(y, \hat y(z)) }{\partial z_j} 
&= \sum_i \frac{\partial \ell\left(y, \hat y\right) }{\partial \hat y_i} \frac{\partial \mathrm{SOFTMAX}(z)_i }{\partial z_j}  \\
&= \sum_i -  \frac{y_i}{\hat y_i} \hat y_j (\mathrm{I} \left[i=j\right]- \hat y_j)  \\
&= \sum_i   \frac{y_i \hat y_j \hat y_j - y_i \hat y_j \mathrm{I} \left[i=j\right]}{\hat y_i}   \\
&= \sum_i   \frac{y_i \hat y_j \hat y_j}{\hat y_i} - \sum_i   \frac{y_i \hat y_j \mathrm{I} \left[i=j\right]}{\hat y_i}   \\
&= \hat y_j - y_i  \\
\frac{\partial \mathrm{SOFTMAX}(z)_i }{\partial z_j}
&= \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]-\mathrm{SOFTMAX}(Z)_j\mathrm{SOFTMAX}(Z)_i\\
&=  \hat y_j (\mathrm{I} \left[i=j\right]- \hat y_j)  \\
\frac{\partial \ell\left(y, \hat y\right) }{\partial \hat y_i} 
&= -  \sum_i \frac{\partial  }{\partial \hat y_i}  y_i \log(\hat y_i) \\
&= -  \frac{y_i}{\hat y_i}   \\
\end{split}
$$


#### derivative of the softmax

$$
\begin{split}
\frac{\partial \mathrm{SOFTMAX}(Z)_i }{\partial Z_j}
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial }{\partial Z_j} \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}} \\
=& \frac{\partial \exp{(Z_{i})}}{\partial Z_j} \frac{1}{\sum_{k} \exp{(Z_{k})}}+ \exp{(Z_{i})}\frac{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}}{\partial Z_j} \\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \frac{\sum_{k} \exp{(Z_{k})}}{\partial Z_j}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]+ \frac{-\exp{(Z_{i})}}{\left(\sum_{k} \exp{(Z_{k})}\right)^{-2}} \exp{(Z_{j})}\\
=& \mathrm{SOFTMAX}(Z)_j \cdot \mathrm{I} \left[i=j\right]-\mathrm{SOFTMAX}(Z)_j\mathrm{SOFTMAX}(Z)_i\\
=& \begin{cases}
\mathrm{SOFTMAX}(Z)_j (1- \mathrm{SOFTMAX}(Z)_j) & ,for\ i=j \\
-\mathrm{SOFTMAX}(Z)_j \mathrm{SOFTMAX}(Z)_i  & ,for\ i\neq j  \\
\end{cases}
\end{split}
$$



### binary classification
- in a multi class problem with $n$ classes the $y \in \mathbb{R}^n$ has $n$ dimensions
- in a binary problem we just need one dimension ($y \in \mathbb{R}$) because $\mathbb{P}(Y=1) = 1-\mathbb{P}(Y=0)$

$$
\begin{split}
\ell(y, \hat y) 
&=  -y \log(\hat y) -(1-y) \log(1-\hat y) \\
\end{split}
$$

#### relationship to the sigmoid function
- when combining the [[nn cross entropy loss]] with a [[sigmoid function]] in the output layer, the [[gradient]] with respect to the [[logit]] $z$ with $\hat y=\sigma(z)$ simplifies to the following


$$
\frac{d \ell(y, \hat y(z)) }{d z} = \hat y -y
$$

$$
\begin{split}
\frac{d \ell(y, \hat y(z)) }{d z}
=& \frac{d \ell(y, \hat y) }{d \hat y} \frac{d \sigma(z) }{d z} \\
=& \frac{\hat y -y)}{\hat y (1- \hat y)} \hat y(1-\hat y)  \\
=& \hat y -y  \\
\frac{d \ell(y, \hat y) }{d \hat y}
=& \frac{d }{d \hat y} \left(-y \log(\hat y) -(1-y) \log(1-\hat y)\right) \\
=& - \frac{y}{\hat y}  +\frac{1-y}{1- \hat y} \\
=&  \frac{\hat y(1-y)-y(1- \hat y) }{\hat y (1- \hat y)}  \\
=&  \frac{\hat y -y + y\hat y +  -y \hat y)}{\hat y (1- \hat y)}  \\
=&  \frac{\hat y -y)}{\hat y (1- \hat y)}  \\
\frac{d \sigma(z) }{d z}
=& \frac{d  }{d z} \frac{1}{1+e^{-z}} \\
=& \sigma(z)(1-\sigma(z)) \\
=& \hat y(1-\hat y) \\
\end{split}
$$



#### derivative of the sigmoid function

$$
\begin{split}
\frac{d}{du}\sigma(u) 
&= \frac{d}{du} \frac{1}{1+e^{-u}} \\
&=  \frac{-1}{(1+e^{-u})^2} \cdot e^{-u} \cdot -1 \\
&=  \frac{e^{-u}}{1+e^{-u}} \frac{1}{1+e^{-u}}\\
&=  \frac{e^{-u}}{1+e^{-u}} \sigma(u)\\
&=  \frac{\frac{e^{-u}}{e^{-u}}}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \sigma(u)\\
&=  \frac{1}{e^{u}+1} \sigma(u)\\
&=  \sigma(-u) \sigma(u)\\
&=  (1-\sigma(u)) \sigma(u)\\
\end{split}
$$





___________
### cross entropy
- [[cross entropy]] is a measure of the dissimilarity between two probability distributions: a **true distribution** $P$ and an **estimated (or assumed) distribution** $Q$
- It quantifies the **expected number of bits** needed to encode samples from $P$
  using a code that is optimized for $Q$
- It is defined as the **expected negative log-likelihood** under $Q$
  when the data is actually drawn from $P$

#### Continuous Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### Discrete Case

$$
\begin{split}
H\left(P , Q \right) 
&= - \sum_{x \in \mathcal{X}} p(x) \log \left( q(x) \right) dx \\
&= - \mathbb{E}_p\left[\log \left( q(x) \right)\right] \\
\end{split}
$$

#### range
- The **minimum** cross-entropy is reached when $P=Q$ in which case it reduces to the **entropy** of $P$:

$$
H(P, Q) = H(P) \quad \text{if and only if} \quad P = Q
$$

- can go to infinity if there are regions where  $p(x) > 0$ but $q(x) = 0$ because $\log \left(q(x)\right)=\log \left(0\right) = -\infty$, and thus the expectation $-\mathbb{E}_{x \sim P}[\log q(x)]$ becomes infinite.

$$
\text{supp}(P) \nsubseteq \text{supp}(Q)
$$
### cross entropy of independent random variables

$$
\begin{split}
H\left(P , Q \right) 
&= - \int_\mathbb{R} p(x) \log \left( q(x) \right) dx \\

\end{split}
$$
### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z)_i 
&= \frac{\exp{(Z_{i})}}{\sum_{k} \exp{(Z_{k})}}
\end{split}
$$

- used as output function in [[classification]] problems, for example with [[neural network]] and [[multinomial logistic regresssion]]

### sigmoid function
- the [[sigmoid function]] $\sigma: \mathbb{R} \to (0,1)$ is defined as follows:
- its the inverse of the [[logit function]]

$$
\sigma(u) = \frac{1}{1+e^{-u}}
$$

#### properties
$$
\sigma(0) = \frac{1}{2}
$$

$$
\begin{split}
\lim_{u\to\infty}\sigma(u) &= 1 \\
\lim_{u\to-\infty}\sigma(u) &= 0 \\
\end{split}
$$

$$
1-\sigma(u) = \frac{1}{1+e^{+u}} = \sigma(-u)
$$

###### proof


$$
\begin{split}
1-\sigma(u) 
&= 1-\frac{1}{1+e^{-u}} \\
&= \frac{1+e^{-u}}{1+e^{-u}}-\frac{1}{1+e^{-u}} \\
&= \frac{e^{-u}}{1+e^{-u}} \\
&= \frac{1}{\frac{1}{e^{-u}}+\frac{e^{-u}}{e^{-u}}} \\
&= \frac{1}{e^{--u}+1} \\
&= \sigma(-u) \\
\end{split}
$$


Tags: mathematics WS2526 ml
<!--ID: 1764519362362-->
END
