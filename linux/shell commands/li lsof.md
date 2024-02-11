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
#### type: type of file
- `DIR`: opend directory
- `unix`: unix domain socket ([[li local socket]])
- `REG`: regular [[li file|file]]
- `IPv4/IPv6`: internet domain socket [[network socket]]
- `FIFO`: [[li named pipes]]
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
#### type: type of file
- `DIR`: directory
- `REG`: regular file
- `IPv4`: notwork connection using [[IP|IPv4]]
- `IPv6`: notwork connection using [[IP|IPv6]]
#### `FD`: more information about the file descriptor
- `cwd` - current working directory
- `txt` - binary file
- `mem` - memory mapped file
- integer number for [[li standard streams]] and open [[li file|files]]
- opening mode: (`r` for read access, `w` for write access, `u` for read and write access)

### [[li file descriptor]]
- [[li file descriptor]] unique identifier for
	- [[li standard streams]]
	- [[li file|open files]]
	- [[li socket|open sockets]] ([[li local socket]] or [[network socket]])
- each [[li process]] has its own [[li file descriptor]] table
- identified by positive integer values
- [[li file descriptor|file descriptors]] can be [[li redirection|redirected]] into each other or chained togather using [[li pipe]] or [[li tee]]

Tags: code linux
<!--ID: 1707667667199-->
END

START
Basic
[[shell command]] `lsof`
- 4 flags
- what does it do
- provided information (4 + 5)

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
#### type: type of file
- `DIR`: directory
- `REG`: regular file
- `IPv4`: notwork connection using [[IP|IPv4]]
- `IPv6`: notwork connection using [[IP|IPv6]]
#### `FD`: more information about the file descriptor
- `cwd` - current working directory
- `txt` - binary file
- `mem` - memory mapped file
- integer number for [[li standard streams]] and open [[li file|files]]
- opening mode: (`r` for read access, `w` for write access, `u` for read and write access)

### [[li file descriptor]]
- [[li file descriptor]] unique identifier for
	- [[li standard streams]]
	- [[li file|open files]]
	- [[li socket|open sockets]] ([[li local socket]] or [[network socket]])
- each [[li process]] has its own [[li file descriptor]] table
- identified by positive integer values
- [[li file descriptor|file descriptors]] can be [[li redirection|redirected]] into each other or chained togather using [[li pipe]] or [[li tee]]

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
#### type: type of file
- `DIR`: directory
- `REG`: regular file
- `IPv4`: notwork connection using [[IP|IPv4]]
- `IPv6`: notwork connection using [[IP|IPv6]]
#### `FD`: more information about the file descriptor
- `cwd` - current working directory
- `txt` - binary file
- `mem` - memory mapped file
- integer number for [[li standard streams]] and open [[li file|files]]
- opening mode: (`r` for read access, `w` for write access, `u` for read and write access)

### [[li file descriptor]]
- [[li file descriptor]] unique identifier for
	- [[li standard streams]]
	- [[li file|open files]]
	- [[li socket|open sockets]] ([[li local socket]] or [[network socket]])
- each [[li process]] has its own [[li file descriptor]] table
- identified by positive integer values
- [[li file descriptor|file descriptors]] can be [[li redirection|redirected]] into each other or chained togather using [[li pipe]] or [[li tee]]

Tags: code linux
<!--ID: 1707667667206-->
END