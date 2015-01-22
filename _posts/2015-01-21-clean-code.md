#### Naming
* Naming Classes
  * poorly named classes are a magnet, attracting code and difficult to understand their purpose
  * Guidelines
    * Nouns, a thing, creating an instance of a thing
    * Specific as possible. Cohesion
    * Single responsibility
    * Avoid general suffixes
      * avoid Manager or Info, Product is fine
* Methods
  * a name so descriptive that the reader doesn't have to read the method body to figure out what it does
* Warning Signs
  * And, or, if -> too many things being done
* Side Effects
  * GetUser shouldn't create a session
  * ChargeCreditCard shouldn't send an email
* Abbreviations
  * no standard, don't use them
* Booleans
  * bool names should sound like true/false questions
  * dirty -> open, start, status, login
  * if (isOpen, done, isActive, loggedIn)
* Symmetry
  * states that toggle, consistently use matching pairs
  * on/off not on/disable

#### Conditionals
1. Clear intent
2. Use the right tool
3. Bite-size logic
4. Sometimes code isn't the answer

* Boolean Comparisons
  * Compare booleans implicitly if(isLoggedIn) not if(isLoggedIn==true)
* Boolean Assignments
  * assign booleans implcitly
    * bool goingSomewhere = cash > 6.00;
* Positive Conditionals
  * don't be anti-negative!
  * use positive conditionals, if(loggedIn) not if(!isNotLoggedIn)
* Ternary Elegance
   * registrationFee = isSpeaker ? 0 : 50
   * fewer lines, less opportunity for mistakes, easier to read
   * don't chain ternary's together
* Stringly Typed
  *  avoid being "stringly" typed (eg. employeeType == "manager")
  *  use enums for strongly typed support -> employee.Type == EmployeeType.Manager
    * goes native, VS will help, intellisense etc.
* Magic Numbers
  * magic numbers expect the reader to fill in the gaps
  * consts or enums make it readable eg. drinkingAgeLimit or Status.Active
* Complex Conditionals 
  * conditionals tend to grow over time
  * intermediate variables -> assign to a variable that describes the intent (bool eligibleForPension = )
  * encapsulate into a function -> if(ValidFileRequest(fileExtension, active))
    * allows to ignore the body of the method when reading
* Polymorphism vs Enums
  * favor polymorphism over enums for behaviour 
  * replace switch statements that occur more than once
  * delegate from status enum to subclasses, ActiveUser, InactiveUser, LockedUser.login()
* Be declarative
  * replace a loop with Linq to objects
  * replaces looping procedural to readable declarative
* Table driven methods
  * replace complex if statements with database data
  * insurance rates, pricing structures etc.
  * avoid hardcoding data into the code, easily changeable without recompilation

#### Functions
* When to Create a Function
  * avoid duplication
  * indentation -> 
  * unclear intent -> function names to assist
  * >1 task
* Duplication
  * fewer places to maintain, fix etc.
  * look for patterns
* Excessive indentation -> arrow code
  * make it easier to read by removing so much indentation
  * extract method -> move a chunk of code to a function
  * reader can choose to read at whatever level of detail they wish
* Return Early
  * return as soon as the condition has been found, eg. is username valid?
* Fail Fast
  * guard clauses to assert that input is valid, throw exception immediately
  * reduces indentation
* Convey Intent
  * clarify by using a function and function name instead of a comment
* Do One Thing
  *  aids the reader, promotes re-use, eases naming and testing, avoids side-effects
* Mayfly Variables
  * don't init variables at the top of the function
  * variables only live a short time
  * JIT variables
* Parameters
  * strive for 0 to 2 parameters
  * easier to understand, test etc.
  * helps assure function does one thing
  * watch out for flag arguments eg. emailUser
* What's Too Long?
  * signs -> whitespace and comments
    * scrolling required
    * naming issues
    * multiple conditionals
    * hard to digest -> multiple layers of distraction
    * remember the rule of 7, more than 7 of something is too difficult to process
  * Bob Martin 
    * functions rarely be over 20 lines
    * hardly ever over 100 lines
    * no more than 3 parameters
  * linux style guide : simple functions can be longer, complex functions should be short
* Exceptions
  * unrecoverable
    * null ref
    * file not found
    * access denied
  * recoverable
    * retry connection
    * try different file
    * wait and try again
  * ignorable
    * click logging
  * catching an exception and continuing is fail slow, allow it to bubble up instead
  * keep the try/catch body standalone to make it clear

#### Classes
SOLID principles and Design Patterns courses by Steve Smith

* Classes are like headings in a book -> well named give a clue of the content
* When to Create?
  * new concept -> abstract or real-world
  * found some low cohesion within an existing class? split it out
  * promote re-use with small, targeted classes
  * reduce complexity -> solve once and hide away
  * clarify parameters -> convert a loose bag of variables into a class
* Cohesion
  * Class responsibilities should be strongly-related
    * readability
    * increases likelihood of reuse
    * avoids attracting the lazy
  * watch out for methods that don't interact with the rest of the class
    * fields that are only used by one method
    * classes that change often
  * specific names lead to smalled more cohesive classes 
* When is a class too small?
  *  rare
  *  classes that rely heavily on each other
  *  one class relies on another completely
  *  too many small moving parts?
* Primitive Obsession
  * passing around bags of data? maybe time to create a class
  * trade off between too many params should be an object and fewer params being more specific about dependency
* Principle of Proximity
  * strive to make code read top to bottom when possible
  * keep related actions together so convenient to read
* The Outline Rule
  * collapsed code should read like an outline
  * multiple layers of abstraction, methods calling child methods etc.
  * easy to review at the appropriate level of abstraction

#### Comments
* Necessity and Crutch
 * prefer expressive code over comments
 * use comments when code alone can't be sufficient
* Redundant Comments -> repeating the code in comment like "set i = 1", not DRY
* Intent => comments to clarify intent can be replaced with code eg. 2 changed to Status.Inactive
* Apologies and Warnings -> don't apologize, fix or leave a TODO if you must. Warnings are stupid
* Zombie Code -> commented out code should be removed, will be read and comes up in searches etc.
  * signal to noise ratio -> ruined by Zombie code
* Dividers and Brace Trackers
  *  comments breaking up long functions? => refactor
  *  comments describing closing braces? => refactor
* Bloated Header => keep to a minimum
* Defect Log -> change metadata, like commit comments, belong in source control
* Clean Comments
  * TODO or HACK supported by VS
  * watch out for todos that are actually warnings and apologies
  * some high level overview comments "summary comments" can be useful if an additional content is needed
  * documentation "see url for api" can be useful if can't be expressed in code
