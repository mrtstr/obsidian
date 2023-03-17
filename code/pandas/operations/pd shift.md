
START
Basic
- create a now column containing the values of [[pd Column]] `A` but shifted forward by 2 with 0 insted of [[pd NaN]]
- create a now column containing the values of [[pd Column]] `A` but shifted forward by 2 circular
| | A | B | 
|---:|----:|----:| 
| 0 | 0 | 6 | 
| 1 | 1 | 7 | 
| 2 | 2 | 8 | 
| 3 | 3 | 9 | 
| 4 | 4 | 10 | 
| 5 | 5 | 11 |

Back: 

```python
(
	df
	.assign(A_shifted = df["A"].shift(2, fill_value=0))
	.assign(A_shifted_circular = np.roll(df["A"], 2))
)

```

| | A | B | A_shifted | A_shifted_circular | 
|---:|----:|----:|------------:|---------------------:| 
| 0 | 0 | 6 | 0 | 4 | 
| 1 | 1 | 7 | 0 | 5 | 
| 2 | 2 | 8 | 0 | 0 | 
| 3 | 3 | 9 | 1 | 1 | 
| 4 | 4 | 10 | 2 | 2 | 
| 5 | 5 | 11 | 3 | 3 |

Tags: code, pandas
<!--ID: 1679071317487-->
END