## LLM scaling laws
- predict model performance of [[LLM]] based on 
	- **data consumption**: number of tokens $D$
	- **training effort**: number of FLOPs $C$
	- **model size**: number of parameters $N$
→ how to spend money efficiently to achieve the best outcome


### kaplan power laws
- predict the validation [[cross entropy loss]] $\ell$ based on 
- $\ell_\infty$ is the irreducible loss: entropy of natural language
- $A_*$ and $\alpha_*$ are fitted parameters

$$
\ell(N, D, C) = \ell_\infty + A_N N^{-\alpha_N} + A_D D^{-\alpha_D} + A_C C^{-\alpha_C}
$$

- **result**: loss improves smoothly and predictably but with diminishing returns
- **problem**: assumed fixed data and training settings, which led to overestimating optimal model size and underestimating how much data large models need

### chinchilla scaling laws
- given a **compute budget**: how to scale the model **parameters $N$** and the **training tokens $D$**
	→ Parameters and data should scale equally (Double model size → double training tokens)
- suggests **smaller models and more data** than the **kaplan power laws**

$$
N_\mathrm{opt} \sim C^{0.49} \quad D_\mathrm{opt} \sim C^{0.51}
$$

example

$$
\begin{split}
C' &= 10 C \\
N' &= 10^{0.51} N = 3.09 N \\
D' &= 10^{0.49} D = 3.24 D \\
\end{split}
$$


**Impact**
- found out that current models were too large and under trained, which leads to
	- Higher loss for same compute
	- inefficient inference
	- Poor generalization

### inference optimal
- the **chinchilla scaling laws** and the **kaplan power laws** are about aciving the best possible training loss per budget but in reality we also want the inference cost to be low
	→ much smaller models

# anki

START
Basic
[[LLM scaling laws]]
- general goal
- two scaling laws and what is used in reality
Back: 
## LLM scaling laws
- predict model performance of [[LLM]] based on 
	- **data consumption**: number of tokens $D$
	- **training effort**: number of FLOPs $C$
	- **model size**: number of parameters $N$
→ how to spend money efficiently to achieve the best outcome


### kaplan power laws
- predict the validation [[cross entropy loss]] $\ell$ based on 
- $\ell_\infty$ is the irreducible loss: entropy of natural language
- $A_*$ and $\alpha_*$ are fitted parameters

$$
\ell(N, D, C) = \ell_\infty + A_N N^{-\alpha_N} + A_D D^{-\alpha_D} + A_C C^{-\alpha_C}
$$

- **result**: loss improves smoothly and predictably but with diminishing returns
- **problem**: assumed fixed data and training settings, which led to overestimating optimal model size and underestimating how much data large models need

### chinchilla scaling laws
- given a **compute budget**: how to scale the model **parameters $N$** and the **training tokens $D$**
	→ Parameters and data should scale equally (Double model size → double training tokens)
- suggests **smaller models and more data** than the **kaplan power laws**

$$
N_\mathrm{opt} \sim C^{0.49} \quad D_\mathrm{opt} \sim C^{0.51}
$$

example
$$
\begin{split}
C' &= 10 C \\
N' &= 10^{0.51} N = 3.09 N \\
D' &= 10^{0.49} D = 3.24 D \\
\end{split}
$$

**Impact**
- found out that current models were too large and under trained, which leads to
	- Higher loss for same compute
	- inefficient inference
	- Poor generalization

### inference optimal
- the **chinchilla scaling laws** and the **kaplan power laws** are about aciving the best possible training loss per budget but in reality we also want the inference cost to be low
	→ much smaller models


Tags: ml WS2526
<!--ID: 1764596399405-->
END

START
Basic
[[LLM scaling laws]]
- impact the **chinchilla scaling laws** had on model development and why
- what do they say needs to be done when the training bugest in FLOPS increases by 10
Back: 
## LLM scaling laws
- predict model performance of [[LLM]] based on 
	- **data consumption**: number of tokens $D$
	- **training effort**: number of FLOPs $C$
	- **model size**: number of parameters $N$
→ how to spend money efficiently to achieve the best outcome


### kaplan power laws
- predict the validation [[cross entropy loss]] $\ell$ based on 
- $\ell_\infty$ is the irreducible loss: entropy of natural language
- $A_*$ and $\alpha_*$ are fitted parameters

$$
\ell(N, D, C) = \ell_\infty + A_N N^{-\alpha_N} + A_D D^{-\alpha_D} + A_C C^{-\alpha_C}
$$

- **result**: loss improves smoothly and predictably but with diminishing returns
- **problem**: assumed fixed data and training settings, which led to overestimating optimal model size and underestimating how much data large models need


### chinchilla scaling laws
- given a **compute budget**: how to scale the model **parameters $N$** and the **training tokens $D$**
	→ Parameters and data should scale equally (Double model size → double training tokens)
- suggests **smaller models and more data** than the **kaplan power laws**

$$
N_\mathrm{opt} \sim C^{0.49} \quad D_\mathrm{opt} \sim C^{0.51}
$$

example
$$
\begin{split}
C' &= 10 C \\
N' &= 10^{0.51} N = 3.09 N \\
D' &= 10^{0.49} D = 3.24 D \\
\end{split}
$$

**Impact**
- found out that current models were too large and under trained, which leads to
	- Higher loss for same compute
	- inefficient inference
	- Poor generalization

### inference optimal
- the **chinchilla scaling laws** and the **kaplan power laws** are about aciving the best possible training loss per budget but in reality we also want the inference cost to be low
	→ much smaller models


Tags: ml WS2526
<!--ID: 1764596399409-->
END

