### universal approximation theorem
- fundamental theorem that justifies why [[neural network]] are so powerful
- for every continuous function $f$ there exists a [[nn multilayer perceptron]] with a single layer and a non-linear [[nn activation function]] that can approximate $f$ with an arbitrary precision with enough parameters


![[nn multilayer perceptron#multilayer perceptron]]


# anki

START
Basic
[[nn universal approximation theorem]]
Back: 
### universal approximation theorem
- fundamental theorem that justifies why [[neural network]] are so powerful
- for every continuous function $f$ there exists a [[nn multilayer perceptron]] with a single layer and a non-linear [[nn activation function]] that can approximate $f$ with an arbitrary precision with enough parameters

## multilayer perceptron
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


Tags: mathematics ml WS2526
<!--ID: 1763312483792-->
END