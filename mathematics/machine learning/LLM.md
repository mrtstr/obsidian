[[neural network]]
[[transformer block]]

# anki

START
Basic
- innovations improving on the original transformer architecture from **attention is all you need** (6)
- hardware scaling innovations (4)

Back: 
- [[rotary position embeddings]] instead of [[sinusoidal positional encoding]]→ large context windows
- [[self attention layer#group query attention layer]] instead of [[self attention layer#multihead self attention layer]] → memory and compute efficiency
- [[RMSNorm Layer]] instead of [[norm layer]] → memory and compute efficiency
- [[rectified linear unit#swish gated linear unit]] instead of [[rectified linear unit]] → better gradients
- [[residual block]]: pre norm layer instead of post norm layer → **improves stability** and allows for deeper models
- low precision number format: `bf16` instead of `f32` → memory efficiency

hardware scaling techniques
- [[scaling of LLM training#data parallelism]]
- [[scaling of LLM training#pipeline parallelism]]
- [[scaling of LLM training#tensor parallelism]]
- [[scaling of LLM training#ZeRO (Zero Redundancy Optimizer)]]


Tags: mathematics ml WS2526
<!--ID: 1764257200502-->
END