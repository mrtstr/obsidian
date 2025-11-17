### rectified linear unit (ReLu)
- most widely used [[nn activation function]] for hidden layers of [[neural network]] 
- $\mathrm{ReLu}: \mathbb{R} \to \mathbb{R}^+$ is defined as follows

$$
\mathrm{ReLu}(z)=\max(0, z)
$$

### gated linear unit
- [[nn rectified linear unit]] has only two modes: either the information is passed completely or is blocked
- [[nn rectified linear unit#gated linear unit]] adds mechanism that can control the form of information that does thru the node using the [[sigmoid function]]
	- $>1$ → information is fully passed
	- $<0$ → information is blocked
	- between $0$ and $1$ → information is partially allowed through
- there are extra parameters trained that control the input of the [[sigmoid function]]

$$
\mathrm{GLU}(X) = \left(XW_1 + b_1\right) \odot \sigma\left(XW_2 + b_2\right)
$$
#### pros
- **Better Gradient Flow**
	- Avoids "dying ReLU" problem
	- Better gradient flow and optimization properties
	- Can completely shut off dimensions when needed (unlike ReLU which only zeros negatives)
	- smooth [[gradient]]
- **Higher Expressiveness**: 
	- Allows dynamic, input-dependent feature selection
- **Better Performance per Parameter**
- **Improved Reasoning Behavior for LLMs**
### cons
- more expensive to calculate and needs extra parameters

### swish gated linear unit
- sale concept as the [[nn rectified linear unit#gated linear unit]] but the [[sigmoid function]] is replaced with a swish gate
- best performance and standard for LLMs
- SwiGLU specifically has smooth, non-zero gradients almost everywhere


# anki

START
Basic
[[nn rectified linear unit]]
- concept
- two improved versions with pros (4) and cons (1)
Back: 
### rectified linear unit (ReLu)
- most widely used [[nn activation function]] for hidden layers of [[neural network]] 
- $\mathrm{ReLu}: \mathbb{R} \to \mathbb{R}^+$ is defined as follows

$$
\mathrm{ReLu}(z)=\max(0, z)
$$

### gated linear unit
- [[nn rectified linear unit]] has only two modes: either the information is passed completely or is blocked
- [[nn rectified linear unit#gated linear unit]] adds mechanism that can control the form of information that does thru the node using the [[sigmoid function]]
	- $>1$ → information is fully passed
	- $<0$ → information is blocked
	- between $0$ and $1$ → information is partially allowed through
- there are extra parameters trained that control the input of the [[sigmoid function]]

$$
\mathrm{GLU}(X) = \left(XW_1 + b_1\right) \odot \sigma\left(XW_2 + b_2\right)
$$
#### pros
- **Better Gradient Flow**
	- Avoids "dying ReLU" problem
	- Better gradient flow and optimization properties
	- Can completely shut off dimensions when needed (unlike ReLU which only zeros negatives)
	- smooth [[gradient]]
- **Higher Expressiveness**: 
	- Allows dynamic, input-dependent feature selection
- **Better Performance per Parameter**
- **Improved Reasoning Behavior for LLMs**
### cons
- more expensive to calculate and needs extra parameters

### swish gated linear unit
- sale concept as the [[nn rectified linear unit#gated linear unit]] but the [[sigmoid function]] is replaced with a swish gate
- best performance and standard for LLMs
- SwiGLU specifically has smooth, non-zero gradients almost everywhere



Tags: mathematics ml WS2526
<!--ID: 1763391965779-->
END