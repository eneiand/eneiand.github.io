### jQuery Fundamentals

#### jQuery Fundamentals

* Why use jQuery
  *  a single js file
  *  cross browser (IE6 popular)
  *  selectors (select things in the dom and manipulate them)
  *  events
  *  ajax
  *  plugins
  *  why?
    * crossbrowser
    * concise way to locate elements
    * less worry about the browser
* Getting Started with jQuery
  *  1.x for IE 6-8, or 2.x if no need for IE 6-8 
* Using Content Delivery Networks
  * caching and parallelism 
* Using the jQuery ready() Function
````
  $(document).ready(function(){
// to detect when a page has loaded and is ready to use
  });
````  
  * called once DOM hierarchy is loaded but before all image have loaded
  * different to window.onload = function(){}
    *  faster to use jQuery
    *  doesn't wait for images etc.
    *  similar to putting the scripts at the bottom of the document
* Getting to Know the jQuery Documentation
  * api.jquery.com
  
#### Using jQuery Selectors

* What are selectors?
  * allow page elements to be selected
  * selector identified an HTML element/tag that you will manipulate with jQuery Code
  * $(selectorExpression)
* Selecting Nodes by Tag Name
  * $('p') selects all <p> elements
  * $('p, a, span') selects all paragraphs, anchors and span elements
  * $('table tr') selects all tr elements that are descendants of the table element
  * affect all the objects that are returned:
    * $('p').css('background-color', 'green');
    * $('div').each(function(){ //this is each div })
* Selecting Nodes by ID
  * use the # character to select elements by ID
  * $('#myID')
* Selecting Nodes by Class Name
  * use the '.' character to selecte elements with a particular class
  * be careful because it will scan the whole DOM
  * would have to loop if using native javascript
  * $('.BlueDiv, .ThisDiv') to select anything with class of BlueDiv or ThisDiv
  * $('a.myClass') to select just <a> tags with class="myClass"
* Selecting Nodes by Attribute
  * use brackets [attribute] to select based on attribute name and/or attribute value
  * when you see square brackets think "where"
  * $('a[title]') selects all <a> tags WHERE there is a title attribute
  * $('a[title="ProgrammingInfo"]') select all <a> tags WHERE the title attribute = "ProgrammingInfo"
* Selecting Input Nodes
  * $(':input') selects all elements used for input including: input, select, textarea, button, image, radio and more
  * $('input') selects only the input tags
* Additional Selector Features
  * :contains() will select elements that contain the text $('div:contains("pluralsight")')
  * $('tr:odd') and $('tr:even') is the syntax for selecting odd or even rows respectively
  * $('element:first-child') selects the first child of every element group. also last or specific child
  * [attribue^="value"] selects where attribute begins with or [attribute$="value"] for ends with
  * [attribute*="value"] attributes where text contains
* codylindley.com/jqueryselectors

#### Interacting with the DOM

* iterating through nodes
  *  .each(function(index, element)) is used to iterate through jQuery objects
  *  this represents the raw object, wrap it in $(this) to get a jQuery object (access to helper methods etc.)
  *  element === this
* modifying properties and attributes
  * this.propertyName (inside the each), this being the raw DOM object, can be used to modify an object's properties directly 
  * object attributes can be accessed using attr()
    * $('img').attr('title', 'My Image Title');
    * iterates without needing to do each
    * modify multiple attributes by passing a JSON object
* adding and removing nodes
  * append(), appendTo(), prepend(), prependTo(), remove()
  * appending adds children at the end of the matching element
    * $('.officePhone').append('<span>(office)</span>');
  * prepending adds children at the beginning of the matching element
  * .wrap() 
    * $('.state').wrap('<div class="US_State"/>');
    * wraps anything with class 'state' in a div with class 'US_State'
* modifying styles
  *  .css() function used to modify an object's style
  *  accepts JSON
* modifying classes
  * addClass(), hasClass(), removeClass(), toggleClass()
  * best practice compared to .css
  * $('p').addClass('newClass')
  * if($('p').hasClass('newClass)){
  * remove specific or all classes with removeClass

#### Handling Events
* jQuery Event Model Benefits
  * event attach techniques are different between "Most Browsers" and pre IE9
  * events notify a program that a user performed some types of actions
  * jQuery provides cross browser, compact way to do this
* Handling Events
  * jQuery event shortcut functions. click(), blur(),  focus(), dblclick(), change() etc.
  * mouseenter(), mouseleave()
  * api.jquery.com/category/events
  * grab the dom object, use the shortcut function to attach a callback to it
  * $('#myID').click(function(){//do something});
  * $('#myID').click() //fires the click on the div
  * often hook up events when the document has fired the ready event
  * event object is passed to the callback
    * e.pageX, e.pageY, e.target (raw DOM)
    * this is the raw object too
* Binding to Events
  * what is the on() function?, the core event function, event shortcuts delegate to it, used to be called bind
  * .on('click', function(){});
  * attaches a handler to an event for the selected elements
  * unbind events using off();
  * use a space to bind to multiple events ('mouseenter mouseleave')
* live(), delegate() and on()
  * handle adding lots of event handlers more efficiently
  * uses bubbling to allow parents to handle the child event (table with lots of trs)
  * delegate lets oyu specify the context (parent) to hanlde hte event
  * on is the latest way to do this, add the child type param
    *   $('#customers tbody').on('click', 'tr', function(){});
    *   new children still receive the handling
* Handling Hover Events
  * pass two event handlers to the hover shortcut
  * equivalent to on mouseenter and on mouseleave
  * or pass just one function that gets fired on both
