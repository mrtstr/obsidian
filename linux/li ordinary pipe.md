### [[li ordinary pipe]] concept
- mechanism for unidirectional [[li interprocess communication]]
- can be used with one [[li file descriptor]] for writing and one for reading unsing the FIFO order
- can be created togather with the read and wirte [[li file descriptor]] using the [[li pipe]] [[li syscall]] 
- usually the [[li file descriptor|file descriptors]] are passed to child [[li child process]] in order to enable them to comunicate with each other

### [[li syscall]]
![[linux/sys calls/li pipe#pipe(pipefd[2])]]

### [[shell command]]
- the [[li stdin]] and [[li stdout]] streams con be piped togather using the `|` operator in [[li shell command]]
```sh
command1 | command2 | command3
# the stdout of command 1 will be the stdin of command2
# the stdout of command 2 will be the stdin of command3
```

### examples
```sh
cat myfile | head -5 | grep c 
# 1) print output of file 
# 2) forward stdout to stdin of a command collecting only first 5 lines
# 3) forward stdout to stdin of a command filtering
cat myfile2 myfile 2>&1 1>/dev/null | grep something
# 1) redirecting stderr to stdout 
# 2) redirecting stdout to the bit bucker
# -> only stderr will be returned
# 3) filtering for something
```

## related
![[li file descriptor#li file descriptor]]
# anki

START
Basic
[[li ordinary pipe]] 
- concept
- system call
- usage in a shell command

Back: 

### [[li ordinary pipe]] concept
- mechanism for unidirectional [[li interprocess communication]]
- can be used with one [[li file descriptor]] for writing and one for reading unsing the FIFO order
- can be created togather with the read and wirte [[li file descriptor]] using the [[li pipe]] [[li syscall]] 
- usually the [[li file descriptor|file descriptors]] are passed to child [[li child process]] in order to enable them to comunicate with each other

![[o_pipe 1.jpg]]

#### pipe(pipefd[2])
- [[li syscall]] for creating a [[li ordinary pipe]]
- returns a [[li return code]], opends a ordinary/unnamed pipe and writes the input and output [[li file descriptor]] in the array `pipefd`

#### [[shell command]]
- the [[li stdin]] and [[li stdout]] streams con be piped togather using the `|` operator in [[li shell command]]
```sh
command1 | command2 | command3
# the stdout of command 1 will be the stdin of command2
# the stdout of command 2 will be the stdin of command3
```

#### [[li file descriptor]]
- [[li file descriptor]] unique identifier for any kind of data stream
	- `CHR`: character special file(special part of the file system e.g. for a device or [[li standard streams]]) 
	- `DIR`: opend directory
	- `unix`: unix domain socket ([[li unix domain socket]])
	- `REG`: regular [[li file|file]]
	- `IPv4/IPv6`: internet domain socket [[li internet domain socket]]
	- `FIFO`: [[li FIFO special file]]
→ same interface 
- opening modes:
	- `r`: read only
	- `w`: write only
	- `u`: read and write
- index (small integer) to an entry in the [[li process]] table of open [[li file descriptor|file descriptors]]
Tags: code linux
<!--ID: 1708245724879-->
END


START
Basic
example: pipeling togather [[li shell command|shell commands]] qith their [[li standard streams]]

Back: 
- the [[li stdin]] and [[li stdout]] streams con be piped togather using the `|` operator in [[li shell command]]
```sh
command1 | command2 | command3
# the stdout of command 1 will be the stdin of command2
# the stdout of command 2 will be the stdin of command3
```

### examples
```sh
cat myfile | head -5 | grep c 
# 1) print output of file 
# 2) forward stdout to stdin of a command collecting only first 5 lines
# 3) forward stdout to stdin of a command filtering
cat myfile2 myfile 2>&1 1>/dev/null | grep something
# 1) redirecting stderr to stdout 
# 2) redirecting stdout to the bit bucker
# -> only stderr will be returned
# 3) filtering for something
```
Tags: code linux
<!--ID: 1700412026134-->
END


START
Basic
[[li shell command]] for 
- print output of file and print only lines that was in the top 5  lines and contain a c
- call and command and filter the std error for a word
Back: 

```sh
cat myfile | head -5 | grep c 
# 1) print output of file 
# 2) forward stdout to stdin of a command collecting only first 5 lines
# 3) forward stdout to stdin of a command filtering
cat myfile2 myfile 2>&1 1>/dev/null | grep something
# 1) redirecting stderr to stdout 
# 2) redirecting stdout to the bit bucker
# -> only stderr will be returned
# 3) filtering for something
```

## [[li ordinary pipe]]
- system command for [[li interprocess communication]]
- for chaining processes togather by their [[li standard streams]]
- [[stdout]] of one process is piped in the [[li stdin]] of another [[li process]]
- [[li ordinary pipe|pipes]] then are unidirectional byte streams
```sh
command1 | command2 | command3
# the stdout of command 1 will be the stdin of command2
# the stdout of command 2 will be the stdin of command3
```
Tags: code linux
<!--ID: 1700412026137-->
END

START
Basic
[[linux]] [[li shell command]]:
difference [[li redirection]] and [[li ordinary pipe]]

Back: 
-  [[li redirection]] redirects [[li file descriptor]] to each other
- [[li ordinary pipe]] sents [[li stdout]] steams of one [[li process]] to the [[li stdin]] stream of another [[li process]] (command)
Tags: code linux
<!--ID: 1700412026140-->
END