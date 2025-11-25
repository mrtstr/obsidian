
### in context learning
- ability of LLMs to **learn tasks from examples provided in the prompt** without updating the weight
- emerges naturally from large-scale training on the next-token prediction objective because the model was trained on billions of fragments containing:
	• examples → solution
	• question → answer
	• pattern → continuation
#### algorithmic ICL
- algorithm-like behaviors: copying, sorting, repeating patterns, matching prefixes
- example: prompt: **A B C ... A B ?** → prediction: **C**
#### semantic ICL
- The model leverages its latent world knowledge and aligns it with the examples inside the prompt
	→ deduces what the user wants based on patterns in the examples
- example: 
	- prompt: **cat → German: Katze, English: dog → German: ?**  
	- prediction: **Hund**

#### limitations
- no reliable instruction following and very sensitive to formatting
- no guarantees of correctness, safety, preference alignment, consistency
	→ model may ignore instructions


### what LLMs do
- the model is not following instructions, it just continues the input with the statistically most likely tokens
#### instructions

**input:** translate Blume from German to English
**output:** translate blume into english. translate blume from German to English online

- the model is not following the instructions, but it gives the following because its often following in dictionary websites
	- dictionary-style elaborations
	- repeated restatements
	- related German compound words

#### patterns

**input**
	Translate the following German words into English.
	Use exactly this format: German -> English
	Do not add explanations.
	Milch -> milk
	Butter -> butter
	Fenster -> window
	Blume ->
**output**: 
	flower

**input**
	Convert the information into JSON.
	Example:
	Input: name=Alice, age=10, city=Berlin
	Output: {"name": "Alice", "age": 10, "city": "Berlin"}
	Input: name=Bob, age=25, city=Munich
	Output: {"name": "Bob", "age": 25, "city": "Munich"}
	Input: name=Clara, age=32, city=Hamburg
	Output:
**output**: 
	{"name": "Clara", "age": 32, "city": "Hamburg"}


- the model continues the pattern becauseit'ss the most likely continuation based on the training data

# anki

START
Basic
What do LLMs do when they retrieve instructions?
- give a few examples
Back: 
### what LLMs do
- the model is not following instructions, it just continues the input with the statistically most likely tokens
#### instructions

**input:** translate Blume from German to English
**output:** translate blume into english. translate blume from German to English online

- the model is not following the instructions, but it gives the following because its often following in dictionary websites
	- dictionary-style elaborations
	- repeated restatements
	- related German compound words

#### patterns

**input**
	Translate the following German words into English.
	Use exactly this format: German -> English
	Do not add explanations.
	Milch -> milk
	Butter -> butter
	Fenster -> window
	Blume ->
**output**: 
	flower

**input**
	Convert the information into JSON.
	Example:
	Input: name=Alice, age=10, city=Berlin
	Output: {"name": "Alice", "age": 10, "city": "Berlin"}
	Input: name=Bob, age=25, city=Munich
	Output: {"name": "Bob", "age": 25, "city": "Munich"}
	Input: name=Clara, age=32, city=Hamburg
	Output:
**output**: 
	{"name": "Clara", "age": 32, "city": "Hamburg"}


- the model continues the pattern becauseit'ss the most likely continuation based on the training data

_____________

### in context learning
- ability of LLMs to **learn tasks from examples provided in the prompt** without updating the weight
- emerges naturally from large-scale training on the next-token prediction objective because the model was trained on billions of fragments containing:
	• examples → solution
	• question → answer
	• pattern → continuation
#### algorithmic ICL
- algorithm-like behaviors: copying, sorting, repeating patterns, matching prefixes
- example: prompt: **A B C ... A B ?** → prediction: **C**
#### semantic ICL
- The model leverages its latent world knowledge and aligns it with the examples inside the prompt
	→ deduces what the user wants based on patterns in the examples
- example: 
	- prompt: **cat → German: Katze, English: dog → German: ?**  
	- prediction: **Hund**

#### limitations
- no reliable instruction following and very sensitive to formatting
- no guarantees of correctness, safety, preference alignment, consistency
	→ model may ignore instructions


Tags: ml WS2526
<!--ID: 1764080803396-->
END



START
Basic
[[nn in context learning]]
- concept
- why does it happen?
- two types of ICL
- limitations (2)
Back: 

### in context learning
- ability of LLMs to **learn tasks from examples provided in the prompt** without updating the weight
- emerges naturally from large-scale training on the next-token prediction objective because the model was trained on billions of fragments containing:
	• examples → solution
	• question → answer
	• pattern → continuation
#### algorithmic ICL
- algorithm-like behaviors: copying, sorting, repeating patterns, matching prefixes
- example: prompt: **A B C ... A B ?** → prediction: **C**
#### semantic ICL
- The model leverages its latent world knowledge and aligns it with the examples inside the prompt
	→ deduces what the user wants based on patterns in the examples
- example: 
	- prompt: **cat → German: Katze, English: dog → German: ?**  
	- prediction: **Hund**

#### limitations
- no reliable instruction following and very sensitive to formatting
- no guarantees of correctness, safety, preference alignment, consistency
	→ model may ignore instructions

___________


### what LLMs do
- the model is not following instructions, it just continues the input with the statistically most likely tokens
#### instructions

**input:** translate Blume from German to English
**output:** translate blume into english. translate blume from German to English online

- the model is not following the instructions, but it gives the following because its often following in dictionary websites
	- dictionary-style elaborations
	- repeated restatements
	- related German compound words

#### patterns

**input**
	Translate the following German words into English.
	Use exactly this format: German -> English
	Do not add explanations.
	Milch -> milk
	Butter -> butter
	Fenster -> window
	Blume ->
**output**: 
	flower

**input**
	Convert the information into JSON.
	Example:
	Input: name=Alice, age=10, city=Berlin
	Output: {"name": "Alice", "age": 10, "city": "Berlin"}
	Input: name=Bob, age=25, city=Munich
	Output: {"name": "Bob", "age": 25, "city": "Munich"}
	Input: name=Clara, age=32, city=Hamburg
	Output:
**output**: 
	{"name": "Clara", "age": 32, "city": "Hamburg"}


- the model continues the pattern becauseit'ss the most likely continuation based on the training data



Tags: ml WS2526
<!--ID: 1764080803400-->
END