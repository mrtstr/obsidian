### ANN search
- used in [[vector stores]] for the retrieval process in [[retrieval augmented generation]]
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



# anki

START
Basic
[[ANN search]]
- overview of ANN search strategies (4)
- comparison based on speed memory and precision

Back: 

### ANN search
- **goal**: find vectors that are close enough to the true nearest neighbors, much faster than a full similarity scan 
- → trades accuracy for speed (configurable)
- organizes data in structured indexes such that it only needs to scan a fraction of the data
- there are multiple strategies to achieve that
- the **Facebook AI Similarity Search** library contains an implementation of most of them

![[Pasted image 20260111191931.png]]
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

_______
## vector stores
- store tuples of (embedding, data) and are optimized for searching embeddings that are most similar to a given query vector → **semantic search** at **scale** by operating on **geometry in high-dimensional space**

$$
\arg\min_i \cos\mathrm{sim}(q, d_i)
$$

- problem: since there are a lot of vectors stored, checking each would be $\mathcal{O}(N)$ which is too slow → **approximated k nearest neighbor search** using [[ANN search]] algorithms
- plays an important role in the [[retrieval augmented generation]] for finding the initial candidates

Tags: ml WS2526
<!--ID: 1768155888416-->
END


START
Basic
[[ANN search#Hierarchical Navigable Small World Graph (HNSW)]]
- (Flat) Navigable Small World Graph (NSW): algorithm
- which improvement provides HNSW?
- how to insert a new node?
- how to retrieve top k elements?

Back: 
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

______


### ANN search
- **goal**: find vectors that are close enough to the true nearest neighbors, much faster than a full similarity scan 
- → trades accuracy for speed (configurable)
- organizes data in structured indexes such that it only needs to scan a fraction of the data
- there are multiple strategies to achieve that
- the **Facebook AI Similarity Search** library contains an implementation of most of them

![[Pasted image 20260111191931.png]]
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

___________

## vector stores
- store tuples of (embedding, data) and are optimized for searching embeddings that are most similar to a given query vector → **semantic search** at **scale** by operating on **geometry in high-dimensional space**

$$
\arg\min_i \cos\mathrm{sim}(q, d_i)
$$

- problem: since there are a lot of vectors stored, checking each would be $\mathcal{O}(N)$ which is too slow → **approximated k nearest neighbor search** using [[ANN search]] algorithms
- plays an important role in the [[retrieval augmented generation]] for finding the initial candidates

Tags: ml WS2526
<!--ID: 1768155888420-->
END

START
Basic
[[ANN search#Inverted File Index (IVF)]]
- concept
- what is it used for

[[ANN search#Quantization-Based Indexes (Quantized)]]
- concept
- what is it used for
- two versions
Back: 
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

______

### ANN search
- **goal**: find vectors that are close enough to the true nearest neighbors, much faster than a full similarity scan 
- → trades accuracy for speed (configurable)
- organizes data in structured indexes such that it only needs to scan a fraction of the data
- there are multiple strategies to achieve that
- the **Facebook AI Similarity Search** library contains an implementation of most of them

![[Pasted image 20260111191931.png]]
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



## vector stores
- store tuples of (embedding, data) and are optimized for searching embeddings that are most similar to a given query vector → **semantic search** at **scale** by operating on **geometry in high-dimensional space**

$$
\arg\min_i \cos\mathrm{sim}(q, d_i)
$$

- problem: since there are a lot of vectors stored, checking each would be $\mathcal{O}(N)$ which is too slow → **approximated k nearest neighbor search** using [[ANN search]] algorithms
- plays an important role in the [[retrieval augmented generation]] for finding the initial candidates

Tags: ml WS2526
<!--ID: 1768155888423-->
END
