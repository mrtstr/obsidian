## retrieval augmented generation
- the [[LLM]] contains knowledge in its weights that has the following limitations
	1) **static**: cannot update after [[nn pretraining]]
	2) **opaque**: impossible to inspect what the model “knows”
	3) **incomplete**: [[nn pretraining]] data is finite and often outdated
	4) **hallucination-prone**: model produces confident but incorrect answers
- the [[nn retrieval augmented generation]] process overcomes the limitations by retrieving additional information and adding it to the context of the [[LLM]]

### general approach
- vector database that constrains text chunks as tuples (**chunk enbedding**, **chunk**)
- when a user sends a prompt the prompt is mapped in the same embedding space of the chunks and similar chunks are searched in the vector database
- the best matches are then **ranked**, and the best ones are **assembled** and **added to the context window**

![[Pasted image 20260105103416.png]]

1. Document Preparation (Offline)
	- gather raw documents
	- chunk them
	- compute embeddings of chunks
	- insert them in a vector database
2. Query Embedding (Online)
	- embed user query
3. Retrieval
	- search similar vectors in store
	- retrieve top-k candidates
4. Reranking (Optional)
	- reorder candidates using stronger but more expensive models → improve precision before generation
5. Context Assembly
	- select, truncate and order chunks
	- fit them in the models context window
6. Generation
	- generate response based in user query and additional information


### embedding (chunks)
- a model $e$ maps the text into a $d$ dimensional dense vector space (e.g. $d=384, 768, 1536$)
$$e: \text{text} \to \mathbb{R}^d$$
- similar text should be geometrically close in the vector space such that we can rank by distance
$$
\arg\min_i\text{distance} (q, d_i) \quad \text{with } q=e(x), d_i=e(\text{chunk}_i)
$$
- [[nn encoder decoder transformers|encoder transformers]] like **BERT** can be used for calculating the embeddings, but there are models specifically designed for that **[[nn Sentence-BERT]]**

![[nn Sentence-BERT#Sentence-BERT]]
# anki

START
Basic
[[nn retrieval augmented generation]]
- general concept
- limitations of [[LLM]] that it should help to overcome (4)

Back: 
## retrieval augmented generation
- the [[LLM]] contains knowledge in its weights that has the following limitations
	1) **static**: cannot update after [[nn pretraining]]
	2) **opaque**: impossible to inspect what the model “knows”
	3) **incomplete**: [[nn pretraining]] data is finite and often outdated
	4) **hallucination-prone**: model produces confident but incorrect answers
- the [[nn retrieval augmented generation]] process overcomes the limitations by retrieving additional information and adding it to the context of the [[LLM]]

### general approach
- vector database that constrains text chunks as tuples (**chunk enbedding**, **chunk**)
- when a user sends a prompt the prompt is mapped in the same embedding space of the chunks and similar chunks are searched in the vector database
- the best matches are then **ranked**, and the best ones are **assembled** and **added to the context window**

![[Pasted image 20260105103419.png]]

1. Document Preparation (Offline)
	- gather raw documents
	- chunk them
	- compute embeddings of chunks
	- insert them in a vector database
2. Query Embedding (Online)
	- embed user query
3. Retrieval
	- search similar vectors in store
	- retrieve top-k candidates
4. Reranking (Optional)
	- reorder candidates using stronger but more expensive models → improve precision before generation
5. Context Assembly
	- select, truncate and order chunks
	- fit them in the models context window
6. Generation
	- generate response based in user query and additional information
Tags: mathematics ml WS2526
<!--ID: 1767615347926-->
END

START
Basic
[[nn retrieval augmented generation]]
- general approach: 6 steps

Back: 
## retrieval augmented generation
- the [[LLM]] contains knowledge in its weights that has the following limitations
	1) **static**: cannot update after [[nn pretraining]]
	2) **opaque**: impossible to inspect what the model “knows”
	3) **incomplete**: [[nn pretraining]] data is finite and often outdated
	4) **hallucination-prone**: model produces confident but incorrect answers
- the [[nn retrieval augmented generation]] process overcomes the limitations by retrieving additional information and adding it to the context of the [[LLM]]

### general approach
- vector database that constrains text chunks as tuples (**chunk enbedding**, **chunk**)
- when a user sends a prompt the prompt is mapped in the same embedding space of the chunks and similar chunks are searched in the vector database
- the best matches are then **ranked**, and the best ones are **assembled** and **added to the context window**

![[Pasted image 20260105103423.png]]

1. Document Preparation (Offline)
	- gather raw documents
	- chunk them
	- compute embeddings of chunks
	- insert them in a vector database
2. Query Embedding (Online)
	- embed user query
3. Retrieval
	- search similar vectors in store
	- retrieve top-k candidates
4. Reranking (Optional)
	- reorder candidates using stronger but more expensive models → improve precision before generation
5. Context Assembly
	- select, truncate and order chunks
	- fit them in the models context window
6. Generation
	- generate response based in user query and additional information
Tags: mathematics ml WS2526
<!--ID: 1767615347932-->
END