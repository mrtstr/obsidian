- for [[serializing]] a sequenz of [[pa RecordBatch|RecordBatches]] of the same [[pa Schema]] to a byte [[stream]]
- can be used with all [[pa NativeFile|pyarrow stream formats]] 
- does not support [[random access]] 
	→ must be processed from start to end
- supports [[zero copy]] reads
- can be created with `pa.ipc.new_stream(sink, schema)` taking a [[pa NativeFile]] and a [[pa Schema]] as parameter
- can be read with `pa.ipc.open_stream(buffer)`

## example
- create a [[pa RecordBatch]]
- write the [[serializing|serialize]] it and write it 5 times to a [[pa Buffer]] using a `BufferOutputStream`
- close the stream and finalize the [[pa Buffer]]
```python
data = [
    pa.array([1, 2, 3, 4]),
    pa.array(['foo', 'bar', 'baz', None]),
    pa.array([True, None, False, True])
]

batch = pa.record_batch(data, names=['f0', 'f1', 'f2'])

sink = pa.BufferOutputStream()
with pa.ipc.new_stream(sink, batch.schema) as writer:
   for _ in range(5):
      writer.write_batch(batch)

buf = sink.getvalue()
```
- read ([[serializing|deserialize]]) the [[pa RecordBatch|RecordBatches]]
```python
with pa.ipc.open_stream(buf) as reader:
  print(reader.schema)
	# f0: int64
	# f1: string
	# f2: bool
  batches = [b for b in reader]
```

## difference to [[pa RecordBatchFileWriter]]
- [[pa RecordBatchStreamWriter]] does not support [[random access]]
- [[pa RecordBatchFileWriter]] does support [[random access]]
	- source must have a `seek` method

# anki

START
Basic
[[pa RecordBatchStreamWriter]]
- concept (6)

Back: 
- for [[serializing]] a sequenz of [[pa RecordBatch|RecordBatches]] of the same [[pa Schema]] to a byte [[stream]]
- can be used with all [[pa NativeFile|pyarrow stream formats]] 
- does not support [[random access]] 
	→ must be processed from start to end
- supports [[zero copy]] reads
- can be created with `pa.ipc.new_stream(sink, schema)` taking a [[pa NativeFile]] and a [[pa Schema]] as parameter
- can be read with `pa.ipc.open_stream(buffer)`


## example
- create a [[pa RecordBatch]]
- write the [[serializing|serialize]] it and write it 5 times to a [[pa Buffer]] using a `BufferOutputStream`
- close the stream and finalize the [[pa Buffer]]
```python
data = [
    pa.array([1, 2, 3, 4]),
    pa.array(['foo', 'bar', 'baz', None]),
    pa.array([True, None, False, True])
]

batch = pa.record_batch(data, names=['f0', 'f1', 'f2'])

sink = pa.BufferOutputStream()
with pa.ipc.new_stream(sink, batch.schema) as writer:
   for _ in range(5):
      writer.write_batch(batch)

buf = sink.getvalue()
```
- read ([[serializing|deserialize]]) the [[pa RecordBatch|RecordBatches]]
```python
with pa.ipc.open_stream(buf) as reader:
  print(reader.schema)
	# f0: int64
	# f1: string
	# f2: bool
  batches = [b for b in reader]
```

Tags: code pyarrow
<!--ID: 1682842974586-->
END


START
Basic
[[pa RecordBatchStreamWriter]] example
- create a [[pa RecordBatch]]
- write the [[serializing|serialize]] it and write it 5 times to a [[pa Buffer]] 
- reamemory mapped datad ([[serializing|deserialize]]) the [[pa RecordBatch|RecordBatches]]

Back: 
- for [[serializing]] a sequenz of [[pa RecordBatch|RecordBatches]] of the same [[pa Schema]] to a byte [[stream]]
- can be used with all [[pa NativeFile|pyarrow stream formats]] 
- does not support [[random access]] 
	→ must be processed from start to end
- supports [[zero copy]] reads
- can be created with `pa.ipc.new_stream(sink, schema)` taking a [[pa NativeFile]] and a [[pa Schema]] as parameter
- can be read with `pa.ipc.open_stream(buffer)`


## example
- create a [[pa RecordBatch]]
- write the [[serializing|serialize]] it and write it 5 times to a [[pa Buffer]] using a `BufferOutputStream`
- close the stream and finalize the [[pa Buffer]]
```python
data = [
    pa.array([1, 2, 3, 4]),
    pa.array(['foo', 'bar', 'baz', None]),
    pa.array([True, None, False, True])
]

batch = pa.record_batch(data, names=['f0', 'f1', 'f2'])

sink = pa.BufferOutputStream()
with pa.ipc.new_stream(sink, batch.schema) as writer:
   for _ in range(5):
      writer.write_batch(batch)

buf = sink.getvalue()
```
- read ([[serializing|deserialize]]) the [[pa RecordBatch|RecordBatches]]
```python
with pa.ipc.open_stream(buf) as reader:
  print(reader.schema)
	# f0: int64
	# f1: string
	# f2: bool
  batches = [b for b in reader]
```

Tags: code pyarrow
<!--ID: 1682842974591-->
END