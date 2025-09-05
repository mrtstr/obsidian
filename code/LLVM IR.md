### LLVM IR
low level intermediate representation used in the [[compiler]] of multiple languages like [[rust]], C/C++, julia


```
define i32 @add(i32 %a, i32 %b) {
entry:
    %sum = add i32 %a, %b
    ret i32 %sum
}
```