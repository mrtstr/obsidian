## Command
```
kubectl exec <pod name> [-c <container name>] [options] -- <command>
```
### options
	i  Pass stdin to the container
	t  Stdin is a TTY


### Examples
#### open shell on [[pod]]
```
kubectl exec -it <pod name> -c <container name> -- /bin/bash
```

#### execute a file on [[pod]] and sent all outputs to local terminal
```
kubectl exec -it nowa-demand-forecast -- script.sh

```

#### execute a file in background without sending output to local terminal 
- sent all [[output streams]] to a file on the [[pod]] (&>)
- run the [[shell command]] in background (&)
```
kubectl exec <pod name> -- bash -c "python /root/hello.py &> output.log &"
```


START
Basic
run a command on a kubernetes [[pod]]
- command
- options
- examples:
	- open shell
	- execute command and pass output to local terminal
	- execute file in background and write output in file on pod
Back: 
## Command
```
kubectl exec <pod name> [-c <container name>] [options] -- <command>
```
### options
	i  Pass stdin to the container
	t  Stdin is a TTY


### Examples
#### open shell on [[pod]]
```
kubectl exec -it <pod name> -c <container name> -- /bin/bash
```

#### execute a file on [[pod]] and sent all outputs to local terminal
```
kubectl exec -it nowa-demand-forecast -- script.sh

```

#### execute a file in background without sending output to local terminal 
- sent all [[output streams]] to a file on the [[pod]] (&>)
- run the [[shell command]] in background (&)
```
kubectl exec <pod name> -- bash -c "python /root/hello.py &> output.log &"
```

Tags: code, kubernetes
<!--ID: 1666875324166-->
END