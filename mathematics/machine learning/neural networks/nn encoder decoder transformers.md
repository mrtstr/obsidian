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

Tags: ml WS2526
<!--ID: 1762781311517-->
END

