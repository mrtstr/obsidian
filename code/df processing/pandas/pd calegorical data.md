memory efficient saving of high [[cardinality]] categorical data in [[pandas]] [[pd dataframe]]

```python
pd_df1 = pd.DataFrame(
	{
		"col1": {"a": 1, "b":2, "c":3, "d":4},
		"col2": {"a": 5, "b":6, "c":7, "d":8},
		"col3": {"a": 9, "b":10, "c":11, "d":12},
	}
)
pd_df1["col4"] = list("AABB")
pd_df1["col5"] = list("CDCD")

df = pd.concat([pd_df1, pd_df1, pd_df1])
display(df)

#col1 col2 col3 col4 col5 
#a 1 5 9 A C b 
#2 6 10 A D 
#c 3 7 11 B C 
#d 4 8 12 B D 
#a 1 5 9 A C 
#b 2 6 10 A D 
#c 3 7 11 B C 
#d 4 8 12 B D 
#a 1 5 9 A C 
#b 2 6 10 A D 
#c 3 7 11 B C 
#d 4 8 12 B D 
print(df.memory_usage(deep=True))
#Index 696 
#col1 96 
#col2 96 
#col3 96 
#col4 696 
#col5 696 
df = df.astype({"col4": "category", "col5": "category"})
print(df.memory_usage(deep=True))

#Index 696 
#col1 96 
#col2 96 
#col3 96 
#col4 236 
#col5 236 
```

# anki

START
Basic
pandas: how to save categorical data efficient (with example)
Back: 
memory efficient saving of high [[cardinality]] categorical data in [[pandas]] [[pd dataframe]]

```python
pd_df1 = pd.DataFrame(
	{
		"col1": {"a": 1, "b":2, "c":3, "d":4},
		"col2": {"a": 5, "b":6, "c":7, "d":8},
		"col3": {"a": 9, "b":10, "c":11, "d":12},
	}
)
pd_df1["col4"] = list("AABB")
pd_df1["col5"] = list("CDCD")

df = pd.concat([pd_df1, pd_df1, pd_df1])
display(df)

#col1 col2 col3 col4 col5 
#a 1 5 9 A C b 
#2 6 10 A D 
#c 3 7 11 B C 
#d 4 8 12 B D 
#a 1 5 9 A C 
#b 2 6 10 A D 
#c 3 7 11 B C 
#d 4 8 12 B D 
#a 1 5 9 A C 
#b 2 6 10 A D 
#c 3 7 11 B C 
#d 4 8 12 B D 
print(df.memory_usage(deep=True))
#Index 696 
#col1 96 
#col2 96 
#col3 96 
#col4 696 
#col5 696 
df = df.astype({"col4": "category", "col5": "category"})
print(df.memory_usage(deep=True))

#Index 696 
#col1 96 
#col2 96 
#col3 96 
#col4 236 
#col5 236 
```
Tags: code, pandas
<!--ID: 1668090818845-->
END