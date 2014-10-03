## JavaScript From Scratch
javascript everywhere

### Fundamentals
* write javascript in a script tag in a html page or something like jsbin, plunker etc.
* get comfortable iwth partial knowledge
* building blocks
  * numbers
  * strings
  * variables
  * operators, binary and unary
  * anything that evaluates to a value is referred to as an expression
  * statements, any collection of expressions

### Program Flow

* if statements
* braces 

### Truth
* boolean type can be true or false
* &&, ||, !
* Falsy values (evaluate to false)
  *  null, undefined, NaN, "", 0
* Truthy values
  * everything else
* == is simple equality (0 == false) is true
* === is exact equality (0 === false) is false

### Functions
* too few arguments? set to undefined
* too many arguments? ignored
* no return value? undefined
* hoisting -> function is lifted as if defined at the top of the file
* the only thing that creates scope in javascript is functions
* a function scopes its variables at the time it is declared, not at the time it is run

### Data and Objects
* objects are collections of properties
  * non-existent properties are undefined
* arrays act as collections, the only real collection type in javascript
  * push and pop
  * length
* strings
  * charAt
  * indexOf
  * split -> turn into an array of words
  * slice -> pick out a piece of the string
