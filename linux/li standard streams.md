### [[li standard streams|standard streams]]
- all [[li process|linux processes]] (except [[li deamon]]) have 3 [[li standard streams]]
- [[li interprocess communication|interconnected]] input and output communication channels between a [[li process]] and its environment when it begins execution
- identified by a [[li file descriptor]] of the [[li process]]
- can be [[li redirection|redicrected]] and chained ([[li ordinary pipe]])
- a [[li child process]] inherits the standard streams of its [[li parent process]]


### terminal [[li process|processes]]
- when a [[li process]] is started from a [[li terminal]] the [[li standard streams]] are connected to the keyboard ([[li stdin]]) and the display ([[li stdout]], [[li stderr]])
![[309px-Stdstreams-notitle.svg.png]]

![[li redirection#li redirection of li file descriptor file descriptors into each other]]


![[li ordinary pipe#li ordinary pipe]]

![[li tee#`tee`]]


# Anki

START
Basic
#### [[li standard streams|standard streams]]
- concept (2)
- identification
- redicrection (with examples)
- chaining 
Back: 

- all [[li process|linux processes]] (except [[li deamon]]) have 3 [[li standard streams]]
- [[li interprocess communication|interconnected]] input and output communication channels between a [[li process]] and its environment when it begins execution
- identified by a [[li file descriptor]] of the [[li process]]
- can be [[li redirection|redicrected]] and chained ([[li ordinary pipe]])
- a [[li child process]] inherits the standard streams of its [[li parent process]]

### [[li redirection]] of [[li file descriptor|file descriptors]] into each other
- [[li file descriptor|file descriptors]] ([[li standard streams]], [[li file|open files]], [[linux/li socket|open sockets]]) can be redirected into each other with the following syntax `[source file discriptor]>&[dest file descriptor]`
- in case of a not opend [[li file]] `[source file discriptor]>[file path]` will open the file and redirect into it
- `>>` will append to a [[li file descriptor]] while `>` will overwrite the existing content

### example: [[li redirection]] of [[li file]] into [[li stdin]]  
- [[li file]] can be redirected to a [[li stdin]] channel using the `<` operator
```sh
head -n 5 < myfile
# is eqivalent to
cat myfile | head -n 5
```


### example [[li redirection]] of [[li stdout]] and [[li stderr]] into [[li file|files]]
- [[li stdout]] has alwas the [[li file descriptor]] 1 and [[li stderr]] always 2
- They can be redicrected into [[li file|files]] (If the file you are redirecting to does not exist, it will be created)
- in case of [[li stdout]] the 1 is not nessary
```sh
ls 1> myfile          # write stdout of ls in myfile (replace)
ls > myfile           # short form 
ls 1>> myfile         # write stdout of ls in myfile (append)
ls >> myfile          # short form 
sleep -1 2> myfile   # write stderr of command in myfile (append)
sleep -1 2>> myfile  # write stderr of command in myfile (replace)
```

### [[li ordinary pipe]]
- system command for [[li interprocess communication]]
- for chaining processes togather by their [[li standard streams]]
- [[li stdout]] of one process is piped in the [[li stdin]] of another [[li process]]
- [[li ordinary pipe|pipes]] then are unidirectional byte streams

```sh
command1 | command2 | command3
# the stdout of command 1 will be the stdin of command2
# the stdout of command 2 will be the stdin of command3
```

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
<!--ID: 1707667667213-->
END