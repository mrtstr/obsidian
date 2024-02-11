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

### [[li redirection]] of [[li standard streams]]
#### [[li redirection]] of [[li file]] into [[li stdin]]  

- [[li file]] can be redirected to a [[li stdin]] channel using the `<` operator
```sh
head -n 5 < myfile
# is eqivalent to
cat myfile | head -n 5
```


#### [[li redirection]] of [[li stdout]] and [[li stderr]] into [[li file|files]]
- the operators `>` and `>>` control the [[li stdout]] stream and can forward then into arbitrary [[li file]]
- If the file you are redirecting to does not exist, it will be created. 

```sh
ls 1> myfile          # write stdout of ls in myfile (replace)
ls 1>> myfile         # write stdout of ls in myfile (append)
sleep -1 &> myfile   # write stdout and stderr of ls in myfile (append)
sleep -1 &>> myfile  # write stdout and stderr of ls in myfile (replace)
```

```sh
cat file1 >> myfile  # append myfile with the content of file1
echo hallo >> myfile # appand line with hallo to myfile
echo > myfile        # delete content of myfile
cat file1 > file2    # replace conentent of file2 with content of file1
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