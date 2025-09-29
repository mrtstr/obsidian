## library crates
- way to expose compiled code to other **programs or [[r crate]]**.
- generated during the [[compiler#code generation]] and**not executable** themselves
- inputs to the [[compiler#linking]] process (dynamic or static) and for dynamic libs loaded at runtime
- **ABI** = how functions/data look at the binary boundary (calling convention, name mangling, layout…).
    
### lib / rlib
- Intermediate/static artifact produced by the [[r compiler]] and for the [[r compiler]]
- for static [[compiler#linking]]
- `*.rlib` (Rust static artifact) file

### dylib / cdylib
- library for dynamic [[compiler#linking]] can be used as interface to other languages
-  files types depend on the operating system
	- `.so` for [[linux]]
	- `.dylib` for macOS 
	- `.dll` for window
- available in two different ABIs
	- `dylib`: uses **Rust ABI** (unstable and rare)
	-  `cdylib`: uses **C-ABI** = the stable, widely supported ABI used by C. Most languages (Python, Ruby, Java via JNI, etc.) can interop with it.


### staticlib
- **Static** C-ABI library (`.a`/`.lib`)
- Final archive of object files linked **at build time** into a host program
- **Consumer:** Non-Rust linkers (C/C++/Swift, etc.).

# ----------

![[compiler#compiler]]
# anki

START
Basic
[[r library crates]]
- general concept
- 3 different types
- intended consumer and how they are used during linking / runtime

Back: 
## rust library crates
- way to expose compiled code to other **programs or crates**.
- generated during the [[compiler#code generation]] and**not executable** themselves
- inputs to the [[compiler#linking]] process (dynamic or static) and for dynamic libs loaded at runtime
- **ABI** = how functions/data look at the binary boundary (calling convention, name mangling, layout…).
    
### lib / rlib
- Intermediate/static artifact produced by the [[r compiler]] and for the [[r compiler]]
- for static [[compiler#linking]]
- `*.rlib` (Rust static artifact) file

### dylib / cdylib
- library for dynamic [[compiler#linking]] can be used as interface to other languages
-  files types depend on the operating system
	- `.so` for [[linux]]
	- `.dylib` for macOS 
	- `.dll` for window
- available in two different ABIs
	- `dylib`: uses **Rust ABI** (unstable and rare)
	-  `cdylib`: uses **C-ABI** = the stable, widely supported ABI used by C. Most languages (Python, Ruby, Java via JNI, etc.) can interop with it.


### staticlib
- **Static** C-ABI library (`.a`/`.lib`)
- Final archive of object files linked **at build time** into a host program
- **Consumer:** Non-Rust linkers (C/C++/Swift, etc.).


_______________

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

Tags: code rust
<!--ID: 1759138897663-->
END