- [[pa NativeFile]] is the base class for all [[pyarrow]] [[stream|streams]]
- used for writing bytes to the memory ([[pa Buffer]]) or on dict ([[pa filesystem]])
- can be readable, writeable or both
- can support random access or not

## extensions
- `OSFile`
	- a native file that uses your operating system’s file descriptors
- `MemoryMappedFile`
	- for reading ([[zero copy]]) and writing with memory maps
- `BufferReader`
	- for reading [[pa Buffer]] objects as a file
- `BufferOutputStream`
	- for writing data in-memory, producing a [[pa Buffer]] at the end
- `FixedSizeBufferWriter` 
	- for writing data into an already allocated Buffer
- `HdfsFile`
	- for reading and writing data to the [[HDFS]]
-  `PythonFile`
	- for interfacing with [[python]] file objects in C++

## high level [[API]]
### `pa.input_stream(source, buffer_size)`
- takes a memory location ([[pa Buffer]]) or a[[file system]] path and returns the fitteing extenson of [[pa NativeFile]] for reading from the location
```python
with pa.input_stream(source=empty_buffer) as reader:
	byte_string = reader.read()
```

### `pa.output_stream(source, buffer_size)`
- takes a memory location ([[pa Buffer]]) or a [[file system]] path and returns the fitteing extenson of [[pa NativeFile]] for writing to the location
```python
with pa.output_stream(source=empty_buffer) as writer:
	writer.write(b'halllllllo')
```

# examples

## create a emply [[pa Buffer]], write a [[py string]] to it and read it again
- the following code snippets are equivalent because `output_stream` will return `FixedSizeBufferWriter` and `input_stream` will return a `BufferReader` when given a buffer

### high level [[API]]
```python
empty_buffer = pa.allocate_buffer(25)
with pa.output_stream(source=empty_buffer) as writer:
	writer.write(b'halllllllo')

with pa.input_stream(source=empty_buffer) as reader:
	byte_string = reader.read()

byte_string
# b'halllllllo\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'
```

### low level [[API]]
```python
empty_buffer = pa.allocate_buffer(25)

with pa.FixedSizeBufferWriter(source=empty_buffer) as writer:
	writer.write(b'halllllllo')

with pa.BufferReader(empty_buffer) as reader:
	byte_string = reader.read()

byte_string
# b'halllllllo\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'
```

## wirte to the local [[file system]]
### low level [[API]]
- `pa.OSFile` can be used like the buildin [[python]] [[py read and write]] [[API]]
```python
with pa.OSFile('example3.dat', 'wb') as f:
    f.write(b'some example data')
```
### high level [[API]]
- `pa.output_stream` will return `pa.OSFile` when given a local [[pa filesystem]] pathpa.OSFile
```python
with pa.output_stream('example4.dat') as f:
    f.write(b'some example data')
```

# anki
START
Basic
[[pyarrow]] [[pa NativeFile|streams]]
- concept
- properties (2)
- types/extensions (7)
- high level api
Back: 
- [[pa NativeFile]] is the base class for all [[pyarrow]] [[stream|streams]]
- used for writing bytes to the memory ([[pa Buffer]]) or on dict ([[pa filesystem]])
- can be readable, writeable or both
- can support random access or not

## extensions
- `OSFile`
	- a native file that uses your operating system’s file descriptors
- `MemoryMappedFile`
	- for reading ([[zero copy]]) and writing with memory maps
- `BufferReader`
	- for reading [[pa Buffer]] objects as a file
- `BufferOutputStream`
	- for writing data in-memory, producing a [[pa Buffer]] at the end
- `FixedSizeBufferWriter` 
	- for writing data into an already allocated Buffer
- `HdfsFile`
	- for reading and writing data to the [[HDFS]]
-  `PythonFile`
	- for interfacing with [[python]] file objects in C++

## high level [[API]]
### `pa.input_stream(source, buffer_size)`
- takes a memory location ([[pa Buffer]]) or a[[file system]] path and returns the fitteing extenson of [[pa NativeFile]] for reading from the location
```python
with pa.input_stream(source=empty_buffer) as reader:
	byte_string = reader.read()
```

### `pa.output_stream(source, buffer_size)`
- takes a memory location ([[pa Buffer]]) or a [[file system]] path and returns the fitteing extenson of [[pa NativeFile]] for writing to the location
```python
with pa.output_stream(source=empty_buffer) as writer:
	writer.write(b'halllllllo')
```

Tags: code pyarrow
<!--ID: 1682248340842-->
END

START
Basic
[[pyarrow]] [[pa NativeFile|streams]] examples
- create an emply [[pa Buffer]], write a [[py string]] to it and read it again
	- using the high and low level [[API]]

Back: 

- the following code snippets are equivalent because `output_stream` will return `FixedSizeBufferWriter` and `input_stream` will return a `BufferReader` when given a buffer

### high level [[API]]
```python
empty_buffer = pa.allocate_buffer(25)
with pa.output_stream(source=empty_buffer) as writer:
	writer.write(b'halllllllo')

with pa.input_stream(source=empty_buffer) as reader:
	byte_string = reader.read()

byte_string
# b'halllllllo\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'
```

### low level [[API]]
```python
empty_buffer = pa.allocate_buffer(25)

with pa.FixedSizeBufferWriter(source=empty_buffer) as writer:
	writer.write(b'halllllllo')

with pa.BufferReader(empty_buffer) as reader:
	byte_string = reader.read()

byte_string
# b'halllllllo\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'
```
Tags: code pyarrow
<!--ID: 1682248340845-->
END



START
Basic
[[pyarrow]] [[pa NativeFile|streams]] examples
- wirte a [[py string]] to the local [[file system]]
	- using the high and low level [[API]]

Back: 

## wirte to the local [[file system]]
### low level [[API]]
- `pa.OSFile` can be used like the buildin [[python]] [[py read and write]] [[API]]
```python
with pa.OSFile('example3.dat', 'wb') as f:
    f.write(b'some example data')
```
### high level [[API]]
- `pa.output_stream` will return `pa.OSFile` when given a local [[pa filesystem]] pathpa.OSFile
```python
with pa.output_stream('example4.dat') as f:
    f.write(b'some example data')
```

Tags: code pyarrow
<!--ID: 1682248340848-->
END