## encoder decoder transformers
- A model with an **encoder** stack and a **decoder** stack.
- both have the same [[nn transformer block]] based architecture
- They share the same _ingredients_ ([[nn transformer block]] = [[nn multihead self attention layer]], MLP, [[nn norm layer]], [[nn residual block]]), **but** the **decoder block** has (a) **causal** self-attention and (b) an extra **cross-attention** sublayer to read the encoder’s outputs. The **encoder** uses **bidirectional** self-attention (no causal mask).
##### encoder
- Transformer that maps an input sequence to **contextual, bidirectional** embeddings
- Used for understanding tasks (classification, retrieval) or as the **memory** that a [[nn decoder transformers]] **cross-attends** to

##### decoder
- Uses **causal** self-attention over previously generated tokens and (optionally) **cross-attention** to encoder outputs.
- Generates **one token at a time** (autoregressive); during training uses teacher forcing; at inference caches K/V for speed.
##### examples

- **GPT/Claude (text-only):** **decoder-only**; all context is fed as a prefix and the model predicts next tokens autoregressively.
- **Classification:** Often **encoder-only** (e.g., BERT → [CLS] head), **but not required**—decoder-only models can classify via a small head or prompting.
- **Multimodal:** Non-text inputs (images, audio) are passed through a **modality encoder** first. The language **decoder** then either **cross-attends** to those features or consumes them as **prefix tokens**. (So the picture isn’t “fed to the encoder model together with text”; rather, an **image encoder** feeds the **decoder**.)

![[Pasted image 20251110135530.png]]

# ----------

![[nn decoder transformers#decoder transformers]]

![[nn transformer block#transformer block]]
# anki

START
Basic
[[nn encoder decoder transformers]]
- difference and similarities between encoders and decoders models
- why does a [[nn decoder transformers]] need an additional encoder?
- example for encoder only, decoder only and encoder + decoder models
Back: 
## encoder decoder transformers
- A model with an **encoder** stack and a **decoder** stack.
- both have the same [[nn transformer block]] based architecture
- They share the same _ingredients_ ([[nn transformer block]] = [[nn multihead self attention layer]], MLP, [[nn norm layer]], [[nn residual block]]), **but** the **decoder block** has (a) **causal** self-attention and (b) an extra **cross-attention** sublayer to read the encoder’s outputs. The **encoder** uses **bidirectional** self-attention (no causal mask).
##### encoder
- Transformer that maps an input sequence to **contextual, bidirectional** embeddings
- Used for understanding tasks (classification, retrieval) or as the **memory** that a [[nn decoder transformers]] **cross-attends** to

##### decoder
- Uses **causal** self-attention over previously generated tokens and (optionally) **cross-attention** to encoder outputs.
- Generates **one token at a time** (autoregressive); during training uses teacher forcing; at inference caches K/V for speed.
##### examples

- **GPT/Claude (text-only):** **decoder-only**; all context is fed as a prefix and the model predicts next tokens autoregressively.
- **Classification:** Often **encoder-only** (e.g., BERT → [CLS] head), **but not required**—decoder-only models can classify via a small head or prompting.
- **Multimodal:** Non-text inputs (images, audio) are passed through a **modality encoder** first. The language **decoder** then either **cross-attends** to those features or consumes them as **prefix tokens**. (So the picture isn’t “fed to the encoder model together with text”; rather, an **image encoder** feeds the **decoder**.)

![[Pasted image 20251110135535.png]]

_________
### transformer block
### input

- the input $X \in \mathbb{R}^{B \times S \times D}$ is coming out of the [[nn embedding layer]] if its the first [[nn transformer block]] or the previous [[nn transformer block]]
- it represent a sequence of token embeddings/features of the length $S$ with each feature/embedding being represented as a dense vector in the $\mathbb{R}^{D}$
	→ $X_{(i, *)}$ is the representation at the token position $i$
		- Layer 0: token embedding
		- Higher layers: **contextualized** representation at position $i$ 
- **B** — **Batch size**: how many sequences processed together (ignored in the following for convenience)
- **S** — **Sequence length**: tokens per sequence = size of the context window
- **D** — **Model dimension**: Size of the representation of each token's embedding (first layer) / each features representation 


### architecture

→ [[nn residual block]] ([[nn norm layer]] + [[nn multihead self attention layer]])
- normalize
- build contextualized features ("communication")

$$
\begin{split}
X^{(1)} = X + \mathrm{Dropout}\left(\mathrm{MHA}\left(\mathrm{LN}(X)\right), \mathrm{mask}\right)
\end{split}
$$


→ [[nn residual block]] ([[nn norm layer]] +[[nn feed forward network]])
- normalize
- after communication, each token **computes** richer features from what it just gathered—like feature mixing and pattern extraction

$$
\begin{split}
X^{(2)} = X^{(1)}  +  \mathrm{Dropout}\left(\mathrm{MLP}\left(\mathrm{LN}\left(X^{(1)}\right)\right)\right)
\end{split}
$$


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

### inference
- during inference, we tokenize the user input and pass it through the model to calculate the predicted distribution of the next token $Y$ and sample the next token from it
- when sampling a [[nn temperature]] can be used to adapt the variance, or we can always use the token with the highest likelihood
- If the user input is a sequence of length $S$ the output would also be of length $S$, but we would just need the last element and ignore the rest
- then we pass the user input plus the first generated token in the model to generate the second token and repeat that process until the full response is generated
- not that we don't have to recalculate the output for the whole user input because we can cache the logits for efficiency
Tags: ml WS2526
<!--ID: 1762781311517-->
END

