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
