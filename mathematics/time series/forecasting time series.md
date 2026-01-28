## forecasting time series
- given the observations $X_1, ..., X_n$ from a [[stationary process|stationary]] [[time series]] with zero mean
- the goal is to predict $X_{n+h}$ with the [[conditional expectation]] $\mathbb{E}\left[X_{n+h}| X_1, ..., X_n\right]$
- because the [[conditional expectation]] might be hard to predict often [[linear model]] are used

$$
\hat X_{n+h} = \sum_{i=1}^n x_i X_i 
$$
- the best linear predictor is the $X_{n+h}^*$ is the linear predictor that minimizes the [[mean square error]]

$$
\hat X_{n+h}^* = arg\min_g \mathbb{E}\left[\left(X_{n+h} - \sum_{i=1}^n x_i X_i\right)^2\right]
$$
# ----------------

![[time series#time series]]

# anki


START
Basic
- how can [[time series]] be forecasted: general framework
- optimal way plus approximation

Back: 
## forecasting time series
- given the observations $X_1, ..., X_n$ from a [[stationary process|stationary]] [[time series]] with zero mean
- the goal is to predict $X_{n+h}$ with the [[conditional expectation]] $\mathbb{E}\left[X_{n+h}| X_1, ..., X_n\right]$
- because the [[conditional expectation]] might be hard to predict often [[linear model]] are used

$$
\hat X_{n+h} = \sum_{i=1}^n x_i X_i 
$$

- the best linear predictor is the $X_{n+h}^*$ is the linear predictor that minimizes the [[mean square error]]

$$
\hat X_{n+h}^* = arg\min_g \mathbb{E}\left[\left(X_{n+h} - \sum_{i=1}^n x_i X_i\right)^2\right]
$$

Tags: mathematics time_series WS2425
<!--ID: 1734893934051-->
END
