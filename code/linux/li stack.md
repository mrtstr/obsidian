## [[li stack]]
- segment inside the [[li virtual memory]] space of a [[li process]]
- execution memory of a [[li thread]] → a [[li process]] can have multiple [[li stack|stacks]]
- **Fixed size:**(set when the [[li thread]] is created)
- contains local variables, function arguments, and control information (e.g. adress pointers), including return addresses
- manages by the [[li memory management unit]] of the [[li kernel]]
- LIFO (Last-In-First-Out) data structure
- lifetime of data is limited to the end of the scope
- when a function is called the stack grows and when the function is exited everything is removed except the reurn values


# anki

START
Basic
## [[li stack]]
- concept
- size
- management

Back: 
- segment inside the [[li virtual memory]] space of a [[li process]]
- execution memory of a [[li thread]] → a [[li process]] can have multiple [[li stack|stacks]]
- **Fixed size:**(set when the [[li thread]] is created)
- contains local variables, function arguments, and control information (e.g. adress pointers), including return addresses
- manages by the [[li memory management unit]] of the [[li kernel]]
- LIFO (Last-In-First-Out) data structure
- lifetime of data is limited to the end of the scope
- when a function is called the stack grows and when the function is exited everything is removed except the reurn values
![[Program_memory_layout.pdf 5.jpg]]
Tags: code linux
<!--ID: 1701528585799-->
END