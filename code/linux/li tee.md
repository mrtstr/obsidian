## `tee`
`tee` sends its [[li stdin]] to a [[li file]] and its [[stdout]] 
```sh
ls | tee myfile
# write the current folders and file f1 and print out
ls | tee f1 > f2
# write the current folders and file f1 and f2 (dont print out)
ls | tee f1 | tee f2
# write the current folders and file f1 and f2 and print out
```

# anki

START
Basic
what does the [[li shell command]] `tee` do?
Back: 
`tee` sends its [[li stdin]] to a [[li file]] and its [[stdout]] 
```sh
ls | tee myfile
# write the current folders and file f1 and print out
ls | tee f1 > f2
# write the current folders and file f1 and f2 (dont print out)
ls | tee f1 | tee f2
# write the current folders and file f1 and f2 and print out
```
Tags: code linux
<!--ID: 1700412026087-->
END

START
Basic
 [[li shell command]] for the following:
- write the current folders and file f1 and print out
- write the current folders and file f1 and f2 (dont print out)
- write the current folders and file f1 and f2 and print out
Back: 
`tee` sends its [[li stdin]] to a [[li file]] and its [[stdout]] 
```sh
ls | tee myfile
# write the current folders and file f1 and print out
ls | tee f1 > f2
# write the current folders and file f1 and f2 (dont print out)
ls | tee f1 | tee f2
# write the current folders and file f1 and f2 and print out
```
Tags: code linux
<!--ID: 1700412026093-->
END