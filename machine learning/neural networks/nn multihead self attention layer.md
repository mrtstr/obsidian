### multihead self attention layer

### single attention head
#### input
- Input $X \in \mathbb{R}^{B \times S \times D}$

- **B** — **Batch size** (how many sequences processed together).
- **S** — **Sequence length** (tokens per sequence)
- **D** — **Model dimension** 


#### scaled dot-product attention
- each weight [[matrix]] is a [[linear map]] to the $\mathbb{R}^{d_h}$
- **d_h** — **Per-head hidden size** (the [[dimensions]] of each head’s Q/K/V).

- $W_Q^{(h)}\in \mathbb{R}^{D\times d_h}$
- $W_X^{(h)}\in \mathbb{R}^{D\times d_h}$
- $W_V^{(h)}\in \mathbb{R}^{D\times d_h}$


$$
\begin{split}
Q^{(h)} = XW_Q \\
K^{(h)} = KW_K \\
V^{(h)} = XW_V \\
\end{split}
$$

$$
\begin{split}
A^{(h)} =\mathrm{SOFTMAX}\left(\frac{Q^{(h)}K^{(h)\top}}{\sqrt{d_h}}+\mathrm{mask}\right)
\end{split}
$$

$$
\begin{split}
O^{(h)} = A^{(h)}V^{(h)}
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