### residual block
- skip conception layer in a [[neural network]] 
- adds a layer $F$ that can be bypassed 
	→ adds expressiveness but reduces the vanishing gradient problem

$$
\mathrm{RB}(x) = x + \mathrm{Dropout}\left(F(x)\right)
$$
### pre vs post layer norm
- a [[nn residual block]] is often combined with a [[nn norm layer]]
- initially the layer norm was applied after the [[nn residual block]] (post layer norm)

$$
\mathrm{RB}(x) = LN\left(x + F\left(x\right)\right)
$$
- later this was improved to pre layer norm

$$
\mathrm{RB}(x) = x + F\left(LN\left(x\right)\right)
$$
- pre layern norm **improves stability** and allows for deeper models (100 layers +)
- **preserves the original signal** untransformed
- improves overall robustness

![[nn norm layer#norm layer]]
# anki


START
Basic
[[nn residual block]] and [[nn norm layer]]
- benefits of [[nn residual block]] 
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


START
Basic
pre vs post layer norm
- concept and pros/cons
Back: 

### pre vs post layer norm
- a [[nn residual block]] is often combined with a [[nn norm layer]]
- initially the layer norm was applied after the [[nn residual block]] (post layer norm)

$$
\mathrm{RB}(x) = LN\left(x + F\left(x\right)\right)
$$
- later this was improved to pre layer norm

$$
\mathrm{RB}(x) = x + F\left(LN\left(x\right)\right)
$$
- pre layern norm **improves stability** and allows for deeper models (100 layers +)
- **preserves the original signal** untransformed
- improves overall robustness

_____________

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
<!--ID: 1763387136532-->
END
