

### Compiler

Takes a source program and generates a target program which might be run at a later time.
Source to source translation (or preprocessors) can also be considered a compiler, but things like preprocessors
do simplistic replace and don't attempt to semantically understand the source language like compilers.
Many compilers generate assembly instead of machine language

### Tombstone diagram (T-diagram)

https://en.wikipedia.org/wiki/Tombstone_diagram

from a source language (left of T) to a target language (right of T) realised in an implementation language (bottom of T). 

## Bootstrapping

A typical bootstrap process works in three or four stages:

Stage 0: preparing an environment for the bootstrap compiler to work with.
Stage 1: the bootstrap compiler is produced.
Stage 2: a full compiler is produced by the bootstrap compiler.
Stage 3: a full compiler is produced by the stage 2 full compiler.
The full compiler is built twice in order to compare the outputs of the two stages. If they are different, either the bootstrap or the full compiler contains a bug.

You can write a really feeble C compiler in assembly or machine code, then bootstrap from there (You write a minimal compiler in assembler (yuck) for a minimal set of the language and then use that compiler to implement extra features of the language. Building your way up until you have a compiler with all the language features for itself).
Or hand assembling first compiler into machine code.

### Self hosting compilers

The process of creating a self-hosting compiler begins with a compiler implementation in a language that already exists. Coffeescript was originally written in Ruby. The Scala v2 compiler is also self-hosting, and its v1 was was written in Java. The first version of your new compiler needs to be able to parse your source files (written in your new language) and turn them into something that your computer can execute.

You then use the old compiler to compile your new one, and now you can throw away the old compiler in the original implementation language forever. You have new source code and a new runnable version of the compiler, so you have no need for the old versions any more. You can continue to swing up the ladder by writing a new version of the language using the current version, compiling it using the current version, and then throwing the current version away forever too.

v0 of a compiler might be written in a lower level language, but v1 onwards can start adding/augmenting features via high level programming itself.


