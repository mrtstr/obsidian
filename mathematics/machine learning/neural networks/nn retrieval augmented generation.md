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
- vector database that constrains text chunks as tuples (**chunk embedding**, **chunk**)
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

##### chunk size trade off
- good compromise: 200-500 tokens
small chunks
- higher recall
- more precises context matching
- loss of context and coherence
large chunks
- lower recall
- risk of irrelevant information
- better semantic coherence
##### contextual retrieval
- general idea: **enrich each chunk with context**
- use an [[LLM]] to generate a short context description and add it to the chunk
→ Chunks become self-contained, and the embeddings encode the local and global meaning

### quality metrics
#### retrieval recall
- fraction of relevant chunks that appear in the retrieved results → if there are 100 relevant documents in the data but only 50 appear in the top results the recall is 0.5
- maximum depends on the quality of the embeddings

### retrieval process

#### dense retrieval
- used dense representations that encode **semantic meaning** using [[LLM]] models and not just work overlap
- query and chunks are embedded in the same vector space
- retrieve top $k$ chunks based on cosine similarity bases on approximating [[nn ANN search]] algorithms

$$
\arg\min_i \cos\mathrm{sim}(q, d_i)
$$

- weakness: might miss exact IDs or serial numbers or names with low training frequency → sparse retrieval can help here

![[nn ANN search#ANN search]]
#### sparse retrieval
- documents are represented by their **words with occurrence frequency**
- ranking based on **overlap of exact word occurrences**
- most common method: [[BM25]]
- weakness: doesn't cover semantic similarity's and synonyms 
- but good for rare specific terms

![[BM25#BM25]]

#### hybrid retrieval
- combines the strengths of dense (semantic meaning) and sparse (lexical meaning) retrieving
- query the candidates with both approaches and generate a combined ranking using **Reciprocal Rank Fusion**

##### Reciprocal Rank Fusion
- combines the ranks of multiple ranking systems
- $k$ is a constant, often ground $60$

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)}
$$

example: if a document is 2. in system A and 5. in system B it has the following $\mathrm{RRF}$ score

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)} = \frac{1}{60+2} + \frac{1}{60+5}
$$


### ranking
- optional step after retrieval: use more **expensive methods** on a **small candidate set** to **maximize precision**
- during retrieval the most important was scalability: we need to scan missions of documents fast to extract a set of candidates

##### Cross-Encoder ranking
- give query and each chunk to a encoder + classifier and that it score the relevance
- pro: more precises then embedding similarity, handles negation and constraints
- con: to slow and expensive for large scale retrieval
##### LLM based ranking
- give and query and all candidates to an [[LLM]] and let it rank them
- pro: strong semantic understanding, handles constrains
- cons: very expensive and slows

### context assembly
- take the ranked chunks and assemble the context (needs to fit in the context budget $B$)
#### potential problems
- if the amount of context is too large and the relevant information might get ignored because the attention is spread across low ranked token which leads to more hallucination
→ context quality beats context quality
#### strategies
- deduplicate overlapping content
- strategies: **just take the top chunks** until the context budget or **prefer shorter high ranked chunks**

### query decomposition
- in a standard [[nn retrieval augmented generation]] we assume that the entire necessary information can be retrieved in one query, but this is not always possible
- solution: **Multi-Step Query**: use a **simple rule based logic** or the **[[LLM]] itself** to decompose the problem into multiple sub problems to fetch all necessary information

$$
z = \mathrm{RAG}(x) \Rightarrow z_1 = \mathrm{RAG}(x_1), \quad z_2 = \mathrm{RAG}(x_2)
$$
#### pro
- higher recall for complex problems
- better evidence coverage → lower hallucination risk

#### contra
- increased latency
- more system complexity

### evaluation
- if the final result fails it can be caused by one step in the process failing → end to end metrics are not sufficient
	- **retrieval**: the right information was not found
	- **re-ranking**: the right information was ranked too low
	- **generation**: the information was in the context window but was ignored
#### retrieval evaluation
- evaluated using prepared query's and documents with relevance labels (mostly binary)
# anki

START
Basic
[[nn retrieval augmented generation#query decomposition]]
- general concepts
- different approaches
- pros and cons

Back: 

### query decomposition
- in a standard [[nn retrieval augmented generation]] we assume that the entire necessary information can be retrieved in one query, but this is not always possible
- solution: **Multi-Step Query**: use a **simple rule based logic** or the **[[LLM]] itself** to decompose the problem into multiple sub problems to fetch all necessary information

$$
z = \mathrm{RAG}(x) \Rightarrow z_1 = \mathrm{RAG}(x_1), \quad z_2 = \mathrm{RAG}(x_2)
$$
#### pro
- higher recall for complex problems
- better evidence coverage → lower hallucination risk

#### contra
- increased latency
- more system complexity

_____________

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
<!--ID: 1768678971889-->
END

START
Basic
[[nn retrieval augmented generation#context assembly]]
- general task
- strategies
- potential problems

Back: 

### context assembly
- take the ranked chunks and assemble the context (needs to fit in the context budget $B$)
#### potential problems
- if the amount of context is too large and the relevant information might get ignored because the attention is spread across low ranked token which leads to more hallucination
→ context quality beats context quality
#### strategies
- deduplicate overlapping content
- strategies: **just take the top chunks** until the context budget or **prefer shorter high ranked chunks**

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
<!--ID: 1768678971892-->
END

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
- chunk size trade off
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

##### chunk size trade off
- good compromise: 200-500 tokens
small chunks
- higher recall
- more precises context matching
- loss of context and coherence
large chunks
- lower recall
- risk of irrelevant information
- better semantic coherence
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


START
Basic
[[nn retrieval augmented generation#chunking]]
- pros and cons of large and small chunks
- what is often a good compromise?

Back: 
##### chunk size trade off
- good compromise: 200-500 tokens
small chunks
- higher recall
- more precises context matching
- loss of context and coherence
large chunks
- lower recall
- risk of irrelevant information
- better semantic coherence
### chunking
- process of converting documents in multiple pieces → defines the **atomic unit of knowledge** in RAG
- overlapping helps to preserve the context and increases storage and compute cost
- chunking strategies
	1) sentence based chunking
	2) semantic chunking
	3) section aware chunking (headings, paragraphs)
	4) chunks as semantic units
- good chunking is very important for the downstream process

##### chunk size trade off
- good compromise: 200-500 tokens
small chunks
- higher recall
- more precises context matching
- loss of context and coherence
large chunks
- lower recall
- risk of irrelevant information
- better semantic coherence
##### contextual retrieval
- general idea: **enrich each chunk with context**
- use an [[LLM]] to generate a short context description and add it to the chunk
→ Chunks become self-contained, and the embeddings encode the local and global meaning



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
<!--ID: 1768123447451-->
END


START
Basic
[[nn retrieval augmented generation#retrieval process]]: two approaches
- how are documents encoded
- how does the ranking work
- strength and weaknesses
- what is the giving the best results

Back: 
### retrieval process

#### dense retrieval
- used dense representations that encode **semantic meaning** using [[LLM]] models and not just work overlap
- query and chunks are embedded in the same vector space
- retrieve top $k$ chunks based on cosine similarity bases on approximating [[nn ANN search]] algorithms

$$
\arg\min_i \cos\mathrm{sim}(q, d_i)
$$

- weakness: might miss exact IDs or serial numbers or names with low training frequency → sparse retrieval can help here

#### sparse retrieval
- documents are represented by their **words with occurrence frequency**
- ranking based on **overlap of exact word occurrences**
- most common method: [[BM25]]
- weakness: doesn't cover semantic similarity's and synonyms 
- but good for rare specific terms
#### hybrid retrieval
- combines the strengths of dense (semantic meaning) and sparse (lexical meaning) retrieving
- query the candidates with both approaches and generate a combined ranking using **Reciprocal Rank Fusion**

##### Reciprocal Rank Fusion
- combines the ranks of multiple ranking systems
- $k$ is a constant, often ground $60$

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)}
$$

example: if a document is 2. in system A and 5. in system B it has the following $\mathrm{RRF}$ score

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)} = \frac{1}{60+2} + \frac{1}{60+5}
$$



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
<!--ID: 1768229318740-->
END



START
Basic
[[nn retrieval augmented generation#retrieval process]]: dense retrieval
- how are documents represented
- how are documents ranked
- how does the retrieval process work? (4 algorithms)
- weaknesses

Back: 
#### dense retrieval
- used dense representations that encode **semantic meaning** using [[LLM]] models and not just work overlap
- query and chunks are embedded in the same vector space
- retrieve top $k$ chunks based on cosine similarity bases on approximating [[nn ANN search]] algorithms

$$
\arg\min_i \cos\mathrm{sim}(q, d_i)
$$

- weakness: might miss exact IDs or serial numbers or names with low training frequency → sparse retrieval can help here

### ANN search
- used in [[nn vector stores]] for the retrieval process in [[nn retrieval augmented generation]]
- **goal**: find vectors that are close enough to the true nearest neighbors, much faster than a full similarity scan 
- → trades accuracy for speed (configurable)
- organizes data in structured indexes such that it only needs to scan a fraction of the data
- there are multiple strategies to achieve that
- the **Facebook AI Similarity Search** library contains an implementation of most of them

![[Pasted image 20260111190859.png]]
#### Inverted File Index (IVF)
when setting up
1) train $k$ centroids using k-means
2) assign each vector to its nearest centroid
when querying
3) find centroid that is most similar to the query vector
4) search only in the cluster

- **pro**: fast and scales well
- **contra**: result depends on the number of clusters and can miss neighbors in unsearched clusters

#### Quantization-Based Indexes (Quantized)
- compress vectors to use less memory and search faster
- **Scalar Quantization**: use lower precision numbers
- **Product Quantization**: split dense vector in groups and encode each group with a smaller sequence using a lookup table

- **pro**: fast and lower memory usage
- **contra**: lower precision

#### Hierarchical Navigable Small World Graph (HNSW)
- combines the NSW with the skip list concept to reduce the number of hops needed to find similar nodes
- has multiple layers with horizontal connections
	- bottom layer: contains all nodes
	- middle layer: contains 50% of the nodes
	- top layer: contains 5% of the nodes
- start searching at the top layer and use vertical connections to find similar nodes fast
##### (Flat) Navigable Small World Graph (NSW)
- use a graph structure where each node (=vector) is connected
- use greedy search to navigate the graph (move to the closed neighbor until no improvements possible)
##### inserting in the graph
- start at a random node
- add connections to the closeted neighbors until no improvement possible
- prune back to $n$ elements by preferring close distance and diversity
##### retrieving top $k$ elements
- search the graph greedy and keep the similarity scores and stop when there are no nodes with a higher similarity than the $kth$ highest known node in the neighborhood
- return the $k$ elements with the lowest scores

____________
### retrieval process

#### dense retrieval
- used dense representations that encode **semantic meaning** using [[LLM]] models and not just work overlap
- query and chunks are embedded in the same vector space
- retrieve top $k$ chunks based on cosine similarity bases on approximating [[nn ANN search]] algorithms

$$
\arg\min_i \cos\mathrm{sim}(q, d_i)
$$

- weakness: might miss exact IDs or serial numbers or names with low training frequency → sparse retrieval can help here

#### sparse retrieval
- documents are represented by their **words with occurrence frequency**
- ranking based on **overlap of exact word occurrences**
- most common method: [[BM25]]
- weakness: doesn't cover semantic similarity's and synonyms 
- but good for rare specific terms
#### hybrid retrieval
- combines the strengths of dense (semantic meaning) and sparse (lexical meaning) retrieving
- query the candidates with both approaches and generate a combined ranking using **Reciprocal Rank Fusion**

##### Reciprocal Rank Fusion
- combines the ranks of multiple ranking systems
- $k$ is a constant, often ground $60$

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)}
$$

example: if a document is 2. in system A and 5. in system B it has the following $\mathrm{RRF}$ score

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)} = \frac{1}{60+2} + \frac{1}{60+5}
$$



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
<!--ID: 1768229318742-->
END



START
Basic
[[nn retrieval augmented generation#retrieval process]]: sparse retrieval
- how are documents represented
- how are documents ranked
- weaknesses

Back: 
#### sparse retrieval
- documents are represented by their **words with occurrence frequency**
- ranking based on **overlap of exact word occurrences**
- most common method: [[BM25]]
- weakness: doesn't cover semantic similarity's and synonyms 
- but good for rare specific terms

### BM25
- classical ranking function from information retrieval
- based on **explicit word occurrence** (exact word overlap)
- used for sparse retrieval in [[nn retrieval augmented generation]]

$$
\mathrm{score(q, d)} = \sum_{t \in q} \mathrm{IDF}(t) \cdot \frac{\mathrm{TF(t, d)}}{\mathrm{TF(t, d)}+\mathrm{normalization}(d)}
$$

- $\mathrm{IDF}(t)$: how rare is the term $t$ across the document collection
- $\mathrm{TF(t, d)}$: how often does term $t$ appear in the document $d$
- $\mathrm{normalization}(d)$: based on the length of document $d$ → ensures that long and short documents are treated fairly

#### criteria
- rare words have a higher weight
- long and short documents are treated fairly
- diminishing returns: first occurrences have a high impact but the followings less and less

____________
### retrieval process

#### dense retrieval
- used dense representations that encode **semantic meaning** using [[LLM]] models and not just work overlap
- query and chunks are embedded in the same vector space
- retrieve top $k$ chunks based on cosine similarity bases on approximating [[nn ANN search]] algorithms

$$
\arg\min_i \cos\mathrm{sim}(q, d_i)
$$

- weakness: might miss exact IDs or serial numbers or names with low training frequency → sparse retrieval can help here

#### sparse retrieval
- documents are represented by their **words with occurrence frequency**
- ranking based on **overlap of exact word occurrences**
- most common method: [[BM25]]
- weakness: doesn't cover semantic similarity's and synonyms 
- but good for rare specific terms
#### hybrid retrieval
- combines the strengths of dense (semantic meaning) and sparse (lexical meaning) retrieving
- query the candidates with both approaches and generate a combined ranking using **Reciprocal Rank Fusion**

##### Reciprocal Rank Fusion
- combines the ranks of multiple ranking systems
- $k$ is a constant, often ground $60$

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)}
$$

example: if a document is 2. in system A and 5. in system B it has the following $\mathrm{RRF}$ score

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)} = \frac{1}{60+2} + \frac{1}{60+5}
$$



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
<!--ID: 1768229318745-->
END



START
Basic
[[nn retrieval augmented generation#retrieval process]]: hybrid retrieval
- how are documents represented
- how are documents ranked

example: if a document is 2. in system A and 5. in system B after which score is it ranked?


Back: 
#### hybrid retrieval
- combines the strengths of dense (semantic meaning) and sparse (lexical meaning) retrieving
- query the candidates with both approaches and generate a combined ranking using **Reciprocal Rank Fusion**

##### Reciprocal Rank Fusion
- combines the ranks of multiple ranking systems
- $k$ is a constant, often ground $60$

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)}
$$

example: if a document is 2. in system A and 5. in system B it has the following $\mathrm{RRF}$ score

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)} = \frac{1}{60+2} + \frac{1}{60+5}
$$


____________
### retrieval process

#### dense retrieval
- used dense representations that encode **semantic meaning** using [[LLM]] models and not just work overlap
- query and chunks are embedded in the same vector space
- retrieve top $k$ chunks based on cosine similarity bases on approximating [[nn ANN search]] algorithms

$$
\arg\min_i \cos\mathrm{sim}(q, d_i)
$$

- weakness: might miss exact IDs or serial numbers or names with low training frequency → sparse retrieval can help here

#### sparse retrieval
- documents are represented by their **words with occurrence frequency**
- ranking based on **overlap of exact word occurrences**
- most common method: [[BM25]]
- weakness: doesn't cover semantic similarity's and synonyms 
- but good for rare specific terms
#### hybrid retrieval
- combines the strengths of dense (semantic meaning) and sparse (lexical meaning) retrieving
- query the candidates with both approaches and generate a combined ranking using **Reciprocal Rank Fusion**

##### Reciprocal Rank Fusion
- combines the ranks of multiple ranking systems
- $k$ is a constant, often ground $60$

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)}
$$

example: if a document is 2. in system A and 5. in system B it has the following $\mathrm{RRF}$ score

$$
\mathrm{RRF(d)} = \sum_i \frac{1}{k+\mathrm{rank}_i(d)} = \frac{1}{60+2} + \frac{1}{60+5}
$$



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
<!--ID: 1768229318747-->
END


START
Basic
[[nn retrieval augmented generation#ranking]]
- why is it needed and whats to difference to the retrieval step?
- two approaches with pros and cons


Back: 
### ranking
- optional step after retrieval: use more **expensive methods** on a **small candidate set** to **maximize precision**
- during retrieval the most important was scalability: we need to scan missions of documents fast to extract a set of candidates

##### Cross-Encoder ranking
- give query and each chunk to a encoder + classifier and that it score the relevance
- pro: more precises then embedding similarity, handles negation and constraints
- con: to slow and expensive for large scale retrieval
##### LLM based ranking
- give and query and all candidates to an [[LLM]] and let it rank them
- pro: strong semantic understanding, handles constrains
- cons: very expensive and slows

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
<!--ID: 1768232529845-->
END