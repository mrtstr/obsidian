## compiler
- translates source code in binary code

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

in [[rust]] the binary already contains 
- all installed [[r crate]]
- the program itself
- all layers of the standard library [[r std]], [[r core]] and [[r alloc]]

#### linking
- during the execution 
- The compiler can translate _each source file_ into an **object file** (`.o`, `.obj`) that contains machine code **plus placeholders** for things it doesn’t know yet (like “where is `printf` located in memory?”).
The **linker** resolves these placeholders.