## vector stores
- store tuples of (embedding, data) and are optimized for searching embeddings that are most similar to a given query vector → **semantic search** at **scale** by operating on **geometry in high-dimensional space**

$$
\arg\min_i \cos\mathrm{sim}(q, d_i)
$$

- problem: since there are a lot of vectors stored, checking each would be $\mathcal{O}(N)$ which is too slow → **approximated k nearest neighbor search** using [[nn ANN search]] algorithms
- plays an important role in the [[nn retrieval augmented generation]] for finding the initial candidates


![[nn ANN search#ANN search]]