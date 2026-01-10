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

![[Pasted image 20260110165421.png]]
#### BERT
- [[nn encoder decoder transformers|encoder]] [[LLM]] that generates contextual token level representations of the input
- uses bidirectional [[nn self attention layer|self attention]] (no masking)


# anki

START
Basic
[[nn sentence BERT]]
- concept and difference to normal BERT
- what it it used for?
- how is it trained?

Back: 
### sentence BERT
- build on top of **BERT** and is [[nn supervised fine tuning|fine tuned]] on sentence pair similarity
- enables semantic search, clustering and [[nn retrieval augmented generation]]
- the final output (=sentence representation) is created by applying pooling on the tokens
	- **mean pooling**: taking the mean over the token embeddings
	- **max pooling**: taking the element wise maximum over the token embeddings

### training procedure
- start with a [[nn pretraining]] BERT model
- create a training set with sentence pairs with the known similarity score
- during the training pass both sentences of the tuples during the same BERT model and calculate the [[cosine]] similarity
- training with the known similarity labels

![[Pasted image 20260110170002.png]]
#### BERT
- [[nn encoder decoder transformers|encoder]] [[LLM]] that generates contextual token level representations of the input
- uses bidirectional [[nn self attention layer|self attention]] (no masking)



Tags: ml WS2526
<!--ID: 1768062256217-->
END
