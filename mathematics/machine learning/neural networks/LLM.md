[[neural network]]
[[nn transformer block]]

# anki

START
Basic
- innovations improving on the original transformer architecture from **attention is all you need** (6)
- hardware scaling innovations (4)

Back: 
- [[nn rotary position embeddings]] instead of [[nn sinusoidal positional encoding]]→ large context windows
- [[nn self attention layer#group query attention layer]] instead of [[nn self attention layer#multihead self attention layer]] → memory and compute efficiency
- [[nn RMSNorm Layer]] instead of [[nn norm layer]] → memory and compute efficiency
- [[nn rectified linear unit#swish gated linear unit]] instead of [[nn rectified linear unit]] → better gradients
- [[nn residual block]]: pre norm layer instead of post norm layer → **improves stability** and allows for deeper models
- low precision number format: `bf16` instead of `f32` → memory efficiency

hardware scaling techniques
- [[nn LLM training#data parallelism]]
- [[nn LLM training#pipeline parallelism]]
- [[nn LLM training#tensor parallelism]]
- [[nn LLM training#ZeRO (Zero Redundancy Optimizer)]]


Tags: mathematics ml WS2526
<!--ID: 1764257200502-->
END