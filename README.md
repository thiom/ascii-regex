# Regular Expressions Interpreter

## Overview

This is an interpreter for regular expressions. It is a command-line app that takes a regex 
as an initial input. After that, it will read given input strings one by one and tell if the language (defined by the RE) 
recognizes them or not. The syntax of the regex is based on the formal definition of 
[regular expressions](https://en.wikipedia.org/wiki/Regular_expression) 
in their formal definition in 
[formal language theory](https://en.wikipedia.org/wiki/Formal_language).

Regexes will support the following operators:

|Operator  |Syntax  | Matches|
--- | --- | --- |
|Union | 0\|1 | "0" or "1"|  
|Star |a* | 0 or more "a"|
|Concatenation | ab | "a" followed by "b"|
|Group | (a\|b)* | 0 or more "a" or "b"|


## Implementation

An regular expression can be viewed as a simple programming language. The purpose of this program is to make the RE 
into an executable program that will read input strings and determine whether they belong to the language that is defined by the 
RE. The interpretation part of the program mostly follows common design patterns for writing interpreters. 
That is, there is a scanner (or lexer) that will read input as characters one by one and split it into tokens. These 
tokens will then be passed to the parser which will try to understand some syntactical structure from the input and 
construct an AST (abstract syntax tree). After that, the AST will be coverted into NFA (nondeterministic finite automaton) 
and the NFA will be converted into DFA (deterministic finite automaton). These two conversion are based on the 
techniques described in the books "Introduction to the Theory of Computation" and "Engineering a Compiler". 
Finally, the DFA will be used for testing if the language (defined by the regex) will recognize the 
input strings. 

![](https://github.com/thiom/tiralab/blob/main/docs/img/rs-regex-overview.png)

### Docs

[Usage instructions](./docs/user_guide.md)  

[Implementation](./docs/implementation_doc.pdf) 

