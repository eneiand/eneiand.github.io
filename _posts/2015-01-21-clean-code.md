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
