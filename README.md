Terminologies in Javascript
======
This is a collection of terminologies in Javascript. More like a reference book.

To help understand basic and advanced concepts in Javascript.

# Terms
---
### Call Stack
Call stack is where javascript stores the context of function calls.

Every time a function is called, the current context is put on top of this
“stack”. When the function returns, it removes the top context from the
stack and uses it to continue execution.
The call stack is very useful in debugging and makes up the Error stack when an error occured.
### Lexical Scoping
Lexical Scoping defines how variable names are resolved in nested functions: inner functions contain the scope of parent functions even if the parent function has returned. It is somewhat the same thing as Closures in Javascript
