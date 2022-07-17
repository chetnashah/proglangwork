

### Definition

Does both parsing and evaluation of expressions, both at runtime.
Can think of interpeter as a virtual machine whose source program is high level language.
Modern cpu is a good example of an interpreter which does `fetch,decode,execute`.

An interpreter for language `X` is a program (or a machine, or just some kind of mechanism in general) that `executes any program p` written in language X such that it `performs the effects and evaluates the results as prescribed by the specification of X`. 

CPUs are usually interpreters for their respective instructions sets, although modern high-performance workstation CPUs are actually more complex than that; they may actually have an underlying proprietary private instruction set and either translate (compile) or interpret the externally visible public instruction set.

Semantic error checking happens at runtime

Typically an interpreter will run tree walk routines like `eval` on source language ASTs.

## Frontend

Tokenization, parsing and AST creation

## Parse tree

In order to generate a valid parse tree, a CFG grammar is needed, since the parse tree is organized accordingly.

A CFG is known to define syntax of a language and are specified in EBNF syntax.


## JIT vs interpreter

With JVM, both interpreter and compiler (the JVM compiler and not the source-code compiler like javac) produce native code (aka Machine language code for the underlying physical CPU like x86) from byte code.

Interpreters will typically do line by line machine code execution (usually a lookup table), no scope for multi-line analysis or optimization.

Where as JIT can do multi line analysis/optimized native code. Typically in JVM interpreter stats are collected to find hotspots, which would serve as candidates for compilation and save time in future to interpretation.
