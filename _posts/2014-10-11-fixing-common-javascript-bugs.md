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

#### Function Bugs

#### Value, Variable, and Literal Bugs

#### Object Bugs
