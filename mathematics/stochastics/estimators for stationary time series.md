### mean estimators for stationary time series
- given an observation $X_1, ..., X_n$ from a [[stationary process|stationary]] [[time series]]
- the mean $\mu = \mathbb{E}[X_i]$ can be estimated with the following [[statistical estimator]]

$$
\hat X_n = \sum_{i \in [n]} X_i
$$
- $X_n$ is an [[estimator consitency#$ sqrt{n}$ consitency|root n consistent]] [[statistical estimator]] for 
- the [[statistical estimator]] converges in distribution to a [[normal distribution]]

$$
\sqrt{n} (X_n - \mu) \xrightarrow{\mathcal{D}} \mathcal{N}\left(0, \sum_{h = 1}^\infty \rho(h) \right)
$$

### autocorrelation estimators for stationary time series
- given an observation $X_1, ..., X_n$ from a [[stationary process|stationary]] [[time series]]
- the [[autocorrelation (ACF)]] $\rho(h)$ can be estimated with the following [[statistical estimator]] (for $h \leq n$)

$$
\hat\rho_n(h) = \frac{1}{n} \sum_{t=1}^{n-|h|} \left(X_t- X_n\right)\left(X_{t+h}- X_n\right)
$$

- under suitable assumptions $\hat\rho_n(h)$ is [[estimator consitency#$ sqrt{n}$ consitency|root n consistent]] and [[normal distribution]]

# -------------------

![[estimator consitency#$ sqrt{n}$ consitency]]

![[autocorrelation (ACF)#autocorrelation (ACF) for stationary processes]]


# anki



START
Basic
[[statistical estimator]] for the mean and [[autocorrelation (ACF)]] of [[stationary process|stationary]] [[time series]]
- what can be said about their [[estimator consitency]] and [[distribution]]

Back: 
### mean estimators for stationary time series
- given an observation $X_1, ..., X_n$ from a [[stationary process|stationary]] [[time series]]
- the mean $\mu = \mathbb{E}[X_i]$ can be estimated with the following [[statistical estimator]]

$$
\hat X_n = \sum_{i \in [n]} X_i
$$
- $X_n$ is an [[estimator consitency#$ sqrt{n}$ consitency|root n consistent]] [[statistical estimator]] for 
- the [[statistical estimator]] converges in distribution to a [[normal distribution]]

$$
\sqrt{n} (X_n - \mu) \xrightarrow{\mathcal{D}} \mathcal{N}\left(0, \sum_{h = 1}^\infty \rho(h) \right)
$$

### autocorrelation estimators for stationary time series
- given an observation $X_1, ..., X_n$ from a [[stationary process|stationary]] [[time series]]
- the [[autocorrelation (ACF)]] $\rho(h)$ can be estimated with the following [[statistical estimator]] (for $h \leq n$)

$$
\hat\rho_n(h) = \frac{1}{n} \sum_{t=1}^{n-|h|} \left(X_t- X_n\right)\left(X_{t+h}- X_n\right)
$$

- under suitable assumptions $\hat\rho_n(h)$ is [[estimator consitency#$ sqrt{n}$ consitency|root n consistent]] and [[normal distribution]]

________________

### autocorrelation (ACF) for stationary processes

$$
\begin{split}
\rho_{XX}(t_1, t_2) 
&= \rho_{XX}(t, t + h) \qquad \text{with } h = t_2-t_1\\
&= \rho_{XX}(h) \\
&= \frac{ \mathbb{COV}\left[X_{t}, X_{t - h}\right]}{\mathbb{VAR}\left[X_{t}\right]} 
\qquad \text{with arbitray } \tau, h
\end{split}
$$


### $\sqrt{n}$ consitency
- given a [[statistical estimator]] $T_n$ for a chracateristics $\tau(\vartheta)$
- $T_n$ is consistence if it [[convergence in probability|converges in probability]] against $\tau(\vartheta)$

$$
\forall \vartheta \in \Theta: 
\forall \epsilon > 0:  
\exists \delta > 0: 
\exists N: \forall n > N:
\exists C > 0:  
\mathbb{P}_\vartheta\left(\sqrt{n}||T_n - \tau(\vartheta)||
 \geq C \right) \leq \epsilon
$$

- or in [[stochasic landau notation]]:

$$
\begin{split}
\sqrt{n}\left(T_n  - \tau(\vartheta) \right)=  \mathcal{o}_{\mathbb{P}_\vartheta}(1) \\
T_n = \tau(\vartheta) + \mathcal{o}_{\mathbb{P}_\vartheta}\left(n^{-\frac{1}{2}}\right) \\
\end{split}
$$


Tags: mathematics time_series WS2425
<!--ID: 1734890698104-->
END
