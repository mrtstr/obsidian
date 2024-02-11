## [[li return code|return code]]
- Integer code returned to a [[li parent process]] by an [[li process]] when terminating (success or failure)
- a [[li parent process]] can capture the [[li return code]] of its [[li child process|child processes]] using the [[li syscall]] [[li wait]] which is waiting till the [[li child process]] terminated and returs is [[li return code]]
- the [[li return code]] is stored in the [[li process table]] untill the [[li parent process]] requested (reaped) it
- a [[li process]] that is [[li process termination|terminated]] will stay in the [[li process table]] until the [[li parent process]] requested its [[li return code]] 
- `0` in case of a success and `1 to 255` for everything else

## example
- `$?` reads the [[li return code]] of the last [[li shell command|command]] executed
- To get the exit code of a command type `echo $?` at the command prompt

```sh
sleep 5
echo $?   # will return 0 because sleep was successfull 
sleep -1
echo $?   # will return 1 because sleep was not successfull 
```

## relevant

![[li wait#li wait wait]]

![[li process table#li process table process table]]

# Anki

START
Basic
[[li return code]]
- concept
- how does a [[li parent process]] retriev the [[li return code]] of its [[li child process]] and what happens when he dont
- where is the [[li return code]] stored
- what happens when the parent process does not request the [[li return code]]
- how to get the [[li return code]] of the last executed [[li shell command]]

Back: 
## [[li return code|return code]]
- Integer code returned to a [[li parent process]] by an [[li process]] when terminating (success or failure)
- a [[li parent process]] can capture the [[li return code]] of its [[li child process|child processes]] using the [[li syscall]] [[li wait]] which is waiting till the [[li child process]] terminated and returs is [[li return code]]
- the [[li return code]] is stored in the [[li process table]] untill the [[li parent process]] requested (reaped) it
- a [[li process]] that is [[li process termination|terminated]] will stay in the [[li process table]] until the [[li parent process]] requested its [[li return code]] 
- `0` in case of a success and `1 to 255` for everything else

- `$?` reads the [[li return code]] of the last [[li shell command|command]] executed
- To get the exit code of a command type `echo $?` at the command prompt

```sh
sleep 5
echo $?   # will return 0 because sleep was successfull 
sleep -1
echo $?   # will return 1 because sleep was not successfull 
```

Tags: code linux
<!--ID: 1700385886825-->
END