### uncertainty quantification
- let $X^*$ be a [[random variable]] that contains all the information relevant for another [[random variable]] $Y$ at the time of the forecast
- let $X$ be the features used for training the model
- in that setting $\mathbb{P}\left(Y | X^* \right) = \epsilon$ would be the unavoidable uncertainty called the [[white noise]]
- the model uncertainty would be based of the conditional [[probability measure]] $\mathbb{P}\left(Y | X, f \right)$ that has only a subset of all information available and suffers from model imperfections


![[white noise#white noise]]


# anki

START
Basic
- define the concepts of model uncertainty and noise in a forecast

Back: 
### uncertainty quantification
- let $X^*$ be a [[random variable]] that contains all the information relevant for another [[random variable]] $Y$ at the time of the forecast
- let $X$ be the features used for training the model
- in that setting $\mathbb{P}\left(Y | X^* \right) = \epsilon$ would be the unavoidable uncertainty called the [[white noise]]
- the model uncertainty would be based of the conditional [[probability measure]] $\mathbb{P}\left(Y | X, f \right)$ that has only a subset of all information available and suffers from model imperfections

_______________

### white noise
[[time series]] $(e_t, t \in \mathbb{Z})$ with 
- zero mean $\mathbb{E}[e_t] = 0$  
- [[correlation|uncorralated]] values $t \neq s \Rightarrow  \mathbb{COV}[e_t, e_s] = \mathbb{COR}[e_t, e_s] = 0$

#### independent white noise
- if $e_t$ are [[stochastic independent]]

#### i.i.d white noise
- if $e_t$ are i.i.d
#### gaussian white noise
- [[white noise]] with [[normal distribution|normal distributed]] values $e_t \sim \mathcal{N}(0, \sigma^2)$
- gaussian white noise is always i.i.d whilte noise


Tags: mathematics statistics SS25
<!--ID: 1746506622145-->
END