### [[li ordinary pipe]]
- system command for [[li interprocess communication]]
- for chaining processes togather by their [[li standard streams]]
- [[li stdout]] of one process is piped in the [[li stdin]] of another [[li process]]
- [[li pipe|pipes]] then are unidirectional byte streams

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

### 3.6.3.1 Ordinary Pipes

-   Ordinary pipes are uni-directional, with a reading end and a writing end. ( If bidirectional communications are needed, then a second pipe is required. )
-   In UNIX ordinary pipes are created with the system call "int pipe( int fd [ ] )".
    -   The return value is 0 on success, -1 if an error occurs.
    -   The int array must be allocated before the call, and the values are filled in by the pipe system call:
        -   fd[ 0 ] is filled in with a file descriptor for the reading end of the pipe
        -   fd[ 1 ] is filled in with a file descriptor for the writing end of the pipe
    -   UNIX pipes are accessible as files, using standard read( ) and write( ) system calls.
    -   Ordinary pipes are only accessible within the process that created them.
        -   Typically a parent creates the pipe before forking off a child.
        -   When the child inherits open files from its parent, including the pipe file(s), a channel of communication is established.
        -   Each process ( parent and child ) should first close the ends of the pipe that they are not using. For example, if the parent is writing to the pipe and the child is reading, then the parent should close the reading end of its pipe after the fork and the child should close the writing end.
-   Figure 3.22 shows an ordinary pipe in UNIX, and Figure 3.23 shows code in which it is used.


# anki
START
Basic
[[li ordinary pipe]]
- concept

Back: 

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