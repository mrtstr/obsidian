Indexing on [[pd DataFrame]] with [[pd MultiIndex]]

![[pd MultiIndex#example multiindex df]]
- [[pd MultiIndex]] as accessed using [[py tuple]] and slices
- or using a [[pandas|pd]].IndexSlice
```python
idx = pd.IndexSlice
mi_df.loc[idx[:, :], "A"]
mi_df.loc[(slice(None), slice(None)), "A"]  # complete dimensions

# 2 blue 0.940415 
# 1 blue 0.437798 
# 2 red 0.154805 
# 1 red 0.888439
mi_df.loc[idx[:, "blue"], "A"]
mi_df.loc[(slice(None), "blue"), "A"]  # filter only by the second level of the index
# 2 blue 0.940415 
# 1 blue 0.437798
mi_df.loc[idx[2, :], "A"]
mi_df.loc[(2, slice(None)), "A"]  # filter only by the first level of the index
# 2 blue 0.940415 
# 2 red 0.154805
```


# Anki

START
Basic
[[pandas]] [[pd MultiIndex]]: how to select data? (2)
Back: 
- [[pd MultiIndex]] as accessed using [[py tuple]] and slices
- or using a [[pandas|pd]].IndexSlice
```python
idx = pd.IndexSlice
mi_df.loc[idx[:, :], "A"]
mi_df.loc[(slice(None), slice(None)), "A"]  # complete dimensions

# 2 blue 0.940415 
# 1 blue 0.437798 
# 2 red 0.154805 
# 1 red 0.888439
mi_df.loc[idx[:, "blue"], "A"]
mi_df.loc[(slice(None), "blue"), "A"]  # filter only by the second level of the index
# 2 blue 0.940415 
# 1 blue 0.437798
mi_df.loc[idx[2, :], "A"]
mi_df.loc[(2, slice(None)), "A"]  # filter only by the first level of the index
# 2 blue 0.940415 
# 2 red 0.154805
```

Tags: code, pandas
<!--ID: 1668090818831-->
END