# Operations between [[pd DataFrame]] and [[pd Series]]
![[pd DataFrame#example df]]
### aligning [[pd Series|series]] [[pd Index|index]] with [[pd DataFrame|dataframe]] [[pd Column|columns]] and broadcast over the [[pd Column|column]] [[pd Index|index]](default)

```python
pd_series = pd.Series({
	"col1": 1,
	"col2": 10,
})

pd_series * pd_df1

# col1 col2 col3 
# a 1.0 50.0 NaN 
# b 2.0 60.0 NaN 
# c 3.0 70.0 NaN 
# d 4.0 80.0 NaN
```