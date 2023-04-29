- [[pyarrow]] [[pa Dataset|dataset]] tool for working with lager than memory data
- saving data paritioned on disc (e.g. as [[parquet]]) 
- can be loaded chunk wise
- [[pa Table]] like [[API]]

## example: creating a partitioned dataset

1) partition the data and save it on the disc
```python
import pyarrow.dataset as ds

ds.write_dataset( # create a
	data = df, # The data to write
	# This can be a Dataset instance or in-memory Arrow data
	base_dir = "savedir", 
	# The root directory where to write the dataset.
	format="parquet", # The format in which to write the dataset
	# {e.g. “parquet” or “csv”.}
	partitioning=["years"] # how to partition the dataframe
	# here: group by column "years"
)
```
2) load the [[pa Dataset]]
```python
dataset = ds.dataset(
	"savedir",
	format="parquet",
	partitioning=["years"]
)
```
## example: lazy load partitions one by one to memory
```python
current_year = datetime.datetime.utcnow().year
for table_chunk in dataset.to_batches():
	print("AGES", pc.subtract(current_year, table_chunk["years"]))

# AGES [ 33 ] 
# AGES [ 28, 28 ] 
# AGES [ 23, 23 ]
```
## example: convert chunks to [[pd dataframe]]
### chunk for chunk
```python
for table_chunk in dataset.to_batches():
	display(table_chunk.to_pandas())
```

| days | months | years | 
|-------:|---------:|--------:| 
| 1 | 1 | 1990 | 

| days | months | years | 
|-------:|---------:|--------:| 
| 17 | 5 | 1995 | 
| 28 | 1 | 1995 | 

| days | months | years | 
|-------:|---------:|--------:| 
| 12 | 3 | 2000 | 
| 23 | 7 | 2000 |

### complete dataset
```python
dataset.to_table().to_pandas()
```

| days | months | years | 
|-------:|---------:|--------:| 
| 1 | 1 | 1990 | 
| 17 | 5 | 1995 | 
| 28 | 1 | 1995 | 
| 12 | 3 | 2000 | 
| 23 | 7 | 2000 |


## example: convert [[pa Dataset]] to [[pl dataframe]]

### chunk for chunk
```python
for table_chunk in dataset.to_batches():
	print(pl.from_arrow(table_chunk))
```

| days | months | years | 
|-------:|---------:|--------:| 
| 1 | 1 | 1990 | 

| days | months | years | 
|-------:|---------:|--------:| 
| 17 | 5 | 1995 | 
| 28 | 1 | 1995 | 

| days | months | years | 
|-------:|---------:|--------:| 
| 12 | 3 | 2000 | 
| 23 | 7 | 2000 |

### complete dataset
```python
pl.from_arrow(list(dataset.to_batches()))
```

| days | months | years | 
|-------:|---------:|--------:| 
| 1 | 1 | 1990 | 
| 17 | 5 | 1995 | 
| 28 | 1 | 1995 | 
| 12 | 3 | 2000 | 
| 23 | 7 | 2000 |

# anki

START
Basic
[[pa Dataset]]
- concept (4)
Back: 
- [[pyarrow]] [[pa Dataset|dataset]] tool for working with lager than memory data
- saving data paritioned on disc (e.g. as [[parquet]]) 
- can be loaded chunk wise
- [[pa Table]] like [[API]]

Tags: code pyarrow
<!--ID: 1681116839430-->
END



START
Basic

- save the following table as a partitoned (by year) [[parquet]] file
- lazy load the chunks and calculate the age for each chunk

| days | months | years | 
|-------:|---------:|--------:| 
| 1 | 1 | 1990 | 
| 12 | 3 | 2000 | 
| 17 | 5 | 1995 | 
| 23 | 7 | 2000 | 
| 28 | 1 | 1995 |

Back: 
- [[pyarrow]] [[pa Dataset|dataset]] tool for working with lager than memory data
- saving data paritioned on disc (e.g. as [[parquet]]) 
- can be loaded chunk wise
- [[pa Table]] like [[API]]
### example
1) partition the data and save it on the disc
```python
import pyarrow.dataset as ds

ds.write_dataset( # create a
	data = df, # The data to write
	# This can be a Dataset instance or in-memory Arrow data
	base_dir = "savedir", 
	# The root directory where to write the dataset.
	format="parquet", # The format in which to write the dataset
	# {e.g. “parquet” or “csv”.}
	partitioning=["years"] # how to partition the dataframe
	# here: group by column "years"
)
```
2) load the [[pa Dataset]]
```python
dataset = ds.dataset(
	"savedir",
	format="parquet",
	partitioning=["years"]
)
```
3) lazy load partitions one by one to memory
```python
current_year = datetime.datetime.utcnow().year
for table_chunk in dataset.to_batches():
	print("AGES", pc.subtract(current_year, table_chunk["years"]))

# AGES [ 33 ] 
# AGES [ 28, 28 ] 
# AGES [ 23, 23 ]
```
Tags: code pyarrow
<!--ID: 1682756007910-->
END