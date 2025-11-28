## backpropagation
- let $f_\theta$ be [[neural network]] with $L$ layers and element wise [[nn activation function]] $g^{(i)}$ and let $l$ be a [[loss function]]
- the goal is to solve the following [[unconstraint optimization problem]] with [[gradient descent]]

$$
\hat\theta = \arg\min_{\theta} \frac{1}{m} \sum_{i=1}^m l\left(y^{(i)}, f_\theta \left(x^{(i)}\right)\right)
$$
- in the following we will just work with a single $(x, y)$ tuple but since the [[derivative]] is linear this can easily be extended to a sum


### algorithm
0) $\mathrm{a}^{(0)}=x$
1) forward pass: for $i \in 1, ..., L$

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

2) calculate

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\nabla_ {W^{(L)}} l &= \left( \underbrace {a^{(L-1)}}_{\mathbb{R}^{n_{L-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_L \times n_{L-1}} \\
 \nabla_ {b^{(L)}} l 
&= \delta^{(L)\top} \in \mathbb{R}^{n_{L}} \\
\end{split}
$$

3) backwards pass for $k \in L-1, ..., 1$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\delta^{(k+1)\top}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
W^{(k+1)}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}  \in \mathbb{R}^{1\times n_{k}}\\
\nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_k \times n_{k-1}} \\
 \nabla_ {b^{(k)}} l 
&= \delta^{(k)\top} \in \mathbb{R}^{n_{k}} \\
\end{split}
$$


4) return $\nabla_\theta l=\left(\nabla_W^{(1)}, \nabla_b^{(1)}, ..., \nabla_W^{(L)}, \nabla_b^{(L)}\right)$ 
### element wise solution for the gradient
- let $\delta^{(k)}_j$ be the [[partial derivative]] of the loss function with respect to the $j \in \left\{1, ..., n^{(k)}\right\}$ element of the output of the $k \in \left\{1, ..., L\right\}$ layer

$$
\begin{split}
\delta^{(k)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(W^{(k)} \mathrm{a}^{(i-1)} + b^{(k)}\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(\sum_j\sum_i W_{ji} a^{k-1}_i + b^k\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)} \\
\end{split}
$$

- based on $\delta^{(k)}_j$ we can calculate the [[partial derivative]] of the loss after an arbitrary parameter of the weight matrix of an arbitrary layer $W_{ji}^{(k)}$ by applying the [[chain rule]] (depending on the activation of the previous layer $a^{(k-1)}$)

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial W_{ji}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(W_{ji}^{(k)}\right)\right)\right)}{\partial W_{ji}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{k}}} \right)^\top
\end{split}
$$
- the same approach can be used for the bias term $b_{j}^{(k)}$ 

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial b_{j}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(b_{j}^{(k)}\right)\right)\right)}{\partial b_{j}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i b_{j}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \delta^{(k)}_j \\
  &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {b^{(k)}} l 
  &=\delta^{(k)\top} \in \mathbb{R}^{n_{k}}
\end{split}
$$

- the [[derivative]] of the loss with respect to the $j$ element of the output of a layer $\delta^{(l)}_j$ can be expressed as a product of the derivative of its [[nn activation function]] multiplied by a weighted sum of the $\delta^{(l-1)}$ of the previous layer

$$
\begin{split}
\delta^{(L)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(L)}\right)\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \sum_i  \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_i^{(L)}} \cdot \frac{\partial g\left(\mathrm{z}^{(L)}\right)_i}{\partial \mathrm{z}^{(L)}_j}  \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_j^{(L)}} \cdot \frac{\partial g\left(\mathrm{z}_j^{(L)}\right)}{\partial \mathrm{z}^{(L)}_j}  \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_j^{(L)}} \cdot g'\left(\mathrm{z}_j^{(L)}\right)  \\
\end{split}
$$

$$
\begin{split}
\delta^{(l-1)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(l)}\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(l)}\right)\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(l)}\right)\right)}{\partial \mathrm{z}^{(l)}_i} \frac{\partial \mathrm{z}^{(l)}_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  \frac{\partial \mathrm{z}^{(l)}_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  \frac{\partial \left(W^{(l)}g\left(\mathrm{z}^{(l-1)}\right) + b^{(l)}\right)_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  
  \frac{\partial \left(\sum_c W^{(l)}_{i c}\, g\left(z^{(l-1)}_c\right) + b^{(l)}_i\right)}
       {\partial z^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  
  \frac{\partial \left( W^{(l)}_{i j}\, g\left(z^{(l-1)}_j\right)\right)}
       {\partial z^{(l-1)}_j} \\
&=  g'\!\left(z^{(l-1)}_j\right) \sum_i \delta^{(l)}_i  
  W^{(l)}_{i j} \,
\end{split}
$$


### vector solution for the gradient
- for the parameters we have the following

$$
\begin{split}
\nabla_ {W^{(k)}} l &= \left(\underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{k}}} \right)^\top \\
  &= \left( a^{(k-1)}\delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right) \right)^\top \\
\nabla_ {b^{(k)}} l &= \delta^{(k)\top}\in \mathbb{R}^{n_{k}} \\
&= \left(\delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right)\right)^\top \\
\end{split}
$$

- we have the following [[derivative]] of the [[loss function]] with respect to the output of the layer $k$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}}\in \mathbb{R}^{1\times n_k} \\
\end{split}
$$

- this can be decomposed to the outer [[derivative]] of the [[loss function]] with respect to the activation of the $k$ layer $\mathrm{a}^{(k)}$ and the [[derivative]] of the [[nn activation function]] $g^{(k)}$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}}_{\mathbb{R}^{1\times n_k}} 
\underbrace{\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}}_{\mathbb{R}^{n_k\times n_k}} \in \mathbb{R}^{1\times n_k}  \\

&= 
\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}
Dg^{(k)}\left( \mathrm{z}^{(k)}\right) \\

\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}
&=\frac{\partial g^{(k)}\left( \mathrm{z}^{(k)}\right)}{\partial \mathrm{z}^{(k)}} =Dg^{(k)}\left( \mathrm{z}^{(k)}\right)\\
\end{split}
$$

- in the last layer $L$ we have the following [[derivative]]

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\end{split}
$$

- in all following layers $k$ we can express the [[derivative]] depending on the [[derivative]] of the previous layer $\delta^{(k)\top}$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}^{(k)}}Dg\left( \mathrm{z}^{(k)}\right) \\
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{z}^{(k+1)}}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}\\
&= \delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right) \\
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
&= \frac{\partial W^{(k+1)}\mathrm{a}^{(k)} + b^{(k+1)}}{\partial \mathrm{a}^{(k)}} \\
\end{split}
$$

# ------------

![[neural network#neural network]]

![[chain rule#multi variable case]]
# anki
START
Basic
[[nn backpropagation]]
- let $\delta^{(k)}_j$ be the [[partial derivative]] of the loss function with respect to the $j \in \left\{1, ..., n^{(k)}\right\}$ element of the output of the $k \in \left\{1, ..., L\right\}$ layer
- calculate  $\nabla_ {W^{(k)}} l$ and $\nabla_ {b^{(k)}} l$

$$
\begin{split}
\delta^{(k)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
\end{split}
$$

Back: 

- let $\delta^{(k)}_j$ be the [[partial derivative]] of the loss function with respect to the $j \in \left\{1, ..., n^{(k)}\right\}$ element of the output of the $k \in \left\{1, ..., L\right\}$ layer

$$
\begin{split}
\delta^{(k)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(W^{(k)} \mathrm{a}^{(i-1)} + b^{(k)}\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(\sum_j\sum_i W_{ji} a^{k-1}_i + b^k\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)} \\
\end{split}
$$

- based on $\delta^{(k)}_j$ we can calculate the [[partial derivative]] of the loss after an arbitrary parameter of the weight matrix of an arbitrary layer $W_{ji}^{(k)}$ by applying the [[chain rule]] (depending on the activation of the previous layer $a^{(k-1)}$)

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial W_{ji}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(W_{ji}^{(k)}\right)\right)\right)}{\partial W_{ji}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{k}}} \right)^\top
\end{split}
$$
- the same approach can be used for the bias term $b_{j}^{(k)}$ 

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial b_{j}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(b_{j}^{(k)}\right)\right)\right)}{\partial b_{j}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i b_{j}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \delta^{(k)}_j \\
  &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {b^{(k)}} l 
  &=\delta^{(k)\top} \in \mathbb{R}^{n_{k}}
\end{split}
$$



## backpropagation
- let $f_\theta$ be [[neural network]] with $L$ layers and element wise [[nn activation function]] $g^{(i)}$ and let $l$ be a [[loss function]]
- the goal is to solve the following [[unconstraint optimization problem]] with [[gradient descent]]

$$
\hat\theta = \arg\min_{\theta} \frac{1}{m} \sum_{i=1}^m l\left(y^{(i)}, f_\theta \left(x^{(i)}\right)\right)
$$
- in the following we will just work with a single $(x, y)$ tuple but since the [[derivative]] is linear this can easily be extended to a sum


### algorithm
0) $\mathrm{a}^{(0)}=x$
1) forward pass: for $i \in 1, ..., L$

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

2) calculate

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\nabla_ {W^{(L)}} l &= \left( \underbrace {a^{(L-1)}}_{\mathbb{R}^{n_{L-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_L \times n_{L-1}} \\
 \nabla_ {b^{(L)}} l 
&= \delta^{(L)\top} \in \mathbb{R}^{n_{L}} \\
\end{split}
$$

3) backwards pass for $k \in L-1, ..., 1$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\delta^{(k+1)\top}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
W^{(k+1)}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}  \in \mathbb{R}^{1\times n_{k}}\\
\nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_k \times n_{k-1}} \\
 \nabla_ {b^{(k)}} l 
&= \delta^{(k)\top} \in \mathbb{R}^{n_{k}} \\
\end{split}
$$


4) return $\nabla_\theta l=\left(\nabla_W^{(1)}, \nabla_b^{(1)}, ..., \nabla_W^{(L)}, \nabla_b^{(L)}\right)$ 
### element wise solution for the gradient
- let $\delta^{(k)}_j$ be the [[partial derivative]] of the loss function with respect to the $j \in \left\{1, ..., n^{(k)}\right\}$ element of the output of the $k \in \left\{1, ..., L\right\}$ layer

$$
\begin{split}
\delta^{(k)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(W^{(k)} \mathrm{a}^{(i-1)} + b^{(k)}\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(\sum_j\sum_i W_{ji} a^{k-1}_i + b^k\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)} \\
\end{split}
$$

- based on $\delta^{(k)}_j$ we can calculate the [[partial derivative]] of the loss after an arbitrary parameter of the weight matrix of an arbitrary layer $W_{ji}^{(k)}$ by applying the [[chain rule]] (depending on the activation of the previous layer $a^{(k-1)}$)

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial W_{ji}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(W_{ji}^{(k)}\right)\right)\right)}{\partial W_{ji}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{k}}} \right)^\top
\end{split}
$$
- the same approach can be used for the bias term $b_{j}^{(k)}$ 

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial b_{j}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(b_{j}^{(k)}\right)\right)\right)}{\partial b_{j}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i b_{j}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \delta^{(k)}_j \\
  &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {b^{(k)}} l 
  &=\delta^{(k)\top} \in \mathbb{R}^{n_{k}}
\end{split}
$$

- the [[derivative]] of the loss with respect to the $j$ element of the output of a layer $\delta^{(l)}_j$ can be expressed as a product of the derivative of its [[nn activation function]] multiplied by a weighted sum of the $\delta^{(l-1)}$ of the previous layer

$$
\begin{split}
\delta^{(L)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(L)}\right)\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \sum_i  \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_i^{(L)}} \cdot \frac{\partial g\left(\mathrm{z}^{(L)}\right)_i}{\partial \mathrm{z}^{(L)}_j}  \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_j^{(L)}} \cdot \frac{\partial g\left(\mathrm{z}_j^{(L)}\right)}{\partial \mathrm{z}^{(L)}_j}  \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_j^{(L)}} \cdot g'\left(\mathrm{z}_j^{(L)}\right)  \\
\end{split}
$$

$$
\begin{split}
\delta^{(l-1)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(l)}\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(l)}\right)\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(l)}\right)\right)}{\partial \mathrm{z}^{(l)}_i} \frac{\partial \mathrm{z}^{(l)}_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  \frac{\partial \mathrm{z}^{(l)}_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  \frac{\partial \left(W^{(l)}g\left(\mathrm{z}^{(l-1)}\right) + b^{(l)}\right)_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  
  \frac{\partial \left(\sum_c W^{(l)}_{i c}\, g\left(z^{(l-1)}_c\right) + b^{(l)}_i\right)}
       {\partial z^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  
  \frac{\partial \left( W^{(l)}_{i j}\, g\left(z^{(l-1)}_j\right)\right)}
       {\partial z^{(l-1)}_j} \\
&=  g'\!\left(z^{(l-1)}_j\right) \sum_i \delta^{(l)}_i  
  W^{(l)}_{i j} \,
\end{split}
$$


### vector solution for the gradient
- for the parameters we have the following

$$
\begin{split}
\nabla_ {W^{(k)}} l &= \left(\underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{k}}} \right)^\top \\
  &= \left( a^{(k-1)}\delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right) \right)^\top \\
\nabla_ {b^{(k)}} l &= \delta^{(k)\top}\in \mathbb{R}^{n_{k}} \\
&= \left(\delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right)\right)^\top \\
\end{split}
$$

- we have the following [[derivative]] of the [[loss function]] with respect to the output of the layer $k$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}}\in \mathbb{R}^{1\times n_k} \\
\end{split}
$$

- this can be decomposed to the outer [[derivative]] of the [[loss function]] with respect to the activation of the $k$ layer $\mathrm{a}^{(k)}$ and the [[derivative]] of the [[nn activation function]] $g^{(k)}$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}}_{\mathbb{R}^{1\times n_k}} 
\underbrace{\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}}_{\mathbb{R}^{n_k\times n_k}} \in \mathbb{R}^{1\times n_k}  \\

&= 
\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}
Dg^{(k)}\left( \mathrm{z}^{(k)}\right) \\

\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}
&=\frac{\partial g^{(k)}\left( \mathrm{z}^{(k)}\right)}{\partial \mathrm{z}^{(k)}} =Dg^{(k)}\left( \mathrm{z}^{(k)}\right)\\
\end{split}
$$

- in the last layer $L$ we have the following [[derivative]]

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\end{split}
$$

- in all following layers $k$ we can express the [[derivative]] depending on the [[derivative]] of the previous layer $\delta^{(k)\top}$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}^{(k)}}Dg\left( \mathrm{z}^{(k)}\right) \\
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{z}^{(k+1)}}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}\\
&= \delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right) \\
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
&= \frac{\partial W^{(k+1)}\mathrm{a}^{(k)} + b^{(k+1)}}{\partial \mathrm{a}^{(k)}} \\
\end{split}
$$


_____________


## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[nn activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
- the output of each layer is called the activation vector $\mathrm{a}^{(i)}$ with the first being the input of the model $\mathrm{a}^{(0)}=x \in \mathbb{R}^{n_0}$ 

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

- the complete model can be represented by a function $f_\theta$

$$
\begin{split}
f_\theta &= \mathrm{a}^{(L)} \\
\theta &= \left(W^{(1)}, b^{(1)}, ..., W^{(L)}, b^{(L)}\right) \\
\end{split}
$$

- note: if none of the [[nn activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers


## chain rule
### single variable case
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$

#### intuition chain rule
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$


### multi variable case
let 
- $x \in \mathbb{R}^{n}$ 
- $g: \mathbb{R}^n \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}$ 

$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x_i} 
&= \lim_{h \to 0} \frac{ f\left(g(x + e_i h)\right) - f\left(g(x )\right) }{h}  \\
&= \sum_{j=1}^m   \frac{\partial f\left(g(x)\right)}{\partial g(x)_j} \frac{\partial g(x)_j}{\partial x_i} \\
&= Df\left(g(x)\right) Dg(x)_{(: i)} \in \mathbb{R} \\
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= D{g \circ f}(x) \\
&= Df\left(g(x)\right) Dg(x) \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

- with the [[jacobian]] $Df\left(g(x)\right) \in \mathbb{R}^{1\times m}$ and $Dg(x) \in \mathbb{R}^{m \times n}$ 
#### dimensions
- let $F = f\left(g(x)\right)$
- the rule for the decomposing the [[derivative]] with the [[chain rule]] is outer times inner and the dimensions are as follows

$$
\begin{split}
DF(x) = 
\underbrace{\left.Df(u)\right|_{u=g(x)}}_{
\mathbb{R}^{\mathrm{dim}(f) \times \mathrm{dim}(g)}} 
\quad
\underbrace{Dg(x)}_{\mathbb{R}^{\mathrm{dim}(g) \times \mathrm{dim}(x)}} 
\in \mathbb{R}^{\mathrm{dim}(F) \times \mathrm{dim}(x)} \\
\end{split}
$$

#### proof

- $g$ and $f$ are [[differentiable]] so that the following exists

$$
\begin{split}
g(x+h) 
=& g(x) + Dg(x)h + \varphi_g(h), \quad &\frac{||\varphi_g(h)||}{||h||} \to_{h \to 0} 0 \\
f\left(u+v(h)\right) =& f(u) + Df(u)v(h) + \varphi_f\left(v(h)\right) , \qquad &\frac{||\varphi_f(v)||}{||v||} \to_{v \to 0} 0  \\
\end{split}
$$
- now define

$$
\begin{split}
u :=& g(x)  \\
v(h) :=& Dg(x)h + \varphi_g(h)  \\
g(x+h) =& u + v(h)
\end{split}
$$
- now insert

$$
\begin{split}
f(g(x+h))
&= f(u + v(h)) \\
&= f(u) + Df(u)[v(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u)[Dg(x)[h] + \varphi_g(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u) Dg(x)[h] + \underbrace{ Df(u)\varphi_g(h) + \varphi_f(v(h))}_{r(h)} \\
r(h) &= Df(u)\varphi_g(h) + \varphi_f(v(h)), \quad  \frac{||r(h)||}{||h||} \to_{h \to 0} 0
\end{split}
$$

- it follows that

$$
\begin{split}
D f\left(g(x)\right) 
&= \underbrace{\left. Df\left(u\right) \right |_{u=g(x)}}_{\in \mathbb{R}^{1\times m}}\underbrace{ Dg(x)}_{\in \mathbb{R}^{m\times n}} \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

#### intuition
- if the ith dimension of $x$ changes by a delta, this can lead to a change of all dimensions of $g(x)$ and each change of a $g(x)_j$ can lead to a change of $f\left(g(x)\right)$ 
- by summing up the effects we have the [[partial derivative]]

$$
\lim_{h \to 0} \sum_{j=1}^m  \frac{ g(x+e_ih)_j -  g(x)_j}{h}  \cdot \frac{ f\left(g(x) + e_j h\right)-f\left(g(x)\right)}{h}   $$


Tags: mathematics WS2526 ml
<!--ID: 1764141526847-->
END


START
Basic
[[nn backpropagation]]
- let $\delta^{(k)}$ be the [[partial derivative]] of the loss function with respect the output of the $k \in \left\{1, ..., L\right\}$ layer
- calculate the [[derivative]] in vector form for the last layer and for hidden layers

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}}\in \mathbb{R}^{1\times n_k} \\
\end{split}
$$

## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[nn activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
- the output of each layer is called the activation vector $\mathrm{a}^{(i)}$ with the first being the input of the model $\mathrm{a}^{(0)}=x \in \mathbb{R}^{n_0}$ 

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

- the complete model can be represented by a function $f_\theta$

$$
\begin{split}
f_\theta &= \mathrm{a}^{(L)} \\
\theta &= \left(W^{(1)}, b^{(1)}, ..., W^{(L)}, b^{(L)}\right) \\
\end{split}
$$

- note: if none of the [[nn activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers


Back: 

- we have the following [[derivative]] of the [[loss function]] with respect to the output of the layer $k$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}}\in \mathbb{R}^{1\times n_k} \\
\end{split}
$$

- this can be decomposed to the outer [[derivative]] of the [[loss function]] with respect to the activation of the $k$ layer $\mathrm{a}^{(k)}$ and the [[derivative]] of the [[nn activation function]] $g^{(k)}$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}}_{\mathbb{R}^{1\times n_k}} 
\underbrace{\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}}_{\mathbb{R}^{n_k\times n_k}} \in \mathbb{R}^{1\times n_k}  \\

&= 
\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}
Dg^{(k)}\left( \mathrm{z}^{(k)}\right) \\

\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}
&=\frac{\partial g^{(k)}\left( \mathrm{z}^{(k)}\right)}{\partial \mathrm{z}^{(k)}} =Dg^{(k)}\left( \mathrm{z}^{(k)}\right)\\
\end{split}
$$

- in the last layer $L$ we have the following [[derivative]]

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\end{split}
$$

- in all following layers $k$ we can express the [[derivative]] depending on the [[derivative]] of the previous layer $\delta^{(k)\top}$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}^{(k)}}Dg\left( \mathrm{z}^{(k)}\right) \\
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{z}^{(k+1)}}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}\\
&= \delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right) \\
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
&= \frac{\partial W^{(k+1)}\mathrm{a}^{(k)} + b^{(k+1)}}{\partial \mathrm{a}^{(k)}} \\
\end{split}
$$


## backpropagation
- let $f_\theta$ be [[neural network]] with $L$ layers and element wise [[nn activation function]] $g^{(i)}$ and let $l$ be a [[loss function]]
- the goal is to solve the following [[unconstraint optimization problem]] with [[gradient descent]]

$$
\hat\theta = \arg\min_{\theta} \frac{1}{m} \sum_{i=1}^m l\left(y^{(i)}, f_\theta \left(x^{(i)}\right)\right)
$$
- in the following we will just work with a single $(x, y)$ tuple but since the [[derivative]] is linear this can easily be extended to a sum


### algorithm
0) $\mathrm{a}^{(0)}=x$
1) forward pass: for $i \in 1, ..., L$

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

2) calculate

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\nabla_ {W^{(L)}} l &= \left( \underbrace {a^{(L-1)}}_{\mathbb{R}^{n_{L-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_L \times n_{L-1}} \\
 \nabla_ {b^{(L)}} l 
&= \delta^{(L)\top} \in \mathbb{R}^{n_{L}} \\
\end{split}
$$

3) backwards pass for $k \in L-1, ..., 1$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\delta^{(k+1)\top}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
W^{(k+1)}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}  \in \mathbb{R}^{1\times n_{k}}\\
\nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_k \times n_{k-1}} \\
 \nabla_ {b^{(k)}} l 
&= \delta^{(k)\top} \in \mathbb{R}^{n_{k}} \\
\end{split}
$$


4) return $\nabla_\theta l=\left(\nabla_W^{(1)}, \nabla_b^{(1)}, ..., \nabla_W^{(L)}, \nabla_b^{(L)}\right)$ 
### element wise solution for the gradient
- let $\delta^{(k)}_j$ be the [[partial derivative]] of the loss function with respect to the $j \in \left\{1, ..., n^{(k)}\right\}$ element of the output of the $k \in \left\{1, ..., L\right\}$ layer

$$
\begin{split}
\delta^{(k)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(W^{(k)} \mathrm{a}^{(i-1)} + b^{(k)}\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(\sum_j\sum_i W_{ji} a^{k-1}_i + b^k\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)} \\
\end{split}
$$

- based on $\delta^{(k)}_j$ we can calculate the [[partial derivative]] of the loss after an arbitrary parameter of the weight matrix of an arbitrary layer $W_{ji}^{(k)}$ by applying the [[chain rule]] (depending on the activation of the previous layer $a^{(k-1)}$)

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial W_{ji}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(W_{ji}^{(k)}\right)\right)\right)}{\partial W_{ji}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{k}}} \right)^\top
\end{split}
$$
- the same approach can be used for the bias term $b_{j}^{(k)}$ 

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial b_{j}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(b_{j}^{(k)}\right)\right)\right)}{\partial b_{j}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i b_{j}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \delta^{(k)}_j \\
  &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {b^{(k)}} l 
  &=\delta^{(k)\top} \in \mathbb{R}^{n_{k}}
\end{split}
$$

- the [[derivative]] of the loss with respect to the $j$ element of the output of a layer $\delta^{(l)}_j$ can be expressed as a product of the derivative of its [[nn activation function]] multiplied by a weighted sum of the $\delta^{(l-1)}$ of the previous layer

$$
\begin{split}
\delta^{(L)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(L)}\right)\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \sum_i  \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_i^{(L)}} \cdot \frac{\partial g\left(\mathrm{z}^{(L)}\right)_i}{\partial \mathrm{z}^{(L)}_j}  \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_j^{(L)}} \cdot \frac{\partial g\left(\mathrm{z}_j^{(L)}\right)}{\partial \mathrm{z}^{(L)}_j}  \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_j^{(L)}} \cdot g'\left(\mathrm{z}_j^{(L)}\right)  \\
\end{split}
$$

$$
\begin{split}
\delta^{(l-1)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(l)}\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(l)}\right)\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(l)}\right)\right)}{\partial \mathrm{z}^{(l)}_i} \frac{\partial \mathrm{z}^{(l)}_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  \frac{\partial \mathrm{z}^{(l)}_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  \frac{\partial \left(W^{(l)}g\left(\mathrm{z}^{(l-1)}\right) + b^{(l)}\right)_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  
  \frac{\partial \left(\sum_c W^{(l)}_{i c}\, g\left(z^{(l-1)}_c\right) + b^{(l)}_i\right)}
       {\partial z^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  
  \frac{\partial \left( W^{(l)}_{i j}\, g\left(z^{(l-1)}_j\right)\right)}
       {\partial z^{(l-1)}_j} \\
&=  g'\!\left(z^{(l-1)}_j\right) \sum_i \delta^{(l)}_i  
  W^{(l)}_{i j} \,
\end{split}
$$


### vector solution for the gradient
- for the parameters we have the following

$$
\begin{split}
\nabla_ {W^{(k)}} l &= \left(\underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{k}}} \right)^\top \\
  &= \left( a^{(k-1)}\delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right) \right)^\top \\
\nabla_ {b^{(k)}} l &= \delta^{(k)\top}\in \mathbb{R}^{n_{k}} \\
&= \left(\delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right)\right)^\top \\
\end{split}
$$

- we have the following [[derivative]] of the [[loss function]] with respect to the output of the layer $k$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}}\in \mathbb{R}^{1\times n_k} \\
\end{split}
$$

- this can be decomposed to the outer [[derivative]] of the [[loss function]] with respect to the activation of the $k$ layer $\mathrm{a}^{(k)}$ and the [[derivative]] of the [[nn activation function]] $g^{(k)}$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}}_{\mathbb{R}^{1\times n_k}} 
\underbrace{\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}}_{\mathbb{R}^{n_k\times n_k}} \in \mathbb{R}^{1\times n_k}  \\

&= 
\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}
Dg^{(k)}\left( \mathrm{z}^{(k)}\right) \\

\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}
&=\frac{\partial g^{(k)}\left( \mathrm{z}^{(k)}\right)}{\partial \mathrm{z}^{(k)}} =Dg^{(k)}\left( \mathrm{z}^{(k)}\right)\\
\end{split}
$$

- in the last layer $L$ we have the following [[derivative]]

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\end{split}
$$

- in all following layers $k$ we can express the [[derivative]] depending on the [[derivative]] of the previous layer $\delta^{(k)\top}$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}^{(k)}}Dg\left( \mathrm{z}^{(k)}\right) \\
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{z}^{(k+1)}}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}\\
&= \delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right) \\
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
&= \frac{\partial W^{(k+1)}\mathrm{a}^{(k)} + b^{(k+1)}}{\partial \mathrm{a}^{(k)}} \\
\end{split}
$$

_____________


## chain rule
### single variable case
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$

#### intuition chain rule
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$


### multi variable case
let 
- $x \in \mathbb{R}^{n}$ 
- $g: \mathbb{R}^n \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}$ 

$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x_i} 
&= \lim_{h \to 0} \frac{ f\left(g(x + e_i h)\right) - f\left(g(x )\right) }{h}  \\
&= \sum_{j=1}^m   \frac{\partial f\left(g(x)\right)}{\partial g(x)_j} \frac{\partial g(x)_j}{\partial x_i} \\
&= Df\left(g(x)\right) Dg(x)_{(: i)} \in \mathbb{R} \\
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= D{g \circ f}(x) \\
&= Df\left(g(x)\right) Dg(x) \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

- with the [[jacobian]] $Df\left(g(x)\right) \in \mathbb{R}^{1\times m}$ and $Dg(x) \in \mathbb{R}^{m \times n}$ 
#### dimensions
- let $F = f\left(g(x)\right)$
- the rule for the decomposing the [[derivative]] with the [[chain rule]] is outer times inner and the dimensions are as follows

$$
\begin{split}
DF(x) = 
\underbrace{\left.Df(u)\right|_{u=g(x)}}_{
\mathbb{R}^{\mathrm{dim}(f) \times \mathrm{dim}(g)}} 
\quad
\underbrace{Dg(x)}_{\mathbb{R}^{\mathrm{dim}(g) \times \mathrm{dim}(x)}} 
\in \mathbb{R}^{\mathrm{dim}(F) \times \mathrm{dim}(x)} \\
\end{split}
$$

#### proof

- $g$ and $f$ are [[differentiable]] so that the following exists

$$
\begin{split}
g(x+h) 
=& g(x) + Dg(x)h + \varphi_g(h), \quad &\frac{||\varphi_g(h)||}{||h||} \to_{h \to 0} 0 \\
f\left(u+v(h)\right) =& f(u) + Df(u)v(h) + \varphi_f\left(v(h)\right) , \qquad &\frac{||\varphi_f(v)||}{||v||} \to_{v \to 0} 0  \\
\end{split}
$$
- now define

$$
\begin{split}
u :=& g(x)  \\
v(h) :=& Dg(x)h + \varphi_g(h)  \\
g(x+h) =& u + v(h)
\end{split}
$$
- now insert

$$
\begin{split}
f(g(x+h))
&= f(u + v(h)) \\
&= f(u) + Df(u)[v(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u)[Dg(x)[h] + \varphi_g(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u) Dg(x)[h] + \underbrace{ Df(u)\varphi_g(h) + \varphi_f(v(h))}_{r(h)} \\
r(h) &= Df(u)\varphi_g(h) + \varphi_f(v(h)), \quad  \frac{||r(h)||}{||h||} \to_{h \to 0} 0
\end{split}
$$

- it follows that

$$
\begin{split}
D f\left(g(x)\right) 
&= \underbrace{\left. Df\left(u\right) \right |_{u=g(x)}}_{\in \mathbb{R}^{1\times m}}\underbrace{ Dg(x)}_{\in \mathbb{R}^{m\times n}} \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

#### intuition
- if the ith dimension of $x$ changes by a delta, this can lead to a change of all dimensions of $g(x)$ and each change of a $g(x)_j$ can lead to a change of $f\left(g(x)\right)$ 
- by summing up the effects we have the [[partial derivative]]

$$
\lim_{h \to 0} \sum_{j=1}^m  \frac{ g(x+e_ih)_j -  g(x)_j}{h}  \cdot \frac{ f\left(g(x) + e_j h\right)-f\left(g(x)\right)}{h}   $$


Tags: mathematics WS2526 ml
<!--ID: 1764243748861-->
END


START
Basic
[[nn backpropagation]] summary: definitions and solutions for the following
- calculate  $\nabla_ {W^{(k)}} l$ and $\nabla_ {b^{(k)}} l$
- $\delta^{(k)}$ and $\delta^{(L)}$

Back: 
## backpropagation
- let $f_\theta$ be [[neural network]] with $L$ layers and element wise [[nn activation function]] $g^{(i)}$ and let $l$ be a [[loss function]]
- the goal is to solve the following [[unconstraint optimization problem]] with [[gradient descent]]

$$
\hat\theta = \arg\min_{\theta} \frac{1}{m} \sum_{i=1}^m l\left(y^{(i)}, f_\theta \left(x^{(i)}\right)\right)
$$
- in the following we will just work with a single $(x, y)$ tuple but since the [[derivative]] is linear this can easily be extended to a sum


### algorithm
0) $\mathrm{a}^{(0)}=x$
1) forward pass: for $i \in 1, ..., L$

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

2) calculate

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\nabla_ {W^{(L)}} l &= \left( \underbrace {a^{(L-1)}}_{\mathbb{R}^{n_{L-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_L \times n_{L-1}} \\
 \nabla_ {b^{(L)}} l 
&= \delta^{(L)\top} \in \mathbb{R}^{n_{L}} \\
\end{split}
$$

3) backwards pass for $k \in L-1, ..., 1$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\delta^{(k+1)\top}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
W^{(k+1)}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}  \in \mathbb{R}^{1\times n_{k}}\\
\nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_k \times n_{k-1}} \\
 \nabla_ {b^{(k)}} l 
&= \delta^{(k)\top} \in \mathbb{R}^{n_{k}} \\
\end{split}
$$


4) return $\nabla_\theta l=\left(\nabla_W^{(1)}, \nabla_b^{(1)}, ..., \nabla_W^{(L)}, \nabla_b^{(L)}\right)$ 
### element wise solution for the gradient
- let $\delta^{(k)}_j$ be the [[partial derivative]] of the loss function with respect to the $j \in \left\{1, ..., n^{(k)}\right\}$ element of the output of the $k \in \left\{1, ..., L\right\}$ layer

$$
\begin{split}
\delta^{(k)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(W^{(k)} \mathrm{a}^{(i-1)} + b^{(k)}\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(\sum_j\sum_i W_{ji} a^{k-1}_i + b^k\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)} \\
\end{split}
$$

- based on $\delta^{(k)}_j$ we can calculate the [[partial derivative]] of the loss after an arbitrary parameter of the weight matrix of an arbitrary layer $W_{ji}^{(k)}$ by applying the [[chain rule]] (depending on the activation of the previous layer $a^{(k-1)}$)

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial W_{ji}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(W_{ji}^{(k)}\right)\right)\right)}{\partial W_{ji}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{k}}} \right)^\top
\end{split}
$$
- the same approach can be used for the bias term $b_{j}^{(k)}$ 

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial b_{j}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(b_{j}^{(k)}\right)\right)\right)}{\partial b_{j}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i b_{j}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \delta^{(k)}_j \\
  &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {b^{(k)}} l 
  &=\delta^{(k)\top} \in \mathbb{R}^{n_{k}}
\end{split}
$$

- the [[derivative]] of the loss with respect to the $j$ element of the output of a layer $\delta^{(l)}_j$ can be expressed as a product of the derivative of its [[nn activation function]] multiplied by a weighted sum of the $\delta^{(l-1)}$ of the previous layer

$$
\begin{split}
\delta^{(L)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(L)}\right)\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \sum_i  \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_i^{(L)}} \cdot \frac{\partial g\left(\mathrm{z}^{(L)}\right)_i}{\partial \mathrm{z}^{(L)}_j}  \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_j^{(L)}} \cdot \frac{\partial g\left(\mathrm{z}_j^{(L)}\right)}{\partial \mathrm{z}^{(L)}_j}  \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_j^{(L)}} \cdot g'\left(\mathrm{z}_j^{(L)}\right)  \\
\end{split}
$$

$$
\begin{split}
\delta^{(l-1)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(l)}\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(l)}\right)\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(l)}\right)\right)}{\partial \mathrm{z}^{(l)}_i} \frac{\partial \mathrm{z}^{(l)}_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  \frac{\partial \mathrm{z}^{(l)}_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  \frac{\partial \left(W^{(l)}g\left(\mathrm{z}^{(l-1)}\right) + b^{(l)}\right)_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  
  \frac{\partial \left(\sum_c W^{(l)}_{i c}\, g\left(z^{(l-1)}_c\right) + b^{(l)}_i\right)}
       {\partial z^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  
  \frac{\partial \left( W^{(l)}_{i j}\, g\left(z^{(l-1)}_j\right)\right)}
       {\partial z^{(l-1)}_j} \\
&=  g'\!\left(z^{(l-1)}_j\right) \sum_i \delta^{(l)}_i  
  W^{(l)}_{i j} \,
\end{split}
$$


### vector solution for the gradient
- for the parameters we have the following

$$
\begin{split}
\nabla_ {W^{(k)}} l &= \left(\underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{k}}} \right)^\top \\
  &= \left( a^{(k-1)}\delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right) \right)^\top \\
\nabla_ {b^{(k)}} l &= \delta^{(k)\top}\in \mathbb{R}^{n_{k}} \\
&= \left(\delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right)\right)^\top \\
\end{split}
$$

- we have the following [[derivative]] of the [[loss function]] with respect to the output of the layer $k$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}}\in \mathbb{R}^{1\times n_k} \\
\end{split}
$$

- this can be decomposed to the outer [[derivative]] of the [[loss function]] with respect to the activation of the $k$ layer $\mathrm{a}^{(k)}$ and the [[derivative]] of the [[nn activation function]] $g^{(k)}$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}}_{\mathbb{R}^{1\times n_k}} 
\underbrace{\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}}_{\mathbb{R}^{n_k\times n_k}} \in \mathbb{R}^{1\times n_k}  \\

&= 
\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}
Dg^{(k)}\left( \mathrm{z}^{(k)}\right) \\

\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}
&=\frac{\partial g^{(k)}\left( \mathrm{z}^{(k)}\right)}{\partial \mathrm{z}^{(k)}} =Dg^{(k)}\left( \mathrm{z}^{(k)}\right)\\
\end{split}
$$

- in the last layer $L$ we have the following [[derivative]]

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\end{split}
$$

- in all following layers $k$ we can express the [[derivative]] depending on the [[derivative]] of the previous layer $\delta^{(k)\top}$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}^{(k)}}Dg\left( \mathrm{z}^{(k)}\right) \\
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{z}^{(k+1)}}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}\\
&= \delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right) \\
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
&= \frac{\partial W^{(k+1)}\mathrm{a}^{(k)} + b^{(k+1)}}{\partial \mathrm{a}^{(k)}} \\
\end{split}
$$

## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[nn activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
- the output of each layer is called the activation vector $\mathrm{a}^{(i)}$ with the first being the input of the model $\mathrm{a}^{(0)}=x \in \mathbb{R}^{n_0}$ 

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

- the complete model can be represented by a function $f_\theta$

$$
\begin{split}
f_\theta &= \mathrm{a}^{(L)} \\
\theta &= \left(W^{(1)}, b^{(1)}, ..., W^{(L)}, b^{(L)}\right) \\
\end{split}
$$

- note: if none of the [[nn activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers


_____________


## chain rule
### single variable case
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$

#### intuition chain rule
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$


### multi variable case
let 
- $x \in \mathbb{R}^{n}$ 
- $g: \mathbb{R}^n \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}$ 

$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x_i} 
&= \lim_{h \to 0} \frac{ f\left(g(x + e_i h)\right) - f\left(g(x )\right) }{h}  \\
&= \sum_{j=1}^m   \frac{\partial f\left(g(x)\right)}{\partial g(x)_j} \frac{\partial g(x)_j}{\partial x_i} \\
&= Df\left(g(x)\right) Dg(x)_{(: i)} \in \mathbb{R} \\
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= D{g \circ f}(x) \\
&= Df\left(g(x)\right) Dg(x) \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

- with the [[jacobian]] $Df\left(g(x)\right) \in \mathbb{R}^{1\times m}$ and $Dg(x) \in \mathbb{R}^{m \times n}$ 
#### dimensions
- let $F = f\left(g(x)\right)$
- the rule for the decomposing the [[derivative]] with the [[chain rule]] is outer times inner and the dimensions are as follows

$$
\begin{split}
DF(x) = 
\underbrace{\left.Df(u)\right|_{u=g(x)}}_{
\mathbb{R}^{\mathrm{dim}(f) \times \mathrm{dim}(g)}} 
\quad
\underbrace{Dg(x)}_{\mathbb{R}^{\mathrm{dim}(g) \times \mathrm{dim}(x)}} 
\in \mathbb{R}^{\mathrm{dim}(F) \times \mathrm{dim}(x)} \\
\end{split}
$$

#### proof

- $g$ and $f$ are [[differentiable]] so that the following exists

$$
\begin{split}
g(x+h) 
=& g(x) + Dg(x)h + \varphi_g(h), \quad &\frac{||\varphi_g(h)||}{||h||} \to_{h \to 0} 0 \\
f\left(u+v(h)\right) =& f(u) + Df(u)v(h) + \varphi_f\left(v(h)\right) , \qquad &\frac{||\varphi_f(v)||}{||v||} \to_{v \to 0} 0  \\
\end{split}
$$
- now define

$$
\begin{split}
u :=& g(x)  \\
v(h) :=& Dg(x)h + \varphi_g(h)  \\
g(x+h) =& u + v(h)
\end{split}
$$
- now insert

$$
\begin{split}
f(g(x+h))
&= f(u + v(h)) \\
&= f(u) + Df(u)[v(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u)[Dg(x)[h] + \varphi_g(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u) Dg(x)[h] + \underbrace{ Df(u)\varphi_g(h) + \varphi_f(v(h))}_{r(h)} \\
r(h) &= Df(u)\varphi_g(h) + \varphi_f(v(h)), \quad  \frac{||r(h)||}{||h||} \to_{h \to 0} 0
\end{split}
$$

- it follows that

$$
\begin{split}
D f\left(g(x)\right) 
&= \underbrace{\left. Df\left(u\right) \right |_{u=g(x)}}_{\in \mathbb{R}^{1\times m}}\underbrace{ Dg(x)}_{\in \mathbb{R}^{m\times n}} \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

#### intuition
- if the ith dimension of $x$ changes by a delta, this can lead to a change of all dimensions of $g(x)$ and each change of a $g(x)_j$ can lead to a change of $f\left(g(x)\right)$ 
- by summing up the effects we have the [[partial derivative]]

$$
\lim_{h \to 0} \sum_{j=1}^m  \frac{ g(x+e_ih)_j -  g(x)_j}{h}  \cdot \frac{ f\left(g(x) + e_j h\right)-f\left(g(x)\right)}{h}   $$


Tags: mathematics WS2526 ml
<!--ID: 1764243748864-->
END


START
Basic
[[nn backpropagation]]
- algorithm

Back: 
## backpropagation
- let $f_\theta$ be [[neural network]] with $L$ layers and element wise [[nn activation function]] $g^{(i)}$ and let $l$ be a [[loss function]]
- the goal is to solve the following [[unconstraint optimization problem]] with [[gradient descent]]

$$
\hat\theta = \arg\min_{\theta} \frac{1}{m} \sum_{i=1}^m l\left(y^{(i)}, f_\theta \left(x^{(i)}\right)\right)
$$
- in the following we will just work with a single $(x, y)$ tuple but since the [[derivative]] is linear this can easily be extended to a sum


### algorithm
0) $\mathrm{a}^{(0)}=x$
1) forward pass: for $i \in 1, ..., L$

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

2) calculate

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\nabla_ {W^{(L)}} l &= \left( \underbrace {a^{(L-1)}}_{\mathbb{R}^{n_{L-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_L \times n_{L-1}} \\
 \nabla_ {b^{(L)}} l 
&= \delta^{(L)\top} \in \mathbb{R}^{n_{L}} \\
\end{split}
$$

3) backwards pass for $k \in L-1, ..., 1$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\delta^{(k+1)\top}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
W^{(k+1)}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}  \in \mathbb{R}^{1\times n_{k}}\\
\nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{L}}} \right)^\top \in \mathbb{R}^{n_k \times n_{k-1}} \\
 \nabla_ {b^{(k)}} l 
&= \delta^{(k)\top} \in \mathbb{R}^{n_{k}} \\
\end{split}
$$


4) return $\nabla_\theta l=\left(\nabla_W^{(1)}, \nabla_b^{(1)}, ..., \nabla_W^{(L)}, \nabla_b^{(L)}\right)$ 
### element wise solution for the gradient
- let $\delta^{(k)}_j$ be the [[partial derivative]] of the loss function with respect to the $j \in \left\{1, ..., n^{(k)}\right\}$ element of the output of the $k \in \left\{1, ..., L\right\}$ layer

$$
\begin{split}
\delta^{(k)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(W^{(k)} \mathrm{a}^{(i-1)} + b^{(k)}\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(\sum_j\sum_i W_{ji} a^{k-1}_i + b^k\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)} \\
\end{split}
$$

- based on $\delta^{(k)}_j$ we can calculate the [[partial derivative]] of the loss after an arbitrary parameter of the weight matrix of an arbitrary layer $W_{ji}^{(k)}$ by applying the [[chain rule]] (depending on the activation of the previous layer $a^{(k-1)}$)

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial W_{ji}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(W_{ji}^{(k)}\right)\right)\right)}{\partial W_{ji}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {W^{(k)}} l &= \left( \underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{k}}} \right)^\top
\end{split}
$$
- the same approach can be used for the bias term $b_{j}^{(k)}$ 

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial b_{j}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(b_{j}^{(k)}\right)\right)\right)}{\partial b_{j}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i b_{j}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \delta^{(k)}_j \\
  &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
  \Rightarrow \nabla_ {b^{(k)}} l 
  &=\delta^{(k)\top} \in \mathbb{R}^{n_{k}}
\end{split}
$$

- the [[derivative]] of the loss with respect to the $j$ element of the output of a layer $\delta^{(l)}_j$ can be expressed as a product of the derivative of its [[nn activation function]] multiplied by a weighted sum of the $\delta^{(l-1)}$ of the previous layer

$$
\begin{split}
\delta^{(L)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(L)}\right)\right)}{\partial \mathrm{z}^{(L)}_j} \\
&= \sum_i  \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_i^{(L)}} \cdot \frac{\partial g\left(\mathrm{z}^{(L)}\right)_i}{\partial \mathrm{z}^{(L)}_j}  \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_j^{(L)}} \cdot \frac{\partial g\left(\mathrm{z}_j^{(L)}\right)}{\partial \mathrm{z}^{(L)}_j}  \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}_j^{(L)}} \cdot g'\left(\mathrm{z}_j^{(L)}\right)  \\
\end{split}
$$

$$
\begin{split}
\delta^{(l-1)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(l)}\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(l)}\right)\right)}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \frac{\partial \mathcal{l}\left(y, g\left(\mathrm{z}^{(l)}\right)\right)}{\partial \mathrm{z}^{(l)}_i} \frac{\partial \mathrm{z}^{(l)}_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  \frac{\partial \mathrm{z}^{(l)}_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  \frac{\partial \left(W^{(l)}g\left(\mathrm{z}^{(l-1)}\right) + b^{(l)}\right)_i}{\partial \mathrm{z}^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  
  \frac{\partial \left(\sum_c W^{(l)}_{i c}\, g\left(z^{(l-1)}_c\right) + b^{(l)}_i\right)}
       {\partial z^{(l-1)}_j} \\
&= \sum_i \delta^{(l)}_i  
  \frac{\partial \left( W^{(l)}_{i j}\, g\left(z^{(l-1)}_j\right)\right)}
       {\partial z^{(l-1)}_j} \\
&=  g'\!\left(z^{(l-1)}_j\right) \sum_i \delta^{(l)}_i  
  W^{(l)}_{i j} \,
\end{split}
$$


### vector solution for the gradient
- for the parameters we have the following

$$
\begin{split}
\nabla_ {W^{(k)}} l &= \left(\underbrace {a^{(k-1)}}_{\mathbb{R}^{n_{k-1} \times 1}} \quad\underbrace{\delta^{(k)}}_{\mathbb{R}^{1 \times n_{k}}} \right)^\top \\
  &= \left( a^{(k-1)}\delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right) \right)^\top \\
\nabla_ {b^{(k)}} l &= \delta^{(k)\top}\in \mathbb{R}^{n_{k}} \\
&= \left(\delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right)\right)^\top \\
\end{split}
$$

- we have the following [[derivative]] of the [[loss function]] with respect to the output of the layer $k$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}}\in \mathbb{R}^{1\times n_k} \\
\end{split}
$$

- this can be decomposed to the outer [[derivative]] of the [[loss function]] with respect to the activation of the $k$ layer $\mathrm{a}^{(k)}$ and the [[derivative]] of the [[nn activation function]] $g^{(k)}$

$$
\begin{split}
\delta^{(k)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}}_{\mathbb{R}^{1\times n_k}} 
\underbrace{\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}}_{\mathbb{R}^{n_k\times n_k}} \in \mathbb{R}^{1\times n_k}  \\

&= 
\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(k)}}
Dg^{(k)}\left( \mathrm{z}^{(k)}\right) \\

\frac{\partial \mathrm{a}^{(k)}}{\partial \mathrm{z}^{(k)}}
&=\frac{\partial g^{(k)}\left( \mathrm{z}^{(k)}\right)}{\partial \mathrm{z}^{(k)}} =Dg^{(k)}\left( \mathrm{z}^{(k)}\right)\\
\end{split}
$$

- in the last layer $L$ we have the following [[derivative]]

$$
\begin{split}
\delta^{(L)}
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{a}^{(L)}}}_{\mathbb{R}^{1\times n_L}} 
\underbrace{Dg^{(L)}\left( \mathrm{z}^{(L)}\right)}_{\mathbb{R}^{n_L\times n_L}} \in \mathbb{R}^{1\times n_L}  \\
\end{split}
$$

- in all following layers $k$ we can express the [[derivative]] depending on the [[derivative]] of the previous layer $\delta^{(k)\top}$

$$
\begin{split}
\delta^{(k)}
&= \frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{a}^{(k)}}Dg\left( \mathrm{z}^{(k)}\right) \\
&= 
\underbrace{\frac{\partial \mathcal{l}\left(y, \mathrm{a}^{(L)}\right)}{\partial \mathrm{z}^{(k+1)}}}_{\mathbb{R}^{1\times n_{k+1}}}
\underbrace{
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
}_{\mathbb{R}^{n_{k+1}\times n_{k}}}
\underbrace{
Dg\left( \mathrm{z}^{(k)}\right)
}_{\mathbb{R}^{n_{k}\times n_{k}}}\\
&= \delta^{(k+1)\top}W^{(k+1)}Dg\left( \mathrm{z}^{(k)}\right) \\
\frac{\partial \mathrm{z}^{(k+1)}}{\partial \mathrm{a}^{(k)}}
&= \frac{\partial W^{(k+1)}\mathrm{a}^{(k)} + b^{(k+1)}}{\partial \mathrm{a}^{(k)}} \\
\end{split}
$$

## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}\in \mathbb{R}^{n_i \times n_{i-1}}$ and a bias $b^{(i)}\in \mathbb{R}^{n_i}$ and a (potentially non-linear) [[nn activation function]] $g^{(i)}: \mathbb{R}^{n_i} \to  \mathbb{R}^{n_i}$
- the output of each layer is called the activation vector $\mathrm{a}^{(i)}$ with the first being the input of the model $\mathrm{a}^{(0)}=x \in \mathbb{R}^{n_0}$ 

$$
\begin{split}
\mathrm{z}^{(i)} &= W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)} \\
\mathrm{a}^{(i)} 
&= g^{(i)}\left(\mathrm{z}^{(i)}\right)  \\
&= g^{(i)}\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)  \\
\end{split}
$$

- the complete model can be represented by a function $f_\theta$

$$
\begin{split}
f_\theta &= \mathrm{a}^{(L)} \\
\theta &= \left(W^{(1)}, b^{(1)}, ..., W^{(L)}, b^{(L)}\right) \\
\end{split}
$$

- note: if none of the [[nn activation function]] is non-linear, the model would collapse in a [[nn linear layer]] even with multiple layers


_____________


## chain rule
### single variable case
- [[derivative]] of the [[composition]] of two [[function|functions]]

$$
\frac{df\left(g(x)\right)}{dx} = \frac{df\left(g(x)\right)}{dg(x)} \cdot \frac{dg(x)}{dx} 
$$

#### intuition chain rule
- the rate of change of $f$ to $x$ is equal to the rate of change of $f$ to $g$ times the rate of change of $g$ to $x$
- if a car is $5$ times faster than a bike and a bike is 4 times faster than a wakling person than the car is $20 = 4 	\times 5$ faster than a waling person

$$
\frac{\Delta \text{car distance}}{\Delta \text{time}} = \frac{\Delta \text{car distance}}{\Delta \text{bike distance}} \times \frac{\Delta \text{bike distance}}{\Delta \text{time}}
$$


### multi variable case
let 
- $x \in \mathbb{R}^{n}$ 
- $g: \mathbb{R}^n \to \mathbb{R}^m$ 
- $f: \mathbb{R}^m \to \mathbb{R}$ 

$$
\begin{split}
\frac{\partial f\left(g(x)\right)}{\partial x_i} 
&= \lim_{h \to 0} \frac{ f\left(g(x + e_i h)\right) - f\left(g(x )\right) }{h}  \\
&= \sum_{j=1}^m   \frac{\partial f\left(g(x)\right)}{\partial g(x)_j} \frac{\partial g(x)_j}{\partial x_i} \\
&= Df\left(g(x)\right) Dg(x)_{(: i)} \in \mathbb{R} \\
\frac{\partial f\left(g(x)\right)}{\partial x} 
&= D{g \circ f}(x) \\
&= Df\left(g(x)\right) Dg(x) \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

- with the [[jacobian]] $Df\left(g(x)\right) \in \mathbb{R}^{1\times m}$ and $Dg(x) \in \mathbb{R}^{m \times n}$ 
#### dimensions
- let $F = f\left(g(x)\right)$
- the rule for the decomposing the [[derivative]] with the [[chain rule]] is outer times inner and the dimensions are as follows

$$
\begin{split}
DF(x) = 
\underbrace{\left.Df(u)\right|_{u=g(x)}}_{
\mathbb{R}^{\mathrm{dim}(f) \times \mathrm{dim}(g)}} 
\quad
\underbrace{Dg(x)}_{\mathbb{R}^{\mathrm{dim}(g) \times \mathrm{dim}(x)}} 
\in \mathbb{R}^{\mathrm{dim}(F) \times \mathrm{dim}(x)} \\
\end{split}
$$

#### proof

- $g$ and $f$ are [[differentiable]] so that the following exists

$$
\begin{split}
g(x+h) 
=& g(x) + Dg(x)h + \varphi_g(h), \quad &\frac{||\varphi_g(h)||}{||h||} \to_{h \to 0} 0 \\
f\left(u+v(h)\right) =& f(u) + Df(u)v(h) + \varphi_f\left(v(h)\right) , \qquad &\frac{||\varphi_f(v)||}{||v||} \to_{v \to 0} 0  \\
\end{split}
$$
- now define

$$
\begin{split}
u :=& g(x)  \\
v(h) :=& Dg(x)h + \varphi_g(h)  \\
g(x+h) =& u + v(h)
\end{split}
$$
- now insert

$$
\begin{split}
f(g(x+h))
&= f(u + v(h)) \\
&= f(u) + Df(u)[v(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u)[Dg(x)[h] + \varphi_g(h)] + \varphi_f(v(h)) \\
&= f(u) + Df(u) Dg(x)[h] + \underbrace{ Df(u)\varphi_g(h) + \varphi_f(v(h))}_{r(h)} \\
r(h) &= Df(u)\varphi_g(h) + \varphi_f(v(h)), \quad  \frac{||r(h)||}{||h||} \to_{h \to 0} 0
\end{split}
$$

- it follows that

$$
\begin{split}
D f\left(g(x)\right) 
&= \underbrace{\left. Df\left(u\right) \right |_{u=g(x)}}_{\in \mathbb{R}^{1\times m}}\underbrace{ Dg(x)}_{\in \mathbb{R}^{m\times n}} \in \mathbb{R}^{1 \times n} \\
\end{split}
$$

#### intuition
- if the ith dimension of $x$ changes by a delta, this can lead to a change of all dimensions of $g(x)$ and each change of a $g(x)_j$ can lead to a change of $f\left(g(x)\right)$ 
- by summing up the effects we have the [[partial derivative]]

$$
\lim_{h \to 0} \sum_{j=1}^m  \frac{ g(x+e_ih)_j -  g(x)_j}{h}  \cdot \frac{ f\left(g(x) + e_j h\right)-f\left(g(x)\right)}{h}   $$


Tags: mathematics WS2526 ml
<!--ID: 1764251723186-->
END
