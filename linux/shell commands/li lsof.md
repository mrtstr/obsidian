## `lsof`
[[shell command]] `lsof` list all open [[li file descriptor|file descriptors]] 
```bash
lsof  # list all open file descriptors
	[-p PID]     # only open files of a specific process
	[-P]         # show used ports
	[-i [:port]]     # show only network file descriptors (and optionally filter for port)
	[-n]     # show ip adress instead of host name
```

```bash
lsof <path of file>  
# list all processes that have currently opened the given file
```

### provided information
#### `FD`: more information about the file descriptor
- `cwd` - current working directory
- `txt` - binary file
- `mem` - memory mapped file
- integer number for [[li standard streams]] and open [[li file|files]]
- opening mode: (`r` for read access, `w` for write access, `u` for read and write access)

### examples
```bash
lsof -i :443 # list file descriptors using the port 443
lsof -p $$ # list file descriptors of the current terminal process
```
## related
![[li file descriptor#li file descriptor]]


# anki
START
Basic
[[shell command]] for listing all currenlty open [[li file descriptor]] (4 flags)
examples
- list only opend [[li file descriptor]] of the current shell session
- list only network [[li file descriptor]]
- list all [[li process|processes]] that have a given file currently opend
- types of [[li file descriptor]] (6)
Back: 
### `lsof`
[[shell command]] `lsof` list all open [[li file descriptor|file descriptors]] 
```bash
lsof  # list all open file descriptors
	[-p PID]     # only open files of a specific process
	[-P]         # show used ports
	[-i [:port]]     # show only network file descriptors (and optionally filter for port)
	[-n]     # show ip adress instead of host name
```

```bash
lsof <path of file>  
# list all processes that have currently opened the given file
```

### provided information
#### `FD`: more information about the file descriptor
- `cwd` - current working directory
- `txt` - binary file
- `mem` - memory mapped file
- integer number for [[li standard streams]] and open [[li file|files]]
- opening mode: (`r` for read access, `w` for write access, `u` for read and write access)

### [[li file descriptor]]
- [[li file descriptor]] unique identifier for any kind of data stream
	- `CHR`: character special file(special part of the file system e.g. for a device or [[li standard streams]]) 
	- `DIR`: opend directory
	- `unix`: unix domain socket ([[li unix domain socket]])
	- `REG`: regular [[li file|file]]
	- `IPv4/IPv6`: internet domain socket [[li network socket]]
	- `FIFO`: [[li FIFO special file]]
→ same interface 
- opening modes:
	- `r`: read only
	- `w`: write only
	- `u`: read and write
- index (small integer) to an entry in the [[li process]] table of open [[li file descriptor|file descriptors]]

Tags: code linux
<!--ID: 1707667667199-->
END

START
Basic
[[shell command]] `lsof`
- 4 flags
- what does it do
- provided information (4+6)

Back: 
### `lsof`
[[shell command]] `lsof` list all open [[li file descriptor|file descriptors]] 
```bash
lsof  # list all open file descriptors
	[-p PID]     # only open files of a specific process
	[-P]         # show used ports
	[-i [:port]]     # show only network file descriptors (and optionally filter for port)
	[-n]     # show ip adress instead of host name
```

```bash
lsof <path of file>  
# list all processes that have currently opened the given file
```

### provided information
#### `FD`: more information about the file descriptor
- `cwd` - current working directory
- `txt` - binary file
- `mem` - memory mapped file
- integer number for [[li standard streams]] and open [[li file|files]]
- opening mode: (`r` for read access, `w` for write access, `u` for read and write access)

### [[li file descriptor]]
- [[li file descriptor]] unique identifier for any kind of data stream
	- `CHR`: character special file(special part of the file system e.g. for a device or [[li standard streams]]) 
	- `DIR`: opend directory
	- `unix`: unix domain socket ([[li unix domain socket]])
	- `REG`: regular [[li file|file]]
	- `IPv4/IPv6`: internet domain socket [[li network socket]]
	- `FIFO`: [[li FIFO special file]]
→ same interface 
- opening modes:
	- `r`: read only
	- `w`: write only
	- `u`: read and write
- index (small integer) to an entry in the [[li process]] table of open [[li file descriptor|file descriptors]]

Tags: code linux
<!--ID: 1707667667202-->
END

START
Basic
[[shell command]]
- list file descriptors using the port 443
- list file descriptors of the current terminal process

Back: 
```bash
lsof -i :443 # list file descriptors using the port 443
lsof -p $$ # list file descriptors of the current terminal process
```

### `lsof`
[[shell command]] `lsof` list all open [[li file descriptor|file descriptors]] 
```bash
lsof  # list all open file descriptors
	[-p PID]     # only open files of a specific process
	[-P]         # show used ports
	[-i [:port]]     # show only network file descriptors (and optionally filter for port)
	[-n]     # show ip adress instead of host name
```

```bash
lsof <path of file>  
# list all processes that have currently opened the given file
```

### provided information
#### `FD`: more information about the file descriptor
- `cwd` - current working directory
- `txt` - binary file
- `mem` - memory mapped file
- integer number for [[li standard streams]] and open [[li file|files]]
- opening mode: (`r` for read access, `w` for write access, `u` for read and write access)

### [[li file descriptor]]
- [[li file descriptor]] unique identifier for any kind of data stream
	- `CHR`: character special file(special part of the file system e.g. for a device or [[li standard streams]]) 
	- `DIR`: opend directory
	- `unix`: unix domain socket ([[li unix domain socket]])
	- `REG`: regular [[li file|file]]
	- `IPv4/IPv6`: internet domain socket [[li network socket]]
	- `FIFO`: [[li FIFO special file]]
→ same interface 
- opening modes:
	- `r`: read only
	- `w`: write only
	- `u`: read and write
- index (small integer) to an entry in the [[li process]] table of open [[li file descriptor|file descriptors]]

Tags: code linux
<!--ID: 1707667667206-->
END