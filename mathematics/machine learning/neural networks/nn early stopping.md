### early stopping
- estimate the true [[risk]] using a validation dataset $\mathcal{V}$ 
- stop when the validation errors stopped improving → prevents over-fitting
- additional parameters: 
	- **evaluation interval** $a$: evaluate each $a$ steps
	- **patience** $g$: step when $g$ steps not validation error improvement

#### regularization effect

#### comparison to l2 regularization
- if we stop early after $t$ steps we have the equivalent effect that we have with [[nn l2 regularization]] with a factor of $\gamma$ and a learning rate of $\alpha$

$$
\begin{split}
\mathcal{w}_\gamma 
&= Q(\Lambda +I\gamma)^{-1}\Lambda Q^\top\widehat{\mathcal{w}} \\
Q^\top\mathcal{w}_\gamma 
&= (\Lambda +I\gamma)^{-1}\Lambda Q^\top\widehat{\mathcal{w}} \\
&= Q^\top \mathcal{w}^{(t)}  \\
&= \left( I - \left(I -\alpha \Lambda\right)^t \right)  Q^\top\widehat{\mathcal{w}}   \\ 
\Rightarrow (\Lambda +I\gamma)^{-1}\Lambda &= I - \left(I -\alpha \Lambda\right)^t \\
\Rightarrow \frac{\lambda_i }{\lambda_i+ \gamma} &= 1 - \left(1 -\alpha \lambda_i\right)^t \\
\Rightarrow  \left(1 -\alpha \lambda_i\right)^t
&= 1 - \frac{\lambda_i }{\lambda_i+ \gamma} \\
&= \frac{\lambda_i+ \gamma - \lambda_i }{\lambda_i+ \gamma} \\
&= \frac{ \gamma  }{\lambda_i+ \gamma} \\
\Rightarrow t \underbrace{\ln\left(1 -\alpha \lambda_i\right)}_{\approx-\alpha\lambda_i}
&= \ln\left(\frac{ \gamma  }{\lambda_i+ \gamma}\right) \\
&= \underbrace{\ln\left(\frac{ 1  }{1+ \frac{\lambda_i}{\gamma}}\right)}_{\approx - \frac{\lambda_i}{\gamma}} \\
\Rightarrow t \alpha\lambda_i &\approx \frac{\lambda_i}{\gamma} \\
\Rightarrow t &\approx \frac{1}{\gamma \alpha} \\
\end{split}
$$



# ---------

![[nn quadratic loss model#quadratic loss model]]

![[geometric series#geometric series]]

![[nn l2 regularization#l2 regularization]]