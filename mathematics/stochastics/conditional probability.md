[[probability space]]
[[conditional distribution]]

## Definition
Probability of [[event space|event]] $A$ happened given that we know [[event space|event]] $B$ happened
$$
\begin{split}
P\left(A \mid B\right) 
&= \frac{P\left(A \cap B\right)}{P\left(B\right)} \\
&= \frac{P\left(B \mid A\right)P\left(A\right)}{P\left(B\right)} \\
&= \frac{P\left(A \mid B\right)P\left(B\right)}{P\left(B\right)}
\end{split}
$$
![[Selection_001.png]]

### decomposition on the [[intersection of sets]] of [[event space|events]] 
$$
P(A \cap B) = P(B) P(A \mid B) = P(A) P(B \mid A)
$$
$$
\begin{split}
P\left(\bigcap_{i=1}^{n} A_i \right)= &
P\left(A_1\right) \cdot 
P\left(A_2 \mid A_1\right) \cdot
P\left(A_3 \mid A_1 \cap A_2 \right) \cdot \:... \: \cdot
P\left(A_n \mid A_1 \cap A_2 \cap \:... \: A_{n-1} \right) \\
=&\prod\limits_{i=1}^{k}P \left( A_i \Bigm\vert
\bigcap_{j=1}^{i-1} A_j \right)
\end{split}
$$

# Anki
START
Basic
conditional probability
- definition
- decomposition on the [[intersection of sets]] of [[event space|events]] 
Back: 
## Definition
Probability of [[event space|event]] $A$ happened given that we know [[event space|event]] $B$ happened
$$
\begin{split}
P\left(A \mid B\right) 
&= \frac{P\left(A \cap B\right)}{P\left(B\right)} \\
&= \frac{P\left(B \mid A\right)P\left(A\right)}{P\left(B\right)} \\
&= \frac{P\left(A \mid B\right)P\left(B\right)}{P\left(B\right)}
\end{split}
$$
![[Selection_001.png]]

## decomposition on the [[intersection of sets]] of [[event space|events]] 
$$
P(A \cap B) = P(B) P(A \mid B) = P(A) P(B \mid A)
$$
$$
\begin{split}
P\left(\bigcap_{i=1}^{n} A_i \right)= &
P\left(A_1\right) \cdot 
P\left(A_2 \mid A_1\right) \cdot
P\left(A_3 \mid A_1 \cap A_2 \right) \cdot \:... \: \cdot
P\left(A_n \mid A_1 \cap A_2 \cap \:... \: A_{n-1} \right) \\
=&\prod\limits_{i=1}^{k}P \left( A_i \Bigm\vert
\bigcap_{j=1}^{i-1} A_j \right)
\end{split}
$$

Tags: mathematics statistics
<!--ID: 1666457499349-->
END


START
Basic
- given a [[partitioned sample space]] $\{B_1, ..., B_n\}$
- proof for the following
$$
\begin{split}
P(A | X) = \sum_{all B_j} P(A| B, X) P(B_j | X)
\end{split}
$$
Back: 

$$
\begin{split}
P(A | X) 
&= \frac{P(A , X) }{P(X)} \\
&= \sum_{all B_j} \frac{P(A , X, B_j) }{P(X)} \\
&= \sum_{all B_j} \frac{P(A | X, B_j) P(B_j | X) P(X) }{P(X)} \\
&= \sum_{all B_j} P(A| B, X) P(B_j | X)
\end{split}
$$
Tags: mathematics statistics
<!--ID: 1707456323135-->
END
