- for [[serializing]] fixed number of [[pa RecordBatch|RecordBatches]] of the same [[pa Schema]] to a byte [[stream]]
- can be used with all [[pa NativeFile|pyarrow stream formats]] 
- supports [[random access]] and [[zero copy]] reads
- can be created with `pa.ipc.new_file(sink, schema)` taking a [[pa NativeFile]] and a [[pa Schema]] as parameter
- can be read with `pa.ipc.open_file(buffer)`

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
with pa.ipc.new_file(sink, batch.schema) as writer:
   for _ in range(5):
      writer.write_batch(batch)

buf = sink.getvalue()
```

- find out the number of [[pa RecordBatch|RecordBatches]] 
- [[random access]] read ([[serializing|deserialize]]) the third [[pa RecordBatch]]
```python
with pa.ipc.open_file(buf) as reader:
   num_record_batches = reader.num_record_batches
b = reader.get_batch(3)
```

## difference to [[pa RecordBatchStreamWriter]]
- [[pa RecordBatchStreamWriter]] does not support [[random access]]
- [[pa RecordBatchFileWriter]] does support [[random access]]
	- source must have a `seek` method


# anki

START
Basic
[[pa RecordBatchFileWriter]]
- concept (5)
- difference to [[pa RecordBatchStreamWriter]]

Back: 
- for [[serializing]] fixed number of [[pa RecordBatch|RecordBatches]] of the same [[pa Schema]] to a byte [[stream]]
- can be used with all [[pa NativeFile|pyarrow stream formats]] 
- supports [[random access]] and [[zero copy]] reads
- can be created with `pa.ipc.new_file(sink, schema)` taking a [[pa NativeFile]] and a [[pa Schema]] as parameter
- can be read with `pa.ipc.open_file(buffer)`

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
with pa.ipc.new_file(sink, batch.schema) as writer:
   for _ in range(5):
      writer.write_batch(batch)

buf = sink.getvalue()
```

- find out the number of [[pa RecordBatch|RecordBatches]] 
- [[random access]] read ([[serializing|deserialize]]) the third [[pa RecordBatch]]
```python
with pa.ipc.open_file(buf) as reader:
   num_record_batches = reader.num_record_batches
b = reader.get_batch(3)
```

## difference to [[pa RecordBatchStreamWriter]]
- [[pa RecordBatchStreamWriter]] does not support [[random access]]
- [[pa RecordBatchFileWriter]] does support [[random access]]
	- source must have a `seek` method

Tags: code pyarrow
<!--ID: 1682842974576-->
END


START
Basic
[[pa RecordBatchFileWriter]] example
- create a [[pa RecordBatch]]
- write the [[serializing|serialize]] it and write it 5 times to a [[pa Buffer]]

- find out the number of [[pa RecordBatch|RecordBatches]] 
- [[random access]] read ([[serializing|deserialize]]) the third [[pa RecordBatch]]

Back: 
- for [[serializing]] fixed number of [[pa RecordBatch|RecordBatches]] of the same [[pa Schema]] to a byte [[stream]]
- can be used with all [[pa NativeFile|pyarrow stream formats]] 
- supports [[random access]] and [[zero copy]] reads
- can be created with `pa.ipc.new_file(sink, schema)` taking a [[pa NativeFile]] and a [[pa Schema]] as parameter
- can be read with `pa.ipc.open_file(buffer)`

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
with pa.ipc.new_file(sink, batch.schema) as writer:
   for _ in range(5):
      writer.write_batch(batch)

buf = sink.getvalue()
```

- find out the number of [[pa RecordBatch|RecordBatches]] 
- [[random access]] read ([[serializing|deserialize]]) the third [[pa RecordBatch]]
```python
with pa.ipc.open_file(buf) as reader:
   num_record_batches = reader.num_record_batches
b = reader.get_batch(3)
```


Tags: code pyarrow
<!--ID: 1682842974582-->
END