$$
\begin{split}
P\left(B_l \mid \bigcap_\limits{i=1}^{n} A_i \right) 

&= \frac{P\left(B_l \cap \bigcap\limits_{i=1}^{n} A_i \right)}
{P\left(\bigcap\limits_{i=1}^{n} A_i \right)} \\

&= \frac{P\left(B_l\right) P\left( \bigcap\limits_{i=1}^{n} A_i \mid B_l \right)}
{
\sum\limits_{j=1}^{k} P(B_j) P\left(\bigcap\limits_{i=1}^{n} A_i \mid B_j\right)
} \\


&= \frac{P\left(B_k\right) \prod\limits_{i=1}^{n}P \left(  A_i \Bigm\vert B_k \cap 
\bigcap\limits_{j=1}^{i-1} A_j \right)}
{
\sum\limits_{j=1}^{k} P(B_j) P\left(\bigcap\limits_{i=1}^{n} A_i \mid B_j\right)
} \\
&= \frac{P\left(B_i \cap \bigcap_{i=1}^{n} A_i \right)}
{\sum\limits_{j=1}^k P\left(A_1 \mid B_j  \cap A_2\right)P\left(B_j \mid A_2\right)} \\
\end{split}
$$