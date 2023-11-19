## [[li return code|return code]]
- Integer code returned to a [[li parent process]] by an [[li process]] when terminating (success or failure)
- `0` in case of a success and `1 to 255` for everything else

- `$?` reads the [[li return code]] of the last [[li shell command|command]] executed
- To get the exit code of a command type `echo $?` at the command prompt

```sh
sleep 5
echo $?   # will return 0 because sleep was successfull 
sleep -1
echo $?   # will return 1 because sleep was not successfull 
```

- a [[li parent process]] can capture the [[li return code]] of its [[li child process|child processes]] using the [[li syscall]] [[li wait]] which is waiting till the [[li child process]] terminated and returs is [[li return code]]

# Anki

START
Basic
[[li return code]]
- concept
- how to get the [[li return code]] of the last executed [[li shell command]]
- how does a [[li parent process]] retriev the [[li return code]] of its [[li child process]]
Back: 
## [[li return code|return code]]
- Integer code returned to a [[li parent process]] by an [[li process]] when terminating (success or failure)
- `0` in case of a success and `1 to 255` for everything else

- `$?` reads the [[li return code]] of the last [[li shell command|command]] executed
- To get the exit code of a command type `echo $?` at the command prompt

```sh
sleep 5
echo $?   # will return 0 because sleep was successfull 
sleep -1
echo $?   # will return 1 because sleep was not successfull 
```

- a [[li parent process]] can capture the [[li return code]] of its [[li child process|child processes]] using the [[li syscall]] [[li wait]] which is waiting till the [[li child process]] terminated and returs is [[li return code]]
Tags: code linux
<!--ID: 1700385886825-->
END