---
publish: true
created: 2025-11-08T12:42:02.122+03:00
modified: 2026-05-27T17:00:03.207+03:00
---

## Types of PLs:

### Machine-Level Lang:

0's and 1's
horrible writability and readability

### Assembly-Level Lang:

### Middle-Level Lang:

C, C++

### High-Level Lang:

Java, Python, C#

## **Programming Paradigms**

### **Imperative**

Has variables, assignment, loops.

Example: C, Java, Python.

### **Functional**

Functions without state or mutable variables.

Example: Haskell, Scheme.

### **Logic**

Based on rules and inference.

Example: Prolog.

### **Object-Oriented**

Objects + classes + messages.

Example: Java, C++, Python.

- “Which paradigm is based on states?” → Imperative

- “Which paradigm uses inference engine?” → Logic

## Interpreter vs. Compiler

#### Compiler:

converts entire code into machine-level language

Pros:

- fast execution

- optimized code

Cons:

- slower compile times
-

#### Interpreter:

converts the code into machine-level language **line by line**

#### Hybrid

Compile to **intermediate form** then interpret/execute.

Examples:

- Java → bytecode → JVM

- C# → IL → CLR

> “Which method compiles to an intermediate form before execution?”

> → Hybrid

##  **Binding (BIG MCQ AREA)**

A **binding** is “a connection between an identifier and something else.”

Examples:

- variable → type

- variable → value <font color="#ffc000"> x = 5;</font>

- variable → memory address

- function → its body

### **Static Binding (compile-time)**

- type binding in C

- overloaded method resolution

- memory layout determination

### **Dynamic Binding (run-time)**

- Python variable types

- Java overridden methods (dynamic dispatch)

- values of variables

> “In Python, the type of a variable is determined at…”

> → Run-time → Dynamic binding 

#### **Static Type Checking**

Languages: C, Java, Rust.

#### **Dynamic Type Checking**

Languages: Python, JavaScript.

## **7. Scope (Another MCQ hotspot)**

### **Static Scope (Lexical Scope)**

Determined by the program’s layout/block structure.

C, Java, Python are lexical.

### **Dynamic Scope**

Depends on the call history/execution path.

No one uses

> “In static scope, references to a variable are determined by…”

> → the structure of the program (where the variable is defined)

## **Lifetime**

How long a variable stays in memory.

- **Static**: entire program run

- **Stack-dynamic**: created when function is called

- **Heap-dynamic**: allocated manually (malloc/new)

- “Local variables in a function have what lifetime?” → stack-dynamic

- “Global variables?” → static

-

## **Syntax vs Semantics**

### **Syntax**

### **Static Semantics**

Rules that are checked _before_ execution but are not syntax.

- type rules

- variable declarations

- scope rules

### **Dynamic Semantics**

What the program _means_ when it runs.

- how expressions evaluate

- what statements do

- the effect on memory

## Lexemes and Tokens

### **Lexeme**

The raw string from the source code.

Example: x, 5, while, +

### **Token**

The _category/type_ of the lexeme.

- IDENTIFIER

- NUMBER

- KEYWORD(while)

- OPERATOR(+)

### **Pattern**

The rule/regex describing what belongs to that token class.

## **Run-Time Organization**

- Data segment (global/static vars)

- Heap

- Stack (function calls, local vars)

MCQs usually ask:

> “Where are local variables stored?”

> → Stack

> “Where does dynamic allocation happen?”

> → Heap

**How does studying programming language concepts improve your ability to express ideas?**

Give an example comparing C++ and Python.

**What are the primary factors that influence the design of a programming language?**

###### **1. Readability**

How easy the language is to understand.

###### **2. Writability**

How easy it is to express solutions in the language.

###### **3. Reliability**

How safe and consistent the language is (type checking, error handling).

###### **4. Cost**

Cost of training, running, maintaining, implementing the language.

**Which factor most strongly affects the writability of a language?**

A) Number of data types

B) Simplicity & readability of syntax

C) Size of programming community

D) Execution speed

### Ambiguity

- **Ambiguous grammar**:

  A grammar that allows **multiple parse trees** for the same input.

- **Caused by**:

  No precedence, no associativity, sloppy rules.

- **Fixed by**:

  Making separate layers (expr, term, factor).

- **Why the professor cares**:

  Ambiguity = unclear meaning → compilers can’t handle it.

### **EBNF adds to BNF:**

- { } → repetition (zero or more, _same as regex_ _\*_)

- `[ ]` → optional

- ( ) → grouping

- - → one or more (in some variations)

- " " → literal strings

These let you avoid recursion for simple patterns.

#### Quick C++ bullshit:

`*p = &a
`\*`means pointer`&\` means the memory address of this var
