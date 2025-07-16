### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$
#### properties
##### the trace is equal to the sum of eigenvalues

$$
\mathrm{trace}(A) = \sum_{i \in [n]} \sigma_i(A)
$$
TODO add proof
##### trace of a matrix product
- for $A, B \in \mathbb{R}^{n \times n}$ 
$$
\mathrm{trace}(AB) = \mathrm{trace}(BA)
$$
proof
$$
\begin{split}
\mathrm{trace}(AB) 
&=\sum_{i \in [n]} \sum_{k \in [n]} a_{i,k} b_{k,i} \\
&=\sum_{k \in [n]} \sum_{i \in [n]} b_{k,i} a_{i,k} \\
&= \mathrm{trace}(BA)\\
\end{split}
$$

##### trace of a transpose
$$
\mathrm{trace}(A) = \mathrm{trace}\left(A^\top\right)
$$
proof
$$
\begin{split}
\mathrm{trace}(A) 
&=\sum_{i \in [n]}  a_{i,i}  
&=\mathrm{trace} \left(A^\top\right)
\end{split}
$$
# anki

START
Basic
[[trace]] of a [[matrix]]
- definition
- relationship [[trace]] to [[eigenvector|eigenvalues]]
- [[trace]] of a [[matrix product]] (with proof)
- [[trace]] of a [[transpose]] (with proof)
Back: 
### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$
### properties
#### the [[trace]] is equal to the [[addition|sum]] of [[eigenvector|eigenvalues]]

$$
\mathrm{trace}(A) = \sum_{i \in [n]} \sigma_i(A)
$$
TODO add proof
#### [[trace]] of a [[matrix product]]
- for $A, B \in \mathbb{R}^{n \times n}$ 
$$
\mathrm{trace}(AB) = \mathrm{trace}(BA)
$$
proof
$$
\begin{split}
\mathrm{trace}(AB) 
&=\sum_{i \in [n]} \sum_{k \in [n]} a_{i,k} b_{k,i} \\
&=\sum_{k \in [n]} \sum_{i \in [n]} b_{k,i} a_{i,k} \\
&= \mathrm{trace}(BA)\\
\end{split}
$$

#### [[trace]] of a [[transpose]]
$$
\mathrm{trace}(A) = \mathrm{trace}\left(A^\top\right)
$$
proof
$$
\begin{split}
\mathrm{trace}(A) 
&=\sum_{i \in [n]}  a_{i,i}  
&=\mathrm{trace} \left(A^\top\right)
\end{split}
$$
Tags: mathematics
<!--ID: 1715521606639-->
END


START
Basic
proof for the following
$$
\mathrm{trace}(AB) = \mathrm{trace}(BA)
$$

Back: 

#### [[trace]] of a [[matrix product]]
- for $A, B \in \mathbb{R}^{n \times n}$ 
$$
\mathrm{trace}(AB) = \mathrm{trace}(BA)
$$
proof
$$
\begin{split}
\mathrm{trace}(AB) 
&=\sum_{i \in [n]} \sum_{k \in [n]} a_{i,k} b_{k,i} \\
&=\sum_{k \in [n]} \sum_{i \in [n]} b_{k,i} a_{i,k} \\
&= \mathrm{trace}(BA)\\
\end{split}
$$
________________________


### trace
- given a [[square matrix]] $A \in \mathbb{R}^{n \times n}$
- the [[trace]] of $A$ is defined as the [[addition|sum]] of the main diagonal
$$
\mathrm{trace}(A) = \sum_{i \in [n]} a_{ii}
$$


#### [[trace]] of a [[transpose]]
$$
\mathrm{trace}(A) = \mathrm{trace}\left(A^\top\right)
$$
proof
$$
\begin{split}
\mathrm{trace}(A) 
&=\sum_{i \in [n]}  a_{i,i}  
&=\mathrm{trace} \left(A^\top\right)
\end{split}
$$
Tags: mathematics
<!--ID: 1716383932088-->
END