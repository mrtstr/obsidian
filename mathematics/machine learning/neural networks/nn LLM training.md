## LLM training
####  batch size
- LLMs require a very large batch size (millions of tokens per step)
	- small batch site → noisy gradient, unstable training
	- Large batch → smoother gradient, faster convergence
### cost
- measured in **FLOP (floating-point operation)**
- number of samples that are processed per step $T_\mathrm{batch}$ depends on the batch site $B$ and the number of tokens per sequence $S$

$$T_\mathrm{batch}=S \cdot B$$
- the number of FLOPS per step depends on the number of token per batch and the number of parameters of the model $N_\mathrm{param}$
- the factors $6$ comes from $2$ operations per parameter for the forward pass and $4$ operations for the backward pass

$$
\mathrm{FLOPS \ per \ setp} \approx 6 \cdot T_\mathrm{batch} \cdot N_\mathrm{param}
$$

- the number of FLOPS scales linear with 
	- the number of layers $L$
	- the batch size $B$
	- the number of heads $H$
	- the sequence length $S$ in the [[nn multilayer perceptron]]
- but quadratic with the model dimension $d_\mathrm{model}$ and in the [[nn self attention layer]] also with the sequence length $S$


# ------------

![[nn decoder transformers#decoder transformers]]


![[nn self attention layer#multihead self attention layer]]

START
Basic
- which batch size to use for LLMs and why?
Back: 

## LLM training
####  batch size
- LLMs require a very large batch size (millions of tokens per step)
	- small batch site → noisy gradient, unstable training
	- Large batch → smoother gradient, faster convergence


Tags: ml WS2526
<!--ID: 1763995026489-->
END

START
Basic
cost of [[nn LLM training]] in FLOPs
- how to estimate the number of FLOPs per step during the training?
- how do the number of FLOPs per step scale with $L$, $B$, $d_\mathrm{model}$, $H$, $S$
Back: 

## LLM training

### cost in FLOPs
- measured in **FLOP (floating-point operation)**
- number of samples that are processed per step $T_\mathrm{batch}$ depends on the batch site $B$ and the number of tokens per sequence $S$

$$T_\mathrm{batch}=S \cdot B$$

- the number of FLOPS per step depends on the number of token per batch and the number of parameters of the model $N_\mathrm{param}$
- the factors $6$ comes from $2$ operations per parameter for the forward pass and $4$ operations for the backward pass

$$
\mathrm{FLOPS \ per \ setp} \approx 6 \cdot T_\mathrm{batch} \cdot N_\mathrm{param}
$$

- the number of FLOPS scales linear with 
	- the number of layers $L$
	- the batch size $B$
	- the number of heads $H$
	- the sequence length $S$ in the [[nn multilayer perceptron]]
- but quadratic with the model dimension $d_\mathrm{model}$ and in the [[nn self attention layer]] also with the sequence length $S$

####  batch size
- LLMs require a very large batch size (millions of tokens per step)
	- small batch site → noisy gradient, unstable training
	- Large batch → smoother gradient, faster convergence


______

## decoder transformers
### concept
- [[neural network]] for generation of content (often text) using [[nn transformer block|transformer blocks]] (e.g. GPT)
- general concept: train the model a [[maximum likelihood estimator]] that predicts the $t+1$ token given the tokens $1, ..., t$ as input 

$$
\begin{split}
\theta = \arg\max \sum_{i=1}^S \log p\left(x_{(t, *)}\right| x_{(<t, *)}, \theta)
\end{split}
$$

### architecture
0) [[nn tokenization]] → token vector $x \in \mathbb{N}^{B \times S}$
1) [[nn embedding layer]] → dense embedding vector $X \in \mathbb{R}^{B \times S \times D}$
2) multiple [[nn transformer block]] → internal dense representation $X_m \in \mathbb{R}^{B \times S \times D}$
3) final [[nn norm layer]] + [[nn linear layer]] → [[logit function|logits]] $Z = \mathrm{LL}\left(\mathrm{LN}\left(X_m\right)\right) \in \mathbb{R}^{B \times S \times V}$
	- mapping from the internal dimension $D$ to the vocabulary size $V$ 
4) [[softmax function]] → probability distribution over the vocabulary $\hat Y = \mathrm{softmax}(Z)  \in \mathbb{R}^{B \times S \times V}$

#### weight sharing
- for the output linear transformation mapping back to $\mathbb{R}^{B \times S \times D} \to \mathbb{R}^{B \times S \times V}$, there are two options 
	- reuse the [[nn embedding layer|embedding matrix]]
	- training a separate matrix
- reusing the [[nn embedding layer|embedding matrix]] **reduces parameters**, **improves generalization** and **encourages symmetry** between encoding and decoding but reduces flexibility between input and output space
### training

- a text as training data is tokenized (see [[nn tokenization]]) to a sequence of token indices  $x \in \mathrm{R}^S$ and the lables $y \in \mathrm{R}^S$ which are a shifted version of $x$ by one position

```
x = tokens[i : i + S]         # inputs
y = tokens[i + 1 : i + S + 1] # targets (next-token)
```

- after the [[nn embedding layer|embedding layer]] we have input data $X$ and the causal mask $M$ that should prevent that information about tokens not known at the time are used
- the model output the [[logit function|logits]] $Z \in \mathbb{R}^{S \times V}$ and after applying the [[softmax function]] we would the $\hat Y \in \mathbb{R}^{S \times V}$ which is a [[distribution]] over the vocabulary

$$
\begin{split}
X& \in \mathbb{R}^{S \times D} \\
M& = 
\left[\begin{matrix}
0 & -\infty & -\infty & -\infty & .. \\
0 & 0       & -\infty & -\infty & .. \\
0 & 0       &  0      & -\infty & .. \\
.. & .. & .. & .. & .. \\
\end{matrix}\right]
\in \mathbb{R}^{S \times S} \\
\end{split}
$$

- for efficiency reasons $\hat Y$ is not calculated during the training
- $Y \in \mathbb{R}^{S \times Z}$ is the true [[distribution]] and thus the one hot encoded token indices which is also not calculated for efficiency reasons
- the [[risk]] that is minimized is the [[cross entropy]] between $Y$ and $\hat Y$ that can be simplified as following with $y \in \mathbb{R}^S$ being the indices of the tokens 

$$
\begin{split}
\mathrm{CE}(Y, Z) 
&= - \sum_{c=1}^V  Y_c \log \mathrm{softmax}(Z)_c \\
&= -  \log  \mathrm{softmax}(Z)_y  \\
\end{split}
$$



## self attention layer
### multihead self attention layer
- the Input [[nn embedding layer]] $X \in \mathbb{R}^{B \times S \times D}$ represents a sequence of token embeddings/features of the length $S$ with each feature/embedding being represented in the $\mathbb{R}^{D}$
	- **B** — **Batch size**: how many sequences processed together (ignored in the following for convenience)
	- **S** — **Sequence length**: tokens per sequence = size of the context window
	- **D** — **Model dimension**: Size of the representation of each token's embedding (first layer) / each features representation 
- $X_{(i, *)}$ is the representation at the token position $i$
	- Layer 0: token embedding
	- Higher layers: **contextualized** representation at position $i$
- $X$ is processed by  $H$ attention heads and each of them is calculating for each input feature $X_{(i, *)}$ and output feature $O_{(i, *)}^{(h)}$ that incorporates its context

#### single attention head
- each weight [[matrix]] is a [[linear map]] to the $\mathbb{R}^{d_h}$ with $d_h$ being the hidden size of the attention head with often $D=d_h \cdot h$
	- weight matrix of the query $W_Q^{(h)}\in \mathbb{R}^{D\times d_h}$
	- weight matrix of the key $W_K^{(h)}\in \mathbb{R}^{D\times d_h}$
	- weight matrix of the value $W_V^{(h)}\in \mathbb{R}^{D\times d_h}$

$$
\begin{split}
Q^{(h)} &= XW_Q^{(h)} \in \mathbb{R}^{S \times d_h}  \\
K^{(h)} &= XW_K^{(h)} \in \mathbb{R}^{S \times d_h}  \\
V^{(h)} &= XW_V^{(h)} \in \mathbb{R}^{S \times d_h} \\
\end{split}
$$

- $Q$ and $K$ are used to extract the importance of the context for each token
- for each token $i$ the query $Q_{(i, *)}$ is representing the token itself and $K_{(j, *)}$ is representing the other tokens and their similarity is the importance that token $j$ has for the next feature of token $i$
	- Query $q_i$: what is feature $i$ looking for
	- Key $k_j$: what feature $j$ has to offer

$$
\begin{split}
x_i &= X_{(i, *)}  \in \mathbb{R}^{1\times D}  \\
q_i &= Q_{(i, *)}= x_iW_Q \in \mathbb{R}^{1 \times d_h} \\
k_j &= K_{(j, *)}= x_jW_K \in \mathbb{R}^{1 \times d_h} \\
\end{split}
$$
#### calculating similarity scores


- the [[inner product]] between $q_i$ and $k_j$ measures the similarity of the vectors and represents the importance that feature $j$ has for feature $i$

$$
\begin{split}
\mathrm{score}(i,j) 
&= \frac{\left(Q K^\top\right)_{\left(i,j\right)}}{\sqrt{d_h}}   \\
&= \frac{Q_{(i, *)} K_{(j, *)}^\top}{\sqrt{d_h}} \\
&= \frac{ X_{(i, *)}W_Q \left(X_{(j, *)}W_K\right)^\top }{\sqrt{d_h}} \\
&= \frac{ X_{(i, *)}M X_{(j, *)}^\top }{\sqrt{d_h}} \\
S&= (\mathrm{score}(i,j) )_{(i\in [S],j\in [S])} \in \mathbb{R}^{S \times S}
\end{split}
$$

#### masking normalizing the similarity scores

- $A$ is a context-and-importance map between tokens with $A_{(i, j)}$ being the importance weight of token $j$ for constructing the next layer feature of $i$ 
- a $\mathrm{mask} \in \{-\infty, 0\}^{S \times S}$ is added to allow and disallows context
- the [[softmax function]] normalizes the score over the context such $\sum_{j=1}^S A_{(i, j)} = 1$

$$
\begin{split}
A^{(h)} 
&=\mathrm{SOFTMAX}\left(\frac{Q^{(h)}K^{(h)\top}}{\sqrt{d_h}} + \mathrm{mask}\right) \\
&=\mathrm{SOFTMAX}_j\left(S_{(i, j)}+ \mathrm{mask}\right) \\
&= \frac{\exp{(\mathrm{score}(i,j)+ \mathrm{mask}(i,j))}}{\sum_{k=1}^S \exp{(\mathrm{score}(i,k)+ \mathrm{mask}(i,k))}}
\end{split}
$$



- the output of the [[softmax function]] can be interpreted as the [[conditional probability]] 
$$
\begin{split}
P(j | i) 
&= \frac{\exp{(\mathrm{score}(i,j))}}{\sum_{k=1}^S \exp{(\mathrm{score}(i,k))}}
\end{split}
$$

#### creating the contextualized feature
- $v_i$ is a transformed representation of the input token $i$

$$
\begin{split}
v_i &= V_{(i, *)}= X_{(i, *)}W_V \in \mathbb{R}^{1 \times d_h} \\
\end{split}
$$

- the feature of the $ith$ token $O^{(h)}_{(i, *)}$ is constructed as a sum of transformed versions of all embedding/input features $v_1,..., v_S$ weighted by the importance they have for token $i$

$$
\begin{split}
O^{(h)} 
&= A^{(h)}V^{(h)} \in \mathbb{R}^{S \times d_h} \\
O^{(h)}_{(i, *)}&= \sum_{k=1}^S A_{(i, k)}^{(h)}V_{(k, *)}^{(h)}  \in \mathbb{R}^{1 \times d_h} \\
\end{split}
$$

#### combining multiple heads
- the weight matrix of the features of attention heads $W_O \in \mathbb{R}^{H \cdot d_h \times D}$ with often $D=H \cdot d_h$

$$
\mathrm{MHA}(X, \mathrm{mask}) = \mathrm{Concat}[O^{(1)}, ..., O^{(H)}] W_O \in \mathbb{R}^{S \times D} 
$$


Tags: ml WS2526
<!--ID: 1763995026493-->
END