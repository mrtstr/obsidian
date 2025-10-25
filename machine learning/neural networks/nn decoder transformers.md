## decoder transformers
- [[neural network]] for generation of content (often text) using [[nn transformer block|transformer blocks]] (e.g. GPT)
- general concept: train the model a [[maximum likelihood estimator]] that predicts the $t+1$ token given the tokens $1, ..., t$ as input 

$$
\begin{split}
\theta = \arg\max \sum_{i=1}^T \log p\left(X_{(t, *)}\right| X_{(<t, *)}, \theta)
\end{split}
$$
- given a text as training data tokenize it as one sequence of token ids

```
x = tokens[i : i + S]         # inputs
y = tokens[i + 1 : i + S + 1] # targets (next-token)
```

# -------------------

![[nn transformer block#transformer block]]


![[nn multihead self attention layer#multihead self attention layer]]