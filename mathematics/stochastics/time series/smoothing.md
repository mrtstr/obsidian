### smooting
- methods for extracting a underlaying patter from a [[time series]] by removing [[white noise|noise]]
- can be interpreted as a [[trend]] [[statistical estimator|estimator]]

### examples

![[weighted mean smoothing#rolling mean smoothing]]

![[exponential smoothing (EMA)#exponential smoothing (EMA)]]

![[kernel smoothing for time series#kernel smoothing for time series]]

# -----------

![[trend#trend]]

![[trend#trend models]]
# anki

START
Basic
[[smoothing]] for [[time series]]
- definition
- 3 examples

Back: 
### smooting
- methods for extracting a underlaying patter from a [[time series]] by removing [[white noise|noise]]
- can be interpreted as a [[trend]] [[statistical estimator|estimator]]

#### rolling mean smoothing
- with $\sum_{i=-k}^k \theta_i=1$ e.g. $\theta_i=\frac{1}{2k+1}$

$$
\hat m_t = \sum_{i=-k}^k \theta_i X_{t+i}
$$

#### exponential smoothing (EMA)

$$
\hat m_t = (1-\alpha) X_t +\alpha m_{t-1}
$$


### kernel smoothing for time series
- generalized [[weighted mean smoothing]] with a shifted and scaled [[kernel function (statistics)]] $K: [-1,1] \to [0, \infty)$ for weighting the samples


$$
\hat X_t=\frac{1}{nh} \frac{1}{\sum_{i=1}^n  K\left(\frac{t-t_i}{h}\right)} \sum_{i=1}^n X_{t_i} K\left(\frac{t-t_i}{h}\right)
$$


______

### trend
- the [[trend]] is a time variant and deterministic component in a [[time series]]
- in the following [[time series#additive model|additive mode]] the deterministic function $m(t)$ would be the [[trend]]

### trend models
- the trend can interpreted a some kind of [[smoothing]] by fitting a deterministic function to the values
#### simple linear trend
$$
m_t = \theta t 
$$
#### general linear trend model

$$
m_t = \sum_{i=0}^k \theta_i \tilde m_t(i) 
$$

- e.g. [[polynomial]] with $\tilde m_t(i) = t^i$


Tags: mathematics time_series WS2425
<!--ID: 1735063121303-->
END
