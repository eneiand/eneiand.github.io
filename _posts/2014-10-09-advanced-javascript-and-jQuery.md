#### Introduction

* Traditional Javascript Functions
  
  ````
  function myFunction(text) {...}
  myFunction = function(text) {...}
  var myFunction = function(text) {...}
  var myObject = { myFunction: function(text) {...}}
  //library, namespace by creating a global object containing my functions
  myObject = {myFunction: function(text){...}}
  ````
  
* Draw Version 1
  * HTML5 Canvas Draw Function
  * checks for the getContext function before attempting to draw, ie check for HTML5 Canvas support

* Extending Draw - Two Parameters
  * function should take parameters to be re-usable and place the square wherever we want

* Draw - Four Parameters
  * add width and height parameters to draw a rectangle

* Draw - Six Parameters
  * stroke and fill to set the colors
  * undefined parameters throwing it off
  * draw function requires all parameters and in the right order
  * every time we added parameters to the function we broke the previous contract
* Stubs
  * function stubs honour the old contract, and call the new function with good parameters, no duplicate code
  * would have to create a new stub with every new version of the function
  * not the ideal long term solution
* Default Parameters
  * provide defaults within the function when parameters are missing
  * useful when one or two parameters are optional
  * optional parameters should be at the end of the list
  * check for undefined with if(typeof fill ==== 'undefined')
* Changing to an Object Parameter
  * use one object parameter instead of multiple native types
  * one parameter (options), check to see if it is an object and replace it with one if not
  * no order required
  * omit anything we want etc, parameters optional by nature
  * still check if we need to fill any defaults
  * to support legacy calls we check the first param for objectness
* Default values in an object
  * add an object to the top level object which contains some defaults. eg. 'drawOptions'

#### Event Handling
* Shorthand Methods
  * for common events shorthand methods can be used 
  * click, hover, dblclick
  * attach handlers when document ready
* Message Functions
  * making use of call lets us explicitly set 'this' 
* More Elements
* Propagation
* No Shorthand


#### Advanced Event Handling

#### Using jQuery Deferred Objects
