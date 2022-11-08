# creating/inserting Columns
- can be created and removed like in a [[py dict]] 
- can be inserted using [[pd dataframe|DataFrame]].insert() using dot chaining and specifying the position
- can be inserted using [[pd dataframe|DataFrame]].assign() which created a copy and lates the orifinal [[pd dataframe]] unchanged
```python
# create new column
df["three"] = df["one"] * df["two"]

# create new column with dot chaining and specifed position
df.insert(loc=0, value=df["one"] * df["two"], column="three")

# create a copy of the orininal dataframe with a new column insered
df.assign(three=lambda x: (df["one"] * df["two"]))
```

# deleting/removing columns
```python
# delete column
del df["two"]

# delete multiple columns
pd_df1.drop(["one", "two"], axis=1)
```

# Anki
START
Basic
pandas
- creating/inserting column (3)
- deleting/removing columns (2)
Back: 
# creating/inserting Columns
- can be created and removed like in a [[py dict]] 
- can be inserted using [[pd dataframe|DataFrame]].insert() using dot chaining and specifying the position
- can be inserted using [[pd dataframe|DataFrame]].assign() which created a copy and lates the orifinal [[pd dataframe]] unchanged
```python
# create new column
df["three"] = df["one"] * df["two"]

# create new column with dot chaining and specifed position
df.insert(loc=0, value=df["one"] * df["two"], column="three")

# create a copy of the orininal dataframe with a new column insered
df.assign(three=lambda x: (df["one"] * df["two"]))
```

# deleting/removing columns
```python
# delete column
del df["two"]

# delete multiple columns
pd_df1.drop(["one", "two"], axis=1)
```
Tags: code, pandas
<!--ID: 1667921722418-->
END