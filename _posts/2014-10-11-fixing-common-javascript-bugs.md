#### Statement Bugs
* Missing Mark Bug
  *  Auto semi-colon insertion has specific rules, hard to remember etc.
  *  put opening curly braces on same line
* Fresh Functoin Bug
  *  requires polyfill in some browsers to do filter, or use reduce 
* Tumble Through Bug
  * switch statement falls through cases
  * an alternative is to store values in an object and lookup
* Srtictly Stray Bug
  * ni production combining scripts can turn on strict mode to the combined file
  * use function strict mode to contain it
* Parsing Parenthesis Bug
  *  js needs some help ot invoke a fnuction immediately
  *  wrap the whole thing in parens
  *  declaration requries it, expression reccomends it for consistency
* Evil Eval Bug
  * don't ues eval, especially when it will allow the uesr to control the input
* Fickle Figure Bug
  *  trailing commas are a problem for IE7 and IE8
  *  JSON.parse does not accept trailing commas

#### Expression and Operator Bugs
* Crude Computation Bug
 * Floating point numbers get off slightly
 * check for less than instead of !== 1
 * deal with whole numbers and convert when needed to fractions
 * Big or BigNumber math libraries help
* Mistaken Mold Bug
  * typeof an array is "object"
  * jQuery $.type is better
  * underscore has _.isArray
* Twisted Truth Bug
  * 0 is falsy, > 0 is truthy
    * 7 falsy values, [undefined, null, false, +0, -0, NaN, ""] 
* Craft Convert Bug
  * using == converts things before comparing
  * use strict equality to consider type ===
  * can check typeof for extra safety
* Problematic Pause Bug
  * comma operator evaluates both of its operands (from left to right) and returns the value of the second operand
  * return max, arg; // will return the value of arg
* Ignored Invention Bug
  * forgetting the new operator 
  * using new, _this_ will refer to _new_ object
  * not using new the _this_ will refer to the _global window_
  * you can check that this is an instance of the object you expect to protect against someone misusing the constructor
  * new sets its constructor to the constructor function being invoked, so you can check instanceof
* Inaccurate Increase Bug
  * pre-increment returns the value after adding one
  * post-increment returns the value before adding one

#### Function Bugs

* Raised Resource Bug
  * function scope, variable hoisting
  * hoisting raises the declaration of the variable to the top of the function
  * it does not hoist the assignment, it is assigned to undefined until that point
  * variables are available to the whole function 
  * best practice therefore is to always declare variables at the top of the function to make it obvious what is happening
* Early Execution Bug
  *  function hoisting
  *  function hoisting is different depending on expression vs. statement
  *  a function expression hoist the declaration and leaves the assignment
  *  function statements hoist both declaration and assignment
* Morphed Method Bug
  *  no method overloading in javascript
  *  simulate it by defining one function and checking that arguments etc
  *  checkign types again, use jQuery or Underscore because javascript returns 'object' for most things
* Confounding Context Bug
  *  value of _this_ is confusing
  *  for inner function, assign _this_ to _that_ for the inner function
  *  strict mode eliminates this coercion to the global object, it is null instead
* Escaped Environment Bug
  *  closing over the variable (i) refers to the last value of i
  *  need to copy the value so can refer to it at that point of time later
  *  or immedately invoke a function that creates another function, taking i as the value and storing it in a closure
* Peculiar Parameter Bug
  *  arguments object is not an array so it does not have a forEach
  *  arguments is array like, it has a length and you can access it [], but it is not an array
  *  you must iterate in a normal for loop or convert it to proper array
* Condemned Criterion Bug
  *  arguments.callee not available in strict mode
  *  give function a name instead and refer to it that way

#### Value, Variable, and Literal Bugs
* Booked Byword Bug
  * delete is a reserved keyword
  * some other words set aside for the future
* Revealing Recall Bug
  *  missing var, javascript will make it global
  *  easy to make this mistake when declaring and assigning like this
````
var index = length = 0
//length is global, should use comma seperator
var index = 0, length = 0;
````
  * use an object literal or IFFE to control namespaces
* Relative Realism Bug
  *  undefined is not a reserved word and could be redefined to be a truthy value
  *  protect the value of undefined by wrapping it in an IFFE and adding _undefined_ to the parameter list
  *  the undefined variable will then have the undefined value, whatever that may be
* Tangled Tag Bug
  *  HTML elements are available via their ids (named elements)
  *  IE8 is weird with this
  *  use a function wrapper to remove it from the global namespace
* Double Define Bug
  * defining the same key twice, the last key in an object literal or parameter in an function with the same name wins 
* Transform Total Bug
  * when parsing an int if the radix is undefined it is defaulted to 8 in ECMAScript 3 (IE8)
  * so the parsing is done in Octal
  * provide a radix always to avoid this bug
* Amount Aware Bug
  * NaN can not be compared to itself, always fales
  * use isNaN(test) instead
  
#### Object Bugs
*  Pregnable Property Bug
  *  for-in loop iterates over enumerable properties, including those inherited from the object's prototype
  *  for-in better for objects than arrays
  *  can use hasOwnProperty to see if the object owns this property
  *  or use a for loop to make sure with array
*  Accidental Ancestry Bug
  *  assigning to a method on a prototype overwrites existing methods
  *  assign the an instance of the supertype's prototype to the subtypes prototype to break the connection
* Eccentric Envelope Bug
  *  using Boolean wrappers and === does not act as we expect because they are different objects
  *  prefer not to use the Boolean wrappers
  *  can use them to convert values to boolean, an alternative is !!
* Translate Time Bug
  *  moment.js knows how to conver Unix epoch
  *  javascript does not
* Perpetual Property Bug
  *  no error if you try to change a readonly property, except in strict mode
* Strange Set Bug
  *  concating an array
  *  one argument to the Array constructor means an array that size of undefined
  * use array literal
* Malformed Message Bug
  * JSON keys must be double quoted, JSON Strings must be double quoted
  * JSON is a string, not an object
  * JSON.parse returns the parsed object
