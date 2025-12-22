## bias complexity tradeoff
- the [[nn bias complexity tradeoff]] describes the relationship between the **error caused by the limited model [[function space]] $\mathcal{H}$** and the **error caused by the training process**

- let $\mathcal{S}=\{(x_1, y_1), ..., (x_m, y_m)\}$ be the [[training dataset]] and true [[data distribution]] $\mathcal{D}$ (often approximated using a large validation set)

$$
\begin{split}
 f_\mathcal{D} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right] \\
 f_\mathcal{S} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{S}}\left[\ell(y, f(x))\right] \\
 \end{split}
$$

- we can decompose the error in the **approximation error** or [[bias]] $\epsilon_\mathrm{app}$ and the **estimation error** $\epsilon_\mathrm{est}$
 
$$
\begin{split}
\mathcal{R}_\mathcal{D}(f_\mathcal{S}) 
&= \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f_\mathcal{S}(x))\right] \\
&= \underbrace{\mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{app}} + \underbrace{ \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{est}}   \\
\end{split}
$$

### tradeoff relationship
- if we increase the size of $\mathcal{H}$ the approximation error will decrease → decreases overall error
- but a more complex model can over fit the training dataset better → increases overall error

### approximation error
- error caused by the limited model [[function space]] $\mathcal{H}$
- $\epsilon_\mathrm{app}$ does not depend on the training data and thus is entirely dependent on the model architecture choice ([[function space]] of the model and [[parameter space]]) 
- error because the model is too small plus the noise or the data

$$
\epsilon_\mathrm{app} = \mathcal{R}_\mathcal{D}(f_\mathcal{D})
$$

- note: there exists a different definition of the approximation error where the noise is removed → difference between the best model in my [[hypothesis space]] minus the performance of the ideal model $f^*$ (which is equal to the noise of the data $\epsilon$)
- in this formulation approximation error is a generalized form of the [[bias]] for a general [[loss function]] (instead of the [[mean square error]])

$$
\begin{split}
\epsilon_\mathrm{app} &= \mathcal{R}_\mathcal{D}(f_\mathcal{D}) - \mathcal{R}_\mathcal{D}(f^*)\\
 f^* &= \arg\min_{f} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right]\\
 \mathcal{R}_\mathcal{D}(f^*) &=  \epsilon = \text{irreducable error} \\
 \end{split}
$$

### estimation error
- error caused in training procedure
- the estimation error $\epsilon_\mathrm{est}$ is the difference [[risk|true risk]] of the trained model and the [[risk|true risk]] of the optimal model in the [[function space]] $\mathcal{H}$

$$
\begin{split}
\epsilon_\mathrm{est}= \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})  \\
\end{split}
$$

- it is dependent on the **training data set**, the **model architecture** and the **leaning algorithm**
- for example can be caused by over fitting or limited data
- can be reduced by [[regularization]] and more training data

### bias complexity tradeoff with MSE loss

$$
\begin{split}
\ell(y, f_\mathcal{S}(x))
&= \left(y - f_\mathcal{S}(x)\right)^2 \\
&= \left(\left(y - f_\mathcal{D}(x)\right) + \left(f_\mathcal{D}(x) - f_\mathcal{S}(x) \right) \right)^2 \\
&= \left(y - f_\mathcal{D}(x)\right)^2 + \left(f_\mathcal{D}(x) - f_\mathcal{S}(x) \right)^2 \\&+ 2\left(y - f_\mathcal{D}(x)\right)\left(f_\mathcal{D}(x) - f_\mathcal{S}(x) \right) \\
\mathcal{R}_\mathcal{D}(f_\mathcal{S}) 
&= \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f_\mathcal{S}(x))\right] \\
&= \underbrace {\mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\left(y - f_\mathcal{D}(x)\right)^2\right]}_{\epsilon_\mathrm{app}} + \underbrace {\mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\left(f_\mathcal{D}(x) - f_\mathcal{S}(x) \right)^2\right]}_{\epsilon_\mathrm{est}}
\end{split}
$$

# anki

START
Basic
[[nn bias complexity tradeoff]]
- calculate the estimation error and the approximation error for the [[mean square error]] [[loss function]]
Back: 
### bias complexity tradeoff with MSE loss

$$
\begin{split}
\ell(y, f_\mathcal{S}(x))
&= \left(y - f_\mathcal{S}(x)\right)^2 \\
&= \left(\left(y - f_\mathcal{D}(x)\right) + \left(f_\mathcal{D}(x) - f_\mathcal{S}(x) \right) \right)^2 \\
&= \left(y - f_\mathcal{D}(x)\right)^2 + \left(f_\mathcal{D}(x) - f_\mathcal{S}(x) \right)^2 \\&+ 2\left(y - f_\mathcal{D}(x)\right)\left(f_\mathcal{D}(x) - f_\mathcal{S}(x) \right) \\
\mathcal{R}_\mathcal{D}(f_\mathcal{S}) 
&= \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f_\mathcal{S}(x))\right] \\
&= \underbrace {\mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\left(y - f_\mathcal{D}(x)\right)^2\right]}_{\epsilon_\mathrm{app}} + \underbrace {\mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\left(f_\mathcal{D}(x) - f_\mathcal{S}(x) \right)^2\right]}_{\epsilon_\mathrm{est}}
\end{split}
$$


## bias complexity tradeoff
- the [[nn bias complexity tradeoff]] describes the relationship between the **error caused by the limited model [[function space]] $\mathcal{H}$** and the **error caused by the training process**

- let $\mathcal{S}=\{(x_1, y_1), ..., (x_m, y_m)\}$ be the [[training dataset]] and true [[data distribution]] $\mathcal{D}$ (often approximated using a large validation set)

$$
\begin{split}
 f_\mathcal{D} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right] \\
 f_\mathcal{S} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{S}}\left[\ell(y, f(x))\right] \\
 \end{split}
$$

- we can decompose the error in the **approximation error** or [[bias]] $\epsilon_\mathrm{app}$ and the **estimation error** $\epsilon_\mathrm{est}$
 
$$
\begin{split}
\mathcal{R}_\mathcal{D}(f_\mathcal{S}) 
&= \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f_\mathcal{S}(x))\right] \\
&= \underbrace{\mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{app}} + \underbrace{ \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{est}}   \\
\end{split}
$$

### tradeoff relationship
- if we increase the size of $\mathcal{H}$ the approximation error will decrease → decreases overall error
- but a more complex model can over fit the training dataset better → increases overall error

### approximation error
- error caused by the limited model [[function space]] $\mathcal{H}$
- $\epsilon_\mathrm{app}$ does not depend on the training data and thus is entirely dependent on the model architecture choice ([[function space]] of the model and [[parameter space]]) 
- error because the model is too small plus the noise or the data

$$
\epsilon_\mathrm{app} = \mathcal{R}_\mathcal{D}(f_\mathcal{D})
$$

- note: there exists a different definition of the approximation error where the noise is removed → difference between the best model in my [[hypothesis space]] minus the performance of the ideal model $f^*$ (which is equal to the noise of the data $\epsilon$)
- in this formulation approximation error is a generalized form of the [[bias]] for a general [[loss function]] (instead of the [[mean square error]])

$$
\begin{split}
\epsilon_\mathrm{app} &= \mathcal{R}_\mathcal{D}(f_\mathcal{D}) - \mathcal{R}_\mathcal{D}(f^*)\\
 f^* &= \arg\min_{f} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right]\\
 \mathcal{R}_\mathcal{D}(f^*) &=  \epsilon = \text{irreducable error} \\
 \end{split}
$$

### estimation error
- error caused in training procedure
- the estimation error $\epsilon_\mathrm{est}$ is the difference [[risk|true risk]] of the trained model and the [[risk|true risk]] of the optimal model in the [[function space]] $\mathcal{H}$

$$
\begin{split}
\epsilon_\mathrm{est}= \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})  \\
\end{split}
$$

- it is dependent on the **training data set**, the **model architecture** and the **leaning algorithm**
- for example can be caused by over fitting or limited data
- can be reduced by [[regularization]] and more training data

Tags: mathematics basics WS2526
<!--ID: 1766390400618-->
END


START
Basic
[[nn bias complexity tradeoff]]
- definition estimation error
- definition approximation error
- what causes the trade off relationship?
Back: 
## bias complexity tradeoff
- the [[nn bias complexity tradeoff]] describes the relationship between the **error caused by the limited model [[function space]] $\mathcal{H}$** and the **error caused by the training process**

- let $\mathcal{S}=\{(x_1, y_1), ..., (x_m, y_m)\}$ be the [[training dataset]] and true [[data distribution]] $\mathcal{D}$ (often approximated using a large validation set)

$$
\begin{split}
 f_\mathcal{D} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right] \\
 f_\mathcal{S} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{S}}\left[\ell(y, f(x))\right] \\
 \end{split}
$$

- we can decompose the error in the **approximation error** or [[bias]] $\epsilon_\mathrm{app}$ and the **estimation error** $\epsilon_\mathrm{est}$
 
$$
\begin{split}
\mathcal{R}_\mathcal{D}(f_\mathcal{S}) 
&= \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f_\mathcal{S}(x))\right] \\
&= \underbrace{\mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{app}} + \underbrace{ \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{est}}   \\
\end{split}
$$

### tradeoff relationship
- if we increase the size of $\mathcal{H}$ the approximation error will decrease → decreases overall error
- but a more complex model can over fit the training dataset better → increases overall error

### approximation error
- error caused by the limited model [[function space]] $\mathcal{H}$
- $\epsilon_\mathrm{app}$ does not depend on the training data and thus is entirely dependent on the model architecture choice ([[function space]] of the model and [[parameter space]]) 
- error because the model is too small plus the noise or the data

$$
\epsilon_\mathrm{app} = \mathcal{R}_\mathcal{D}(f_\mathcal{D})
$$

- note: there exists a different definition of the approximation error where the noise is removed → difference between the best model in my [[hypothesis space]] minus the performance of the ideal model $f^*$ (which is equal to the noise of the data $\epsilon$)
- in this formulation approximation error is a generalized form of the [[bias]] for a general [[loss function]] (instead of the [[mean square error]])

$$
\begin{split}
\epsilon_\mathrm{app} &= \mathcal{R}_\mathcal{D}(f_\mathcal{D}) - \mathcal{R}_\mathcal{D}(f^*)\\
 f^* &= \arg\min_{f} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right]\\
 \mathcal{R}_\mathcal{D}(f^*) &=  \epsilon = \text{irreducable error} \\
 \end{split}
$$

### estimation error
- error caused in training procedure
- the estimation error $\epsilon_\mathrm{est}$ is the difference [[risk|true risk]] of the trained model and the [[risk|true risk]] of the optimal model in the [[function space]] $\mathcal{H}$

$$
\begin{split}
\epsilon_\mathrm{est}= \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})  \\
\end{split}
$$

- it is dependent on the **training data set**, the **model architecture** and the **leaning algorithm**
- for example can be caused by over fitting or limited data
- can be reduced by [[regularization]] and more training data

Tags: mathematics basics WS2526
<!--ID: 1766251304145-->
END



START
Basic
approximation error
- definition
- relationship to the bias
- what causes it?
Back: 

### approximation error
- error caused by the limited model [[function space]] $\mathcal{H}$
- $\epsilon_\mathrm{app}$ does not depend on the training data and thus is entirely dependent on the model architecture choice ([[function space]] of the model and [[parameter space]]) 
- error because the model is too small plus the noise or the data

$$
\epsilon_\mathrm{app} = \mathcal{R}_\mathcal{D}(f_\mathcal{D})
$$

- note: there exists a different definition of the approximation error where the noise is removed → difference between the best model in my [[hypothesis space]] minus the performance of the ideal model $f^*$ (which is equal to the noise of the data $\epsilon$)
- in this formulation approximation error is a generalized form of the [[bias]] for a general [[loss function]] (instead of the [[mean square error]])

$$
\begin{split}
\epsilon_\mathrm{app} &= \mathcal{R}_\mathcal{D}(f_\mathcal{D}) - \mathcal{R}_\mathcal{D}(f^*)\\
 f^* &= \arg\min_{f} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right]\\
 \mathcal{R}_\mathcal{D}(f^*) &=  \epsilon = \text{irreducable error} \\
 \end{split}
$$


_______
## bias complexity tradeoff
- the [[nn bias complexity tradeoff]] describes the relationship between the **error caused by the limited model [[function space]] $\mathcal{H}$** and the **error caused by the training process**

- let $\mathcal{S}=\{(x_1, y_1), ..., (x_m, y_m)\}$ be the [[training dataset]] and true [[data distribution]] $\mathcal{D}$ (often approximated using a large validation set)

$$
\begin{split}
 f_\mathcal{D} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right] \\
 f_\mathcal{S} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{S}}\left[\ell(y, f(x))\right] \\
 \end{split}
$$

- we can decompose the error in the **approximation error** or [[bias]] $\epsilon_\mathrm{app}$ and the **estimation error** $\epsilon_\mathrm{est}$
 
$$
\begin{split}
\mathcal{R}_\mathcal{D}(f_\mathcal{S}) 
&= \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f_\mathcal{S}(x))\right] \\
&= \underbrace{\mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{app}} + \underbrace{ \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{est}}   \\
\end{split}
$$

### tradeoff relationship
- if we increase the size of $\mathcal{H}$ the approximation error will decrease → decreases overall error
- but a more complex model can over fit the training dataset better → increases overall error

### approximation error
- error caused by the limited model [[function space]] $\mathcal{H}$
- $\epsilon_\mathrm{app}$ does not depend on the training data and thus is entirely dependent on the model architecture choice ([[function space]] of the model and [[parameter space]]) 
- error because the model is too small plus the noise or the data

$$
\epsilon_\mathrm{app} = \mathcal{R}_\mathcal{D}(f_\mathcal{D})
$$

- note: there exists a different definition of the approximation error where the noise is removed → difference between the best model in my [[hypothesis space]] minus the performance of the ideal model $f^*$ (which is equal to the noise of the data $\epsilon$)
- in this formulation approximation error is a generalized form of the [[bias]] for a general [[loss function]] (instead of the [[mean square error]])

$$
\begin{split}
\epsilon_\mathrm{app} &= \mathcal{R}_\mathcal{D}(f_\mathcal{D}) - \mathcal{R}_\mathcal{D}(f^*)\\
 f^* &= \arg\min_{f} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right]\\
 \mathcal{R}_\mathcal{D}(f^*) &=  \epsilon = \text{irreducable error} \\
 \end{split}
$$

### estimation error
- error caused in training procedure
- the estimation error $\epsilon_\mathrm{est}$ is the difference [[risk|true risk]] of the trained model and the [[risk|true risk]] of the optimal model in the [[function space]] $\mathcal{H}$

$$
\begin{split}
\epsilon_\mathrm{est}= \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})  \\
\end{split}
$$

- it is dependent on the **training data set**, the **model architecture** and the **leaning algorithm**
- for example can be caused by over fitting or limited data
- can be reduced by [[regularization]] and more training data

Tags: mathematics basics WS2526
<!--ID: 1766251304149-->
END


START
Basic
estimation error
- definition
- what causes it and how to reduce it?
Back: 

### estimation error
- error caused in training procedure
- the estimation error $\epsilon_\mathrm{est}$ is the difference [[risk|true risk]] of the trained model and the [[risk|true risk]] of the optimal model in the [[function space]] $\mathcal{H}$

$$
\begin{split}
\epsilon_\mathrm{est}= \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})  \\
\end{split}
$$

- it is dependent on the **training data set**, the **model architecture** and the **leaning algorithm**
- for example can be caused by over fitting or limited data
- can be reduced by [[regularization]] and more training data
________________
## bias complexity tradeoff
- the [[nn bias complexity tradeoff]] describes the relationship between the **error caused by the limited model [[function space]] $\mathcal{H}$** and the **error caused by the training process**

- let $\mathcal{S}=\{(x_1, y_1), ..., (x_m, y_m)\}$ be the [[training dataset]] and true [[data distribution]] $\mathcal{D}$ (often approximated using a large validation set)

$$
\begin{split}
 f_\mathcal{D} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right] \\
 f_\mathcal{S} &= \arg\min_{f \in \mathcal{H}} \mathbb{E}_{(x, y) \sim \mathcal{S}}\left[\ell(y, f(x))\right] \\
 \end{split}
$$

- we can decompose the error in the **approximation error** or [[bias]] $\epsilon_\mathrm{app}$ and the **estimation error** $\epsilon_\mathrm{est}$
 
$$
\begin{split}
\mathcal{R}_\mathcal{D}(f_\mathcal{S}) 
&= \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f_\mathcal{S}(x))\right] \\
&= \underbrace{\mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{app}} + \underbrace{ \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})}_{\epsilon_\mathrm{est}}   \\
\end{split}
$$

### tradeoff relationship
- if we increase the size of $\mathcal{H}$ the approximation error will decrease → decreases overall error
- but a more complex model can over fit the training dataset better → increases overall error

### approximation error
- error caused by the limited model [[function space]] $\mathcal{H}$
- $\epsilon_\mathrm{app}$ does not depend on the training data and thus is entirely dependent on the model architecture choice ([[function space]] of the model and [[parameter space]]) 
- error because the model is too small plus the noise or the data

$$
\epsilon_\mathrm{app} = \mathcal{R}_\mathcal{D}(f_\mathcal{D})
$$

- note: there exists a different definition of the approximation error where the noise is removed → difference between the best model in my [[hypothesis space]] minus the performance of the ideal model $f^*$ (which is equal to the noise of the data $\epsilon$)
- in this formulation approximation error is a generalized form of the [[bias]] for a general [[loss function]] (instead of the [[mean square error]])

$$
\begin{split}
\epsilon_\mathrm{app} &= \mathcal{R}_\mathcal{D}(f_\mathcal{D}) - \mathcal{R}_\mathcal{D}(f^*)\\
 f^* &= \arg\min_{f} \mathbb{E}_{(x, y) \sim \mathcal{D}}\left[\ell(y, f(x))\right]\\
 \mathcal{R}_\mathcal{D}(f^*) &=  \epsilon = \text{irreducable error} \\
 \end{split}
$$

### estimation error
- error caused in training procedure
- the estimation error $\epsilon_\mathrm{est}$ is the difference [[risk|true risk]] of the trained model and the [[risk|true risk]] of the optimal model in the [[function space]] $\mathcal{H}$

$$
\begin{split}
\epsilon_\mathrm{est}= \mathcal{R}_\mathcal{D}(f_\mathcal{S}) -  \mathcal{R}_\mathcal{D}(f_\mathcal{D})  \\
\end{split}
$$

- it is dependent on the **training data set**, the **model architecture** and the **leaning algorithm**
- for example can be caused by over fitting or limited data
- can be reduced by [[regularization]] and more training data


Tags: mathematics basics WS2526
<!--ID: 1766251304152-->
END