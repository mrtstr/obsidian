Method for [[statistical inference]] in which the [[bayes theorem]] is used to update a [[hypothesis]] that is based on prior knowledge when new [[event space|events]] occur.

## Single Bayesian Update
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
We are interested in the [[probability]] of [[event]] $B_i$, and we have a prior [[hypothesis]] $P(B_i)$. Then we observe the occurrence of and [[stochastic independent|dependent]] [[event]] $A$, and we want to update our [[hypothesis]]. For this we need the [[likelihood]] that [[event]] $A$ happened under the assumption that $B_i$ is true and divide it by the [[probability]] of the observed [[event]] $A$. The [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ is still normalized $\left(\sum P(B_i) = 1 \right)$.  

## Multiple Bayesian Updates
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
We are interested in the [[probability]] of [[event]] $B_i$, and we have a prior [[hypothesis]] $P(B_i)$. Then we observe the occurrence of and [[stochastic independent|dependent]] [[event]] $A$, and we want to update our [[hypothesis]]. For this we need the [[likelihood]] that [[event]] $A$ happened under the assumption that $B_i$ is true and divide it by the [[probability]] of the observed [[event]] $A$. The [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ is still normalized $\left(\sum P(B_i) = 1 \right)$.  
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