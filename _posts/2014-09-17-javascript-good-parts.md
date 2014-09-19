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
* Objects
* Common JavaScript Statements

### Function The Ultimate

* Background on Functions
* Functions as Subroutines
* Protoypal Inheritance (A)
* Prototypal Inheritance (B)

### Problems

### Monads & Gonads

* Introduction to Monads
* The Identity Monad
* The Ajax Monad
* The Maybe Monad
* The Promise Monad (A)
* The Promise Monad (B)
