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
  * any unhandled event is passed to its parent "bubble up"
  * many ways to cancel event processing, return false for example, not all supported cross browser
  * jQuery supports preventDefault()
  * event.preventDefault() in event handler, doesn't cancel propogation, prevents the default behaviour only
  * event.stopPropogation() should be called aswell as preventDefault to completely override and stop the event bubbling
* No Shorthand
  * live attaches event handlers to future elements, not just static ones. works by attaching a handler to the top level dom object
  * delegate works like live but you can specify the point of attachment, not just the top level
  * on and off superscede these methods and are preferred
  * one is only handled once

#### Advanced Event Handling
* Namespace
  *  append namespace to the event name
  *  'click.demo'
  *  allows us to narrow and target specific events to remove, ie I can remove 'click.demo' and leave 'click.test'
  *  useful for jQuery plugin or a library
* Delegation
  * bind event handlers higher in the DOM
    * efficiency
    * centralized processing
    * use on() with the selector parameter to take advantage of dynamic event handling
* Custom Events
  * create new events for DOM elements
  * initiate a custom event with .trigger()
  * eg. triple click
  * jQuery data object is associated with the element of the DOM eg. $(this).data
    * a good place to store persistent data eg. count of clicks
  * $(this).trigger('click3');
  * just use on and 'click3' as if it was build in
* Event Parameters
  * data passed to event handlers must be an object or an array
  * pass the object as a parameter to the event handler
  * add it to the trigger method $(notifyObject).trigger('recordsloaded', objectToPass)
  * to pass to builtin events we must have access to the data, we can give it as a parameter to on() and it will be passed every time the event occurs

#### Using jQuery Deferred Objects
Deferreds are an alternate to callbacks

* Promise
  * a promise states that the result of an asyn process will be reported at some time in the future
  * Ajax functions return a Promise object
* chaining callbacks is usual and problematic way to do several dependent things in a row, example is loading 3 sections of content before enabling a button
* nesting calls to load content one at a time and then enable, 'christmas tree'
* _when_ all content is loaded, _then_ enable the proceed button
* $.when().then()
  * when takes any number of deferreds seperated by commas 
* use get instead of load because it returns a Deferred object
* what to when there is a failure? attach additional function to the then to handle failure
