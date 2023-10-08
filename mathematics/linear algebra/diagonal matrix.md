## diagonal matrix
A [[matrix]] $D$ is a [[diagonal matrix]] when all values that are not on the diagonal are zero
$$
\begin{split}
D \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}   & =  \left( d_{i, j}\right)_{i \in \mathcal{I}, j \in \mathcal{J}} \text{ with } \forall i \neq j : d_{ij} = 0 \\
\end{split}
$$
$$
\begin{split}
D = \begin{pmatrix}
d_{11}         &\ 0         &\ 0 \\
0         &\ d_{22}          &\ 0 \\
0         &\ 0         &\ d_{33}  \\  
\end{pmatrix}
\end{split}
$$


## Properties for $D \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{I} \right|}}$ ([[square matrix]])
1) $det(D) = \prod\limits_{i=1}^{min\left( \left| \mathcal{I} \right| \times \left| \mathcal{J} \right| \right)} d_i$ $D \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{I} \right|}}$ is [[square matrix]]
2) $D = D^\top$ ($D$ is a [[symmetric matrix]])
3) $D^{-1} = diag\left(\left(d_{i}^{-1}\right)_{i \in \mathcal{I}} \right)$ (its [[inverse matrix|inverse]] is a [[diagonal matrix]] with all entry's inverted)
4) $D$ is [[regular matrix]] iff $a_i \neq 0$ 
5) $rank(D)=\sum\limits_{i \in \mathcal{I}}\mathbb{I}\left[a_i \neq 0\right]$


## Applications
- Used in the [[singular value decomposition]]
- [[spectral theorem]]

START
Basic
diagonal matrix
- definition
- Properties for $D \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{I} \right|}}$ ([[square matrix]]) (6)
- Applications (2)
Back: 
## Definition
A [[matrix]] $D$ is a [[diagonal matrix]] when all values that are not on the diagonal are $=0$

$$
\begin{split}
D \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{J} \right|}}   & =  \left( d_{i, j}\right)_{i \in \mathcal{I}, j \in \mathcal{J}} \text{ with } \forall i \neq j : d_{ij} = 0 \\
\end{split}
$$
$$
\begin{split}
D = \begin{pmatrix}
d_{11}         &\ 0         &\ 0 \\
0         &\ d_{22}          &\ 0 \\
0         &\ 0         &\ d_{33}  \\  
\end{pmatrix}
\end{split}
$$

## Properties for $D \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{I} \right|}}$ ([[square matrix]])
1) $det(D) = \prod\limits_{i=1}^{min\left( \left| \mathcal{I} \right| \times \left| \mathcal{J} \right| \right)} d_i$ $D \in \mathbb{R^{\left| \mathcal{I} \right| \times \left| \mathcal{I} \right|}}$ is [[square matrix]]
2) $D = D^\top$ ($D$ is a [[symmetric matrix]])
3) $D^{-1} = diag\left(\left(d_{i}^{-1}\right)_{i \in \mathcal{I}} \right)$ (its [[inverse matrix|inverse]] is a [[diagonal matrix]] with all entry's inverted)
4) $D$ is [[regular matrix]] iff $a_i \neq 0$ 

## Applications
- Used in the [[singular value decomposition]]
- [[spectral theorem]]
Tags: mathematics linear_algebra
<!--ID: 1665918408923-->
END