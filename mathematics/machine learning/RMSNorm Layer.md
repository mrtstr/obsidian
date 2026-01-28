### RMSNorm Layer
- improvement on the original [[norm layer]] that only re-scales but don't shift → the only leaned parameter is $W$ ($\epsilon$ is a small constant for numerical stability)

$$
\mathrm{RMSNorm}(X) = W \odot \frac{X}{\sqrt{\frac{1}{d}\sum X_i^2+\epsilon}}
$$

- simpler: only scaling but no shifting parameter
- faster with similar performance than [[norm layer]] especially for [[transformer block|transformer models]]
# -----------

![[norm layer#norm layer]]


# anki

START
Basic
norm layer used for [[transformer block|transformer]] based LLMs
Back: 
### RMSNorm Layer
- improvement on the original [[norm layer]] that only re-scales but don't shift → the only leaned parameter is $W$ ($\epsilon$ is a small constant for numerical stability)

$$
\mathrm{RMSNorm}(X) = W \odot \frac{X}{\sqrt{\frac{1}{d}\sum X_i^2+\epsilon}}
$$

- simpler: only scaling but no shifting parameter
- faster with similar performance than [[norm layer]] especially for [[transformer block|transformer models]]

### norm layer
- normalize the input and re-scale it with learnt parameters
- **Role:** improves gradient flow in deep nets

$$
\mathrm{LN}(X) = W \odot \frac{X-\mu}{\sigma} + \beta
$$

Tags: ml WS2526
<!--ID: 1763387136528-->
END