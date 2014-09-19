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
* JavaScript Fundamentals
* Numbers
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
