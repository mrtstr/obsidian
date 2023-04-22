- Represents a contiguous memory area
- can be mutable or immutable.

### Attributes
```python
adress # The buffer's address as an integer
size # Nsize in byes.
is_cpu # Whether the buffer is CPU-accessible.
is_mutable # Whether the buffer is mutable.
```

### Methods
```python
equals # Determine if two buffers contain exactly the same data.
hex # Compute hexadecimal representation of the buffer.
slice # Slice this buffer.
to_pybytes # Return this buffer as a Python bytes object.
```

### factory functions

```python
pa.allocate_buffer(size, MemoryPool, resizable) # Allocate a mutable buffer
```

```python
pa.py_buffer(obj) # Construct an Arrow buffer from a Python bytes-like or buffer-like object
```

```python
pa.foreign_buffer(adress, size) # Construct an Arrow buffer
```