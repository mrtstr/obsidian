[[python]]
#### defining a byte [[py string]]
```python
byte_like_object = b'Hello World'
memoryview(byte_like_object) # display physical memory adress
# <memory at 0x7f604d7ffd00>
```

#### converting [[py int]] to [[py bytes-like object]] and back
```python
i= 324324

b = i.to_bytes(length=4, byteorder="big")
# b'\x00\x04\xf2\xe4'
int.from_bytes(b, byteorder='big')
# 324324
```

#### converting [[py string]] to [[py bytes-like object]] and back
```python
s = "sdfsdfds"

b = s.encode()

b.decode()
```


# anki

START
Basic
[[python]] [[py bytes-like object]]
- defining a byte [[py string]] and display the physical memory adress
- converting [[py int]] to [[py bytes-like object]] and back
- converting [[py string]] to [[py bytes-like object]] and back
Back: 
#### defining a byte [[py string]]
```python
byte_like_object = b'Hello World'
memoryview(byte_like_object) # display physical memory adress
# <memory at 0x7f604d7ffd00>
```

#### converting [[py int]] to [[py bytes-like object]] and back
```python
i= 324324

b = i.to_bytes(length=4, byteorder="big")
# b'\x00\x04\xf2\xe4'
int.from_bytes(b, byteorder='big')
# 324324
```

#### converting [[py string]] to [[py bytes-like object]] and back
```python
s = "sdfsdfds"

b = s.encode()

b.decode()
```

Tags: code python
<!--ID: 1682248340832-->
END