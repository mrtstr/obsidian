
### bayesian inference
- [[hierarchical model]] that assumes that the parameters $\theta \sim P_\theta$ as well as the data $\mathcal{D}\subset \mathcal{X} \times \mathcal{Y} \sim P_\mathcal{D}(. \mid \theta)$ are [[random variable]] with a [[distribution]] 
- then the [[bayes theorem]] is used to model the [[conditional distribution]] of the parameters $p(\theta\mid \mathcal{D})$ 

$$
p(\theta\mid \mathcal{D}) = \frac{p(\mathcal{D}\mid \theta)p(\theta)}{p(\mathcal{D})}
$$
- however it is very difficult to compute the $p(\mathcal{D})$ which requires integrating out the parameter conditioning, but we still can maximize $p(\theta\mid \mathcal{D})$ in which case we can ignore $p(\mathcal{D})$ because it doesn't depend on the parameters and is just a constant which leads to the [[maximum aposteriori]] method

$$
p(\mathcal{D}) = \int p(\mathcal{D}\mid \theta)p(\theta) d\theta
$$

### Single Bayesian Update

For a [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ and general [[event space|event]] $A$ the [[bayes theorem]] states the following.
$$
P\left(B_i \mid A\right) 
= \frac{
\overbrace{P\left(A \mid B_i\right)}^\text{likelihood}
\overbrace{P\left(B_i\right)}^\text{prior}
}
{
\underbrace{\sum\limits_{j=1}^k P\left(A \mid B_j\right)P\left(B_j\right)}_{P(A)}
}
$$
We are interested in the [[probability]] of [[event]] $B_i$, and we have a prior [[hypothesis]] $P(B_i)$. Then we observe the occurrence of and [[stochastic independent|dependent]] [[event]] $A$, and we want to update our [[hypothesis]]. For this we need the [[likelihood function]] that [[event]] $A$ happened under the assumption that $B_i$ is true and divide it by the [[probability]] of the observed [[event]] $A$. The [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ is still normalized $\left(\sum P(B_i) = 1 \right)$.  

### Multiple Bayesian Updates
This time we have multiple [[observations]] $\{A_i \mid i = 1,2...,N\}$. From the conditional version of the [[bayes theorem]] we know the following:


$$
\begin{split}
P\left(B_i \mid \bigcap_\limits{i=1}^{N} A_n \right) 

&= \frac{P\left(B_l \cap \bigcap\limits_{n=1}^{N} A_n \right)}
{P\left(\bigcap\limits_{n=1}^{N} A_n \right)} \\

&= \frac{P\left(B_i\right) P\left( \bigcap\limits_{n=1}^{N} A_n \mid B_i \right)}
{
\sum\limits_{l=1}^{k} P(B_l) P\left(\bigcap\limits_{n=1}^{N} A_n \mid B_l\right)
} \\
&= \frac{P\left(B_i\right) P\left(  A_1 \cap A_2 \: \cap \: ... \: \cap \:A_n \mid B_i \right)}
{
\sum\limits_{l=1}^{k} P(B_l) P\left( A_1 \cap A_2 \: \cap \: ... \: \cap \:A_n \mid B_l\right)
} \\
&= \frac{P\left(B_k\right) \prod\limits_{n=1}^{N}P \left(  A_n \Bigm\vert B_k \cap 
\bigcap\limits_{j=1}^{n-1} A_j \right)}
{
\sum\limits_{j=1}^{k} P(B_j) 
\prod\limits_{n=1}^{N}P \left(  A_n \Bigm\vert B_k \cap 
\bigcap\limits_{j=1}^{n-1} A_j \right)
} 
\end{split}
$$
With the [[bayes theorem|conditional version of the bayes theorem]] we know that we can compose the term in the following way.
$$
\begin{split}
P\left(B_i \mid \bigcap_\limits{j=1}^{n} A_j \right) 

&= \frac{
P\left(B_i \cap \bigcap\limits_{j=1}^{n-1} A_j \right)
P\left(A_n \mid B_i \cap \bigcap\limits_{j=1}^{n-1} A_j \right)
}
{

\underbrace{
\sum\limits_{k=1}^{K}
P\left(B_k \cap \bigcap\limits_{j=1}^{n-1} A_j \right)
P\left(A_n \mid B_k \cap \bigcap\limits_{j=1}^{n-1} A_j \right)
}_{P\left(A_n \mid \bigcap\limits_{i=1}^{n-1} A_i\right)}
} 


\end{split}
$$
Here we can see that it is possible to define the posterior in a recursive way. This version is easy to calculate because we can just reuse the posterior of the previous step a prior and do another single Bayesian update.
$$
\begin{split}
P\left(B_i^{(0)}  \right) &:=  P\left(B_i\right) \\
P\left(B_i^{(n)}  \right) &:= P\left(B_i\right)P\left(B_i \mid \bigcap_\limits{i=1}^{N} A_n \right) \\
&= \frac{
\overbrace{
P\left(B_i^{(n-1)}\right)
}^{P\left(B_i \mid \bigcap_\limits{j=1}^{n-1} A_j \right) }
\overbrace{
P\left(A_n \mid B_i^{(n-1)}\right)
}^{P\left(A_n \mid B_i \cap \bigcap\limits_{j=1}^{n-1} A_j \right)}
}
{
\underbrace{
\sum\limits_{l=1}^{k} P(B_l^{(n-1)}) P\left( A_n \mid B_l^{(n-1)}\right)
}_{P\left(A_n \mid \bigcap\limits_{i=1}^{n-1} A_i\right)}
}
\end{split}
$$
## Example
we have a fair coin $B_1$ and a coin with head on both sides $B_2$, and we choose a one of the two coins randomly with $P(B_1) =P(B_1)= \frac{1}{2}$. Then we flip the coin $n$ times, and it allays shows head $\{H_n \mid n = 1,...,N\}$. How big is the probability that we have chosen the fair coin $B_1$.

$$
\begin{split}
P\left(B_1^{(0)}  \right) &=  \frac{1}{2} \\
P\left(B_1^{(1)}  \right) 
&= \frac{
\overbrace{P\left(H_1 \mid B_1^{(0)}\right)}^\text{likelihood}
\overbrace{P\left(B_1^{(0)}\right)}^\text{prior}
}
{
\underbrace{\sum\limits_{i=1}^2 P\left(H_1 \mid B_i^{(0)}\right)P\left(B_i^{(0)}\right)}_{P(H_1)}
} 
= \frac{\frac{1}{2}\cdot\frac{1}{2}}{\frac{1}{2} \cdot 1 + \frac{1}{2} \cdot \frac{1}{2}} = \frac{1}{3} \\
P\left(B_1^{(2)}  \right) 
&= 
\frac{
\overbrace{
P\left(B_1^{(2)}\right)
}^{P\left(B_1 \mid   H_1 \right) }
P\left(H_1 \mid B_1^{(2)}\right)
}
{
\underbrace{
\sum\limits_{l=1}^{2} P\left(B_l^{(2)}\right) P\left( H_2 \mid B_l^{(2)}\right)
}_{P\left(H_2 \mid  H_1 \right)}
}
= \frac{\frac{1}{3}\cdot\frac{1}{2}}{\frac{2}{3} \cdot 1 + \frac{1}{3} \cdot \frac{1}{2}} = \frac{1}{5}\\

\end{split}
$$

# -----------

![[bayes theorem#bayes theorem]]

# anki

START
Basic
[[bayesian inference]]
- general approach
- problem and what to do instead
Back: 
### bayesian inference
- [[hierarchical model]] that assumes that the parameters $\theta \sim P_\theta$ as well as the data $\mathcal{D}\subset \mathcal{X} \times \mathcal{Y} \sim P_\mathcal{D}(. \mid \theta)$ are [[random variable]] with a [[distribution]] 
- then the [[bayes theorem]] is used to model the [[conditional distribution]] of the parameters $p(\theta\mid \mathcal{D})$ 

$$
p(\theta\mid \mathcal{D}) = \frac{p(\mathcal{D}\mid \theta)p(\theta)}{p(\mathcal{D})}
$$

- however it is very difficult to compute the $p(\mathcal{D})$ which requires integrating out the parameter conditioning, but we still can maximize $p(\theta\mid \mathcal{D})$ in which case we can ignore $p(\mathcal{D})$ because it doesn't depend on the parameters and is just a constant which leads to the [[maximum aposteriori]] method

$$
p(\mathcal{D}) = \int p(\mathcal{D}\mid \theta)p(\theta) d\theta
$$

___________
### maximum aposteriori
- [[bayesian inference]] given a [[empirical distribution of a dataset|dataset]] $\mathcal{D}$ with a [[probability density function (PDF)]] $f(\theta)$ and a model $\theta$ with a prior assumed distribution $f(\theta)$
- the model can be trained by maximizing the posterior $f\left(\theta \mid \mathcal{D}\right)$

$$
\overbrace{f\left(\theta \mid \mathcal{D}\right)}^\text{posterior}
= \frac{
\overbrace{f\left(\mathcal{D} \mid \theta\right)}^\text{likelihood}
\overbrace{f\left(\theta\right)}^\text{prior}
}
{
P(\mathcal{D})
}
$$
- for the [[maximum aposteriori]] estimation we have the following
- this works because 
	- we can assume the features $X$ to be constant and thus treat them as given
	- the [[logarithm]] is a [[monotonic function]] and thus does not change the argmax
	- the distribution of the data does not depend on the parameters

$$
\begin{split}
\theta_{MAP} 
&= arg\max_\theta f\left(\theta \mid \mathcal{D}\right) \\
&= arg\max_\theta \frac{f\left(\mathcal{D} \mid \theta\right)f\left(\theta\right)}{P(\mathcal{D})} \\
&= arg\max_\theta f\left(\mathcal{D} \mid \theta\right)f\left(\theta\right) \\
&= arg\max_\theta \log{ f\left(\mathcal{D} \mid \theta\right)f\left(\theta\right)} \\
&= arg\max_\theta \log{ f\left(\mathcal{D} \mid \theta\right)}+\log{f\left(\theta\right)} \\
&= arg\max_\theta \log{ f\left(Y \mid \theta, X\right)}+\log{f\left(\theta\right)} \\
\end{split}
$$

### hierarchical model
- [[probabilistic model]] that use internally multiple [[distribution]] 
- given the following model with a [[hyperparameter]] $\lambda$ 

$$
(X, \theta) \sim \mathcal{M}(\lambda)
$$

- $\mathcal{M}$ can internally consist of multiple probability laws - one that models the distribution of the parameters $\theta$ and one that models the input as a [[random variable]] $X$

$$
\begin{split}
\theta &\sim L(.\mid\lambda) \\
X &\sim L_X(.\mid\theta) \\
\end{split}
$$

### bayes theorem
The [[bayes theorem]] describes the probability of an [[event space|event]] based on prior knowledge. Used for [[bayesian inference]].
With [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ and general [[event space|event]] $A$ follows after [[conditional probability|law of total probability]] and the  [[multiplication rule]]:
$$
P\left(B_i \mid A\right) 
= \frac{P\left(A \mid B_i\right)P\left(B_i\right)}
{\sum\limits_{j=1}^k P\left(A \mid B_j\right)P\left(B_j\right)}
$$
Proof:
$$
\begin{split}
P\left(B_i \mid A\right) 
&= \frac{P\left(A \cap B_i\right)}{P\left(A \right)} \\
&= \frac{P\left(A \cap B_i\right)}{P\left(B_i \right)} \frac{P\left(B_i\right)}{P\left(A \right)} \\
&= \frac{P\left(A | B_i\right)P\left(B_i\right)}{P\left(A \right)} \\
&= \frac{\overbrace{P\left(A \mid B_i\right)P\left(B_i\right)}^\text{multiplication rule}}
{\underbrace{\sum\limits_{j=1}^k P\left(A \mid B_j\right)P\left(B_j\right)}_\text{law of total probability}}
\end{split}
$$



Tags: mathematics statistics SS25
<!--ID: 1752652160583-->
END

START
Basic
bayesian inference: Single Bayesian Update
- definition
- names of the term's
- explanation
Back: 
For a [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ and general [[event space|event]] $A$ the [[bayes theorem]] states the following.
$$
P\left(B_i \mid A\right) 
= \frac{
\overbrace{P\left(A \mid B_i\right)}^\text{likelihood}
\overbrace{P\left(B_i\right)}^\text{prior}
}
{
\underbrace{\sum\limits_{j=1}^k P\left(A \mid B_j\right)P\left(B_j\right)}_{P(A)}
}
$$
We are interested in the [[probability]] of [[event]] $B_i$, and we have a prior [[hypothesis]] $P(B_i)$. Then we observe the occurrence of and [[stochastic independent|dependent]] [[event]] $A$, and we want to update our [[hypothesis]]. For this we need the [[likelihood function]] that [[event]] $A$ happened under the assumption that $B_i$ is true and divide it by the [[probability]] of the observed [[event]] $A$. The [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ is still normalized $\left(\sum P(B_i) = 1 \right)$.  
Tags: mathematics statistics
<!--ID: 1667051814864-->
END



START
Basic
bayesian inference: Multiple Bayesian Updates
- definition
- recursive definition
Back: 
We have multiple [[observations]] $\{A_i \mid i = 1,2...,N\}$ and a [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ . From the conditional version of the [[bayes theorem]] we know the following:


$$
\begin{split}
P\left(B_i \mid \bigcap_\limits{i=1}^{N} A_n \right) 

&= \frac{P\left(B_l \cap \bigcap\limits_{n=1}^{N} A_n \right)}
{P\left(\bigcap\limits_{n=1}^{N} A_n \right)} \\

&= \frac{P\left(B_i\right) P\left( \bigcap\limits_{n=1}^{N} A_n \mid B_i \right)}
{
\sum\limits_{l=1}^{k} P(B_l) P\left(\bigcap\limits_{n=1}^{N} A_n \mid B_l\right)
} \\
&= \frac{P\left(B_i\right) P\left(  A_1 \cap A_2 \: \cap \: ... \: \cap \:A_n \mid B_i \right)}
{
\sum\limits_{l=1}^{k} P(B_l) P\left( A_1 \cap A_2 \: \cap \: ... \: \cap \:A_n \mid B_l\right)
} \\
&= \frac{P\left(B_k\right) \prod\limits_{n=1}^{N}P \left(  A_n \Bigm\vert B_k \cap 
\bigcap\limits_{j=1}^{n-1} A_j \right)}
{
\sum\limits_{j=1}^{k} P(B_j) 
\prod\limits_{n=1}^{N}P \left(  A_n \Bigm\vert B_k \cap 
\bigcap\limits_{j=1}^{n-1} A_j \right)
} 
\end{split}
$$
With the [[bayes theorem|conditional version of the bayes theorem]] we know that we can compose the term in the following way.
$$
\begin{split}
P\left(B_i \mid \bigcap_\limits{j=1}^{n} A_j \right) 

&= \frac{
P\left(B_i \cap \bigcap\limits_{j=1}^{n-1} A_j \right)
P\left(A_n \mid B_i \cap \bigcap\limits_{j=1}^{n-1} A_j \right)
}
{

\underbrace{
\sum\limits_{k=1}^{K}
P\left(B_k \cap \bigcap\limits_{j=1}^{n-1} A_j \right)
P\left(A_n \mid B_k \cap \bigcap\limits_{j=1}^{n-1} A_j \right)
}_{P\left(A_n \mid \bigcap\limits_{i=1}^{n-1} A_i\right)}
} 


\end{split}
$$
Here we can see that it is possible to define the posterior in a recursive way. This version is easy to calculate because we can just reuse the posterior of the previous step a prior and do another single Bayesian update.
$$
\begin{split}
P\left(B_i^{(0)}  \right) &:=  P\left(B_i\right) \\
P\left(B_i^{(n)}  \right) &:= P\left(B_i\right)P\left(B_i \mid \bigcap_\limits{i=1}^{N} A_n \right) \\
&= \frac{
\overbrace{
P\left(B_i^{(n-1)}\right)
}^{P\left(B_i \mid \bigcap_\limits{j=1}^{n-1} A_j \right) }
\overbrace{
P\left(A_n \mid B_i^{(n-1)}\right)
}^{P\left(A_n \mid B_i \cap \bigcap\limits_{j=1}^{n-1} A_j \right)}
}
{
\underbrace{
\sum\limits_{l=1}^{k} P(B_l^{(n-1)}) P\left( A_n \mid B_l^{(n-1)}\right)
}_{P\left(A_n \mid \bigcap\limits_{i=1}^{n-1} A_i\right)}
}
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1667051814869-->
END



START
Basic
bayesian inference example:
We have a fair coin $B_1$ and a coin with head on both sides $B_2$, and we choose a one of the two coins randomly with $P(B_1) =P(B_1)= \frac{1}{2}$. Then we flip the coin $n$ times, and it allays shows head $\{H_n \mid n = 1,...,N\}$. How big is the probability that we have chosen the fair coin $B_1$.
Back:
$$
\begin{split}
P\left(B_1^{(0)}  \right) &=  \frac{1}{2} \\
P\left(B_1^{(1)}  \right) 
&= \frac{
\overbrace{P\left(H_1 \mid B_1^{(0)}\right)}^\text{likelihood}
\overbrace{P\left(B_1^{(0)}\right)}^\text{prior}
}
{
\underbrace{\sum\limits_{i=1}^2 P\left(H_1 \mid B_i^{(0)}\right)P\left(B_i^{(0)}\right)}_{P(H_1)}
} 
= \frac{\frac{1}{2}\cdot\frac{1}{2}}{\frac{1}{2} \cdot 1 + \frac{1}{2} \cdot \frac{1}{2}} = \frac{1}{3} \\
P\left(B_1^{(2)}  \right) 
&= 
\frac{
\overbrace{
P\left(B_1^{(2)}\right)
}^{P\left(B_1 \mid   H_1 \right) }
P\left(H_1 \mid B_1^{(2)}\right)
}
{
\underbrace{
\sum\limits_{l=1}^{2} P\left(B_l^{(2)}\right) P\left( H_2 \mid B_l^{(2)}\right)
}_{P\left(H_2 \mid  H_1 \right)}
}
= \frac{\frac{1}{3}\cdot\frac{1}{2}}{\frac{2}{3} \cdot 1 + \frac{1}{3} \cdot \frac{1}{2}} = \frac{1}{5}\\

\end{split}
$$
Tags: mathematics statistics
<!--ID: 1667051814873-->
END