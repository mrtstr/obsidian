The [[bayes theorem]] describes the probability of an [[event space|event]] based on prior knowledge. Used for [[bayesian inference]].

## [[bayes theorem]]
With [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ and general [[event space|event]] $A$ follows after [[conditional probability|law of total probability]] and the definition of [[conditional probability]]:
$$
P\left(B_i \mid A\right) 
= \frac{P\left(A \mid B_i\right)P\left(B_i\right)}
{\sum\limits_{j=1}^k P\left(A \mid B_j\right)P\left(B_j\right)}
$$
Proof:
$$
\begin{split}
P\left(B_i \mid A\right) 
&= \frac{P\left(A \cap B_i\right)}
{P\left(A \right)} \\

&= \frac{\overbrace{P\left(A \mid B_i\right)P\left(B_i\right)}^\text{conditional probability}}
{\underbrace{\sum\limits_{j=1}^k P\left(A \mid B_j\right)P\left(B_j\right)}_\text{law of total probability}}
\end{split}
$$




## [[conditional probability|conditional]] version of the [[bayes theorem]]

With [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ and general [[event space|events]] $A_1, A_2$ follows out of the [[bayes theorem]]: 

$$
P\left(B_i \mid A_1 \cap A_2\right) 
= \frac{P\left(A_1 \mid B_i  \cap A_2\right)P\left(B_i \mid A_2\right)}
{\sum\limits_{j=1}^k P\left(A_1 \mid B_j  \cap A_2\right)P\left(B_j \mid A_2\right)} 
$$
proof:
$$
\begin{split}
P\left(B_i \mid A_1 \cap A_2\right) 
&= \frac{P\left(B_i  \cap A_1 \cap A_2\right)}
{P\left(A_1 \cap A_2 \right)} \\
&= \frac{P\left(A_1 \mid B_i \cap A_2\right)P\left(B_i  \mid A_2\right)P\left( A_2 \right)}
{P\left(A_1  \mid A_2 \right) P\left( A_2 \right)} \\
&= \frac{P\left(A_1 \mid B_i \cap A_2\right)P\left(B_i  \mid A_2\right)}
{P\left(A_1  \mid A_2 \right) } \\
&= \frac{P\left(A_1 \mid B_i  \cap A_2\right)P\left(B_i \mid A_2\right)}
{
\underbrace{\sum\limits_{j=1}^k P\left(A_1 \mid B_j  \cap A_2\right)P\left(B_j \mid A_2\right)}_\text{law of total probability}
} \\

\end{split}
$$


START
Basic
[[bayes theorem]]
- explanation
- definition 
- proof
Back: 
## Explanation
The [[bayes theorem]] describes the probability of an [[event space|event]] based on prior knowledge. Used for [[bayesian inference]].
## Definition
With [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ and general [[event space|event]] $A$ follows after [[conditional probability|law of total probability]] and the definition of [[conditional probability]]:

$$
P\left(B_i \mid A\right) 
= \frac{P\left(A \mid B_i\right)P\left(B_i\right)}
{\sum\limits_{j=1}^k P\left(A \mid B_j\right)P\left(B_j\right)}
$$
## Proof
$$
\begin{split}
P\left(B_i \mid A\right) 
&= \frac{P\left(A \cap B_i\right)}
{P\left(A \right)} \\

&= \frac{\overbrace{P\left(A \mid B_i\right)P\left(B_i\right)}^\text{conditional probability}}
{\underbrace{\sum\limits_{j=1}^k P\left(A \mid B_j\right)P\left(B_j\right)}_\text{law of total probability}}
\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1664619948140-->
END


START
Basic
[[conditional probability|conditional]] version of the [[bayes theorem]]
- definition
- proof
Back: 
## definition
With [[partitioned sample space]] $\{B_i \mid i = 1,2...,k\}$ and general [[event space|events]] $A_1, A_2$ follows out of the [[bayes theorem]]: 


$$
P\left(B_i \mid A_1 \cap A_2\right) 
= \frac{P\left(A_1 \mid B_i  \cap A_2\right)P\left(B_i \mid A_2\right)}
{\sum\limits_{j=1}^k P\left(A_1 \mid B_j  \cap A_2\right)P\left(B_j \mid A_2\right)} 
$$
## proof
$$
\begin{split}
P\left(B_i \mid A_1 \cap A_2\right) 
&= \frac{P\left(B_i  \cap A_1 \cap A_2\right)}
{P\left(A_1 \cap A_2 \right)} \\
&= \frac{P\left(A_1 \mid B_i \cap A_2\right)P\left(B_i  \mid A_2\right)P\left( A_2 \right)}
{P\left(A_1  \mid A_2 \right) P\left( A_2 \right)} \\
&= \frac{P\left(A_1 \mid B_i \cap A_2\right)P\left(B_i  \mid A_2\right)}
{P\left(A_1  \mid A_2 \right) } \\
&= \frac{P\left(A_1 \mid B_i  \cap A_2\right)P\left(B_i \mid A_2\right)}
{
\underbrace{\sum\limits_{j=1}^k P\left(A_1 \mid B_j  \cap A_2\right)P\left(B_j \mid A_2\right)}_\text{law of total probability}
} \\

\end{split}
$$
Tags: mathematics, statistics
<!--ID: 1667051814884-->
END