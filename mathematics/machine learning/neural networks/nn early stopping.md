### early stopping
- estimate the true [[risk]] using a validation dataset $\mathcal{V}$ 
- stop when the validation errors stopped improving → prevents over-fitting
- additional parameters: 
	- **evaluation interval** $a$: evaluate each $a$ steps
	- **patience** $g$: step when $g$ steps not validation error improvement

#### regularization effect
- looking at the update rule of the [[nn quadratic loss model]] we see that the size of the weights is increasing as we reach the optimum $\widehat{\mathcal{w}}$
- stopping early has a regularizing effect comparable to [[nn l2 regularization]]

$$
\begin{split}
Q^\top \mathcal{w}^{(t)} 
&= \left( I - \left(I -\alpha \Lambda\right)^t \right)  Q^\top\widehat{\mathcal{w}}   \\ 
Q_{(:,i)}^\top \mathcal{w}^{(t)} 
&= \underbrace{\left( 1 - \underbrace{\left(1 -\alpha \lambda_i\right)^t}_{\to_{t\to \infty} 0} \right)}_{\to_{t\to \infty}1}  Q_{(:,i)}^\top\widehat{\mathcal{w}}   \\ 
\end{split}
$$

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

![[nn quadratic loss model#update rule of the quadratic loss model]]

![[geometric series#geometric series]]

![[nn l2 regularization#l2 regularization]]


# anki

START
Basic
[[nn early stopping]] summary
- algorithm
- update rule of the [[nn quadratic loss model]] with reason why early stopping has a regularizing effect
- in which step we have to stop to have a similar effect as [[nn l2 regularization]] with factor $\gamma$ and learning rate $\alpha$

Back: 
### early stopping
- estimate the true [[risk]] using a validation dataset $\mathcal{V}$ 
- stop when the validation errors stopped improving → prevents over-fitting
- additional parameters: 
	- **evaluation interval** $a$: evaluate each $a$ steps
	- **patience** $g$: step when $g$ steps not validation error improvement

#### regularization effect
- looking at the update rule of the [[nn quadratic loss model]] we see that the size of the weights is increasing as we reach the optimum $\widehat{\mathcal{w}}$
- stopping early has a regularizing effect comparable to [[nn l2 regularization]]

$$
\begin{split}
Q^\top \mathcal{w}^{(t)} 
&= \left( I - \left(I -\alpha \Lambda\right)^t \right)  Q^\top\widehat{\mathcal{w}}   \\ 
Q_{(:,i)}^\top \mathcal{w}^{(t)} 
&= \underbrace{\left( 1 - \underbrace{\left(1 -\alpha \lambda_i\right)^t}_{\to_{t\to \infty} 0} \right)}_{\to_{t\to \infty}1}  Q_{(:,i)}^\top\widehat{\mathcal{w}}   \\ 
\end{split}
$$

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


_______________


### quadratic loss model
- using the [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ we have the following quadratic model that is valid near $\widehat{\mathcal{w}}$

$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}^\top(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- the [[nn quadratic loss model]] has the following [[gradient]] with the [[eigendecomposition]] of the [[hessian]] $H=Q\Lambda Q^\top$

$$
\begin{split}
\nabla\widehat{\mathcal{R}}(\mathcal{w}) 
&=  H (\mathcal{w} - \widehat{\mathcal{w}}) \\
&=  Q\Lambda Q^\top (\mathcal{w} - \widehat{\mathcal{w}}) \\

\end{split}
$$

### update rule of the quadratic loss model
- update rule of the [[nn quadratic loss model]]

$$
\begin{split}
\mathcal{w}^{(t)} 
&= \mathcal{w}^{(t-1)}  - \alpha \nabla\mathcal{R}\left(\mathcal{w}^{(t-1)} \right) \\
&= \mathcal{w}^{(t-1)}  - \alpha H\left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
&= QQ^\top\mathcal{w}^{(t-1)}  - \alpha Q\Lambda Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
Q^\top\mathcal{w}^{(t)}  
&= Q^\top\mathcal{w}^{(t-1)}  - \alpha \Lambda Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
&= Q^\top\mathcal{w}^{(t-1)}  - \alpha \Lambda Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} \\
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} \\
Q^\top\left(\mathcal{w}^{(t)} -\widehat{\mathcal{w}}\right) 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} - Q^\top\widehat{\mathcal{w}}  \\
&=  \left(I -\alpha \Lambda\right) Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right)   \\
\end{split}
$$

- when projected in the eigenspace the difference to the optimum is decreasing by a factor of $\left(1 -\alpha \lambda_i\right)$ in every step in the direction of the [[eigenvector]] of the [[eigenvalue]] $\lambda_i$

$$
\begin{split}
Q_{(:,i)}^\top\left(\mathcal{w}^{(t)} -\widehat{\mathcal{w}}\right) 
&=  \left(1 -\alpha \lambda_i\right) Q_{(:,i)}^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right)   \\
\end{split}
$$

- assuming $\mathcal{w}^{(0)}=0$ we can derive the following closed form of the update rule for the [[nn quadratic loss model]]

$$
\begin{split}
Q^\top \mathcal{w}^{(t)} 
&=  \left(I -\alpha \Lambda\right) Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) + Q^\top  \widehat{\mathcal{w}}\\ 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} -\left(I -\alpha \Lambda\right) Q^\top\widehat{\mathcal{w}} + Q^\top  \widehat{\mathcal{w}}\\ 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\left(I-\left(I -\alpha \Lambda\right)\right) Q^\top\widehat{\mathcal{w}} \\ 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} \\ 
Q^\top\mathcal{w}^{(1)}  
&=  \alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\
Q^\top \mathcal{w}^{(2)} 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=  \left(I -\alpha \Lambda\right) \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=  \left(I+\left(I -\alpha \Lambda\right)\right) \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
Q^\top \mathcal{w}^{(3)} 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(2)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=  \left(I -\alpha \Lambda\right) \left(\left(I -\alpha \Lambda\right) \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}\right) +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=   \left(I -\alpha \Lambda\right)^2 \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\left(I -\alpha \Lambda\right)\alpha \Lambda Q^\top\widehat{\mathcal{w}} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=   \left(I -\alpha \Lambda\right)^2 \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\left(I -\alpha \Lambda\right)\alpha \Lambda Q^\top\widehat{\mathcal{w}} +\left(I -\alpha \Lambda\right)^0\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&= \sum_{i=0}^2  \left(I -\alpha \Lambda\right)^i \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
Q^\top \mathcal{w}^{(t)} 
&= \sum_{i=0}^{t-1}  \left(I -\alpha \Lambda\right)^i \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
&= \left( I - \left(I -\alpha \Lambda\right)\right)^{-1}\left( I - \left(I -\alpha \Lambda\right)^t \right) \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
&= \left(\alpha \Lambda\right)^{-1}\left( I - \left(I -\alpha \Lambda\right)^t \right) \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
&= \left( I - \left(I -\alpha \Lambda\right)^t \right)  Q^\top\widehat{\mathcal{w}}   \\ 
\end{split}
$$

- in the dimension $i$ of the eigenspace, we reach the optimum $\widehat{\mathcal{w}}$ as $\left(1 -\alpha \lambda_i\right)^t \to_{t \to \infty} 0$ for $\lambda_i > 0$ and a small enough learning rate $\alpha$

$$
\begin{split}
Q_{(:,i)}^\top \mathcal{w}^{(t)} 
&= \left( 1 - \left(1 -\alpha \lambda_i\right)^t \right)  Q_{(:,i)}^\top\widehat{\mathcal{w}}   \\ 
\end{split}
$$

- to ensure convergence the following condition must hold for all eigenvalues $\lambda_i$

$$
|1 -\alpha \lambda_i| < 1 \Rightarrow 0 < \alpha < \frac{1}{\lambda_i}
$$


Tags: mathematics WS2526
<!--ID: 1767040451723-->
END


START
Basic
given the update rule of the [[nn quadratic loss model]]
- show that [[nn early stopping]] has a similar effect to [[nn l2 regularization]] when stopping in period $t \approx \frac{1}{\gamma \alpha}$

### update rule of the quadratic loss model
- update rule of the [[nn quadratic loss model]]

$$
\begin{split}
\mathcal{w}^{(t)} 
&= \mathcal{w}^{(t-1)}  - \alpha \nabla\mathcal{R}\left(\mathcal{w}^{(t-1)} \right) \\
&= \mathcal{w}^{(t-1)}  - \alpha H\left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
&= QQ^\top\mathcal{w}^{(t-1)}  - \alpha Q\Lambda Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
Q^\top\mathcal{w}^{(t)}  
&= Q^\top\mathcal{w}^{(t-1)}  - \alpha \Lambda Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
&= Q^\top\mathcal{w}^{(t-1)}  - \alpha \Lambda Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} \\
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} \\
Q^\top\left(\mathcal{w}^{(t)} -\widehat{\mathcal{w}}\right) 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} - Q^\top\widehat{\mathcal{w}}  \\
&=  \left(I -\alpha \Lambda\right) Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right)   \\
\end{split}
$$


Back: 

### early stopping
- estimate the true [[risk]] using a validation dataset $\mathcal{V}$ 
- stop when the validation errors stopped improving → prevents over-fitting
- additional parameters: 
	- **evaluation interval** $a$: evaluate each $a$ steps
	- **patience** $g$: step when $g$ steps not validation error improvement

#### regularization effect
- looking at the update rule of the [[nn quadratic loss model]] we see that the size of the weights is increasing as we reach the optimum $\widehat{\mathcal{w}}$
- stopping early has a regularizing effect comparable to [[nn l2 regularization]]

$$
\begin{split}
Q^\top \mathcal{w}^{(t)} 
&= \left( I - \left(I -\alpha \Lambda\right)^t \right)  Q^\top\widehat{\mathcal{w}}   \\ 
Q_{(:,i)}^\top \mathcal{w}^{(t)} 
&= \underbrace{\left( 1 - \underbrace{\left(1 -\alpha \lambda_i\right)^t}_{\to_{t\to \infty} 0} \right)}_{\to_{t\to \infty}1}  Q_{(:,i)}^\top\widehat{\mathcal{w}}   \\ 
\end{split}
$$

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


_______________


### quadratic loss model
- using the [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ we have the following quadratic model that is valid near $\widehat{\mathcal{w}}$

$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}^\top(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- the [[nn quadratic loss model]] has the following [[gradient]] with the [[eigendecomposition]] of the [[hessian]] $H=Q\Lambda Q^\top$

$$
\begin{split}
\nabla\widehat{\mathcal{R}}(\mathcal{w}) 
&=  H (\mathcal{w} - \widehat{\mathcal{w}}) \\
&=  Q\Lambda Q^\top (\mathcal{w} - \widehat{\mathcal{w}}) \\

\end{split}
$$

### update rule of the quadratic loss model
- update rule of the [[nn quadratic loss model]]

$$
\begin{split}
\mathcal{w}^{(t)} 
&= \mathcal{w}^{(t-1)}  - \alpha \nabla\mathcal{R}\left(\mathcal{w}^{(t-1)} \right) \\
&= \mathcal{w}^{(t-1)}  - \alpha H\left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
&= QQ^\top\mathcal{w}^{(t-1)}  - \alpha Q\Lambda Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
Q^\top\mathcal{w}^{(t)}  
&= Q^\top\mathcal{w}^{(t-1)}  - \alpha \Lambda Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
&= Q^\top\mathcal{w}^{(t-1)}  - \alpha \Lambda Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} \\
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} \\
Q^\top\left(\mathcal{w}^{(t)} -\widehat{\mathcal{w}}\right) 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} - Q^\top\widehat{\mathcal{w}}  \\
&=  \left(I -\alpha \Lambda\right) Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right)   \\
\end{split}
$$

- when projected in the eigenspace the difference to the optimum is decreasing by a factor of $\left(1 -\alpha \lambda_i\right)$ in every step in the direction of the [[eigenvector]] of the [[eigenvalue]] $\lambda_i$

$$
\begin{split}
Q_{(:,i)}^\top\left(\mathcal{w}^{(t)} -\widehat{\mathcal{w}}\right) 
&=  \left(1 -\alpha \lambda_i\right) Q_{(:,i)}^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right)   \\
\end{split}
$$

- assuming $\mathcal{w}^{(0)}=0$ we can derive the following closed form of the update rule for the [[nn quadratic loss model]]

$$
\begin{split}
Q^\top \mathcal{w}^{(t)} 
&=  \left(I -\alpha \Lambda\right) Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) + Q^\top  \widehat{\mathcal{w}}\\ 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} -\left(I -\alpha \Lambda\right) Q^\top\widehat{\mathcal{w}} + Q^\top  \widehat{\mathcal{w}}\\ 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\left(I-\left(I -\alpha \Lambda\right)\right) Q^\top\widehat{\mathcal{w}} \\ 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(t-1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}} \\ 
Q^\top\mathcal{w}^{(1)}  
&=  \alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\
Q^\top \mathcal{w}^{(2)} 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(1)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=  \left(I -\alpha \Lambda\right) \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=  \left(I+\left(I -\alpha \Lambda\right)\right) \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
Q^\top \mathcal{w}^{(3)} 
&=  \left(I -\alpha \Lambda\right) Q^\top  \mathcal{w}^{(2)} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=  \left(I -\alpha \Lambda\right) \left(\left(I -\alpha \Lambda\right) \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}\right) +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=   \left(I -\alpha \Lambda\right)^2 \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\left(I -\alpha \Lambda\right)\alpha \Lambda Q^\top\widehat{\mathcal{w}} +\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&=   \left(I -\alpha \Lambda\right)^2 \alpha \Lambda Q^\top\widehat{\mathcal{w}} +\left(I -\alpha \Lambda\right)\alpha \Lambda Q^\top\widehat{\mathcal{w}} +\left(I -\alpha \Lambda\right)^0\alpha \Lambda Q^\top\widehat{\mathcal{w}}  \\ 
&= \sum_{i=0}^2  \left(I -\alpha \Lambda\right)^i \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
Q^\top \mathcal{w}^{(t)} 
&= \sum_{i=0}^{t-1}  \left(I -\alpha \Lambda\right)^i \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
&= \left( I - \left(I -\alpha \Lambda\right)\right)^{-1}\left( I - \left(I -\alpha \Lambda\right)^t \right) \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
&= \left(\alpha \Lambda\right)^{-1}\left( I - \left(I -\alpha \Lambda\right)^t \right) \alpha \Lambda Q^\top\widehat{\mathcal{w}}   \\ 
&= \left( I - \left(I -\alpha \Lambda\right)^t \right)  Q^\top\widehat{\mathcal{w}}   \\ 
\end{split}
$$

- in the dimension $i$ of the eigenspace, we reach the optimum $\widehat{\mathcal{w}}$ as $\left(1 -\alpha \lambda_i\right)^t \to_{t \to \infty} 0$ for $\lambda_i > 0$ and a small enough learning rate $\alpha$

$$
\begin{split}
Q_{(:,i)}^\top \mathcal{w}^{(t)} 
&= \left( 1 - \left(1 -\alpha \lambda_i\right)^t \right)  Q_{(:,i)}^\top\widehat{\mathcal{w}}   \\ 
\end{split}
$$

- to ensure convergence the following condition must hold for all eigenvalues $\lambda_i$

$$
|1 -\alpha \lambda_i| < 1 \Rightarrow 0 < \alpha < \frac{1}{\lambda_i}
$$


Tags: mathematics WS2526
<!--ID: 1767040451728-->
END