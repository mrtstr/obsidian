- Similar to [[pd apply]] but can performe multiple functions at once 
- performed operations on [[pd DataFrame]] or a [[pd DataFrameGroupBy]] objects 
- functions take a [[pd Series]] and return a single value

```python
df.agg(
   func=None, 
   axis=0,
)
```
# example
```python
df = pd.DataFrame(
	[
		("bird", "Falconiformes", 389.0),
		("bird", "Psittaciformes", 24.0),
		("mammal", "Carnivora", 80.2),
		("mammal", "Primates", np.nan),
		("mammal", "Carnivora", 58),
	],
	index=["falcon", "parrot", "lion", "monkey", "leopard"],
	columns=("class", "order", "max_speed"),
)
```
| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |


# anki

START
Basic

Back: 

Tags: code, pandas
END