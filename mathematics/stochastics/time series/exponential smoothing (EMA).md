#### exponential smoothing (EMA)
- [[smoothing]] method for [[time series]] that is only based on the past (asymmetric)

$$
\begin{split}
\hat m_t 
&= \sum_{i=0}^\infty w_i X_{t-i} \quad \text{ with } w_i = \alpha^i (1-\alpha) \\
&= (1-\alpha) X_t + \alpha (1-\alpha)\sum_{i=0}^\infty w_i X_{t-i-1} \\
&= (1-\alpha) X_t +\alpha m_{t-1} \\
\end{split}
$$

$$
\begin{split}
\sum_{i=0}^\infty   \alpha^i (1-\alpha) 
&= (1-\alpha) \sum_{i=0}^\infty   \alpha^i \\
&=   \frac{1-\alpha }{1-\alpha } \\
&=   1 \\
\end{split}
$$

# ---------
![[smoothing#smoothing]]

![[geometric series#geometric series]]


# anki

START
Basic
[[exponential smoothing (EMA)]]
- closed form and recursive
- proof that its normalized

Back: 
#### exponential smoothing (EMA)
- [[smoothing]] method for [[time series]] that is only based on the past (asymmetric)
$$
\begin{split}
\hat m_t 
&= \sum_{i=0}^\infty w_i X_{t-i} \quad \text{ with } w_i = \alpha^i (1-\alpha) \\
&= (1-\alpha) X_t + \alpha (1-\alpha)\sum_{i=0}^\infty w_i X_{t-i-1} \\
&= (1-\alpha) X_t +\alpha m_{t-1} \\
\end{split}
$$

$$
\begin{split}
\sum_{i=0}^\infty   \alpha^i (1-\alpha) 
&= (1-\alpha) \sum_{i=0}^\infty   \alpha^i \\
&=   \frac{1-\alpha }{1-\alpha } \\
&=   1 \\
\end{split}
$$

___________

### geometric series
geometric [[series]] 

$$
\sum_{k=1}^\infty q^k = \frac{1}{1-q}
$$

Tags: mathematics time_series WS2425
<!--ID: 1737311250713-->
END
