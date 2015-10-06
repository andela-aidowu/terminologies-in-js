Terminologies in Javascript
======
This is a collection of terminologies in Javascript. More like a reference book.

To help understand basic and advanced concepts in Javascript.

# Terms
---

<a name="call-stack" />
### Call Stack
Call stack is where javascript stores the context of function calls.

Every time a function is called, the current context is put on top of this
“stack”. When the function returns, it removes the top context from the
stack and uses it to continue execution.
The call stack is very useful in debugging and makes up the Error stack when an error occured.
<a name="higher-order" />
### Higher order functions
Functions that operate on other functions, either by taking them as arguments or by returning them, are called **higher-order functions**.
Higher-order functions allow us to abstract over actions, not just values.

Example:
```
function noisy(f) { 
    return function(arg) {
        console.log("calling with", arg);
        var val = f(arg);
        console.log("called with", arg, "- got", val); return val;
    }; 
}
```

Noisy is a higher-order function. Other common examples includes `Array.prototype.foreach` and other functions that take another function as it's argument (callbacks).
<a name="lexical-scoping" />
### Lexical Scoping
Lexical Scoping defines how variable names are resolved in nested functions: inner functions contain the scope of parent functions even if the parent function has returned. It is somewhat the same thing as Closures in Javascript.

<a name="pure-functions" />
### Pure functions
A pure function is a specific kind of value-producing function that not
only has no side effects but also doesn’t rely on side effects from other
code.
A pure function has the pleasant property that, when called with the same arguments, it always produces the same value (and doesn’t do anything else). 

```
function zeroPad ( number , width ) {
    var string = String ( number ) ;
    while ( string . length < width ) {
        string = "0" + string ;
    }
    return string ;
}
```

function `zeroPad` is a pure function not only because it takes in two arguments and returns a value but also because it does not interact with any code outside the scope of the function.

<a name="recursive-function" />
### Recursive function
A function that calls itself is a recursion
```
function power ( base , exponent ) {
    if ( exponent == 0) {
        return 1;
    } else {
        return base * power ( base , exponent - 1) ;
    }
}
console.log( power (2 , 3) ) ;
```

Though it's more elegant than iterations, it’s about **10 times slower** than the looping version. 

Recursion performance is probably worse than iteration performance, because function calls and returns require **state preservation and restoration**, while iteration simply jumps to another point in a function.
Running through a simple loop is a lot cheaper than calling a function
multiple times.

<a name="side-effects" />
### Side Effects
Almost opposite to [`pure functions`](#pure-functions). A "side effect" is any effect other than that return value. 
Example:
```
function effectB(a, b) {
    var result = a + b
    console.log(result);
    return result;
}
```
The `console.log` in the `effectB` function causes side effect even though it returns a value at the end.
