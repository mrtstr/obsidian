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

### multi query attention layer
- similar to [[nn self attention layer#multihead self attention layer]] but there is only a single key $K$ and value $V$ that is used for all attention heads
- intuition: multiple query's $Q^{(h)}$ that are focusing on specific patterns but the information what a token is providing is the same for all heads

#### pros
1) huge memory saving -> much longer context windows possible
2) faster inference because of less memory movement -> latency reduction
3) less computationally expense and easier implementation because of less matrix multiplications
#### cons
1) can reduce quality of smaller models
2) loss of head diversity

### group query attention layer
- still one query $Q^{(h)}$ per attention head but a single key $K^{(g)}$ and value $V^{(g)}$ per group with a number of groups that is significant lower than the number of heads 

- faster than [[nn self attention layer#multihead self attention layer]] but better quality than [[nn self attention layer#multi query attention layer]]
	→ almost the same performance as $MHA$ but much faster
	-> the best performance per cost 

![[Pasted image 20251117145916.png]]
# -------------------

![[nn embedding layer#embedding layer]]

![[nn tokenization#tokenization]]

![[softmax function#softmax function]]

![[projection#projection into the column space]]


# anki


START
Basic
[[nn self attention layer#multihead self attention layer]]
- concept
- interpretation
- important weight matrices with dimensions and purpose (4)
- interpretation and dimensions of the input
Back: 
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


________________

## embedding layer
- learnable representation of a sequence of tokens (see [[nn tokenization]]) with each token represented as a dense vector of size $D$ that contains information about its position and the token itself
- given a sequence of input token $x \in \mathbb{N}^S$ of length $S$ with a vocabulary size $V$
- $x$ is encoded as a one hot vector $I_E \in \{0,1\}^{S \times V}$
- the positions are encoded with the unity matrix $I_P \in \{0,1\}^{S \times L}$ that has $1$ on the diagonal and zeros everywhere else with $L$ being the maximal sequence length
- the parameters of the embedding [[matrix]] $E\in \mathbb{R}^{V \times D}$ trained during the model training
- the embeddings $X$ are then calculated as follows containing the token embeddings and positional encoding embeddings $PE$

$$
X = I_EE + PE \in \mathbb{R}^{S \times D}
$$

- an additional dimension for the batch size $B$ is added such that $X \in \mathbb{R}^{B \times S \times D}$

### positional encoding
- positional encoding contain the information on which position in the sequence a certain token is
- there are different methods for calculating the positional encoding, one of them is the [[nn sinusoidal positional encoding]]
- the positional encoding changes the direction of the embedding vectors but doesn't change the semantic meaning because the magnitude is much smaller

#### sinusoidal positional encoding
- encodes positional information $PE \in \mathbb{R}^{S \times d}$ in a dense vector
- $p \in \{1, ..., S\}$ is the index in the input while $t \in \{1, ..., d\}$ is the position of the dense vector
- the position in the output vector $j$ defines a frequency $\frac{1}{10000}^{\frac{j}{d}}$ and then each position rotates in that frequency

$$
PE_{t, j} = \begin{cases}
\sin\left(p \cdot\frac{1}{10000}^{\frac{j}{d}}\right), &if \ j \ is \ even \\
\cos\left(p \cdot\frac{1}{10000}^{\frac{j-1}{d}}\right), &if \ j \ is \ odd \\
\end{cases}
$$

- $PE$ is added to the token embeddings in the [[nn embedding layer]]


## tokenization
- translating text to numeric data by converting text into discrete units (= **tokens**)
- the vocabulary is a [[set]] of all possible tokens that are mapped to integer IDs with the [[cardinality]] $V$
- note that the tokenizer is trained independently of its language model (e.g. [[nn decoder transformers]]) but the model can only be used with its own tokenizer

### number of tokens vs size of tokens
- small tokens (for example each letter) leads
	- small vocabulary but long sequences per text
	- no unknown words but makes it harder to lean meaning
- large tokens (for example for each word)
	- inflexible when dealing with new words or typos
	- very large vocabulary but shot sequences per text length
	- makes it easier to lean meaning
- solution → sub-word level tokens generated by for example **Byte-Pair Encoding (BPE)**

- helpful rule of thumb is that one token generally corresponds to ~4 characters of text for common English text
### byte-pair encoding (BPE)
- start with encoding each character as a sequence between 1 and 5 bytes
	- for example, each latter is one byte encoded but special characters are encoded with 5 bytes
- take the complete text and combine the most common occurring byte sequence of length 2 to one token and repeat this until the intended vocabulary size/token size is reached
### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z) 
&= \frac{\exp{(Z_{(i,j)})}}{\sum_{k} \exp{(Z_{(i,k)})}}
\end{split}
$$

- used as output function in [[classification]] problems, for example with [[neural network]] and [[multinomial logistic regresssion]]

Tags: ml WS2526
<!--ID: 1761026390269-->
END


START
Basic
[[nn self attention layer]]
- innovations that make multihead self attention layer more efficient (2)
- pros and cons
- what is currently used?

Back: 

### multi query attention layer
- similar to [[nn self attention layer#multihead self attention layer]] but there is only a single key $K$ and value $V$ that is used for all attention heads
- intuition: multiple query's $Q^{(h)}$ that are focusing on specific patterns but the information what a token is providing is the same for all heads

#### pros
1) huge memory saving -> much longer context windows possible
2) faster inference because of less memory movement -> latency reduction
3) less computationally expense and easier implementation because of less matrix multiplications
#### cons
1) can reduce quality of smaller models
2) loss of head diversity

### group query attention layer
- still one query $Q^{(h)}$ per attention head but a single key $K^{(g)}$ and value $V^{(g)}$ per group with a number of groups that is significant lower than the number of heads 

- faster than [[nn self attention layer#multihead self attention layer]] but better quality than [[nn self attention layer#multi query attention layer]]
	→ almost the same performance as $MHA$ but much faster
	→ the best performance per cost 

![[Pasted image 20251117145923.png]]
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


________________

## embedding layer
- learnable representation of a sequence of tokens (see [[nn tokenization]]) with each token represented as a dense vector of size $D$ that contains information about its position and the token itself
- given a sequence of input token $x \in \mathbb{N}^S$ of length $S$ with a vocabulary size $V$
- $x$ is encoded as a one hot vector $I_E \in \{0,1\}^{S \times V}$
- the positions are encoded with the unity matrix $I_P \in \{0,1\}^{S \times L}$ that has $1$ on the diagonal and zeros everywhere else with $L$ being the maximal sequence length
- the parameters of the embedding [[matrix]] $E\in \mathbb{R}^{V \times D}$ trained during the model training
- the embeddings $X$ are then calculated as follows containing the token embeddings and positional encoding embeddings $PE$

$$
X = I_EE + PE \in \mathbb{R}^{S \times D}
$$

- an additional dimension for the batch size $B$ is added such that $X \in \mathbb{R}^{B \times S \times D}$

### positional encoding
- positional encoding contain the information on which position in the sequence a certain token is
- there are different methods for calculating the positional encoding, one of them is the [[nn sinusoidal positional encoding]]
- the positional encoding changes the direction of the embedding vectors but doesn't change the semantic meaning because the magnitude is much smaller

#### sinusoidal positional encoding
- encodes positional information $PE \in \mathbb{R}^{S \times d}$ in a dense vector
- $p \in \{1, ..., S\}$ is the index in the input while $t \in \{1, ..., d\}$ is the position of the dense vector
- the position in the output vector $j$ defines a frequency $\frac{1}{10000}^{\frac{j}{d}}$ and then each position rotates in that frequency

$$
PE_{t, j} = \begin{cases}
\sin\left(p \cdot\frac{1}{10000}^{\frac{j}{d}}\right), &if \ j \ is \ even \\
\cos\left(p \cdot\frac{1}{10000}^{\frac{j-1}{d}}\right), &if \ j \ is \ odd \\
\end{cases}
$$

- $PE$ is added to the token embeddings in the [[nn embedding layer]]


## tokenization
- translating text to numeric data by converting text into discrete units (= **tokens**)
- the vocabulary is a [[set]] of all possible tokens that are mapped to integer IDs with the [[cardinality]] $V$
- note that the tokenizer is trained independently of its language model (e.g. [[nn decoder transformers]]) but the model can only be used with its own tokenizer

### number of tokens vs size of tokens
- small tokens (for example each letter) leads
	- small vocabulary but long sequences per text
	- no unknown words but makes it harder to lean meaning
- large tokens (for example for each word)
	- inflexible when dealing with new words or typos
	- very large vocabulary but shot sequences per text length
	- makes it easier to lean meaning
- solution → sub-word level tokens generated by for example **Byte-Pair Encoding (BPE)**

- helpful rule of thumb is that one token generally corresponds to ~4 characters of text for common English text
### byte-pair encoding (BPE)
- start with encoding each character as a sequence between 1 and 5 bytes
	- for example, each latter is one byte encoded but special characters are encoded with 5 bytes
- take the complete text and combine the most common occurring byte sequence of length 2 to one token and repeat this until the intended vocabulary size/token size is reached
### softmax function
- the [[softmax function]] $\mathrm{SOFTMAX}: \mathrm{R}^n \to [0,1]^{n}$ turns the input into a [[probability mass function (PMF)]]
	→ normalized positive output of the same dimensions

$$
\begin{split}
\mathrm{SOFTMAX}(Z) 
&= \frac{\exp{(Z_{(i,j)})}}{\sum_{k} \exp{(Z_{(i,k)})}}
\end{split}
$$

- used as output function in [[classification]] problems, for example with [[neural network]] and [[multinomial logistic regresssion]]

Tags: ml WS2526
<!--ID: 1763390171429-->
END

