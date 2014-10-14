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

#### Value, Variable, and Literal Bugs

#### Object Bugs
