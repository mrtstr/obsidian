## Write the data 
- we use a [[pa RecordBatchFileWriter]] to write the [[pa Array]] as a single colimn [[pa RecordBatch]] to the [[pa LocalFileSystem]]
```python
BATCH_SIZE = 10000
NUM_BATCHES = 1000

schema = pa.schema([pa.field('nums', pa.int32())])

with pa.OSFile('bigfile.arrow', 'wb') as sink:
   with pa.ipc.new_file(sink, schema) as writer:
      for row in range(NUM_BATCHES):
            batch = pa.record_batch(
	            [
		            pa.array(range(BATCH_SIZE), 
		            type=pa.int32())
	            ], 
	            schema
            )
            writer.write(batch)
```

## non [[memory mapped data]] accsess

```python
with pa.OSFile('bigfile.arrow', 'rb') as source:
   loaded_array = pa.ipc.open_file(source).read_all()

print("LEN:", len(loaded_array))
LEN: 10000000

print("RSS: {}MB".format(pa.total_allocated_bytes() >> 20))
RSS: 38MB
```

## [[memory mapped data]] accsess
- create a [[pa Table]] with [[pa Buffer|pa Buffers]] that are on disc
	→ no memory is consumed
- convert it [[zero copy]] to a [[pl Dataframe]] cause [[polars]] uses [[pyarrow]] data structures 
```python
with pa.memory_map('bigfile.arrow', 'rb') as source:
   loaded_array = pa.ipc.open_file(source).read_all()

print("LEN:", len(loaded_array))
# LEN: 10000000

print("RSS: {}MB".format(pa.total_allocated_bytes() >> 20))
# RSS: 0MB

print(type(loaded_array))
# pyarrow.lib.Table

df = pl.from_arrow(loaded_array)
print("RSS: {}MB".format(pa.total_allocated_bytes() >> 20))
# RSS: 0MB
```

START
Basic
[[pyarrow]]
- write data to the disc and create a [[pa Table]] and [[pl Dataframe]] from it [[zero copy]] with no memory allocated
Back: 

## Write the data 
- we use a [[pa RecordBatchFileWriter]] to write the [[pa Array]] as a single colimn [[pa RecordBatch]] to the [[pa LocalFileSystem]]
```python
BATCH_SIZE = 10000
NUM_BATCHES = 1000

schema = pa.schema([pa.field('nums', pa.int32())])

with pa.OSFile('bigfile.arrow', 'wb') as sink:
   with pa.ipc.new_file(sink, schema) as writer:
      for row in range(NUM_BATCHES):
            batch = pa.record_batch(
	            [
		            pa.array(range(BATCH_SIZE), 
		            type=pa.int32())
	            ], 
	            schema
            )
            writer.write(batch)
```

## non [[memory mapped data]] accsess

```python
with pa.OSFile('bigfile.arrow', 'rb') as source:
   loaded_array = pa.ipc.open_file(source).read_all()

print("LEN:", len(loaded_array))
LEN: 10000000

print("RSS: {}MB".format(pa.total_allocated_bytes() >> 20))
RSS: 38MB
```

## [[memory mapped data]] accsess
- create a [[pa Table]] with [[pa Buffer|pa Buffers]] that are on disc
	→ no memory is consumed
- convert it [[zero copy]] to a [[pl Dataframe]] cause [[polars]] uses [[pyarrow]] data structures 
```python
with pa.memory_map('bigfile.arrow', 'rb') as source:
   loaded_array = pa.ipc.open_file(source).read_all()

print("LEN:", len(loaded_array))
# LEN: 10000000

print("RSS: {}MB".format(pa.total_allocated_bytes() >> 20))
# RSS: 0MB

print(type(loaded_array))
# pyarrow.lib.Table

df = pl.from_arrow(loaded_array)
print("RSS: {}MB".format(pa.total_allocated_bytes() >> 20))
# RSS: 0MB
```
Tags: code pyarrow
<!--ID: 1682842974594-->
END