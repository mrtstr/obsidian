## Definition [[row echelon form]]
A [[matrix]] $A$ is in [[row echelon form]] oif all non-zero rows have a [[pivot]]

![[pivot#Definition pivot]]


## example
- $A_1$ is not in [[row echelon form]] because row $2$ does not have a [[pivot]]
- $A_2$ is in [[row echelon form]] because $a_{(1:1)}$, $a_{(2:2)}$ and $a_{(3:3)}$ are pivor elements and row $4$ is a zero row
- $A_3$ is in [[row echelon form]] because $a_{(1:1)}$ and $a_{(2:3)}$ are [[pivot]] elements and row $3$ is a zero row


$$
\begin{split}
A_1 = \begin{pmatrix}
a_{(1:1)} &\ a_{(1:2)} &\ 0 \\
0 &\ a_{(2:2)} &\ a_{(2:3)} \\
0		&\  a_{(3:2)} &\ a_{(3:3)} \\  
0		 &0           &\ 0               \\  
\end{pmatrix}
\end{split}
$$

$$
\begin{split}
A_2 = \begin{pmatrix}
a_{(1:1)} &\ a_{(1:2)} &\ 0 \\
0 &\ a_{(2:2)}       &\ a_{(2:3)} \\
0 &\  0        &\ a_{(3:3)} \\  
0 &\  0        &\ 0               \\  
\end{pmatrix}
\end{split}
$$

$$
\begin{split}
A_3 = \begin{pmatrix}
a_{(1:1)} &\ 0 &\ a_{(1:3)} \\
0 &\ 0       &\ a_{(2:3)} \\
0 &\  0        &\ 0 \\  
\end{pmatrix}
\end{split}
$$
### definition basic and non-basic columns

Given a [[matrix]] $A$ in [[row echelon form]].
A column $A_{(*,j)}$ is a basic column is it contains a [[pivot]]
#### example
$A_{(*,1)}$ and $A_{(*,3)}$ are basic columns because $a_{(1:1)}$ and $a_{(2:3)}$ are [[pivot]] elements and  $A_{(*,2)}$ is non-basic
$$
\begin{split}
A_3 = \begin{pmatrix}
a_{(1:1)} &\ 0 &\ a_{(1:3)} \\
0 &\ 0       &\ a_{(2:3)} \\
0 &\  0        &\ 0 \\  
\end{pmatrix}
\end{split}
$$


# Anki

START
Basic
[[row echelon form]]
- defintion
Back: 
## Definition [[row echelon form]]
A [[matrix]] $A$ is in [[row echelon form]] oif all non-zero rows have a [[pivot]]

#### Definition [[pivot]]
An elelemt $a_{ij}$ if m [[matrix]] $A$ is a [[pivot]] element if the following conditions are true
1) $a_{ij} \neq 0$
2) all elements below $a_{ij}$ are zero and all elements on the right of  $a_{ij}$ are zero $\forall k \geq i, l \leq j,(kl) \neq (ij) :a_{kl} = 0$
example
$$
\begin{split}
A = \begin{pmatrix}
a_{(1:1)} &\    a_{(1:2)}     &\ a_{(1:3)} \\
zero         &\ p             &\ a_{(2:3)} \\
zero		&\   zero         &\ a_{(3:3)} \\  
\end{pmatrix}
\end{split}
$$

Tags: mathematics linear_algebra
<!--ID: 1696747212382-->
END


START
Basic
are $A_1$, $A_2$ and $A_3$ in [[row echelon form]]?

$$
\begin{split}
A_1 = \begin{pmatrix}
a_{(1:1)} &\ a_{(1:2)} &\ 0 \\
0 &\ a_{(2:2)} &\ a_{(2:3)} \\
0		&\  a_{(3:2)} &\ a_{(3:3)} \\  
0		 &0           &\ 0               \\  
\end{pmatrix}
\end{split}
$$

$$
\begin{split}
A_2 = \begin{pmatrix}
a_{(1:1)} &\ a_{(1:2)} &\ 0 \\
0 &\ a_{(2:2)}       &\ a_{(2:3)} \\
0 &\  0        &\ a_{(3:3)} \\  
0 &\  0        &\ 0               \\  
\end{pmatrix}
\end{split}
$$

$$
\begin{split}
A_3 = \begin{pmatrix}
a_{(1:1)} &\ 0 &\ a_{(1:3)} \\
0 &\ 0       &\ a_{(2:3)} \\
0 &\  0        &\ 0 \\  
\end{pmatrix}
\end{split}
$$

Back: 

- $A_1$ is not in [[row echelon form]] because row $2$ does not have a [[pivot]]
- $A_2$ is in [[row echelon form]] because $a_{(1:1)}$, $a_{(2:2)}$ and $a_{(3:3)}$ are pivor elements and row $4$ is a zero row
- $A_3$ is in [[row echelon form]] because $a_{(1:1)}$ and $a_{(2:3)}$ are [[pivot]] elements and row $3$ is a zero row

## Definition [[row echelon form]]
A [[matrix]] $A$ is in [[row echelon form]] oif all non-zero rows have a [[pivot]]

#### Definition [[pivot]]
An elelemt $a_{ij}$ if m [[matrix]] $A$ is a [[pivot]] element if the following conditions are true
1) $a_{ij} \neq 0$
2) all elements below $a_{ij}$ are zero and all elements on the right of  $a_{ij}$ are zero $\forall k \geq i, l \leq j,(kl) \neq (ij) :a_{kl} = 0$


Tags: mathematics linear_algebra
<!--ID: 1696747212390-->
END