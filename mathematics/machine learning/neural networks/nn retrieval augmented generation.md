## retrieval augmented generation
- the [[LLM]] contains knowledge in its weights that has the following limitations
	1) **static**: cannot update after [[nn pretraining]]
	2) **opaque**: impossible to inspect what the model “knows”
	3) **incomplete**: [[nn pretraining]] data is finite and often outdated
	4) **hallucination-prone**: model produces confident but incorrect answers
- the [[nn retrieval augmented generation]] process overcomes the limitations by retrieving additional information and adding it to the context of the [[LLM]]
- the [[nn retrieval augmented generation]] adds to the condition of the [[conditional probability]] function $p$

$$
p(y | x , \mathrm{RAG}(x))
$$

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

#### used models
1) general porpouse [[nn sentence BERT]]
2) [[nn sentence BERT]] + domain adaptation
	- optionally the [[nn sentence BERT]] can be adapted on a specific domain to build a [[nn retrieval augmented generation]] that is specifically for a certain domain like medical or legal
3) [[nn sentence BERT]] with cross linual training
4) newer approaches with asymmetrical query/document encoders

![[nn sentence BERT#sentence BERT]]

### chunking
- process of converting documents in multiple pieces → defines the **atomic unit of knowledge** in RAG
- overlapping helps to preserve the context and increases storage and compute cost
- chunking strategies
	1) sentence based chunking
	2) semantic chunking
	3) section aware chunking (headings, paragraphs)
	4) chunks as semantic units
- good chunking is very important for the downstream process

##### contextual retrieval
- general idea: **enrich each chunk with context**
- use an [[LLM]] to generate a short context description and add it to the chunk
→ Chunks become self-contained, and the embeddings encode the local and global meaning

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


START
Basic
[[nn retrieval augmented generation#embedding (chunks)]]
- concept of the embedding space
- used models / approaches (4)
Back: 
### embedding (chunks)
- a model $e$ maps the text into a $d$ dimensional dense vector space (e.g. $d=384, 768, 1536$)
$$e: \text{text} \to \mathbb{R}^d$$
- similar text should be geometrically close in the vector space such that we can rank by distance

$$
\arg\min_i\text{distance} (q, d_i) \quad \text{with } q=e(x), d_i=e(\text{chunk}_i)
$$

#### used models
1) general porpouse [[nn sentence BERT]]
2) [[nn sentence BERT]] + domain adaptation
	- optionally the [[nn sentence BERT]] can be adapted on a specific domain to build a [[nn retrieval augmented generation]] that is specifically for a certain domain like medical or legal
3) [[nn sentence BERT]] with cross linual training
4) newer approaches with asymmetrical query/document encoders

### sentence BERT
- build on top of **BERT** and is [[nn supervised fine tuning|fine tuned]] on sentence pair similarity
- enables semantic search, clustering and [[nn retrieval augmented generation]]
- the final output (=sentence representation) is created by applying pooling on the tokens
	- **mean pooling**: taking the mean over the token embeddings
	- **max pooling**: taking the element wise maximum over the token embeddings
	- **weighted pooling**
	- **CLS token pooling**

#### training procedure
- start with a [[nn pretraining]] BERT model
- create a training set with sentence pairs with the known similarity score
- during the training pass both sentences of the tuples during the same BERT model and calculate the [[cosine]] similarity
- training with the known similarity labels

![[Pasted image 20260110172324.png]]
#### BERT
- [[nn encoder decoder transformers|encoder]] [[LLM]] that generates contextual token level representations of the input
- uses bidirectional [[nn self attention layer|self attention]] (no masking)


____________

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
<!--ID: 1768062256223-->
END


START
Basic
[[nn retrieval augmented generation#chunking]]
- general concept
- chunking strategies (4)
- how to improve the chunks?
- what is **contextual retrieval**?

Back: 

### chunking
- process of converting documents in multiple pieces → defines the **atomic unit of knowledge** in RAG
- overlapping helps to preserve the context and increases storage and compute cost
- chunking strategies
	1) sentence based chunking
	2) semantic chunking
	3) section aware chunking (headings, paragraphs)
	4) chunks as semantic units
- good chunking is very important for the downstream process

##### contextual retrieval
- general idea: **enrich each chunk with context**
- use an [[LLM]] to generate a short context description and add it to the chunk
→ Chunks become self-contained, and the embeddings encode the local and global meaning

____________

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
Tags: ml WS2526
<!--ID: 1768063868950-->
END