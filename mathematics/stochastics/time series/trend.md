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

# -------
![[time series#additive model]]

# anki

START
Basic
[[trend]]
- definition
- two example models

Back: 
### trend
- the [[trend]] is a time variant and deterministic component in a [[time series]]
- in the following example the deterministic function $m(t)$ would be the [[trend]]

##### additive model

$$
X_t = m_t + s_t + c + e_t
$$

- time dependend deterministic [[trend]] $m_t$
- [[seasonality]] $s_t$
- error term $e_t$ (e.g. [[white noise]])
- [[drift]] (static term) $c$
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
<!--ID: 1735063121319-->
END
