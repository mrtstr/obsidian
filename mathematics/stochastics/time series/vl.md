# Mathematical Statistics Notes
## Introduction
The Black-Scholes model is given as:

$$

R_t = e^{t\mu + \sigma W_t}, \quad t \geq 0,

$$
where $W_t$ is standard Brownian motion.

### Discretization and Log-Returns
Assume we have discretized observations for $T$ days with $m$ observations per day, i.e., $t_1, t_2, \dots, t_{N_T}$ with sample size $N_T$. The corresponding log-returns at this higher frequency scale are:

$$

\log R_t = \Delta t \cdot \mu - \frac{1}{2}\sigma^2 + \sigma \epsilon_t, \quad t = 1, \dots, N_T,

$$
where $\epsilon_t \sim \text{i.i.d. } N(0, 1)$.

## Estimating Parameters

Our goal is to estimate $\sigma$ and especially $\mu$. An obvious estimator for $\sigma$ is:
$$

\hat{\sigma}^2 = \frac{1}{T} \sum_{t=1}^{N_T} (\log R_t - \bar{\log R})^2,

$$
where $\bar{\log R}$ is the mean log-return.
### Realized Volatility

Ignoring higher-order terms, we suggest an estimator for realized volatility:

$$

\text{RV} = \sum_{t=1}^{N_T} (\Delta R_t)^2.

$$
## Non-Parametric Estimation

Consider the log-returns given by:
$$

X_{t,n} = \mu_t \Delta t + \sigma_t \epsilon_t,

$$

where $\mu_t$ and $\sigma_t$ depend on time.

### Smoothing

To estimate $\sigma_t$, we use a kernel smoothing approach:

$$

\hat{\sigma}^2(t) = \sum_{i=1}^n K_h(t - t_i) X_i^2,

$$
where $K_h$ is a kernel function and $h > 0$ is the bandwidth.

## Bias-Variance Tradeoff
The observations describe the bias-variance tradeoff, which typically appears in non-parametric statistics. The solution is a sample-size-dependent choice of the bandwidth $h$:

$$

h \to 0 \quad \text{to minimize bias}, \quad n \to \infty \quad \text{to minimize variance}.

$$
## Kernel-Based Estimation
Kernel-based estimators are defined as:
$$

\hat{\sigma}^2(t) = \frac{1}{h} \sum_{i=1}^n K\left(\frac{t - t_i}{h}\right) X_i^2,

$$
where $K$ is a symmetric probability density function.