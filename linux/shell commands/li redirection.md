### [[li redirection]] of [[li file descriptor|file descriptors]] into each other
- [[li file descriptor|file descriptors]] ([[li standard streams]], [[li file|open files]], [[li socket|open sockets]]) can be redirected into each other with the following syntax `[source file discriptor]>&[dest file descriptor]`
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


### example: [[li redirection]] of streams to a [[li bit bucket]]
```sh
ls /usr/bin &> /dev/null
```

### [[li redirection]] [[li file descriptor]] into each other
- when [[li redirection|redirecting]] to a [[li file descriptor]] we need to add `&` before the reciving [[li file descriptor]] to clarify that it's a [[li file descriptor]] (otherwise it would be interpreded as a file name)

```sh
cat myfile2 myfile > log 2>&1
# 1) redirecting stdout to log
# 2) redirecting stderr to the current stdout (which is log)
# -> both are going togather to log

cat myfile2 myfile 2>&1 > log
# 1) redirecting stderr to the current location of stdout
# 2) redirection stdout to file
# -> does not work because only stdout will go to log and stderr will go to stdout

cat myfile2 myfile 2>&1 1>/dev/null
# 1) redirecting stderr to stdout 
# 2) redirecting stdout to the bit bucker
# -> only stderr will be returned

cat myfile2 myfile 2>&1 1>/dev/null | grep something
# can also get redirected for filtering
```


# Anki

START
Basic
how to do a [[li redirection]] of a [[li file]] into [[li stdin]] of a [[shell command]]
how to achive the following with [[li stdin]] redirection
```sh
cat myfile | head -n 5
```
Back: 
- [[li file]] can be redirected to a [[li stdin]] channel using the `<` operator
```sh
head -n 5 < myfile
# is eqivalent to
cat myfile | head -n 5
```

Tags: code linux
<!--ID: 1700412026099-->
END


START
Basic
how to do
- [[li redirection]] of [[li stdout]] and [[li stderr]] into [[li file|files]]
- append and replace

examples
- ite stdout of ls in myfile (replace) (two methods)
- write stdout of ls in myfile (append)  (two methods)
- redirect stderr to file
Back: 
#### [[li redirection]] of [[li file descriptor|file descriptors]] into each other
- [[li file descriptor|file descriptors]] ([[li standard streams]], [[li file|open files]], [[li socket|open sockets]]) can be redirected into each other with the following syntax `[source file discriptor]>&[dest file descriptor]`
- in case of a not opend [[li file]] `[source file discriptor]>[file path]` will open the file and redirect into it
- `>>` will append to a [[li file descriptor]] while `>` will overwrite the existing content

#### [[li redirection]] of [[li stdout]] and [[li stderr]] into [[li file|files]]
- the operators `>` and `>>` control the [[li stdout]] stream and can forward then into arbitrary [[li file]]
- If the file you are redirecting to does not exist, it will be created. 

```sh
ls > myfile          # write stdout of ls in myfile (replace)
ls >> myfile         # write stdout of ls in myfile (append)
sleep -1 &> myfile   # write stdout and stderr of ls in myfile (append)
sleep -1 &>> myfile  # write stdout and stderr of ls in myfile (replace)
```


### [[li redirection]] of arbitray [[li file descriptor]]

- the command `file_discriptor>` allows the [[li redirection]] of an arbitrary [[li file descriptor]] to a arbitray [[li file]]

```sh
echo dddd  1> myfile   # redirect both stderr (1) to file (replace)
echo dddd  > myfile    # equivalent

echo dddd  1>> myfile  # redirect both stderr (1) to file (append)
echo dddd  >> myfile    # equivalent

sdfsdf 2> myfile       # redirect stderr to file (replace)
# myfile conent is sdfsdf: command not found
```


Tags: code linux
<!--ID: 1700412026102-->
END



START
Basic
how to do the following using a [[li shell command]]
- replace conentent of file2 with content of file1
- delete content of myfile
- appand line with hallo to myfile
- append myfile with the content of file1
- redirect stderr of a command in one file and stdout into another
Back: 
#### [[li redirection]] of [[li file descriptor|file descriptors]] into each other
- [[li file descriptor|file descriptors]] ([[li standard streams]], [[li file|open files]], [[li socket|open sockets]]) can be redirected into each other with the following syntax `[source file discriptor]>&[dest file descriptor]`
- in case of a not opend [[li file]] `[source file discriptor]>[file path]` will open the file and redirect into it
- `>>` will append to a [[li file descriptor]] while `>` will overwrite the existing content
### examples
```sh
cat file1 >> myfile  # append myfile with the content of file1
echo hallo >> myfile # appand line with hallo to myfile
echo > myfile        # delete content of myfile
cat file1 > file2    # replace conentent of file2 with content of file1
cat myfile2 myfile 2> err_file 1> out_file 
# redirect stderr of a command in one file and stdout into another
```
Tags: code linux
<!--ID: 1700412026105-->
END


START
Basic
How to ignore the [[stdout]] of a [[li shell command]]
Back: 
#### [[li redirection]] of [[li file descriptor|file descriptors]] into each other
- [[li file descriptor|file descriptors]] ([[li standard streams]], [[li file|open files]], [[li socket|open sockets]]) can be redirected into each other with the following syntax `[source file discriptor]>&[dest file descriptor]`
- in case of a not opend [[li file]] `[source file discriptor]>[file path]` will open the file and redirect into it
- `>>` will append to a [[li file descriptor]] while `>` will overwrite the existing content

#### example
[[li redirection]] of streams to a [[li bit bucket]]
- when we dont need some out
```sh
ls /usr/bin &> /dev/null
```
Tags: code linux
<!--ID: 1700412026108-->
END


START
Basic
how to redirect [[li file descriptor]] into each other
examples for
- redirecting [[stdout]] and [[stderr]] in a [[li file]]
- redirecting only [[li stderr]] to [[li stdout]] (and filter it)
Back: 
#### [[li redirection]] of [[li file descriptor|file descriptors]] into each other
- [[li file descriptor|file descriptors]] ([[li standard streams]], [[li file|open files]], [[li socket|open sockets]]) can be redirected into each other with the following syntax `[source file discriptor]>&[dest file descriptor]`
- in case of a not opend [[li file]] `[source file discriptor]>[file path]` will open the file and redirect into it
- `>>` will append to a [[li file descriptor]] while `>` will overwrite the existing content
#### [[li redirection]] [[li file descriptor]] into each other

```sh
cat myfile2 myfile > log 2>&1
# 1) redirecting stdout to log
# 2) redirecting stderr to the current stdout (which is log)
# -> both are going togather to log

cat myfile2 myfile 2>&1 > log
# 1) redirecting stderr to the current location of stdout
# 2) redirection stdout to file
# -> does not work because only stdout will go to log and stderr will go to stdout

cat myfile2 myfile 2>&1 1>/dev/null
# 1) redirecting stderr to stdout 
# 2) redirecting stdout to the bit bucker
# -> only stderr will be returned

cat myfile2 myfile 2>&1 1>/dev/null | grep something
# can also get redirected for filtering
```

Tags: code linux
<!--ID: 1700412026112-->
END


START
Basic
what is happening in the following [[li shell command]]
```sh
cat myfile2 myfile > log 2>&1

cat myfile2 myfile 2>&1 > log
```

Back: 
#### [[li redirection]] of [[li file descriptor|file descriptors]] into each other
- [[li file descriptor|file descriptors]] ([[li standard streams]], [[li file|open files]], [[li socket|open sockets]]) can be redirected into each other with the following syntax `[source file discriptor]>&[dest file descriptor]`
- in case of a not opend [[li file]] `[source file discriptor]>[file path]` will open the file and redirect into it
- `>>` will append to a [[li file descriptor]] while `>` will overwrite the existing content

### [[li redirection]] [[li file descriptor]] into each other
- when [[li redirection|redirecting]] to a [[li file descriptor]] we need to add `&` before the reciving [[li file descriptor]] to clarify that it's a [[li file descriptor]] (otherwise it would be interpreded as a file name)

```sh
cat myfile2 myfile > log 2>&1
# 1) redirecting stdout to log
# 2) redirecting stderr to the current stdout (which is log)
# -> both are going togather to log

cat myfile2 myfile 2>&1 > log
# 1) redirecting stderr to the current location of stdout
# 2) redirection stdout to file
# -> does not work because only stdout will go to log and stderr will go to stdout
```
Tags: code linux
<!--ID: 1700412026118-->
END


START
Basic
what is happening in the following [[li shell command]]

```sh
cat myfile2 myfile 2>&1 1>/dev/null
```

Back: 
#### [[li redirection]] of [[li file descriptor|file descriptors]] into each other
- [[li file descriptor|file descriptors]] ([[li standard streams]], [[li file|open files]], [[li socket|open sockets]]) can be redirected into each other with the following syntax `[source file discriptor]>&[dest file descriptor]`
- in case of a not opend [[li file]] `[source file discriptor]>[file path]` will open the file and redirect into it
- `>>` will append to a [[li file descriptor]] while `>` will overwrite the existing content

#### [[li redirection]] [[li file descriptor]] into each other
- when [[li redirection|redirecting]] to a [[li file descriptor]] we need to add `&` before the reciving [[li file descriptor]] to clarify that it's a [[li file descriptor]] (otherwise it would be interpreded as a file name)

```sh
cat myfile2 myfile 2>&1 1>/dev/null
# 1) redirecting stderr to stdout 
# 2) redirecting stdout to the bit bucker
# -> only stderr will be returned

cat myfile2 myfile 2>&1 1>/dev/null | grep something
# can also get redirected for filtering
```
Tags: code linux
<!--ID: 1700412026121-->
END



START
Basic
summary [[li redirection]]
- oparator for redirecting [[li stdout]] to a [[li file]]
- oparator for redirecting [[li stderr]] to a [[li file]]
- operator for redirecting a [[li file descriptor]] into another [[li file descriptor]]
- how to ignore a [[li stdout]] or [[li stderr]] stream
Back: 
#### [[li redirection]] of [[li file descriptor|file descriptors]] into each other
- [[li file descriptor|file descriptors]] ([[li standard streams]], [[li file|open files]], [[li socket|open sockets]]) can be redirected into each other with the following syntax `[source file discriptor]>&[dest file descriptor]`
- in case of a not opend [[li file]] `[source file discriptor]>[file path]` will open the file and redirect into it
- `>>` will append to a [[li file descriptor]] while `>` will overwrite the existing content

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
ls > myfile          # write stdout of ls in myfile (replace)
ls >> myfile         # write stdout of ls in myfile (append)
sleep -1 &> myfile   # write stdout and stderr of ls in myfile (append)
sleep -1 &>> myfile  # write stdout and stderr of ls in myfile (replace)
```

### examples
```sh
cat file1 >> myfile  # append myfile with the content of file1
echo hallo >> myfile # appand line with hallo to myfile
echo > myfile        # delete content of myfile
cat file1 > file2    # replace conentent of file2 with content of file1
```

#### [[li redirection]] of arbitray [[li file descriptor]]

- the command `file_discriptor>` allows the [[li redirection]] of an arbitrary [[li file descriptor]] to a arbitray [[li file]]

```sh
echo dddd  1> myfile   # redirect both stderr (1) to file (replace)
echo dddd  > myfile    # equivalent

echo dddd  1>> myfile  # redirect both stderr (1) to file (append)
echo dddd  >> myfile    # equivalent

sdfsdf 2> myfile       # redirect stderr to file (replace)
# myfile conent is sdfsdf: command not found
```

#### [[li redirection]] of streams to a [[li bit bucket]]
- when we dont need some out
```sh
ls /usr/bin &> /dev/null
```

#### [[li redirection]] [[li file descriptor]] into each other
- when [[li redirection|redirecting]] to a [[li file descriptor]] we need to add `&` before the reciving [[li file descriptor]] to clarify that it's a [[li file descriptor]] (otherwise it would be interpreded as a file name)

```sh
cat myfile2 myfile > log 2>&1
# 1) redirecting stdout to log
# 2) redirecting stderr to the current stdout (which is log)
# -> both are going togather to log

cat myfile2 myfile 2>&1 > log
# 1) redirecting stderr to the current location of stdout
# 2) redirection stdout to file
# -> does not work because only stdout will go to log and stderr will go to stdout

cat myfile2 myfile 2>&1 1>/dev/null
# 1) redirecting stderr to stdout 
# 2) redirecting stdout to the bit bucker
# -> only stderr will be returned

cat myfile2 myfile 2>&1 1>/dev/null | grep something
# can also get redirected for filtering
```
Tags: code linux
<!--ID: 1700412026124-->
END


START
Basic
what is happening in the following [[li shell command]]

```sh
cat myfile > f1 > f2
```

Back: 
- `f1` is emply and the conentent of `myfile` is in `f2`
- because the conent was redirected to f2
Tags: code linux
<!--ID: 1700412026128-->
END