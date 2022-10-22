[[probability space]]
[[conditional distribution]]

## Definition
Probability of [[event space|event]] $A$ happened given that we know [[event space|event]] $B$ happened
$$
P(A \mid B) = \frac{P\left(A \cap B\right)}{P\left(B\right)}
$$
![[Selection_001.png]]

### decomposition on the [[intersection]] of [[event space|events]] 
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

## law of total probability
for a [[partition of a sample space]] $B = \{B_i \mid i=1,2,...,k\}$ the following is true:
$$
P(A)=\sum\limits_{i=1}^{k}P(B_i)\cdot P(A \mid B_i)
$$
![[Selection_002.png]]


START
Basic
conditional probability
- definition
- decomposition on the [[intersection]] of [[event space|events]] 
Back: 
## Definition
Probability of [[event space|event]] $A$ happened given that we know [[event space|event]] $B$ happened
$$
P(A \mid B) = \frac{P\left(A \cap B\right)}{P\left(B\right)}
$$
![[Selection_001.png]]

## decomposition on the [[intersection]] of [[event space|events]] 
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

Tags: mathematics, statistics
<!--ID: 1666457499349-->
END


START
Basic
law of total probability
Back: 
## Definition
for a [[partition of a sample space]] $B = \{B_i \mid i=1,2,...,k\}$ the following is true:
$$
P(A)=\sum\limits_{i=1}^{k}P(B_i)\cdot P(A \mid B_i)
$$
![[Selection_002.png]]

Tags: mathematics, statistics
<!--ID: 1666457499354-->
END