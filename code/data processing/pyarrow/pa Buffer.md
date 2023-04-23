- Represents a contiguous memory area with a `datapointer` and a `legth`
- can be mutable or immutable.
- Underlaying data structure of [[pa Array]]
- can be [[zero copy]] sliced by creating another [[pa Buffer]] on the memory within the original [[pa Buffer]] with a child relationship

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

## usage
### can be written to or read from with [[pa NativeFile|streams]]
![[pa NativeFile#create a emply pa Buffer , write a py string to it and read it again]]

### create a [[pa Buffer]] holding the bytes of a [[py bytes-like object]]
create a [[zero copy]] view on the bytes of the object with `pa.py_buffer(obj)

```python
i= 324324
b = i.to_bytes(length=4, "big")
# b'\x00\x04\xf2\xe4'
buff = pa.py_buffer(b)
# <pyarrow.Buffer address=0x7f604de14f80 size=4 is_cpu=True is_mutable=False>
buff.to_pybytes()
# b'\x00\x04\xf2\xe4'
```

```python
pa.foreign_buffer(adress, size) # Construct an Arrow buffer
```


# anki

START
Basic
[[pa Buffer]]
- concept (1)
- properties (1)
- slicing (1)
- attributes (4)
- methods (4)
Back: 
- Represents a contiguous memory area with a `datapointer` and a `legth`
- can be mutable or immutable.
- Underlaying data structure of [[pa Array]]
- can be [[zero copy]] sliced by creating another [[pa Buffer]] on the memory within the original [[pa Buffer]] with a child relationship

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

Tags: code pyarrow
<!--ID: 1682248340851-->
END


START
Basic
[[pa Buffer]]
- example: create a [[pa Buffer]] from a [[py bytes-like object]] and revert the [[pa Buffer]] back to a [[py bytes-like object]]
- what happens in the memory?
Back: 
### create a [[pa Buffer]] holding the bytes of a [[py bytes-like object]]
create a [[zero copy]] view on the bytes of the object with `pa.py_buffer(obj)

```python
i= 324324
b = i.to_bytes(length=4, "big")
# b'\x00\x04\xf2\xe4'
buff = pa.py_buffer(b)
# <pyarrow.Buffer address=0x7f604de14f80 size=4 is_cpu=True is_mutable=False>
buff.to_pybytes()
# b'\x00\x04\xf2\xe4'
```

Tags: code pyarrow
<!--ID: 1682248340853-->
END