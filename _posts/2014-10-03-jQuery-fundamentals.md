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





