### multihead self attention layer

### single attention head
#### input
- Input $X \in \mathbb{R}^{B \times S \times D}$

- **B** — **Batch size** (how many sequences processed together).
- **S** — **Sequence length** (tokens per sequence)
- **D** — **Model dimension** 


#### scaled dot-product attention
- given a sequence of tokens of the length $S$ the goal is to calculate for each token a feature that incorporates its context

- each weight [[matrix]] is a [[linear map]] to the $\mathbb{R}^{d_h}$
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

$$
\begin{split}
x_i &= X_{(i, *)}  \in \mathbb{R}^{D\times 1}  \\
q_i &= Q_{(i, *)}= x_iW_Q \in \mathbb{R}^{1 \times d_h} \\
k_j &= K_{(j, *)}= x_jW_K \in \mathbb{R}^{1 \times d_h} \\
\end{split}
$$


- the [[inner product]] between $q_i$ and $k_j$ can be interpreted as their similarity

- the score $\mathrm{score}(i,j)$
$$
\begin{split}
\mathrm{score}(i,j) 
&= \frac{\left(Q K^\top\right)_{\left(i,j\right)}}{\sqrt{d_h}} \\
&= \frac{Q_{(i, *)} K_{(j, *)}^\top}{\sqrt{d_h}} \\
&= \frac{ X_{(i, *)}W_Q \left(X_{(j, *)}W_K\right)^\top }{\sqrt{d_h}} \\
&= \frac{ X_{(i, *)}M X_{(j, *)}^\top }{\sqrt{d_h}} \\
&= \frac{ x_i^\top M x_j }{\sqrt{d_h}} \\
S&= (\mathrm{score}(i,j) )_{(i\in [S],j\in [S])} \in \mathbb{R}^{S \times S}
\end{split}
$$

- $A$ is a context-and-importance map between tokens with $A_{(i, j)}$ being the importance weight of token $j$ for constructing the next layer feature of $i$ 
- the [[softmax function]] normalizes the score over the context such $\sum_j A_{(i, j)} = 1$

$$
\begin{split}
A^{(h)} 
&=\mathrm{SOFTMAX}\left(\frac{Q^{(h)}K^{(h)\top}}{\sqrt{d_h}}\right) \\
&=\mathrm{SOFTMAX}_j\left(S_{(i, j)}\right) \\
&= \frac{\exp{(\mathrm{score}(i,j))}}{\sum_{k=1}^S \exp{(\mathrm{score}(i,k))}}
\end{split}
$$


- the output of the [[softmax function]] can be interpreted as the [[conditional probability]] 
$$
\begin{split}
P(i | j) 
&= \frac{\exp{(\mathrm{score}(i,j))}}{\sum_{k=1}^S \exp{(\mathrm{score}(i,k))}}
\end{split}
$$


- $v_i$ is transformed representation of the input token $i$
$$
\begin{split}
v_i &= V_{(i, *)}= X_{(i, *)}W_V \in \mathbb{R}^{1 \times d_h} \\
\end{split}
$$

- in the last step the feature of the $ith$ token $O^{(h)}_{(i, *)}$ is constructed as a sum of a transformed version of all taken embedding $v_1,..., v_S$ weighted by the impotence they have for token $i$

$$
\begin{split}
O^{(h)} 
&= A^{(h)}V^{(h)} \in \mathbb{R}^{S \times d_h} \\
O^{(h)}_{(i, *)}&= \sum_{k=1}^S A_{(i, k)}V_{(k, *)}  \in \mathbb{R}^{1 \times d_h} \\
\end{split}
$$


### multiple heads
- **H** — **Number of attention heads**.
$$
\mathrm{MHA}(X) = \mathrm{Concat}[O^{(1)}, ..., O^{(H)}] W_O
$$

(often $D=H \cdot d_h \Leftrightarrow d_h=\frac{D}{H}$)
# -------------------

![[softmax function#softmax function]]

![[projection#projection into the column space]]