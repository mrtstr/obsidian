### quadratic loss model
- using the [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ we have the following quadratic model that is valid near $\widehat{\mathcal{w}}$

$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}^\top(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- the [[quadratic loss model]] has the following [[gradient]] with the [[eigendecomposition]] of the [[hessian]] $H=Q\Lambda Q^\top$

$$
\begin{split}
\nabla\widehat{\mathcal{R}}(\mathcal{w}) 
&=  H (\mathcal{w} - \widehat{\mathcal{w}}) \\
&=  Q\Lambda Q^\top (\mathcal{w} - \widehat{\mathcal{w}}) \\
\end{split}
$$

### update rule of the quadratic loss model
- update rule of the [[quadratic loss model]]

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

- assuming $\mathcal{w}^{(0)}=0$ we can derive the following closed form of the update rule for the [[quadratic loss model]]

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
# anki

START
Basic
[[quadratic loss model]]
- definition
- [[gradient]]
Back: 
### quadratic loss model
- using the [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ we have the following quadratic model that is valid near $\widehat{\mathcal{w}}$

$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}^\top(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- the [[quadratic loss model]] has the following [[gradient]] with the [[eigendecomposition]] of the [[hessian]] $H=Q\Lambda Q^\top$

$$
\begin{split}
\nabla\widehat{\mathcal{R}}(\mathcal{w}) 
&=  H (\mathcal{w} - \widehat{\mathcal{w}}) \\
&=  Q\Lambda Q^\top (\mathcal{w} - \widehat{\mathcal{w}}) \\

\end{split}
$$

Tags: mathematics WS2526
<!--ID: 1767038982812-->
END


START
Basic
update rule of the [[quadratic loss model]]
Back: 


$$
\begin{split}
\mathcal{w}^{(t)} 
&= \mathcal{w}^{(t-1)}  - \alpha \nabla\mathcal{R}\left(\mathcal{w}^{(t-1)} \right) \\
&= \mathcal{w}^{(t-1)}  - \alpha H\left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
&= QQ^\top\mathcal{w}^{(t-1)}  - \alpha Q\Lambda Q^\top  \left(\mathcal{w}^{(t-1)} -\widehat{\mathcal{w}}\right) \\
\end{split}
$$

__________

### quadratic loss model
- using the [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ we have the following quadratic model that is valid near $\widehat{\mathcal{w}}$

$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}^\top(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- the [[quadratic loss model]] has the following [[gradient]] with the [[eigendecomposition]] of the [[hessian]] $H=Q\Lambda Q^\top$

$$
\begin{split}
\nabla\widehat{\mathcal{R}}(\mathcal{w}) 
&=  H (\mathcal{w} - \widehat{\mathcal{w}}) \\
&=  Q\Lambda Q^\top (\mathcal{w} - \widehat{\mathcal{w}}) \\

\end{split}
$$

### update rule of the quadratic loss model
- update rule of the [[quadratic loss model]]

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

- assuming $\mathcal{w}^{(0)}=0$ we can derive the following closed form of the update rule for the [[quadratic loss model]]

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
# an

Tags: mathematics WS2526
<!--ID: 1767038982816-->
END


START
Basic
update rule of the[[quadratic loss model]]
- proof that when projected in the eigenspace the difference to the optimum is decreasing by a factor of $\left(1 -\alpha \lambda_i\right)$ in every step in the direction of the [[eigenvector]] of the [[eigenvalue]] $\lambda_i$
Back: 
### quadratic loss model
- using the [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ we have the following quadratic model that is valid near $\widehat{\mathcal{w}}$

$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}^\top(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- the [[quadratic loss model]] has the following [[gradient]] with the [[eigendecomposition]] of the [[hessian]] $H=Q\Lambda Q^\top$

$$
\begin{split}
\nabla\widehat{\mathcal{R}}(\mathcal{w}) 
&=  H (\mathcal{w} - \widehat{\mathcal{w}}) \\
&=  Q\Lambda Q^\top (\mathcal{w} - \widehat{\mathcal{w}}) \\

\end{split}
$$

### update rule of the quadratic loss model
- update rule of the [[quadratic loss model]]

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

- assuming $\mathcal{w}^{(0)}=0$ we can derive the following closed form of the update rule for the [[quadratic loss model]]

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
<!--ID: 1767038982818-->
END


START
Basic
given the update rule of the [[quadratic loss model]]
- calculate the closed form

### update rule of the quadratic loss model
- update rule of the [[quadratic loss model]]

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
### quadratic loss model
- using the [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ we have the following quadratic model that is valid near $\widehat{\mathcal{w}}$

$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}^\top(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- the [[quadratic loss model]] has the following [[gradient]] with the [[eigendecomposition]] of the [[hessian]] $H=Q\Lambda Q^\top$

$$
\begin{split}
\nabla\widehat{\mathcal{R}}(\mathcal{w}) 
&=  H (\mathcal{w} - \widehat{\mathcal{w}}) \\
&=  Q\Lambda Q^\top (\mathcal{w} - \widehat{\mathcal{w}}) \\

\end{split}
$$

### update rule of the quadratic loss model
- update rule of the [[quadratic loss model]]

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

- assuming $\mathcal{w}^{(0)}=0$ we can derive the following closed form of the update rule for the [[quadratic loss model]]

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
<!--ID: 1767038982820-->
END


START
Basic
given the update rule of the [[quadratic loss model]]
- which condition does the learning rate have to satisfy to ensure convergence?

### update rule of the quadratic loss model
- update rule of the [[quadratic loss model]]

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


### quadratic loss model
- using the [[taylor series|taylor approximation]] of the [[risk]] function in the neighborhood of $\widehat{\mathcal{w}}$ we have the following quadratic model that is valid near $\widehat{\mathcal{w}}$

$$
\begin{split}
\widehat{\mathcal{R}}(\mathcal{w}) 
&= \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) + \overbrace{\nabla_\mathcal{w} \widehat{\mathcal{R}}^\top(\mathcal{w} - \widehat{\mathcal{w}})}^\text{vanishes near the minimum} + \frac{1}{2} (\mathcal{w} - \widehat{\mathcal{w}})^\top H (\mathcal{w} - \widehat{\mathcal{w}}) \\
H &= \nabla^2_\mathcal{w} \widehat{\mathcal{R}}(\widehat{\mathcal{w}}) \\
\end{split}
$$

- the [[quadratic loss model]] has the following [[gradient]] with the [[eigendecomposition]] of the [[hessian]] $H=Q\Lambda Q^\top$

$$
\begin{split}
\nabla\widehat{\mathcal{R}}(\mathcal{w}) 
&=  H (\mathcal{w} - \widehat{\mathcal{w}}) \\
&=  Q\Lambda Q^\top (\mathcal{w} - \widehat{\mathcal{w}}) \\

\end{split}
$$

### update rule of the quadratic loss model
- update rule of the [[quadratic loss model]]

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

- assuming $\mathcal{w}^{(0)}=0$ we can derive the following closed form of the update rule for the [[quadratic loss model]]

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
<!--ID: 1767038982823-->
END