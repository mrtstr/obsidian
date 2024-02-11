
## [[li zombie process|zombie process]]
- after a [[li process]] is [[li process termination|terminated]] its resources ([[li memory]], open [[li file]] etc.) are released, but it stays in the [[li process table]] untill the [[li parent process]] requested its [[li return code]] using [[li wait]]
- in the time between the [[li process]] termination and the requesting of the [[li return code]] the [[li process]] is a [[li zombie process]]
If the parent fails to call `wait`, the process table entry sticks around — and that's what makes it a "zombie".

## Relelvant
![[li wait#li wait wait]]

![[li return code#li return code return code]]


# Anki

START
Basic
what is a [[li zombie process]]
how is it created
how can it be removed
Back: 
## [[li zombie process|zombie process]]
- after a [[li process]] is [[li process termination|terminated]] its resources ([[li memory]], open [[li file]] etc.) are released, but it stays in the [[li process table]] untill the [[li parent process]] requested its [[li return code]] using [[li wait]]
- in the time between the [[li process]] termination and the requesting of the [[li return code]] the [[li process]] is a [[li zombie process]]

### [[li wait|wait]]
-  [[linux]] [[li syscall]] for waiting for the [[li process termination|termination]] of a [[li child process]] and requesting the [[li return code]] from the [[li process table]]
- even if a [[li process]] is [[li process termination|terminated]] it remains in the [[li process table]] untill its [[li return code]] is read/reaped

### [[li return code|return code]]
- Integer code returned to a [[li parent process]] by an [[li process]] when terminating (success or failure)
- a [[li parent process]] can capture the [[li return code]] of its [[li child process|child processes]] using the [[li syscall]] [[li wait]] which is waiting till the [[li child process]] terminated and returs is [[li return code]]
- the [[li return code]] is stored in the [[li process table]] untill the [[li parent process]] requested (reaped) it
- a [[li process]] that is [[li process termination|terminated]] will stay in the [[li process table]] until the [[li parent process]] requested its [[li return code]] 
- `0` in case of a success and `1 to 255` for everything else
Tags: code linux
<!--ID: 1702578315605-->
END