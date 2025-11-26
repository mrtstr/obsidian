## backpropagation
- let $f_\theta$ be [[neural network]] with $L$ layers and element wise [[nn activation function]] $g^{(i)}$ and let $l$ be a [[loss function]]
- the goal is to solve the following [[unconstraint optimization problem]] with [[gradient descent]]

$$
\hat\theta = \arg\min_{\theta} \frac{1}{m} \sum_{i=1}^m l\left(y^{(i)}, f_\theta \left(x^{(i)}\right)\right)
$$
- in the following we will just work with a single $(x, y)$ tuple but since the [[derivative]] is linear this can easily be extended to a sum

### element wise solution
- let $\delta^{(k)}_j$ be the [[partial derivative]] of the loss function with respect to the $j \in \left\{1, ..., n^{(k)}\right\}$ element of the output of the $k \in \left\{1, ..., L\right\}$ layer

$$
\begin{split}
\delta^{(k)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(\sum_j\sum_i W_{ji} a^{k-1}_i + b^k\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)} \\
\end{split}
$$

- based on $\delta^{(k)}_j$ we can calculate the [[partial derivative]] of the loss after an arbitrary parameter of the weight matrix of an arbitrary layer $W_{ji}^{(k)}$ and bias term $b_{j}^{(k)}$ by applying the [[chain rule]] (depending on the activation of the previous layer $a^{(k-1)}$)

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial W_{ji}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(W_{ji}^{(k)}\right)\right)\right)}{\partial W_{ji}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
\end{split}
$$

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial b_{j}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(b_{j}^{(k)}\right)\right)\right)}{\partial b_{j}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i b_{j}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \delta^{(k)}_j \\
\end{split}
$$

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
\delta^{(L-1)}_j
&:= \frac{\partial \mathcal{l}}{\partial \mathrm{z}^{(L-1)}_j} \\
&= \left\langle 
      \frac{\partial \mathcal{l}}{\partial \mathrm{z}^{(L)}} ,
      \frac{\partial \mathrm{z}^{(L)}}{\partial \mathrm{z}^{(L-1)}_j}
   \right\rangle \\
&= \left\langle 
      \boldsymbol{\delta}^{(L)},
      \frac{\partial \mathrm{z}^{(L)}}{\partial \mathrm{z}^{(L-1)}_j}
   \right\rangle
\end{split}
$$

# ------------

![[neural network#neural network]]


# anki
START
Basic
[[nn backpropagation]]
- let $\delta^{(k)}_j$ be the [[partial derivative]] of the loss function with respect to the $j \in \left\{1, ..., n^{(k)}\right\}$ element of the output of the $k \in \left\{1, ..., L\right\}$ layer
- calculate $\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial W_{ji}^{(k)}}$ and $\frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial b_{j}^{(k)}}$

$$
\begin{split}
\delta^{(k)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
\end{split}
$$

Back: 
## backpropagation
- let $f_\theta$ be [[neural network]] with $L$ layers and element wise [[nn activation function]] $g^{(i)}$ and let $l$ be a [[loss function]]
- the goal is to solve the following [[unconstraint optimization problem]] with [[gradient descent]]

$$
\hat\theta = \arg\min_{\theta} \frac{1}{m} \sum_{i=1}^m l\left(y^{(i)}, f_\theta \left(x^{(i)}\right)\right)
$$
- in the following we will just work with a single $(x, y)$ tuple but since the [[derivative]] is linear this can easily be extended to a sum

### element wise solution
- let $\delta^{(k)}_j$ be the [[partial derivative]] of the loss function with respect to the $j \in \left\{1, ..., n^{(k)}\right\}$ element of the output of the $k \in \left\{1, ..., L\right\}$ layer

$$
\begin{split}
\delta^{(k)}_j 
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(W^{(i)} \mathrm{a}^{(i-1)} + b^{(i)}\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial {\left(\sum_j\sum_i W_{ji} a^{k-1}_i + b^k\right)}_j} \\
&= \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)} \\
\end{split}
$$

- based on $\delta^{(k)}_j$ we can calculate the [[partial derivative]] of the loss after an arbitrary parameter of the weight matrix of an arbitrary layer $W_{ji}^{(k)}$ and bias term $b_{j}^{(k)}$ by applying the [[chain rule]] (depending on the activation of the previous layer $a^{(k-1)}$)

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial W_{ji}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(W_{ji}^{(k)}\right)\right)\right)}{\partial W_{ji}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i W_{ji}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial W_{ji}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= a^{(k-1)}_i \cdot \delta^{(k)}_j \\
\end{split}
$$

$$
\begin{split}
 \frac{\partial \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial b_{j}^{(k)}} 
  &= \frac{\partial \mathcal{l}\left(y, f_\theta \left(\mathrm{z}^{(k)}_j\left(b_{j}^{(k)}\right)\right)\right)}{\partial b_{j}^{(k)}} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \frac{\partial  \mathcal{l}\left(y, f_\theta \left(x\right)\right)}{\partial \mathrm{z}^{(k)}_j} \\
 &= \frac{ \partial \mathrm{z}^{(k)}_j}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \frac{\partial \left(\sum_i b_{j}^{(k)} a^{(k-1)}_i + b^{(k)}_j\right)}{\partial b_{j}^{(k)}}  \cdot \delta^{(k)}_j \\
 &= \delta^{(k)}_j \\
\end{split}
$$

_____________


## neural network
- let $L$ be the number of layers of the [[neural network]] 
- each layer $i$ transforms its input with [[linear map]] defined by a weight matrix $W^{(i)}$ and a bias $b^{(i)}$ and a (potentially non-linear) [[nn activation function]] $g^{(i)}$
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


Tags: mathematics WS2526 ml
<!--ID: 1764141526847-->
END
