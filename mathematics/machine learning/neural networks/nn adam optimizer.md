
### adam optimizer
- adaptive moment estimation optimizer ([[nn adam optimizer]]) has the following update rule
- $\hat  m_t$ is the exponential moving average (first moment estimate) of past gradients (bias corrected)
- $\hat  v_t$ is the exponential moving average (second moment estimate) of past squared gradients (bias corrected)
- $\eta(t)$ is the (possibly time-dependent) learning rate.

$$
\theta_{t+1} = \theta_t - \eta(t) \frac{\hat  m_t}{\sqrt{\hat v_t}+\epsilon}
$$

#### intuition
- taking the average $\hat  m_t$ of the past [[gradient|gradients]] instead of taking the [[gradient|gradients]] itself makes the updates more stable and less noisy 
- the second moment $\hat  v_t$ approximates the [[variance]] of the [[gradient|gradients]] scales down the updates then the gradients are changing a lot


# anki

START
Basic
[[nn adam optimizer]]
- update rule and intuition

Back: 
### adam optimizer
- adaptive moment estimation optimizer ([[nn adam optimizer]]) has the following update rule
- $\hat  m_t$ is the exponential moving average (first moment estimate) of past gradients (bias corrected)
- $\hat  v_t$ is the exponential moving average (second moment estimate) of past squared gradients (bias corrected)
- $\eta(t)$ is the (possibly time-dependent) learning rate.

$$
\theta_{t+1} = \theta_t - \eta(t) \frac{\hat  m_t}{\sqrt{\hat v_t}+\epsilon}
$$

#### intuition
- taking the average $\hat  m_t$ of the past [[gradient|gradients]] instead of taking the [[gradient|gradients]] itself makes the updates more stable and less noisy 
- the second moment $\hat  v_t$ approximates the [[variance]] of the [[gradient|gradients]] scales down the updates then the gradients are changing a lot

Tags: ml WS2526
<!--ID: 1763995026497-->
END
