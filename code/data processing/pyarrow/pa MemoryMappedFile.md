- based on [[pyarrow]] [[stream]] [[pa NativeFile]] 
- for working with files ([[zero copy]]) memory mapped from disc

# example 
```python
with pa.OSFile('example3.dat', 'wb') as f:
	f.write(b'some example data')
mmap = pa.memory_map('example3.dat')
```
## read data by iterating 
```python
for _ in range(3):
	print(mmap.read(3))
# b'som' 
# b'e e' 
# b'xam'

mmap.seek(1) # reset iterator to position 2
print(mmap.read(5))
# b'ome e'
```

## creating a [[pa Buffer]] based on the on disc memory
```python
# creating osfile stream and memory mapped file stream
file_obj = pa.OSFile('example3.dat')
mmap = pa.memory_map('example3.dat')

print(pa.total_allocated_bytes()) # 0 
# (no memory allocated at the begining)

buff_mm = mmap.read_buffer()
print(pa.total_allocated_bytes()) # 0
# no memory consumed by buffer created based in memory map
# because the buffer is based on the memory in disc

buff_osf = file_obj.read_buffer()
print(pa.total_allocated_bytes()) # 64
# the buffer based on os file is consuming memory because
# its buffer in memory with copyed data from the disc
```

# Anki

START
Basic
[[pa MemoryMappedFile]]
- concept (2)
- example
	- create it
	- read from it
	- create a buffer from it
Back: 
- based on [[pyarrow]] [[stream]] [[pa NativeFile]] 
- for working with files ([[zero copy]]) memory mapped from disc

# example 
```python
with pa.OSFile('example3.dat', 'wb') as f:
	f.write(b'some example data')
mmap = pa.memory_map('example3.dat')
```
## read data by iterating 
```python
for _ in range(3):
	print(mmap.read(3))
# b'som' 
# b'e e' 
# b'xam'

mmap.seek(1) # reset iterator to position 2
print(mmap.read(5))
# b'ome e'
```

## creating a [[pa Buffer]] based on the on disc memory
```python
# creating osfile stream and memory mapped file stream
file_obj = pa.OSFile('example3.dat')
mmap = pa.memory_map('example3.dat')

print(pa.total_allocated_bytes()) # 0 
# (no memory allocated at the begining)

buff_mm = mmap.read_buffer()
print(pa.total_allocated_bytes()) # 0
# no memory consumed by buffer created based in memory map
# because the buffer is based on the memory in disc
```
Tags: code pyarrow
<!--ID: 1682756007920-->
END

START
Basic
Difference between [[pyarrow]] `MemoryMappedFile` and `OSFile` (with example)

Back: 
- both are [[pyarrow]] [[stream|streams]] for working with data on disc 
- `OSFile` is creating an in memory [[pa Buffer]] when reading (copy complete data from disc to memory)
- `MemoryMappedFile` is creating a [[pa Buffer]] referencing the on disc memory block ([[zero copy]])
```python
# creating osfile stream and memory mapped file stream
file_obj = pa.OSFile('example3.dat')
mmap = pa.memory_map('example3.dat')

print(pa.total_allocated_bytes()) # 0 
# (no memory allocated at the begining)

buff_mm = mmap.read_buffer()
print(pa.total_allocated_bytes()) # 0
# no memory consumed by buffer created based in memory map
# because the buffer is based on the memory in disc

buff_osf = file_obj.read_buffer()
print(pa.total_allocated_bytes()) # 64
# the buffer based on os file is consuming memory because
# its buffer in memory with copyed data from the disc
```
Tags: code pyarrow
<!--ID: 1682756007923-->
END
