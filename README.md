# Jazyk

> *A language for educational suffering - fully documented so you understand exactly why your program crashed (probably).*

[![Status](https://img.shields.io/badge/Status-Code%20404-black)]()
[![License](https://img.shields.io/badge/License-GPL%20V3-white)](LICENSE)

## What is Jazyk?

Jazyk (pronounced "ya-zik", Ukrainian/Russian for "language") is an imperative, statically-typed compiled programming language with manual memory management. It's designed as an educational tool to teach:

- Compiler design and implementation
- Low-level memory management
- Type system internals  
- Common security vulnerabilities and exploitation techniques
- How to blow an entire leg off figuratively

**Think of it as:** C's simplicity + TypeScript's type system + the explicit goal of helping you understand how things break and how easily you can blow your entire leg off.

## Why Does This Exist?

Because understanding *why* programs crash is more valuable than pretending they never will. Jazyk embraces manual memory management with comprehensive documentation that explains every footgun, every undefined behavior, and every way you can blow your leg off.

This isn't a production language. This is a learning tool.

## Key Features (Planned)

- **Manual Memory Management** - Full control, full responsibility, more chances to mess up
- **TypeScript-inspired Type System** - Structural typing, union types, strong inference
- **String Interpolation** - `@(variable)` syntax for clean formatting
- **C-like Syntax** - Familiar but modernized
- **LLVM Backend** - Real compilation to native code
- **Extensive Documentation** - Every dangerous feature thoroughly explained
- **Educational Focus** - Built to teach, not to ship to production because you will probably crash the entire system

## Example (Concept)
```jqz
#include "stdio.jqz"

fun main() -> int {
    var name = "World";
    println("Hello @(name)!");
    
    // You're in charge of memory
    var buffer = malloc(256);
    // ... do stuff ...
    free(buffer);  // Don't forget!
    
    return 0;
}
```

## Project Status

**Currently in planning/design phase**

- [ ] Language specification
- [ ] Lexer implementation
- [ ] Parser implementation  
- [ ] Type checker
- [ ] LLVM IR generation
- [ ] Standard library
- [ ] Documentation site
- [ ] Example programs

## Philosophy

**Explicit over implicit.** If something allocates memory, you should know about it. If something can fail, you should handle it. If something is undefined behavior, we'll document exactly why.

**Education over production.** This language exists to teach compiler design and low-level programming concepts. It's intentionally designed to expose common pitfalls with clear documentation and also because I found the idea funny.

**Suffering with purpose.** Manual memory management is hard. Type systems are complex. Compilers are intricate. But understanding these things deeply makes you a better programmer (no refunds or guarantees).

## Development

Jazyk is being developed in C using LLVM on Alpine Linux (musl).

**Why C?** To understand memory management by practicing it and also because its the base to most modern languages.
**Why LLVM?** Industry-standard, well-documented, handles the hard parts and because I am too dumb to create everything from scratch.
**Why Alpine?** Minimal, clean, forces understanding of the full stack and so I can say, I use Alpine BTW.

## Contributing

With the nature of this project being of an educational type, external contributions are politely or if prompted violently rejected until a stable and satisfactory version is created. After which, contributions are open and welcomed!

However, **ideas, suggestions, and discussions are welcome!** Open an issue if you have thoughts.

## Documentation

Coming soon! The goal is to have documentation that explains:
- How the compiler works (implementation details)
- How the language works (user guide)
- Why things are designed this way (design decisions)
- How common mistakes happen (anti-patterns with explanations)

## Inspiration

- **C** - Syntax, simplicity, explicit control
- **TypeScript** - Type system design
- **HolyC** - Import philosophy (keep it simple)
- **Rust/Zig** - Modern features without excessive hand-holding

## License

GPL v3 License - if you are going to take my code, at least let me look at it too!

## Author

Built by someone learning compiler design while saving for an SSD in Nepal. 🇳🇵

If this project helped you learn something, give it a star!

---

**Note:** This project uses AI (Claude Sonnet 4.5, not Opus because I am broke) as a learning companion and rubber duck for bouncing ideas. Think of it as pair programming with a very patient partner who doesn't judge my 3AM questions or whenever I have questions in general.

*"I don't test my code, if you do find me testing it, it will be in production. Oh, wait this is not meant for production so no tests!"*
