- simple character based [[language model]] with a context of 1
- bad results because the context of one is not sufficient

### process
1) create tuples of characters with their follwoing chracter
2) calculate a $n \times n$ [[matrix]] containing the [[conditional probability]] $A = \left(P(c_{n+1} = char_i \: | \: c_{n} = char_j)\right)_{i \in \mathcal{I}, j \in \mathcal{J}}$ by counting the cases it occures
3) sample from the distributions

# anki

START
Basic
bigram
- what is it?
- how does it work

Back: 

- simple character based [[language model]] with a context of 1
- bad results because the context of one is not sufficient

process
1) create tuples of characters with their follwoing chracter
2) calculate a $n \times n$ [[matrix]] containing the [[conditional probability]] $A = \left(P(c_{n+1} = char_i \: | \: c_{n} = char_j)\right)_{i \in \mathcal{I}, j \in \mathcal{J}}$ by counting the cases it occures
3) sample from the distributions
Tags: ml

END