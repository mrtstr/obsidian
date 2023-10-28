# Operations between [[pd dataframe]] and [[pd series]]
![[pd dataframe#example df]]
### aligning [[pd series|series]] [[pd index|index]] with [[pd dataframe|dataframe]] [[pd column|columns]] and broadcast over the [[pd column|column]] [[pd index|index]](default)

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