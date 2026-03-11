# Scheme-to-x86-64 Compiler

## **Overview**
A high-performance compiler for a subset of the **Scheme** programming language, developed in **OCaml**. It translates source code into optimized **x86-64 Assembly**, producing standalone Linux executables through a custom-built compilation pipeline.

## **Key Features**
* **Functional Parsing**: Implements recursive descent parsing using a custom library of functional **parsing combinators**.
* **Advanced Semantic Analysis**: Handles lexical addressing (Param, Bound, Free), closure conversion, and environment nesting.
* **Low-Level Runtime**: Features a custom-engineered x86-64 runtime environment with **type-tagged data structures** (Closures, Pairs, Strings, Numbers) and memory management.
* **Core Constructs**: Full support for `lambda`, `if`, `let`, recursive applications, and S-expression literal constants.

## **Technical Stack**
* **Implementation Language**: OCaml (Functional Logic).
* **Target Architecture**: x86-64 Assembly (NASM syntax).
* **Toolchain**: Linux, NASM, GCC, Makefile.

## **Compilation Pipeline**
1.  **Read**: Converts raw strings into S-expressions using the parsing combinator library.
2.  **Tag-Parse**: Transforms S-expressions into an **Abstract Syntax Tree (AST)** representing the program structure.

3.  **Semantics**: Performs lexical scoping analysis, variable resolution, and optimizes variable access efficiency.
4.  **Code Gen**: Generates optimized x86-64 assembly instructions for each AST node, integrating with a custom prologue and epilogue.
5.  **Assembly & Link**: Assembles the generated code with **NASM** and links it with **GCC** to create the final executable.
