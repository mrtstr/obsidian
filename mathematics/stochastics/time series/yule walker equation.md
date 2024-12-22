### yule walker equation
- for [[statistical estimator|estimating]] the parameters $a_1, ..., a_p$ of an [[autoregresive (AR) model]]

- fo $h > 0$
$$
\begin{split}
\rho_{X}(h) 
&= a_1 \rho_{X}(h-1) + a_2 \rho_{X}(h-2) + ... + a_p \rho_{X}(h-p) \\
&= \sum_{i=1}^p a_i \rho_{X}(h-i)  \\
\end{split}
$$

- fo $h = 0$
$$
\begin{split}
\rho_{X}(0) - \sigma^2_e
&= \sum_{i=1}^p a_i \rho_{X}(0-i)  \\
\end{split}
$$
- this can be writting as the following [[linear map|linear]] [[matrix]] equation which can be solved for the parameter vector $A$

$$
\begin{split}
RA = r \Leftrightarrow A = R^{-1}r
\end{split}
$$

$$
\begin{split}
A &= \left(\begin{matrix}
a_1 & ... & a_p
\end{matrix}\right) \\
r &= (\rho(r))_{r \in [n]} = \left(\begin{matrix}
\rho(1) & ... & \rho(p)
\end{matrix}\right) \\
R &= (\rho(r-s))_{r, s \in [n]} \left(\begin{matrix}
1 & \rho(1) & ... & \rho(p-1) \\
\rho(1) & 1 & ... & \rho(p-2) \\
 &  & ... & \ \\
 \rho(p-1) & \rho(p-2) & ... & 1 \\
\end{matrix}\right)
\end{split}
$$

### deriving the yule walker equation
- with $\mathbb{E}\left[X_{t} e_{t-h}\right]=\sigma^2_e$ if $h=0$ and zero if not

$$
\begin{split}
X_t 
&=  a_1 X_{t-1} + a_2 X_{t-2} + ... + a_p X_{t-p} + e_t \\
&=  \sum_{i=1}^p a_i X_{t-i} + e_t \\
\mathbb{COV}\left[X_t, X_{t-h}\right] 
&= \mathbb{E}\left[X_tX_{t-h}\right] - 0 \\
&= \sum_{i=1}^p a_i \mathbb{E}\left[X_{t} X_{t-h-i}\right]  + \mathbb{E}\left[X_{t} e_{t-h}\right]\\
&=  \sum_{i=0}^p a_i \mathbb{COV}\left[X_t, X_{t-h-i}\right] + \mathbb{E}\left[X_{t} e_{t-h}\right] \\
\mathbb{COR}\left[X_t, X_{t-h}\right] 
&= \sum_{i=0}^p a_i \mathbb{COR}\left[X_t, X_{t-h-i}\right] + \mathbb{E}\left[X_{t} e_{t-h}\right] \\ 
\rho_{X}(h)
&= \sum_{i=0}^p a_i \rho_{X}(h+i) + \mathbb{E}\left[X_{t} e_{t-h}\right]  \\
&= \sum_{i=0}^p a_i \rho_{X}(h-i) + \mathbb{E}\left[X_{t} e_{t-h}\right] \quad \text{(stationarity)} \\
\end{split}
$$


# -----------------------

![[autocorrelation (ACF)#autocorrelation (ACF) for stationary processes]]

![[autoregresive (AR) model#autoregresive (AR) model]]

# anki

START
Basic
[[yule walker equation]]
- what are they used for
- definition
- matrix form
Back: 
### yule walker equation
- for [[statistical estimator|estimating]] the parameters $a_1, ..., a_p$ of an [[autoregresive (AR) model]]

- fo $h > 0$
$$
\begin{split}
\rho_{X}(h) 
&= a_1 \rho_{X}(h-1) + a_2 \rho_{X}(h-2) + ... + a_p \rho_{X}(h-p) \\
&= \sum_{i=1}^p a_i \rho_{X}(h-i)  \\
\end{split}
$$

- fo $h = 0$
$$
\begin{split}
\rho_{X}(0) - \sigma^2_e
&= \sum_{i=1}^p a_i \rho_{X}(0-i)  \\
\end{split}
$$
- this can be writting as the following [[linear map|linear]] [[matrix]] equation which can be solved for the parameter vector $A$
$$
\begin{split}
RA = r \Leftrightarrow A = R^{-1}r
\end{split}
$$

$$
\begin{split}
A &= \left(\begin{matrix}
a_1 & ... & a_p
\end{matrix}\right) \\
r &= \left(\begin{matrix}
\rho(1) & ... & \rho(p)
\end{matrix}\right) \\
R &= \left(\begin{matrix}
1 & \rho(1) & ... & \rho(p-1) \\
\rho(1) & 1 & ... & \rho(p-2) \\
 &  & ... & \ \\
 \rho(p-1) & \rho(p-2) & ... & 1 \\
\end{matrix}\right)
\end{split}
$$

### deriving the yule walker equation
- with $\mathbb{E}\left[X_{t} e_{t-h}\right]=\sigma^2_e$ if $h=0$ and zero if not

$$
\begin{split}
X_t 
&=  a_1 X_{t-1} + a_2 X_{t-2} + ... + a_p X_{t-p} + e_t \\
&=  \sum_{i=1}^p a_i X_{t-i} + e_t \\
\mathbb{COV}\left[X_t, X_{t-h}\right] 
&= \mathbb{E}\left[X_tX_{t-h}\right] - 0 \\
&= \sum_{i=1}^p a_i \mathbb{E}\left[X_{t} X_{t-h-i}\right]  + \mathbb{E}\left[X_{t} e_{t-h}\right]\\
&=  \sum_{i=0}^p a_i \mathbb{COV}\left[X_t, X_{t-h-i}\right] + \mathbb{E}\left[X_{t} e_{t-h}\right] \\
\mathbb{COR}\left[X_t, X_{t-h}\right] 
&= \sum_{i=0}^p a_i \mathbb{COR}\left[X_t, X_{t-h-i}\right] + \mathbb{E}\left[X_{t} e_{t-h}\right] \\ 
\rho_{X}(h)
&= \sum_{i=0}^p a_i \rho_{X}(h+i) + \mathbb{E}\left[X_{t} e_{t-h}\right]  \\
&= \sum_{i=0}^p a_i \rho_{X}(h-i) + \mathbb{E}\left[X_{t} e_{t-h}\right] \quad \text{(stationarity)} \\
\end{split}
$$

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

### autoregresive (AR) model
- The [[autoregresive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]

models the [[time series]]
- with parameters $a_1, ..., a_p$
- [[white noise]] $e$ (i.i.d. with $\mathbb{E}[e] =0$ and $\mathbb{VAR}[e_t] \in (0, \infty)$)
- constant $\beta$ (sometimes assumed to be zero)

$$
X_t = \sum_{i=1}^p a_i X_{t-i} + \beta + e_t
$$



Tags: mathematics time_series WS2425
<!--ID: 1734801203329-->
END



START
Basic
deriving the [[yule walker equation]]
Back: 

### yule walker equation
- for [[statistical estimator|estimating]] the parameters $a_1, ..., a_p$ of an [[autoregresive (AR) model]]

- fo $h > 0$
$$
\begin{split}
\rho_{X}(h) 
&= a_1 \rho_{X}(h-1) + a_2 \rho_{X}(h-2) + ... + a_p \rho_{X}(h-p) \\
&= \sum_{i=1}^p a_i \rho_{X}(h-i)  \\
\end{split}
$$

- fo $h = 0$
$$
\begin{split}
\rho_{X}(0) - \sigma^2_e
&= \sum_{i=1}^p a_i \rho_{X}(0-i)  \\
\end{split}
$$
- this can be writting as the following [[linear map|linear]] [[matrix]] equation which can be solved for the parameter vector $A$
$$
\begin{split}
RA = r \Leftrightarrow A = R^{-1}r
\end{split}
$$
$$
\begin{split}
A &= \left(\begin{matrix}
a_1 & ... & a_p
\end{matrix}\right) \\
r &= (\rho(r))_{r \in [n]} = \left(\begin{matrix}
\rho(1) & ... & \rho(p)
\end{matrix}\right) \\
R &= (\rho(r-s))_{r, s \in [n]} \left(\begin{matrix}
1 & \rho(1) & ... & \rho(p-1) \\
\rho(1) & 1 & ... & \rho(p-2) \\
 &  & ... & \ \\
 \rho(p-1) & \rho(p-2) & ... & 1 \\
\end{matrix}\right)
\end{split}
$$

### deriving the yule walker equation
- with $\mathbb{E}\left[X_{t} e_{t-h}\right]=\sigma^2_e$ if $h=0$ and zero if not

$$
\begin{split}
X_t 
&=  a_1 X_{t-1} + a_2 X_{t-2} + ... + a_p X_{t-p} + e_t \\
&=  \sum_{i=1}^p a_i X_{t-i} + e_t \\
\mathbb{COV}\left[X_t, X_{t-h}\right] 
&= \mathbb{E}\left[X_tX_{t-h}\right] - 0 \\
&= \sum_{i=1}^p a_i \mathbb{E}\left[X_{t} X_{t-h-i}\right]  + \mathbb{E}\left[X_{t} e_{t-h}\right]\\
&=  \sum_{i=0}^p a_i \mathbb{COV}\left[X_t, X_{t-h-i}\right] + \mathbb{E}\left[X_{t} e_{t-h}\right] \\
\mathbb{COR}\left[X_t, X_{t-h}\right] 
&= \sum_{i=0}^p a_i \mathbb{COR}\left[X_t, X_{t-h-i}\right] + \mathbb{E}\left[X_{t} e_{t-h}\right] \\ 
\rho_{X}(h)
&= \sum_{i=0}^p a_i \rho_{X}(h+i) + \mathbb{E}\left[X_{t} e_{t-h}\right]  \\
&= \sum_{i=0}^p a_i \rho_{X}(h-i) + \mathbb{E}\left[X_{t} e_{t-h}\right] \quad \text{(stationarity)} \\
\end{split}
$$

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

### autoregresive (AR) model
- The [[autoregresive (AR) model]] of order $p$ $AP(p)$ assumes the captures the linear releationship of the current value to the past p $p$ values
- assumes an at least [[stationary process]]

models the [[time series]]
- with parameters $a_1, ..., a_p$
- [[white noise]] $e$ (i.i.d. with $\mathbb{E}[e] =0$ and $\mathbb{VAR}[e_t] \in (0, \infty)$)
- constant $\beta$ (sometimes assumed to be zero)

$$
X_t = \sum_{i=1}^p a_i X_{t-i} + \beta + e_t
$$



Tags: mathematics time_series WS2425
<!--ID: 1734801203334-->
END
