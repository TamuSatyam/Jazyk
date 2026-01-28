# Jazyk Architecture

> **Note:** This document will be updated as the compiler is developed. It serves as both planning doc and reference.

## Overview

Jazyk compiler is implemented in C using LLVM for code generation. The compilation pipeline follows a traditional design:
```
Source Code (.jqz)
    ↓
[Lexer] → Tokens
    ↓
[Parser] → Abstract Syntax Tree (AST)
    ↓
[Semantic Analysis] → Typed AST
    ↓
[LLVM IR Generation] → LLVM IR
    ↓
[LLVM Optimization + Codegen] → Native Binary
```

## Components

### Lexer
**Status:** Not implemented
**Purpose:** Tokenize source code into meaningful units

- Input: Raw `.jqz` source code
- Output: Stream of tokens
- Handles: Keywords, identifiers, literals, operators, symbols
- Special: `@(...)` interpolation syntax in strings

### Parser  
**Status:** Not implemented
**Purpose:** Build Abstract Syntax Tree from tokens

- Technique: Recursive descent parsing
- Grammar: (To be defined in BNF)
- Output: AST representation

### Type System
**Status:** Design phase
**Purpose:** Static type checking with inference

Planned features:
- Primitive types: `int`, `float`, `bool`, `char`, `string`
- Compound types: Arrays, structs
- Type inference for `var` declarations
- Union types: `int | float`
- Structural typing (TypeScript-inspired)

### Memory Management
**Status:** Design phase
**Approach:** Manual allocation/deallocation

- `malloc(size)` - allocate heap memory
- `free(ptr)` - deallocate memory
- No garbage collection
- No automatic reference counting
- Explicit ownership model (to be defined)

### Code Generation
**Status:** Not implemented
**Backend:** LLVM

- Target: Native binaries via LLVM
- Optimization: LLVM's optimization passes
- Platform: Initially x86-64 Linux

## Design Decisions

### Why C?
Learning manual memory management, understanding pointers, staying close to the metal so it's easier to blow up our legs.

### Why LLVM?
Industry standard, excellent documentation, handles platform-specific codegen, most importantly, I am dumb.

### Why Manual Memory?
Educational focus - understanding how memory works is crucial for security and also because I can!

## Future Considerations

- JIT compilation support
- REPL for interactive development
- Debugger integration
- LSP (Language Server Protocol) implementation

---

*This document will evolve with the project. Current status: Planning.*
