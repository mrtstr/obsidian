## [[li wait|wait]]
-  [[linux]] [[li syscall]] for waiting for the [[li process termination|termination]] of a [[li child process]] and requesting the [[li return code]] from the [[li process table]]
- even if a [[li process]] is [[li process termination|terminated]] it remains in the [[li process table]] untill its [[li return code]] is read/reaped

## relevant
![[li return code#li return code return code]]

![[li process table#li process table process table]]

# anki
START
Basic
how can a [[li parent process]] request the [[li return code]] of a [[li child process]]?

Back: 
## [[li wait|wait]]
-  [[linux]] [[li syscall]] for waiting for the [[li process termination|termination]] of a [[li child process]] and requesting the [[li return code]] from the [[li process table]]
- even if a [[li process]] is [[li process termination|terminated]] it remains in the [[li process table]] untill its [[li return code]] is read/reaped

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
- the [[li return code]] is stored in the [[li process table]] untill the [[li parent process]] requested (reaped) it
- a [[li process]] that is [[li process termination|terminated]] will stay in the [[li process table]] until the [[li parent process]] requested its [[li return code]] 
Tags: code linux
<!--ID: 1702578315609-->
END