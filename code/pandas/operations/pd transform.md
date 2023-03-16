- Takes a row or a column as a [[py interatable]]
- performs an operation and return an [[py interatable]] of the same length
- similar to [[pd apply]] but less powerfull because aggragation is not allowed (→ output same length as input)
- similar to [[pd applymap]] but more powerful because the column context can be concidered (like needed for [[np cumsum]])

# example
# anki

START
Basic
[[pd transform]]
- what does it do?
- Differnce to [[pd apply]]
- difference to [[pd applymap]]
Back: 
- Takes a row or a column as a [[py interatable]]
- performs an operation and return an [[py interatable]] of the same length
- similar to [[pd apply]] but less powerfull because aggragation is not allowed (→ output same length as input)
- similar to [[pd applymap]] but more powerful because the column context can be concidered (like needed for [[np cumsum]])
Tags: code, pandas
<!--ID: 1678974652758-->
END


START
Basic
| | class | order | max_speed | 
|:--------|:--------|:---------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | bird | Psittaciformes | 24 | 
| lion | mammal | Carnivora | 80.2 | 
| monkey | mammal | Primates | nan | 
| leopard | mammal | Carnivora | 58 |

```python
df.transform(np.cumsum)
df.apply(np.cumsum)
df.applymap(np.cumsum)
```

Back: 
```python
df.transform(np.cumsum) # works
df.apply(np.cumsum) # works
df.applymap(np.cumsum)
# does not work because applymap is only element wise
```
result:
| | class | order | max_speed | 
|:--------|:---------------------------|:------------------------------------------------------|------------:| 
| falcon | bird | Falconiformes | 389 | 
| parrot | birdbird | FalconiformesPsittaciformes | 413 | 
| lion | birdbirdmammal | FalconiformesPsittaciformesCarnivora | 493.2 | 
| monkey | birdbirdmammalmammal | FalconiformesPsittaciformesCarnivoraPrimates | nan | 
| leopard | birdbirdmammalmammalmammal | FalconiformesPsittaciformesCarnivoraPrimatesCarnivora | 551.2 |

Tags: code, pandas
<!--ID: 1678974652761-->
END