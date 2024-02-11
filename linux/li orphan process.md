## [[li orphan process|orphan process]]
- every [[li process]] needs a [[li parent process]] that is requesting its [[li return code]] after its [[li process termination|termination]] to remove its from the [[li process table]]
- if a [[li process]] [[li process termination|terminates]] and without termination its [[li child process]] the [[li init process]] will inherent all [[li child process]]
- the [[li init process]] automatically reaps its children (adopted or otherwise). 
	→ So if you exit without cleaning up your children, then they will not become zombies 


## [[python]] example for creating an [[li orphan process]]
1) create a cain of [[li parent process]]:` <main>` → `<_create_orphan>` → `<actual orphan (sleep)>`
2) terminate the process `<_create_orphan>`
	→ `<actual orphan (sleep)>` will be inherented by the [[li init process]] because its [[li parent process]] is termianted

```python
from multiprocessing import Process
from time import sleep

def create_orphan(func, *args, **kwargs):
	p = Process(
		target=_create_orphan, 
		args=args, 
		kwargs=kwargs | {"func":func}
	)
	p.start()
	sleep(1)
	p.terminate()

def _create_orphan(*args, **kwargs):
	target = kwargs.pop("func")
	p = Process(target = target, args=args, kwargs=kwargs)
	p.start()
	print(f"PID {p.pid}")

if __name__ == "__main__":
	create_orphan(sleep, 120)
```

## relevant
![[li process table#li process table process table]]


# Anki

START
Basic
- what is a [[li orphan process]]

Back: 
## [[li orphan process|orphan process]]
- every [[li process]] needs a [[li parent process]] that is requesting its [[li return code]] after its [[li process termination|termination]] to remove its from the [[li process table]]
- if a [[li process]] [[li process termination|terminates]] and without termination its [[li child process]] the [[li init process]] will inherent all [[li child process]]
- the [[li init process]] automatically reaps its children (adopted or otherwise). 
	→ So if you exit without cleaning up your children, then they will not become zombies

### [[li return code|return code]]
- Integer code returned to a [[li parent process]] by an [[li process]] when terminating (success or failure)
- a [[li parent process]] can capture the [[li return code]] of its [[li child process|child processes]] using the [[li syscall]] [[li wait]] which is waiting till the [[li child process]] terminated and returs is [[li return code]]
- the [[li return code]] is stored in the [[li process table]] untill the [[li parent process]] requested (reaped) it
- a [[li process]] that is [[li process termination|terminated]] will stay in the [[li process table]] until the [[li parent process]] requested its [[li return code]] 
- `0` in case of a success and `1 to 255` for everything else

Tags: code linux
<!--ID: 1702578315626-->
END

START
Basic
- python example for creating an [[li orphan process]]

Back: 
1) create a cain of [[li parent process]]:` <main>` → `<_create_orphan>` → `<actual orphan (sleep)>`
2) terminate the process `<_create_orphan>`
	→ `<actual orphan (sleep)>` will be inherented by the [[li init process]] because its [[li parent process]] is termianted

```python
from multiprocessing import Process
from time import sleep

def create_orphan(func, *args, **kwargs):
	p = Process(
		target=_create_orphan, 
		args=args, 
		kwargs=kwargs | {"func":func}
	)
	p.start()
	sleep(1)
	p.terminate()

def _create_orphan(*args, **kwargs):
	target = kwargs.pop("func")
	p = Process(target = target, args=args, kwargs=kwargs)
	p.start()
	print(f"PID {p.pid}")

if __name__ == "__main__":
	create_orphan(sleep, 120)
```

## [[li orphan process|orphan process]]
- every [[li process]] needs a [[li parent process]] that is requesting its [[li return code]] after its [[li process termination|termination]] to remove its from the [[li process table]]
- if a [[li process]] [[li process termination|terminates]] and without termination its [[li child process]] the [[li init process]] will inherent all [[li child process]]
- the [[li init process]] automatically reaps its children (adopted or otherwise). 
	→ So if you exit without cleaning up your children, then they will not become zombies


Tags: code linux
<!--ID: 1702578315628-->
END