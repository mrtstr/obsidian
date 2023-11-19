## [[li pipeline]]
- system command for [[li interprocess communication]]
- for chaining processes togather by their [[li standard streams]]
- [[stdout]] of one process is piped in the [[li stdin]] of another [[li process]]
- [[li pipeline|pipes]] then are unidirectional byte streams

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

# anki
START
Basic
[[li pipeline]]
- concept

Back: 

- system command for [[li interprocess communication]]
- for chaining processes togather by their [[li standard streams]]
- [[stdout]] of one process is piped in the [[li stdin]] of another [[li process]]
- [[li pipeline|pipes]] then are unidirectional byte streams

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

## [[li pipeline]]
- system command for [[li interprocess communication]]
- for chaining processes togather by their [[li standard streams]]
- [[stdout]] of one process is piped in the [[li stdin]] of another [[li process]]
- [[li pipeline|pipes]] then are unidirectional byte streams
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
difference [[li redirection]] and [[li pipeline]]

Back: 
-  [[li redirection]] redirects [[li file descriptor]] to each other
- [[li pipeline]] sents [[li stdout]] steams of one [[li process]] to the [[li stdin]] stream of another [[li process]] (command)
Tags: code linux
<!--ID: 1700412026140-->
END