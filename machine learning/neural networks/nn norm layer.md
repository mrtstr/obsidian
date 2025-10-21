### norm layer
- normalize the input and re-scale it with learnt parameters
- **Role:** improves gradient flow in deep nets

$$
\mathrm{LN}(X) = W \odot \frac{X-\mu}{\sigma} + \beta
$$