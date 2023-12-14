
# [[li process termination|process termination]]
- When a [[li process]] terminates, all of its resources ([[li memory]], [[li file descriptor]]...) are released by the [[li kernel]]
- open files are flushed and closed
- the [[li return code]] is returned to the [[li parent process]] (reaping)
- li processes can terminate on their own, can be killed or asked to terminate by a [[li signal]]

## reaping of the [[li return code]]
- when a [[li child process]] exits, some [[li process]] (usualy the [[li parent process]]) must always [[li wait|wait]] for its [[li return code]]

![[li return code#li return code return code]]

- after the termination the [[li return code]] is stored in the [[li process table]] until its read (reaped) by tha [[li parent process]]

![[li process table#li process table process table]]

- if a [[li process]] terminates before its [[li child process]] the [[li init process]] (with `PID` 1) inherents all [[li child process]] ([[li orphan process]]) and the responsability to reap the [[li return code]]

![[li orphan process#li orphan process orphan process]]

- Between the time a child exits and is reaped, it is called a [[li zombie process]]. 

![[li zombie process#li zombie process zombie process]]

## self termination
- a [[li process]] can terminate itself usging the [[li exit]] [[li syscall]]

![[li exit#li exit exit]]

## based on a [[li signal]] from the [[li kernel]]
- the [[li kernel]] can send differnt [[li signal|signals]] to a [[li process]] causing it to terminate
- some of them are based on an illigal action of an error like `SIGILL 4` (Illegal instruction)
- some of them can be handled or even ignored by the [[li process]] itself like `SIGTERM 15`
- some of them can not be irgoned and terminte the [[li process]] abrubtly with an error like `SIGKILL 9`

![[li signal#SIGKILL 9]]

![[li signal#SIGILL 4 (Illegal instruction)]]

![[li signal#SIGTERM 15]]



# Anki

START
Basic
[[li process termination|process termination]]
- summary
- what can cause the termination of a [[li process]] (with details)

Back: 
## [[li process termination|process termination]]
- When a [[li process]] terminates, all of its resources ([[li memory]], [[li file descriptor]]...) are released by the [[li kernel]]
- open files are flushed and closed
- the [[li return code]] is returned to the [[li parent process]] (reaping)
- li processes can terminate on their own, can be killed or asked to terminate by a [[li signal]]


## self termination
- a [[li process]] can terminate itself usging the [[li exit]] [[li syscall]]

#### [[li exit|exit]]
- [[li syscall]] that terminates the calling [[li process]] including all its threads imidiatly
- the [[li kernel]] releases all resources allocated to the calling [[li process]]
- open [[li file descriptor]] if the [[li process]] are closed
- any children of the process are inherited by the [[li process]] with the [[li process id]] 1 (usually the [[li init process]]) → [[li orphan process]]

## based on a [[li signal]] from the [[li kernel]]
- the [[li kernel]] can send differnt [[li signal|signals]] to a [[li process]] causing it to terminate
- some of them are based on an illigal action of an error like `SIGILL 4` (Illegal instruction)
- some of them can be handled or even ignored by the [[li process]] itself like `SIGTERM 15`
- some of them can not be irgoned and terminte the [[li process]] abrubtly with an error like `SIGKILL 9`

#### SIGKILL 9
- kills the [[li process]] abruptly
- producing a fatal error. 
- cannot be irgnored

#### SIGILL 4 (Illegal instruction)
- kills the [[li process]] abruptly
- sent by the [[li kernel]] when the [[li process]] execute an invalid, privileged, or ill-formed instruction
- cannot be ignored.

#### SIGTERM 15
- tells the [[li process]] to exit cleanly. 
- can be ignored or handled in various ways

Tags: code linux
<!--ID: 1702578315616-->
END


START
Basic
[[li process termination|process termination]]
- summary
- what happens when a [[li parent process]] terminates before its [[li child process]]
- what happens after the termination of a [[li process]]

Back: 
## [[li process termination|process termination]]
- When a [[li process]] terminates, all of its resources ([[li memory]], [[li file descriptor]]...) are released by the [[li kernel]]
- open files are flushed and closed
- the [[li return code]] is returned to the [[li parent process]] (reaping)
- li processes can terminate on their own, can be killed or asked to terminate by a [[li signal]]

## reaping of the [[li return code]]
- when a [[li child process]] exits, some [[li process]] (usualy the [[li parent process]]) must always [[li wait|wait]] for its [[li return code]]
- after the termination, the [[li return code]] is stored in the [[li process table]] until its read (reaped) by tha [[li parent process]]
- if a [[li process]] terminates before its [[li child process]] the [[li init process]] (with `PID` 1) inherents all [[li child process]] ([[li orphan process]]) and the responsability to reap the [[li return code]]
- If the parent fails to call `wait`, the process table entry sticks around — and that's what makes it a "zombie".

#### [[li return code|return code]]
- Integer code returned to a [[li parent process]] by an [[li process]] when terminating (success or failure)
- a [[li parent process]] can capture the [[li return code]] of its [[li child process|child processes]] using the [[li syscall]] [[li wait]] which is waiting till the [[li child process]] terminated and returs is [[li return code]]
- the [[li return code]] is stored in the [[li process table]] untill the [[li parent process]] requested (reaped) it
- a [[li process]] that is [[li process termination|terminated]] will stay in the [[li process table]] until the [[li parent process]] requested its [[li return code]] 
- `0` in case of a success and `1 to 255` for everything else


#### [[li process table|process table]]
- maintained by the [[li kernel]]
- arry that contains the [[li process control block|process control blocks]] for all of the current [[li process|processes]] in the system


#### [[li orphan process|orphan process]]
- every [[li process]] needs a [[li parent process]] that is requesting its [[li return code]] after its [[li process termination|termination]] to remove its from the [[li process table]]
- if a [[li process]] [[li process termination|terminates]] and without termination its [[li child process]] the [[li init process]] will inherent all [[li child process]]
- the [[li init process]] automatically reaps its children (adopted or otherwise). 
	→ So if you exit without cleaning up your children, then they will not become zombies
- Between the time a child exits and is reaped, it is called a [[li zombie process]]. 

#### [[li zombie process|zombie process]]
- after a [[li process]] is [[li process termination|terminated]] its resources ([[li memory]], open [[li file]] etc.) are released, but it stays in the [[li process table]] untill the [[li parent process]] requested its [[li return code]] using [[li wait]]
- in the time between the [[li process]] termination and the requesting of the [[li return code]] the [[li process]] is a [[li zombie process]]



Tags: code linux
<!--ID: 1702578315619-->
END


START
Basic


Back: 


Tags: code linux

END