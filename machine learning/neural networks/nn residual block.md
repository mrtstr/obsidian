### residual block
- skip conception layer in a [[neural network]] 
- adds a layer $F$ that can be bypassed 
	→ adds expressiveness but reduces the vanishing gradient problem

$$
\mathrm{RL}(x) = x + \mathrm{Dropout}\left(F(x)\right)
$$

# anki


START
Basic
[[nn residual block]] and [[nn norm layer]]
Back: 
### residual block
- skip conception layer in a [[neural network]] 
- adds a layer $F$ that can be bypassed 
	→ adds expressiveness but reduces the vanishing gradient problem

$$
\mathrm{RL}(x) = x + \mathrm{Dropout}\left(F(x)\right)
$$

### norm layer
- normalize the input and re-scale it with learnt parameters

$$
\mathrm{LN}(x) = W \odot \frac{x-\mu}{\sigma} + \beta
$$

Tags: ml WS2526
<!--ID: 1761026390267-->
END
