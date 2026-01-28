## embedding layer
- learnable representation of a sequence of tokens (see [[tokenization]]) with each token represented as a dense vector of size $D$ that contains information about its position and the token itself
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
- there are different methods for calculating the positional encoding, one of them is the [[sinusoidal positional encoding]]
- the positional encoding changes the direction of the embedding vectors but doesn't change the semantic meaning because the magnitude is much smaller

![[sinusoidal positional encoding#sinusoidal positional encoding]]
### geometric interpretation of embeddings
#### vector length
- the embedding representation of words correlated with their **frequency** in the training data
	- high frequency → more gradient updates → higher vector norms

#### vector direction
- the direction in the embedding space contains **semantic meaning**
- similarity between words can be measured by their difference in direction \ angle and can be measured by the [[cosine]] between them
	- example queen = king - man + woman

- the [[cosine]] shows how similar them meaning of two vectors $e_i$ and $e_j$ is
	- $+1$ → similar meaning
	- $0$ → uncorrelated
	- $-1$ → opposite meaning

$$
\mathrm{cos \ sim}(e_i, e_j) = \frac{\langle e_i, e_j \rangle}{||e_i|| \cdot ||e_j||}
$$

- based on the [[cosine]] similarity we can define the [[cosine]] distance as follows

$$
d_\mathrm{cos} = 1 - \mathrm{cos \ sim}(e_i, e_j)
$$

# ----------------

![[tokenization#tokenization]]


# anki


START
Basic
[[embedding layer]]
- concept
- how its created

Back: 
## embedding layer
- learnable representation of a sequence of tokens (see [[tokenization]]) with each token represented as a dense vector of size $D$ that contains information about its position and the token itself
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
- there are different methods for calculating the positional encoding, one of them is the [[sinusoidal positional encoding]]

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

- $PE$ is added to the token embeddings in the [[embedding layer]]


______

## tokenization
- translating text to numeric data by converting text into discrete units (= **tokens**)
- the vocabulary is a [[set]] of all possible tokens that are mapped to integer IDs with the [[cardinality]] $V$
- note that the tokenizer is trained independently of its language model (e.g. [[decoder transformers]]) but the model can only be used with its own tokenizer

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

### special tokens
- `<sos>` / `<bos>`: start of sequence
- `<eos>` : end of sequence that tells the model to stop generating
- `<pad>` : padding token for batch alignment that is ignored by the loss function and not predicted

### chat template tokens
- `<|system|>`: system prompt that sets global behavior or context
- `<|user|>`: user prompt that marks human input
- `<|assistant|>`: assistant prompt that marks model response

Tags: ml WS2526
<!--ID: 1761397169374-->
END


START
Basic
geometric interpretation of embeddings
- meaning or **vector length** and **vector direction**
- how to measure semantic similarity between words? (2)
- do the positional embeddings destroy the semantic meaning of the token embeddings?
Back: 

### geometric interpretation of embeddings

- the positional encoding changes the direction of the embedding vectors but doesn't change the semantic meaning because the magnitude is much smaller

#### vector length
- the embedding representation of words correlated with their **frequency** in the training data
	- high frequency → more gradient updates → higher vector norms

#### vector direction
- the direction in the embedding space contains **semantic meaning**
- similarity between words can be measured by their difference in direction \ angle and can be measured by the [[cosine]] between them
	- example queen = king - man + woman

- the [[cosine]] shows how similar them meaning of two vectors $e_i$ and $e_j$ is
	- $+1$ → similar meaning
	- $0$ → uncorrelated
	- $-1$ → opposite meaning

$$
\mathrm{cos \ sim}(e_i, e_j) = \frac{\langle e_i, e_j \rangle}{||e_i|| \cdot ||e_j||}
$$

- based on the [[cosine]] similarity we can define the [[cosine]] distance as follows

$$
d_\mathrm{cos} = 1 - \mathrm{cos \ sim}(e_i, e_j)
$$


______

## embedding layer
- learnable representation of a sequence of tokens (see [[tokenization]]) with each token represented as a dense vector of size $D$ that contains information about its position and the token itself
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
- there are different methods for calculating the positional encoding, one of them is the [[sinusoidal positional encoding]]
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

- $PE$ is added to the token embeddings in the [[embedding layer]]



## tokenization
- translating text to numeric data by converting text into discrete units (= **tokens**)
- the vocabulary is a [[set]] of all possible tokens that are mapped to integer IDs with the [[cardinality]] $V$
- note that the tokenizer is trained independently of its language model (e.g. [[decoder transformers]]) but the model can only be used with its own tokenizer

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

### special tokens
- `<sos>` / `<bos>`: start of sequence
- `<eos>` : end of sequence that tells the model to stop generating
- `<pad>` : padding token for batch alignment that is ignored by the loss function and not predicted

### chat template tokens
- `<|system|>`: system prompt that sets global behavior or context
- `<|user|>`: user prompt that marks human input
- `<|assistant|>`: assistant prompt that marks model response

Tags: ml WS2526
<!--ID: 1762276191732-->
END