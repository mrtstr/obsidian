convert [[python]] objects to binary for saving and loading
```python
import pickle

testlist = [1,2,3,4]
print(testlist)     #  [1, 2, 3, 4]

p = pickle.dumps(testlist)
print(p)            #  b'\x80\x04\x95\r\....'


p1 = reader.read()
print(p1)           #  b'\x80\x04\x95\r\....'


p2 = pickle.loads(p1)
print(p2)           #  [1, 2, 3, 4]
```

# Anki
START
Basic
python: pickle with example
Back: 
convert [[python]] objects to binary for saving and loading
```python
import pickle

testlist = [1,2,3,4]
print(testlist)     #  [1, 2, 3, 4]

p = pickle.dumps(testlist)
print(p)            #  b'\x80\x04\x95\r\....'


p1 = reader.read()
print(p1)           #  b'\x80\x04\x95\r\....'


p2 = pickle.loads(p1)
print(p2)           #  [1, 2, 3, 4]
```
Tags: code python
<!--ID: 1666875324177-->
END