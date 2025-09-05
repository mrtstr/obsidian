## compiler
- translates source code in binary code

```
Source Code
   ↓
Lexical Analysis → Tokens
   ↓
Syntax Analysis → AST
   ↓
Semantic Analysis → Checked AST + Symbol Table
   ↓
Intermediate Representation (IR)
   ↓
Optimization → Optimized IR
   ↓
Code Generation → Assembly/Machine Code
   ↓
Linking → Executable
```
#### tokenizing

```rust
let x = 42 + 1;
```

→ Tokens: `let` | `x` | `=` | `42` | `+` | `1` | `;`

#### syntax analysis
- build an abstract syntax tree
- check for syntactic correctness

```scss
Assignment
├── Identifier(x)
└── BinaryExpr(+)
    ├── Literal(42)
    └── Literal(1)
```
#### semantic analysis
- check if the meaning of the AST makes sense:
	- Type checking (e.g., you can’t add a string and a number).
	- Scope and name resolution (ensuring variables and functions exist where used).
	- Enforcing language rules (e.g., `return` only inside functions).

#### intermediate representation
- convert the code into a non human-readable compiler internal programming language that is used during the optimization
- designed to have the following properties
	- **Language-agnostic** → works for many source languages.
	- **Machine-agnostic** → not tied to any single CPU or architecture.
	- **Easy to analyze and optimize** → simpler than real source code, but structured enough to represent complex programs.
- often multiple layer: High-Level IR → Medium-Level IR → Low-Level IR
- example in [[rust]] and C/C++ the Low-Level IR [[LLVM IR]] is used

![[LLVM IR#LLVM IR]]
#### optimization
- optimize the IR to make the program faster without changing its meaning

#### code generation
- generate [[assembly]] instruction based on the CPU architecture
- each Rust source file ([[r crate]] or module) is compiled into an **object file** (`.o` or `.rlib`) separately
- in [[rust]] the binary already contains 
	- all installed [[r crate]]
	- the program itself
	- all layers of the standard library [[r std]], [[r core]] and [[r alloc]]
- creates the final executable binary
##### example

```asm
add:                   ; function label
    mov eax, edi       ; move first argument (a) into eax
    add eax, esi       ; add second argument (b) to eax
    ret                ; return result in eax
```

- convert it to binary [[assembly]]

```csharp
89 f8    ; mov eax, edi
01 f0    ; add eax, esi
c3       ; ret
```

#### linking
- since each [[r object file]] (`.o`, `.obj`) is separate they contain references to symbols in other [[r object file]] ([[r std]], other [[r crate]]...) or the [[system C libraries]]
- during the linking these references are resolved
	- if its a [[rust]] [[r crate]] → copy the code (static linking)
	- if its a [[system C libraries]] → marked as external and resolved at run time (dynamic linking)
- the final layout of the [[li virtual memory]] of the is fixed → memory addresses are assigned

##### **Static vs Dynamic Linking — General Concept**
- **Static linking**: the code from a library (like `libc.a`) is copied into your binary.
    - Pros: no external dependencies at runtime, fully self-contained.
    - Cons: bigger binaries, harder to update (you must rebuild if libc gets patched).
- **Dynamic linking**: the binary contains only references, and the library (`libc.so`, `libstdc++.so`) is loaded at runtime by the OS loader.
    - Pros: smaller binaries, security updates to libc apply instantly.
    - Cons: program won’t run if the right `.so` is missing or incompatible.

# anki

START
Basic
[[compiler]]
- explain the 7 steps with reference to [[rust]]

Back: 
## compiler
- translates source code in binary code

```
Source Code
   ↓
Lexical Analysis → Tokens
   ↓
Syntax Analysis → AST
   ↓
Semantic Analysis → Checked AST + Symbol Table
   ↓
Intermediate Representation (IR)
   ↓
Optimization → Optimized IR
   ↓
Code Generation → Assembly/Machine Code
   ↓
Linking → Executable
```
#### tokenizing

```rust
let x = 42 + 1;
```

→ Tokens: `let` | `x` | `=` | `42` | `+` | `1` | `;`

#### syntax analysis
- build an abstract syntax tree
- check for syntactic correctness

```scss
Assignment
├── Identifier(x)
└── BinaryExpr(+)
    ├── Literal(42)
    └── Literal(1)
```
#### semantic analysis
- check if the meaning of the AST makes sense:
	- Type checking (e.g., you can’t add a string and a number).
	- Scope and name resolution (ensuring variables and functions exist where used).
	- Enforcing language rules (e.g., `return` only inside functions).

#### intermediate representation
- convert the code into a non human-readable compiler internal programming language that is used during the optimization
- designed to have the following properties
	- **Language-agnostic** → works for many source languages.
	- **Machine-agnostic** → not tied to any single CPU or architecture.
	- **Easy to analyze and optimize** → simpler than real source code, but structured enough to represent complex programs.
- often multiple layer: High-Level IR → Medium-Level IR → Low-Level IR
- example in [[rust]] and C/C++ the Low-Level IR [[LLVM IR]] is used

###### LLVM IR
low level intermediate representation used in the [[compiler]] of multiple languages like [[rust]], C/C++, julia


```
define i32 @add(i32 %a, i32 %b) {
entry:
    %sum = add i32 %a, %b
    ret i32 %sum
}
```
#### optimization
- optimize the IR to make the program faster without changing its meaning

#### code generation
- generate [[assembly]] instruction based on the CPU architecture
- each Rust source file ([[r crate]] or module) is compiled into an **object file** (`.o` or `.rlib`) separately
- in [[rust]] the binary already contains 
	- all installed [[r crate]]
	- the program itself
	- all layers of the standard library [[r std]], [[r core]] and [[r alloc]]
- creates the final executable binary
##### example

```asm
add:                   ; function label
    mov eax, edi       ; move first argument (a) into eax
    add eax, esi       ; add second argument (b) to eax
    ret                ; return result in eax
```

- convert it to binary [[assembly]]

```csharp
89 f8    ; mov eax, edi
01 f0    ; add eax, esi
c3       ; ret
```

#### linking
- since each [[r object file]] (`.o`, `.obj`) is separate they contain references to symbols in other [[r object file]] ([[r std]], other [[r crate]]...) or the [[system C libraries]]
- during the linking these references are resolved
	- if its a [[rust]] [[r crate]] → copy the code (static linking)
	- if its a [[system C libraries]] → marked as external and resolved at run time (dynamic linking)
- the final layout of the [[li virtual memory]] of the is fixed → memory addresses are assigned

____________

### system C libraries
- the [[system C libraries]] called **libc** is provided by the operating system
- abstraction layer on top of the [[li syscall]]
- used across all programming languages
- for example `printf`, `malloc`, `fopen` wraps the [[li syscall]] [[li open]] [[li write]] and [[li read]]
- in [[rust]] the [[system C libraries]] are mapped during the [[compiler#linking]] and resolved at runtime

```
Rust code (println!)
   ↓
Rust std (formatting, buffering)
   ↓
libc (write, malloc, etc.)
   ↓
syscall (kernel interface)
   ↓
Operating System Kernel
   ↓
Hardware
```

Tags: code rust
<!--ID: 1757090121523-->
END


START
Basic
what happens in [[rust]] during linking and code generation?
what is the difference between static and dynamic linking?

Back: 

#### code generation
- generate [[assembly]] instruction based on the CPU architecture
- each Rust source file ([[r crate]] or module) is compiled into an **object file** (`.o` or `.rlib`) separately
- in [[rust]] the binary already contains 
	- all installed [[r crate]]
	- the program itself
	- all layers of the standard library [[r std]], [[r core]] and [[r alloc]]

##### example

```asm
add:                   ; function label
    mov eax, edi       ; move first argument (a) into eax
    add eax, esi       ; add second argument (b) to eax
    ret                ; return result in eax
```

- convert it to binary [[assembly]]

```csharp
89 f8    ; mov eax, edi
01 f0    ; add eax, esi
c3       ; ret
```

#### linking
- since each [[r object file]] (`.o`, `.obj`) is separate they contain references to symbols in other [[r object file]] ([[r std]], other [[r crate]]...) or the [[system C libraries]]
- during the linking these references are resolved
	- if its a [[rust]] [[r crate]] → copy the code (static linking)
	- if its a [[system C libraries]] → marked as external and resolved at run time (dynamic linking)
- the final layout of the [[li virtual memory]] of the is fixed → memory addresses are assigned
- creates the final executable binary

##### **Static vs Dynamic Linking — General Concept**
- **Static linking**: the code from a library (like `libc.a`) is copied into your binary.
    - Pros: no external dependencies at runtime, fully self-contained.
    - Cons: bigger binaries, harder to update (you must rebuild if libc gets patched).
- **Dynamic linking**: the binary contains only references, and the library (`libc.so`, `libstdc++.so`) is loaded at runtime by the OS loader.
    - Pros: smaller binaries, security updates to libc apply instantly.
    - Cons: program won’t run if the right `.so` is missing or incompatible.
_________________

### system C libraries
- the [[system C libraries]] called **libc** is provided by the operating system
- abstraction layer on top of the [[li syscall]]
- used across all programming languages
- for example `printf`, `malloc`, `fopen` wraps the [[li syscall]] [[li open]] [[li write]] and [[li read]]
- in [[rust]] the [[system C libraries]] are mapped during the [[compiler#linking]] and resolved at runtime

```
Rust code (println!)
   ↓
Rust std (formatting, buffering)
   ↓
libc (write, malloc, etc.)
   ↓
syscall (kernel interface)
   ↓
Operating System Kernel
   ↓
Hardware
```

## compiler
- translates source code in binary code

```
Source Code
   ↓
Lexical Analysis → Tokens
   ↓
Syntax Analysis → AST
   ↓
Semantic Analysis → Checked AST + Symbol Table
   ↓
Intermediate Representation (IR)
   ↓
Optimization → Optimized IR
   ↓
Code Generation → Assembly/Machine Code
   ↓
Linking → Executable
```
#### tokenizing

```rust
let x = 42 + 1;
```

→ Tokens: `let` | `x` | `=` | `42` | `+` | `1` | `;`

#### syntax analysis
- build an abstract syntax tree
- check for syntactic correctness

```scss
Assignment
├── Identifier(x)
└── BinaryExpr(+)
    ├── Literal(42)
    └── Literal(1)
```
#### semantic analysis
- check if the meaning of the AST makes sense:
	- Type checking (e.g., you can’t add a string and a number).
	- Scope and name resolution (ensuring variables and functions exist where used).
	- Enforcing language rules (e.g., `return` only inside functions).

#### intermediate representation
- convert the code into a non human-readable compiler internal programming language that is used during the optimization
- designed to have the following properties
	- **Language-agnostic** → works for many source languages.
	- **Machine-agnostic** → not tied to any single CPU or architecture.
	- **Easy to analyze and optimize** → simpler than real source code, but structured enough to represent complex programs.
- often multiple layer: High-Level IR → Medium-Level IR → Low-Level IR
- example in [[rust]] and C/C++ the Low-Level IR [[LLVM IR]] is used

###### LLVM IR
low level intermediate representation used in the [[compiler]] of multiple languages like [[rust]], C/C++, julia


```
define i32 @add(i32 %a, i32 %b) {
entry:
    %sum = add i32 %a, %b
    ret i32 %sum
}
```
#### optimization
- optimize the IR to make the program faster without changing its meaning

#### code generation
- generate [[assembly]] instruction based on the CPU architecture
- each Rust source file ([[r crate]] or module) is compiled into an **object file** (`.o` or `.rlib`) separately
- in [[rust]] the binary already contains 
	- all installed [[r crate]]
	- the program itself
	- all layers of the standard library [[r std]], [[r core]] and [[r alloc]]

##### example

```asm
add:                   ; function label
    mov eax, edi       ; move first argument (a) into eax
    add eax, esi       ; add second argument (b) to eax
    ret                ; return result in eax
```

- convert it to binary [[assembly]]

```csharp
89 f8    ; mov eax, edi
01 f0    ; add eax, esi
c3       ; ret
```

#### linking
- since each [[r object file]] (`.o`, `.obj`) is separate they contain references to symbols in other [[r object file]] ([[r std]], other [[r crate]]...) or the [[system C libraries]]
- during the linking these references are resolved
	- if its a [[rust]] [[r crate]] → copy the code (static linking)
	- if its a [[system C libraries]] → marked as external and resolved at run time (dynamic linking)
- the final layout of the [[li virtual memory]] of the is fixed → memory addresses are assigned
- creates the final executable binary

Tags: code rust
<!--ID: 1757090121526-->
END




START
Basic
what are following files used for and when are they created?
- `.o`/`.obj`
- `.rlib`
- `.so`
Back: 

- `.o`/`.obj` → binary of source file after code gen
- `.rlib` → contains collection of `.o`/`.obj` files with metadata that is created during code gen and is not executable but linkable
- `.so` → shared library like [[system C libraries]]
#### code generation
- generate [[assembly]] instruction based on the CPU architecture
- each Rust source file ([[r crate]] or module) is compiled into an **object file** (`.o` or `.rlib`) separately
- in [[rust]] the binary already contains 
	- all installed [[r crate]]
	- the program itself
	- all layers of the standard library [[r std]], [[r core]] and [[r alloc]]

##### example

```asm
add:                   ; function label
    mov eax, edi       ; move first argument (a) into eax
    add eax, esi       ; add second argument (b) to eax
    ret                ; return result in eax
```

- convert it to binary [[assembly]]

```csharp
89 f8    ; mov eax, edi
01 f0    ; add eax, esi
c3       ; ret
```

#### linking
- since each [[r object file]] (`.o`, `.obj`) is separate they contain references to symbols in other [[r object file]] ([[r std]], other [[r crate]]...) or the [[system C libraries]]
- during the linking these references are resolved
	- if its a [[rust]] [[r crate]] → copy the code (static linking)
	- if its a [[system C libraries]] → marked as external and resolved at run time (dynamic linking)
- the final layout of the [[li virtual memory]] of the is fixed → memory addresses are assigned
- creates the final executable binary

##### **Static vs Dynamic Linking — General Concept**
- **Static linking**: the code from a library (like `libc.a`) is copied into your binary.
    - Pros: no external dependencies at runtime, fully self-contained.
    - Cons: bigger binaries, harder to update (you must rebuild if libc gets patched).
- **Dynamic linking**: the binary contains only references, and the library (`libc.so`, `libstdc++.so`) is loaded at runtime by the OS loader.
    - Pros: smaller binaries, security updates to libc apply instantly.
    - Cons: program won’t run if the right `.so` is missing or incompatible.
_________________

### system C libraries
- the [[system C libraries]] called **libc** is provided by the operating system
- abstraction layer on top of the [[li syscall]]
- used across all programming languages
- for example `printf`, `malloc`, `fopen` wraps the [[li syscall]] [[li open]] [[li write]] and [[li read]]
- in [[rust]] the [[system C libraries]] are mapped during the [[compiler#linking]] and resolved at runtime

```
Rust code (println!)
   ↓
Rust std (formatting, buffering)
   ↓
libc (write, malloc, etc.)
   ↓
syscall (kernel interface)
   ↓
Operating System Kernel
   ↓
Hardware
```

## compiler
- translates source code in binary code

```
Source Code
   ↓
Lexical Analysis → Tokens
   ↓
Syntax Analysis → AST
   ↓
Semantic Analysis → Checked AST + Symbol Table
   ↓
Intermediate Representation (IR)
   ↓
Optimization → Optimized IR
   ↓
Code Generation → Assembly/Machine Code
   ↓
Linking → Executable
```
#### tokenizing

```rust
let x = 42 + 1;
```

→ Tokens: `let` | `x` | `=` | `42` | `+` | `1` | `;`

#### syntax analysis
- build an abstract syntax tree
- check for syntactic correctness

```scss
Assignment
├── Identifier(x)
└── BinaryExpr(+)
    ├── Literal(42)
    └── Literal(1)
```
#### semantic analysis
- check if the meaning of the AST makes sense:
	- Type checking (e.g., you can’t add a string and a number).
	- Scope and name resolution (ensuring variables and functions exist where used).
	- Enforcing language rules (e.g., `return` only inside functions).

#### intermediate representation
- convert the code into a non human-readable compiler internal programming language that is used during the optimization
- designed to have the following properties
	- **Language-agnostic** → works for many source languages.
	- **Machine-agnostic** → not tied to any single CPU or architecture.
	- **Easy to analyze and optimize** → simpler than real source code, but structured enough to represent complex programs.
- often multiple layer: High-Level IR → Medium-Level IR → Low-Level IR
- example in [[rust]] and C/C++ the Low-Level IR [[LLVM IR]] is used

###### LLVM IR
low level intermediate representation used in the [[compiler]] of multiple languages like [[rust]], C/C++, julia


```
define i32 @add(i32 %a, i32 %b) {
entry:
    %sum = add i32 %a, %b
    ret i32 %sum
}
```
#### optimization
- optimize the IR to make the program faster without changing its meaning

#### code generation
- generate [[assembly]] instruction based on the CPU architecture
- each Rust source file ([[r crate]] or module) is compiled into an **object file** (`.o` or `.rlib`) separately
- in [[rust]] the binary already contains 
	- all installed [[r crate]]
	- the program itself
	- all layers of the standard library [[r std]], [[r core]] and [[r alloc]]

##### example

```asm
add:                   ; function label
    mov eax, edi       ; move first argument (a) into eax
    add eax, esi       ; add second argument (b) to eax
    ret                ; return result in eax
```

- convert it to binary [[assembly]]

```csharp
89 f8    ; mov eax, edi
01 f0    ; add eax, esi
c3       ; ret
```

#### linking
- since each [[r object file]] (`.o`, `.obj`) is separate they contain references to symbols in other [[r object file]] ([[r std]], other [[r crate]]...) or the [[system C libraries]]
- during the linking these references are resolved
	- if its a [[rust]] [[r crate]] → copy the code (static linking)
	- if its a [[system C libraries]] → marked as external and resolved at run time (dynamic linking)
- the final layout of the [[li virtual memory]] of the is fixed → memory addresses are assigned
- creates the final executable binary

Tags: code rust
<!--ID: 1757090121531-->
END