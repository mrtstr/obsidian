- [[pyarrow]] [[pa Dataset|dataset]] tool for working with lager than memory data
- saving data paritioned on disc (e.g. as [[parquet]]) 
- inspect and select/filter data before loading to memory as [[pa Table]] or a iterator over [[pa RecordBatch|pa RecordBatches]] in case of large data

## example: creating a partitioned dataset

1) partition the data and save it on the disc
```python
pyarrow.dataset.write_dataset( # create a
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
dataset = pyarrow.dataset.dataset(
	"savedir",
	format="parquet",
	partitioning=["years"]
)
```

## load data chunk for chunk
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

## load complete dataset
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

## filter dataset before loading
```python
dataset.filter(
   pa.dataset.field("months") == 1
).to_table()
```

| | days | months | years |
|---:|-------:|---------:|--------:|
| 0 | 1 | 1 | 1990 |
| 1 | 28 | 1 | 1995 |


## renaming columns and manupulating data before loading
```python
projection = {
	"days_renamed": ds.field("days").cast("float32"),
	"months_is_one": ds.field("months")==1,
	"years_named": ds.field("years"),
}

dataset.to_table(columns=projection)
```

| days_renamed | months_is_one | years_named |
|---------------:|:----------------|--------------:|
| 1 | True | 1990 |
| 17 | False | 1995 |
| 28 | True | 1995 |
| 12 | False | 2000 |
| 23 | False | 2000 |

# anki

START
Basic
[[pa Dataset]]
- concept (3)
Back: 
- [[pyarrow]] [[pa Dataset|dataset]] tool for working with lager than memory data
- saving data paritioned on disc (e.g. as [[parquet]]) 
- inspect and select/filter data before loading to memory as [[pa Table]] or a iterator over [[pa RecordBatch|pa RecordBatches]] in case of large data

Tags: code pyarrow
<!--ID: 1681116839430-->
END



START
Basic
create a [[pa Dataset]] from the following table partitoned (by year)

| days | months | years | 
|-------:|---------:|--------:| 
| 1 | 1 | 1990 | 
| 12 | 3 | 2000 | 
| 17 | 5 | 1995 | 
| 23 | 7 | 2000 | 
| 28 | 1 | 1995 |

Back: 
### [[pa Dataset]]
- [[pyarrow]] [[pa Dataset|dataset]] tool for working with lager than memory data
- saving data paritioned on disc (e.g. as [[parquet]]) 
- inspect and select/filter data before loading to memory as [[pa Table]] or a iterator over [[pa RecordBatch|pa RecordBatches]] in case of large data
### example
1) partition the data and save it on the disc
```python
pyarrow.dataset.write_dataset( # create a
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
dataset = pyarrow.dataset.dataset(
	"savedir",
	format="parquet",
	partitioning=["years"]
)
```

Tags: code pyarrow
<!--ID: 1682756007910-->
END



START
Basic
given the following [[pa Dataset]] 

| days | months | years | 
|-------:|---------:|--------:| 
| 1 | 1 | 1990 | 
| 12 | 3 | 2000 | 
| 17 | 5 | 1995 | 
| 23 | 7 | 2000 | 
| 28 | 1 | 1995 |


```python
pyarrow.dataset.write_dataset( # create a
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

```python
dataset = pyarrow.dataset.dataset(
	"savedir",
	format="parquet",
	partitioning=["years"]
)
```

1)  load data chunk for chunk
2) load complete dataset
3) filter dataset before loading (month has to be 1)

Back: 
## load data chunk for chunk
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

## load complete dataset
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

## filter dataset before loading
```python
dataset.filter(
   pa.dataset.field("months") == 1
).to_table()
```

| | days | months | years |
|---:|-------:|---------:|--------:|
| 0 | 1 | 1 | 1990 |
| 1 | 28 | 1 | 1995 |

Tags: code pyarrow
<!--ID: 1682842974600-->
END


START
Basic
given the following [[pa Dataset]] 

| days | months | years | 
|-------:|---------:|--------:| 
| 1 | 1 | 1990 | 
| 12 | 3 | 2000 | 
| 17 | 5 | 1995 | 
| 23 | 7 | 2000 | 
| 28 | 1 | 1995 |


```python
pyarrow.dataset.write_dataset( # create a
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

```python
dataset = pyarrow.dataset.dataset(
	"savedir",
	format="parquet",
	partitioning=["years"]
)
```

manupulate the data before loading it
- raname the column `days` to `days_renamed` and cast it to float
- select a column named `months_is_one` that is true when month is one and else false
- select the column `years` renamed to `years_named`

Back: 
```python
projection = {
	"days_renamed": ds.field("days").cast("float32"),
	"months_is_one": ds.field("months")==1,
	"years_named": ds.field("years"),
}

dataset.to_table(columns=projection)
```

| days_renamed | months_is_one | years_named |
|---------------:|:----------------|--------------:|
| 1 | True | 1990 |
| 17 | False | 1995 |
| 28 | True | 1995 |
| 12 | False | 2000 |
| 23 | False | 2000 |

Tags: code pyarrow
<!--ID: 1682842974603-->
END