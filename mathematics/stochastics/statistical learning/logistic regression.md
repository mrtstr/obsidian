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

##### model distribution

- for a given sample $x$ with out model the the following [[distribution]]

$$
\begin{split}
\mathcal{P}(y|x, \theta) 
&= \sigma\left(\theta^\top \varphi(x) \right)^y + \left(1-\sigma\left(\theta^\top \varphi(x) \right)\right)^y \\
&= \sigma\left( (-1)^{y+1}\theta^\top \varphi(x) \right)  \\
&= \frac{1}{1+e^{(-1)^y{\varphi}(x)^\top\theta}} \\
\end{split}
$$

##### maximum likelihood estimator

- for a [[training dataset]] $\{(x_1, y_1), ..., (x_m, y_m)\}$ we have the following [[log likelihood]] with the [[maximum likelihood estimator]] $\widehat \theta_{ML}$

$$
\begin{split}
\mathcal{L}(\theta) 
&= \sum_{i=1}^m \ln \mathcal{P}(y_i|x_i, \theta) \\
&= \sum_{i=1}^m \ln \sigma\left( (-1)^{y_i+1}\theta^\top \varphi(x_i) \right) \\
\end{split}
$$

$$
\widehat \theta_{ML} = \arg\min_\theta - \mathcal{L}(\theta) 
$$
##### decision boundary
- we can define the following **decision rule** using the fact that the [[sigmoid function]] $\sigma(u)$ is greater than $\frac{1}{2}$ if $u\geq0$ 

$$
\begin{split}
h_\theta(x) 
&= \begin{cases}
1, &if \ \mathcal{P}(y|x, \theta) \geq \frac{1}{2} \\
0, &else \\
\end{cases} \\
&= \begin{cases}
1, &if \ \theta^\top \varphi(x) \geq 0 \\
0, &if \ \theta^\top \varphi(x) < 0 \\
\end{cases} \\
\end{split}
$$

- since we have the following [[decision boundary]] $H$ that is separating the the feature space

$$
H(\theta) = \left\{ x :  \theta^\top \varphi(x) = 0\right\}
$$

- one one side of $H$ we have $\{x \in X : h_\theta(x)=1\}$ and on the other side $\{x \in X : h_\theta(x)=0\}$


##### ML formulation with the cross entropy
- with the [[cross entropy]] [[loss function]] we have the following with the model output $\hat y = \sigma\left( (-1)^{y+1}\theta^\top \varphi(x) \right)$

$$
\begin{split}
\mathrm{CE}(y, \hat y) 
&= - y \ln(\hat y) - (1-y) \ln(1-\hat y) \\
\end{split}
$$

- this is measuring the distance between the true distribution $y$ and the estimated distribution $\hat y$ 
- given a [[training dataset]] $\mathcal{D} = \{(x_1, y_1), ..., (x_m, y_m)\}$ we can train the model by minimizing the [[risk#empirical risk]] $\mathcal{\widehat R}(\theta)$ which is the mean [[cross entropy]] which is equivalent to the [[expectation]] of the [[cross entropy]] over the [[empirical distribution of a dataset]]

$$
\begin{split}
\mathcal{\widehat R}(\theta) 
&= \mathbb{E}_{(x, y) \sim P_\mathcal{D}}\left[\mathrm{CE}\left(y, \sigma\left( (-1)^{y+1}\theta^\top \varphi(x) \right)\right) \right] \\
&= \frac{1}{m} \sum_{i=1}^m \mathrm{CE}(y_i, \hat y_i)  \\
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
# ---------------


![[sigmoid function#sigmoid function]]

![[log likelihood#log likelihood]]



# anki

START
Basic
[[logistic regression]] summary
- definition
- two label conventions
- [[maximum likelihood estimator]] and how to calculate it
- how to prevent [[overfitting]]
Back: 
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
__________________

### log likelihood
- given a [[data distribution|dataset]] $\mathcal{D}$ then the [[log likelihood]] is defined as follows

$$
\begin{split}
\mathcal{L}(\theta)
&= \log\left(p(\mathcal{D}|\theta)\right) \\
&= \log\left(\prod_{(X_i, Y_i)\sim \mathcal{D}} p(X_i, Y_i|\theta)\right) \\
&= \sum_{(X_i, Y_i)\sim \mathcal{D}} \log\left( p(X_i, Y_i|\theta)\right) \\
\end{split}
$$


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
#### application
- often used to predict probabilities in binary [[classification]] problems, e.g. [[logistic regression]]

#### inverse of the sigmoid function
- the [[inverse function]] on the [[sigmoid function]] is the [[logit function]]

$$
\begin{split}
\sigma(\mathrm{logit}(p) ) 
&= \frac{1}{1+e^{-\log\left(\frac{p}{1-p}\right)}} \\
&= \frac{1}{1+\left(e^{\log\left(\frac{p}{1-p}\right)}\right)^{-1}} \\
&= \frac{1}{1+\frac{1-p}{p}} \\
&= \frac{1}{1+\frac{1}{p}-1} \\
&= p \\
\end{split}
$$

Tags: mathematics statistics SS25
<!--ID: 1752944639529-->
END


START
Basic
[[logistic regression]] with standard (0, 1) label convention
- model distribution
- maximum likelihood estimator (no closed form)
- decision boundary
- ML formulation with the cross entropy
Back: 
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

##### model distribution

- for a given sample $x$ with out model the the following [[distribution]]

$$
\begin{split}
\mathcal{P}(y|x, \theta) 
&= \sigma\left(\theta^\top \varphi(x) \right)^y + \left(1-\sigma\left(\theta^\top \varphi(x) \right)\right)^y \\
&= \sigma\left( (-1)^{y+1}\theta^\top \varphi(x) \right)  \\
&= \frac{1}{1+e^{(-1)^y{\varphi}(x)^\top\theta}} \\
\end{split}
$$

##### maximum likelihood estimator

- for a [[training dataset]] $\{(x_1, y_1), ..., (x_m, y_m)\}$ we have the following [[log likelihood]] with the [[maximum likelihood estimator]] $\widehat \theta_{ML}$

$$
\begin{split}
\mathcal{L}(\theta) 
&= \sum_{i=1}^m \ln \mathcal{P}(y_i|x_i, \theta) \\
&= \sum_{i=1}^m \ln \sigma\left( (-1)^{y_i+1}\theta^\top \varphi(x_i) \right) \\
\end{split}
$$

$$
\widehat \theta_{ML} = \arg\min_\theta - \mathcal{L}(\theta) 
$$
##### decision boundary
- we can define the following **decision rule** using the fact that the [[sigmoid function]] $\sigma(u)$ is greater than $\frac{1}{2}$ if $u\geq0$ 

$$
\begin{split}
h_\theta(x) 
&= \begin{cases}
1, &if \ \mathcal{P}(y|x, \theta) \geq \frac{1}{2} \\
0, &else \\
\end{cases} \\
&= \begin{cases}
1, &if \ \theta^\top \varphi(x) \geq 0 \\
0, &if \ \theta^\top \varphi(x) < 0 \\
\end{cases} \\
\end{split}
$$

- since we have the following [[decision boundary]] $H$ that is separating the the feature space

$$
H(\theta) = \left\{ x :  \theta^\top \varphi(x) = 0\right\}
$$

- one one side of $H$ we have $\{x \in X : h_\theta(x)=1\}$ and on the other side $\{x \in X : h_\theta(x)=0\}$


##### ML formulation with the cross entropy
- with the [[cross entropy]] [[loss function]] we have the following with the model output $\hat y = \sigma\left( (-1)^{y+1}\theta^\top \varphi(x) \right)$

$$
\begin{split}
\mathrm{CE}(y, \hat y) 
&= - y \ln(\hat y) - (1-y) \ln(1-\hat y) \\
\end{split}
$$

- this is measuring the distance between the true distribution $y$ and the estimated distribution $\hat y$ 
- given a [[training dataset]] $\mathcal{D} = \{(x_1, y_1), ..., (x_m, y_m)\}$ we can train the model by minimizing the [[risk#empirical risk]] $\mathcal{\widehat R}(\theta)$ which is the mean [[cross entropy]] which is equivalent to the [[expectation]] of the [[cross entropy]] over the [[empirical distribution of a dataset]]

$$
\begin{split}
\mathcal{\widehat R}(\theta) 
&= \mathbb{E}_{(x, y) \sim P_\mathcal{D}}\left[\mathrm{CE}\left(y, \sigma\left( (-1)^{y+1}\theta^\top \varphi(x) \right)\right) \right] \\
&= \frac{1}{m} \sum_{i=1}^m \mathrm{CE}(y_i, \hat y_i)  \\
\end{split}
$$


__________________

### log likelihood
- given a [[data distribution|dataset]] $\mathcal{D}$ then the [[log likelihood]] is defined as follows

$$
\begin{split}
\mathcal{L}(\theta)
&= \log\left(p(\mathcal{D}|\theta)\right) \\
&= \log\left(\prod_{(X_i, Y_i)\sim \mathcal{D}} p(X_i, Y_i|\theta)\right) \\
&= \sum_{(X_i, Y_i)\sim \mathcal{D}} \log\left( p(X_i, Y_i|\theta)\right) \\
\end{split}
$$


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
#### application
- often used to predict probabilities in binary [[classification]] problems, e.g. [[logistic regression]]

#### inverse of the sigmoid function
- the [[inverse function]] on the [[sigmoid function]] is the [[logit function]]

$$
\begin{split}
\sigma(\mathrm{logit}(p) ) 
&= \frac{1}{1+e^{-\log\left(\frac{p}{1-p}\right)}} \\
&= \frac{1}{1+\left(e^{\log\left(\frac{p}{1-p}\right)}\right)^{-1}} \\
&= \frac{1}{1+\frac{1-p}{p}} \\
&= \frac{1}{1+\frac{1}{p}-1} \\
&= p \\
\end{split}
$$

Tags: mathematics statistics SS25

END


START
Basic
[[logistic regression]] with standard (0, 1) label convention
- loss function with [[cross entropy]] and relationship to the [[risk#empirical risk]] and [[risk]]
Back: 

### ML formulation with the cross entropy
- with the [[cross entropy]] [[loss function]] we have the following with the model output $\hat y = \sigma\left( (-1)^{y+1}\theta^\top \varphi(x) \right)$

$$
\begin{split}
\mathrm{CE}(y, \hat y) 
&= - y \ln(\hat y) - (1-y) \ln(1-\hat y) \\
\end{split}
$$

- this is measuring the distance between the true distribution $y$ and the estimated distribution $\hat y$ 
- given a [[training dataset]] $\mathcal{D} = \{(x_1, y_1), ..., (x_m, y_m)\}$ we can train the model by minimizing the [[risk#empirical risk]] $\mathcal{\widehat R}(\theta)$ which is the mean [[cross entropy]] which is equivalent to the [[expectation]] of the [[cross entropy]] over the [[empirical distribution of a dataset]]

$$
\begin{split}
\mathcal{\widehat R}(\theta) 
&= \mathbb{E}_{(x, y) \sim P_\mathcal{D}}\left[\mathrm{CE}\left(y, \sigma\left( (-1)^{y+1}\theta^\top \varphi(x) \right)\right) \right] \\
&= \frac{1}{m} \sum_{i=1}^m \mathrm{CE}(y_i, \hat y_i)  \\
\end{split}
$$


### risk
- the [[risk]] is the [[expectation|expected]] [[loss function|loss]] over the entire [[data distribution]] $\mathcal{P}_{XY}$
- given a [[loss function]] $L(y, \hat{y})$ the [[risk]] is defined as following

$$
\begin{split}
\mathcal{R}(\theta) 
&= \mathbb{E}_{(x,y) \sim \mathcal{P}_{XY}}\left[L\left(f_\theta(x), y\right)\right] \\
\end{split}
$$

### empirical risk
- the empirical [[risk]] is the approximation of the true [[risk]] and using the [[training dataset]] $\mathcal{D}_{train}=\{(x_i, y_i): i \in [n]\}$

$$
\begin{split}
\mathcal{\hat{R}}(\theta) 
&= \frac{1}{n} \sum_{i=1}^n L\left(f_\theta(x_i), y_i\right) \\
\end{split}
$$


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

##### model distribution

- for a given sample $x$ with out model the the following [[distribution]]

$$
\begin{split}
\mathcal{P}(y|x, \theta) 
&= \sigma\left(\theta^\top \varphi(x) \right)^y + \left(1-\sigma\left(\theta^\top \varphi(x) \right)\right)^y \\
&= \sigma\left( (-1)^{y+1}\theta^\top \varphi(x) \right)  \\
&= \frac{1}{1+e^{(-1)^y{\varphi}(x)^\top\theta}} \\
\end{split}
$$

##### maximum likelihood estimator

- for a [[training dataset]] $\{(x_1, y_1), ..., (x_m, y_m)\}$ we have the following [[log likelihood]] with the [[maximum likelihood estimator]] $\widehat \theta_{ML}$

$$
\begin{split}
\mathcal{L}(\theta) 
&= \sum_{i=1}^m \ln \mathcal{P}(y_i|x_i, \theta) \\
&= \sum_{i=1}^m \ln \sigma\left( (-1)^{y_i+1}\theta^\top \varphi(x_i) \right) \\
\end{split}
$$

$$
\widehat \theta_{ML} = \arg\min_\theta - \mathcal{L}(\theta) 
$$
##### decision boundary
- we can define the following **decision rule** using the fact that the [[sigmoid function]] $\sigma(u)$ is greater than $\frac{1}{2}$ if $u\geq0$ 

$$
\begin{split}
h_\theta(x) 
&= \begin{cases}
1, &if \ \mathcal{P}(y|x, \theta) \geq \frac{1}{2} \\
0, &else \\
\end{cases} \\
&= \begin{cases}
1, &if \ \theta^\top \varphi(x) \geq 0 \\
0, &if \ \theta^\top \varphi(x) < 0 \\
\end{cases} \\
\end{split}
$$

- since we have the following [[decision boundary]] $H$ that is separating the the feature space

$$
H(\theta) = \left\{ x :  \theta^\top \varphi(x) = 0\right\}
$$

- one one side of $H$ we have $\{x \in X : h_\theta(x)=1\}$ and on the other side $\{x \in X : h_\theta(x)=0\}$




__________________

### log likelihood
- given a [[data distribution|dataset]] $\mathcal{D}$ then the [[log likelihood]] is defined as follows

$$
\begin{split}
\mathcal{L}(\theta)
&= \log\left(p(\mathcal{D}|\theta)\right) \\
&= \log\left(\prod_{(X_i, Y_i)\sim \mathcal{D}} p(X_i, Y_i|\theta)\right) \\
&= \sum_{(X_i, Y_i)\sim \mathcal{D}} \log\left( p(X_i, Y_i|\theta)\right) \\
\end{split}
$$


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
#### application
- often used to predict probabilities in binary [[classification]] problems, e.g. [[logistic regression]]

#### inverse of the sigmoid function
- the [[inverse function]] on the [[sigmoid function]] is the [[logit function]]

$$
\begin{split}
\sigma(\mathrm{logit}(p) ) 
&= \frac{1}{1+e^{-\log\left(\frac{p}{1-p}\right)}} \\
&= \frac{1}{1+\left(e^{\log\left(\frac{p}{1-p}\right)}\right)^{-1}} \\
&= \frac{1}{1+\frac{1-p}{p}} \\
&= \frac{1}{1+\frac{1}{p}-1} \\
&= p \\
\end{split}
$$

Tags: mathematics statistics SS25

END