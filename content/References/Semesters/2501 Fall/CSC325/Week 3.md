---
publish: true
created: 2025-10-01T11:09:00.694+03:00
modified: 2026-05-27T17:00:02.990+03:00
---

## Notes from Zain

### Compilation process

_Forgot first one (slide 21)_

#### Syntax analyzer:

Checks syntax and grammar if its part of the PL. Creates a parse tree or abstract syntax tree (AST). Output: Shows statement order, block structure.

#### Semantic analysis:

Checks type checking error (undeclared variables or functions) and scope rules and makes sure operations make sense. (Cant add integer to string) Output: a verified AST with no semantic errors (if any errors found the compiler will produce with an error message)

#### Optimization:

Removes redundant operations, simplifies expressions and applies other optimizations. Output: optimized version of the code.

#### Code generation:

Translates optimized intermediate representation into machine code or assembly language.

#### Assembly:

Converts the assembly code into machine code (binary).

#### Linking:

Replaces function names and variables names with memory addresses and combines separate object files into one executable. Output: Final executable file. (.exe on Windows, or a binary file on Linux/Unix)

---

### Interpretation process

Will translate the entire program into machine
code beforehand, line by line.

- easier debugging
- more memory efficient
- slower program

#### Lexical Analysis (Tokenization)

Breaks down source code into tokens. Tokens are smallest units of meaning in the language such as keywords operations identifiers and literals.

#### Parsing (Syntax Analysis)

Checks sequence of tokens to ensure syntax is correct. Builds a parse tree that represents the logical structure of the program.

#### Semantic Analysis

Checks if the programs logic is correct.

#### Execution

The interpreter executes the code directly. The interpreter does not generate separate machine code file like a compiler, instead it executes code immediately.

#### Runtime Errors and Feedback

since the process is line by line it can encounter runtimes errors during execution. if it runs into an error it reports it immediately.

---

### Hybrid process

hybrid process is context of PLs that use both compilation and interpretation to execute a program Uses advantages of both compiling (efficient optimized machine code) and interpreting (blah blah).
Hybrid has two major components: Compilation and Interpretation.
Steps:

- Compilation to Intermediate code (Bytecode)
- Execution by Virtual Machine (VM)
- Just-In-Time (JIT) Compilation (Optional Optimization):
  improves performance.

---

### Compiler vs interpreter

_Check slide: 39_ & 40

---

#### Java example

java is compiled before program runs. If there is an error, the compiler will stop and report it, but the program won't execute.

```Java
public class Main {
	public static void main(String[] args) {
		int x = 10;
		int y = "text";
		System.out.println(x + y);
    }
}
```

#### Python example

In python (interpreted language), the program is executed line by line. Errors are caught as the code is executed. Error below is a runtime error.

```python
print("Hello World")
x = 10
10 y = "text"
print(x + y)
```

---

### Programming environments

#### Integrated Development Environment (IDE):

Comprehensive suit of tools like code editor, compiler, debugger and other utilities to support development process.

- Visual Studio
  For .NET and C++
- Eclipse
  For Java
- PyCharm
  For Python

#### Text Editors:

Lightweight tools used for writing code. not feature-rich like IDEs but can be customized with plugins for language specific features.

- Sublime Text
- Atom
- Notepad+++

#### Command Line Interface (CLI):

interface used for executing programs, running scripts, using version control system.

- Bash (Unix)
- PowerShell (Windows)
- Terminal (MacOS)

#### Online/Cloud Based:

Run code directly from a browser. These environments often offer collaborative features and eliminate need for setting up local development tools.

- Repl.it
- GitHub Codespaces
- Google Colab (for Python)

---
