## embeddings
- learnable representation of a sequence of tokens with each token represented as a dense vector of size $D$ that contains information about its position and the token itself
- Build the Vocabulary which is a mapping from of all possible symbols to ids and size $V$
- with a sequence length $S$ encode all input token as one hot vector $I_E \in \{0,1\}^{S \times V}$
- the positions are encoded with the unity matrix $I_P \in \{0,1\}^{S \times L}$ that has $1$ on the diagonal and zeros everywhere else with $L$ being the maximal sequence length
- Train an embedding [[matrix]] $E\in \mathbb{R}^{V \times D}$ and a positional encoding [[matrix]] $P \in \mathbb{R}^{L \times D}$ to get the embeddings $X$ are then calculated as follows containing the token and positional encoding
- an additional dimension for the batch size $B$ is added such that $X \in \mathbb{R}^{B \times S \times D}$

$$
X = I_EE + I_PP \in \mathbb{R}^{S \times D}
$$

# anki


START
Basic
[[nn embeddings]]
- concept
- how its created

Back: 
## embeddings
- learnable representation of a sequence of tokens with each token represented as a dense vector of size $D$ that contains information about its position and the token itself
- Build the Vocabulary which is a mapping from of all possible symbols to ids and size $V$
- with a sequence length $S$ encode all input token as one hot vector $I_E \in \{0,1\}^{S \times V}$
- the positions are encoded with the unity matrix $I_P \in \{0,1\}^{S \times L}$ that has $1$ on the diagonal and zeros everywhere else with $L$ being the maximal sequence length
- Train an embedding [[matrix]] $E\in \mathbb{R}^{V \times D}$ and a positional encoding [[matrix]] $P \in \mathbb{R}^{L \times D}$ to get the embeddings $X$ are then calculated as follows containing the token and positional encoding
- an additional dimension for the batch size $B$ is added such that $X \in \mathbb{R}^{B \times S \times D}$

$$
X = I_EE + I_PP \in \mathbb{R}^{S \times D}
$$

Tags: ml WS2526
<!--ID: 1761397169374-->
END
