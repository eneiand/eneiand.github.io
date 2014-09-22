### Programming Style & Your Brain

* The Way We Think
  * Some styles are profoundly better than others
  * Gut and Head are two systems we use (Thinking Fast and Slow)
    *  head takes a long time and takes a lot of effort
    *  gut solves simple, close problems quickly
    *  gut provides the working assumptions to the head
    *  invalid inputs all the time
    *  advertising targets and sells to the gut
* The Programming Thought Process
  * computer programs are the most complicated things that people make
  * hard to do with our brains as in "The Way We Think"
  * programming language still our best tool
  * the need for perfection is one of the problems, all possible inputs
  * we release software early to find imperfection
  * programming uses head and gut, tradeoffs required
* JavaScript: Good Parts and Bad Parts
  * some of the best good parts and worst bad parts 
  * JSLint checks you are using sane subset of the language
  * always put curly braces on right (auto semi-colon insertion error otherwise)
  * prefer forms that are error resistant
  * switch statement, similar and inspired by goto statement (fallthrough hazard)
    * error vs. elegance
    * if I never intentionally fallthrough, I can find the places where I accidentally fallthrough
  * we spend most of our time making mistakes and fixing them
* Understanding Good Programming
  * "That hardly ever happens" === "It happens"
  * trying to be perfect? you can't allow it to ever happen
  * a good style can help produce better programs, reduce your error rate
  * style is not about personal preference and self-expresion
  * programs must communicate clearly to people, not just get past the compiler
  * never rely on  automatic semicolon insertion
  * with statement is unpredictable, we are trying to avoid confusion
* Avoiding Confusing Code (A)
  * confusion must be avoided, it is where bugs come from
  * equality operator (==) does type coercion before comparison
  * always use ===
  * always use the more reliable feature
  * avoid forms that are difficult to distinguish from common errors
  * make your programs look like what they do
  * javascript has function scope, not block scope
    * declare all variables at the top of the function (makes it the same as hoisting)
    * declare all functions before you call them
  * i (induction variable) in a loop is not scoped to the loop, it is scoped to the function and should be moved to the top
  * write in the language you are writing in
  * the 'let' statement in the next version will replace var, no hoisting
* Avoiding Confusing Code (B)
  * global variables are evil, sometimes required because no other way to binding code units together
  * use UPPER_CASE, should be rare and stand out
  * Constructor functions should be named with InitialCaps
  * implicit global variables, if you don't use var you get a global
  * use x+=1 instead of x++
  * always put in the curly braces every time
  * as our processes become more agile, our processes must become more resilient
  * bad stylists: under educated, old school, thrill seeker, exhibitionist
  * time spent in the abyss (debugging) needs to be limited 
* Using JSLint
  * forms that can hide defects are considered defective
  * language subsetting
  * avoid premature optimization

### And Then There Was JavaScript

* The History of Javascript
  *  Netscape wanted a similar experience to HyperCard in the browser
  *  Brendan Eich given 10 days to design it
  *  influenced by Java, Scheme, Self -> LiveScript
  *  change name to JavaScript to give it a relationship to Sun Java at the time
  *  MS replicated Javascript and called it JScript
  *  ECMA -> ECMAScript agreed to standardise the language
  *  ES5 has default and strict
  *  work in ES5/strict now
  *  bad parts come from legacy, good intentions and haste
* JavaScript Fundamentals
  *  an object is a dynamic collection of properties
  *  every property has a key string that is unique within that object
  *  get, set, delete. dot or bracket notation
  *  object literals
    * an expressive notation for creating objects
    * var my_object = {foo: bar};
  * Classes v Prototypes
    * can simulate Classes in a prototyped system, not the other way
    * Working with Prototypes
      * make an object that you like
      * create new instances that inherit from that object (Object.create)
      * customize the new objects
      * taxonomy and classification are not necessary
        * difficult to do without perfect domain knowledge
  * sometimes called Delegation
    * an object can say "anything I don't know what to do, ask that other object"
  * also sometimes called Differential Inheritance
  * new operator, creates an object that inherits from the functions prototype
  * functions inherited from a prototype are included in the for in enumeration
    * often have to check with 'hasOwnProperty'
  * bad stuff
    * keys must be strings
    * anything you pass as a key will be coerced
* Numbers
  * One number type
  * No Integer type, but ints are a subset of floating point
  * 64-bit floating point
  * IEEE-754 aka "Double"
  * associative law does not hold (computers sometimes require approximation)
    * (a + b) + c === a + (b + c)
    * produces false for some values of a,b,c
    * integers under 9 quadrillion are ok
  * decimal fractions are approximate in IEEE-754
  * you can add functionality to objects by adding methods to the prototype
    * only really reasonable in library development
  * numbers can have methods (it is an object)
  * Seperate Math object for min, max, floor etc and constants
  * NaN comes from IEEE too (a special number)
    * the result of undefined or erroneous operations
    * toxic
    * NaN is not equal to anything, including NaN itself
  * Infinity is another special number anything above Number.MAX_VALUE
  * _but_ Number.MAX_VALUE + 1 does not equal Infinity 
* Strings and Arrays
  * 2 boolean values 
  * 0 or more 16 bit unicode characters
  * UCS-2
  * No charcter type
  * Strings are immutable
  * single or double quotes with \escapement
  * use " for external strings (html templates, text to the user)
  * use ' for internal strings and characters (names of properties)
  * + can concat or add, hard to predict what it will do when typeless
  * String(num) to convert number to String
  * Number(str) or +str
  * parseInt a little difficult to use, it thinks a leading 0 is octal, always put in 10 radix to make it explicit
  * length property on Strings
  * Array is a linear sequence of memory that can be indexed by number -> NOT what javascript has
  * Array in javascript is an object, indexes are converted to strings and used as names for retrieving values
  * no need to give it a length or type when creating an array
  * special length property of Array is always 1 larger than the highest integer subscript
  * don't use for in with arrays
    *  doesn't guarantee the order you will visit the properties in
  * append to arrays using myList[myList.length] = 'new string'
  * map and forEach are very useful
  * array sort function sorts numbers as strings, can pass own sort function
  * delete leaves a hole (undefined), use splice instead
* Objects
  * use objects when the names are arbitrary strings
  * use arrays when the names are sequential integers
  * Date function is based on Java's Date class
  * RegExp for pattern matching, very difficult to get right
  * All values are objects except null and undefined, undefined is "not even null" eg. a non-existing property
    * don't store undefined in an object, can't tell the difference
  * typeof
    * object -> 'object'
    * array -> 'object' _not helpful_
    * null -> 'object' _just wrong_ typed pointers where 0 means 'object' and null
    * Array.isArray
  * Falsy values:
    * false
    * null
    * undefined
    * "" (empty string)
    * 0
    * NaN
    * All other values (including all objects) are truthy
      * "0" "false" 
  * Loosely typed, any of these types can be stored in a variable or passed as a parameter. Not untyped.
  * Reference, never copied, === asks are they the same object  

* Common JavaScript Statements
  * Identifiers
    * start with letter or _ or $
    * convention is that variables, paramters, memebers and function names start with lowercase
    * except for constructor functions and global variables
    * initial _ should be reserved for implementations
    * $ should be reserved for machines
  * Comments
    * // slashslash line comment
    * /* slashstar block comment */
  * Operators
    * usual, some act differently (+) 
    * % is remainder, not modulo -> remainder takes sign from the first argument ( -1 % 8 // -1, not 7), modulo takes sign from last argument
    * use === and !== no coercion
    * && logical and or guard operator
      * if first operand is truthy (result is not true or false, it is one of the operands which are truthy or falsy)
        * then result is second operand
        * else result is first operand
      * can check for null references using 'return a && a.member', all objects are truthy so if not null, then returns a.member otherwise the falsy value of a
    * || default operator, aka logical or
      * if first operand is truthy
        * then result is first operand
        * else result is second operand
      * can be used to fill in default values. var last = input || nr_items
      * may not always work as expected if first operand is a number, because 0 is falsy.
    * ! logical not operator
      * if the operand is truthy, the result is false, otherwise the result is true
      * !! produces booleans. so takes any value, convert to bool and ensure it matches original value
        * _converts_ truthy -> true _and_ falsy -> false
    * Bitwise
      * & | ^ >> >>> <<
      * converts to a 32 bit int, does the shifting, converts back
      * not faster, use the clearer thing
    * Break statement
      * statements can have labels, allowing break to that statement
    * switch statement
      * switch value does not need to be a number
      * case values can be expressions
      * case falls through without a break
    * for in requires filtering to get it right
    * throw anything, there is an Error constructor if you wish
    * the catch in a try clause catches everything (loose typing)

### Function The Ultimate

* Background on Functions
  * just functions for everything -> method, class, constructor, modules
  * function expression
    *  'function' creates a function value (executable object) which can then be invoked
    *  optional name, used for recursion or stacktrace
    *  parameters
    *  body
    *  function objects are first class
      * passed as an argument to a function
      * may be returned from a function
      * may be assigned to a variable
      * may be stored in an object or array
    * function objects inherit from Function.prototype
  * var statement
    * declares and initializes variables within a function
  * function statement
    * 'function' 
    * mandatory name
    *  same params and body
    *  function foo() {}
      * expands to var foo = function foo(){};
      * further expands to var foo= undefined; foo = function foo() {};
      * assignment of the function is also hoisted
    * if the first token in a statement is function, then it is a function statement
  * only functions have scope
  * declare all variables at the top of the function
  * declare all functions before you call them
  * return statement
    * no expression? then the return value is 'undefined'
    * except for constructors (called with new operator), whose default return value is 'this'
  * two pseudo parameters, arguments and this
    * arguments contains all the arguments from the invocation
      * array like (has a length) but not an array
      * supports variable lengths of arguments
    * _this_
      * contains a reference to the object of invocation
      * _this_ allows a method to know what object it is concerned with
      * _this_ allows a single function object to service many objects
    * invocation operator  ()
      * function called with too many arguments? the extra arguments ignored
      * missing arguments are set to undefined
    * Invocation forms
      * Method form (thisObject.methodName(arguments))
        * _this_ is set to thisObject, the object containing the function 
      * Function form (no specific object)
        * _this_ is set to the global object, in future it will be bound to undefined
        * an inner function does not get access to the outer this
          * var that = _this_;
          * every function gets its own _this_
          * same rules as to _this_ binding applies to the inner function
      * Constructor form (new FunctionValue(arguments))
        * a new object ({}) is created and assigned to _this_
        * if no explicit return value, then _this_ will be returned
      * Apply form (functionObject.apply(thisObject, arguments))
        *  _this_ is set explicitly
      * _this_ is bound at invocation time

* Functions as Subroutines
  * subroutines?
    * code reuse
    * decomposition
    * modularity
    * expressiveness, designing your own language
    * Higher Order, functions become parameters and return values
  * Recursion
    * function is defined in terms of itself
    * Quicksort
    * in recursion parameters replace variables
  * Closure
    * comes from set theory, a central idea in javascript 
    * context of an inner function includes the scope of the outer function 
    * the inner function enjoys that context even after the parent functions have returned
    * replaces global variables, and slow private variables with a single, private variable to the inner function
    * return a function immediately which continues to enjoy access to the variable
    * inner function doesn't have copies, it is still bound to the original values

* Protoypal Inheritance (A)
  * Prototypal but syntax tries to look classical so confused
  * inheritance via the prototype object
  
* Prototypal Inheritance (B)
  * treat the function as a module
  ```
    (function () {
        var ...
        function ...
        function ...
    }());
  ```
  * hide private state in the outer function that the returned object has access to
  * Power Constructors
    * make on object
    * define some variables and functions (private members)
    * augment the object with privileged methods (closes over private state)
    * return object
  * don't make functions in a loop
    *  wasteful
    *  confusing because the new function closes over the loop's variables, not over their current values. So you get their final values when executing later.
    *  move the create step to a new function which will create the closure that is required each time

### Problems

### Monads & Gonads

* Introduction to Monads
* The Identity Monad
* The Ajax Monad
* The Maybe Monad
* The Promise Monad (A)
* The Promise Monad (B)
