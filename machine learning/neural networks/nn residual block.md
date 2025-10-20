### residual block
- skip conception layer in a [[neural network]] 
- adds a layer $F$ that can be bypassed 
	→ adds expressiveness but reduces the vanishing gradient problem

$$
\mathrm{RL}(x) = x + \mathrm{Dropout}\left(F(x)\right)
$$