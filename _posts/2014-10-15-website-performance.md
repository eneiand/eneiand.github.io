#### Make Performance a Priority
* Why Web Performance?
  * don't focus entirely on optimisation, it is part of the overall process
  * be aware of the user, they may not have the hardware you have
  * performance golden rule:
    * "80-90% of the end-user response time is spent on the frontent. Start there." - Steve Souders
* Performance and User Experience
  * performance is important to an end user
  * webpagetest.org
  * the order in which things load can greatly enhance the perception of the site
  * "visual completeness"
  * document ready is the point that a user can meaningfully interact with the page
  * choices and tradeoffs impact web performance
  * whichloadsfaster.com
* How We Get Web Performance
  * $ even a tenth of a second can  cost companies money (Google, Amazon)
  * Quality, high performance is quality
  * web, measurement and perception
    * consider the user, ads over content ?
  * efficiency, speed and memory
  * performance, benchmark and optimize
    * need to be able to quantify, get actual numbers
    * user studies
* Focus on the Critical Path
  * "premature optimizatoin is the root of all evil" -- Donald Knuth
  * decide what is critical, the 3%
  * Optimization, noncritical vs critical
  * "noncritical path optimization is the root of all evil"
  * 100ms no difference, 1000ms there was a delay but ok
  * composed operations -> "Death by a thousand papercuts"
  * inefficiency is systemic
* The Total Cost of Ownership
  * The myth of the refactor, broken refactor promise
  * long term cost of ownership of non-performant code is greater
  * we need performant by default
    * scale back when code readability important, the opposite of what happens at the moment 
  * most of "front-end" optimization happens in the middle end
    * templating, URL Routing, Headers, Caching, Ajax etc.
    * http://middleEnd.com
  
#### The Middle-End: YSlow

YSlow plugin, easy way to test performance of loading of a page.
The Big 14!

* YSlow Rules
  * Fewer HTTP Requests
    * how can we get same content with fewer requsts?
    * organise critical stuff vs non-critical stuff
  * Use a CDN
    * static resources should be on a CDN
    * more points of presence than an individual has. Asia, Australia etc.
    * shared caching
  * Expires/Cache-Control Header
    * make sure these are correct for each resource corresponding to our intent
    * stable (jQuery) vs unstable
  * Gzip
  * Stylesheets at the top (browser often blocks until these are received)
  * Scripts at the bottom (not waiting for DOM, prioritising what you need)
  * No CSS Expressions
  * External JS/CSS for caching, no inline
  * Fewer DNS Lookups, not too many domains
  * Minify JS/CSS (should be higher)
  * Avoid redirects
  * Avoid duplicate scripts, eg. requiring multiple versions of JQuery
  * ETags turn it on, avoid the default, a fingerprint for a file
  * Cacheable Ajax
  * some of these are contradictory, 3 & 13, 1 and 8, 2 and 9
* YSlow Rules, Continued
  *  
* Beyond the Big 14
  * fewer http requests
    * image spriting
    * use background position to show only a particular image
    * concat js/css
  * GZIP
    * mod_deflate
    * gzip test site
  * Conditional Requests
    * expires/cache-control/etag
    * don't need expires and etag
  * developer.yahoo.com/performance/rules.html
    * reduce cookie size
      * sent with every request every time
      * cookie-free domains (domain only for resources that don't need cookies)
    * optimize sprites
      * horizontally organised is more efficient than veritcally organised
      * avoid one giant image
    * <img src=""> fires a request!
  * Exercise 1
    * www.bbc.co.uk -> D, 64 
    * www.skysports.com -> D, 65
    * news.ycombinator.com -> A, 100
    * www.red-gate.com -> D, 68
      * Move javascript to the bottom
      * combine the 21 js. 13 css and 17 images
      * use a CDN

#### The Middle-End: Resources
* Images
  *  average web page size is increasing
    * js increasing faster
  * image optimization 
    * you can optimise most images without reducing quality 
    * www.smushit.com/ysmush.it
    * imageoptimizer.net
    * pmt.sourceforge.net/pngcrush
  * image spriting
    * spriteme.org
    * spritegen.website-performance.org
    * www.floweringmind.com/sprite-creator
  * inline images
    * reduces requests
    * ties caching to css
      * dopiaza.org/tools/datauri
      * dataurl.net/#dataurlmaker
* Minification
  *  compressorrater.thruhere.net -> compares various options for compression
  *  marijnhaverbeke.nl/uglifyjs -> consistently better now
  *  minifycss.com/css-compressor
  *  jsbeautifier.org -> take minified and put in spacing
  *  cssbeautify.org -> take minified and put in spacing
*  Concatenation
   *   zBugs.com -> a summary
   *   robert nyman concatenating, minifying article
     * http://robertnyman.com/2010/01/19/tools-for-concatenating-and-minifying-css-and-javascript-files-in-different-development-environments/  
* Exercise 2

#### The Middle-End: Architecture and Communication
* Understanding the Middle-end
 * a layer between what happens purely in the front-end and purely in the back-end
 * templating, ajax
 * a buffer between the two ends
* Introduction to Architecture
  * SPA, excitement is that you can serve the markup once instead of 10 times
  * javascript templating engine
  * could decide where the line lies depending on the device
* Data Validation
  * often end up writing the same stateless validation code twice, js and back-end
  * middle end using server side javascript lets us re-use the code
  * like node.js (a good option)  but simpler is what Kyle suggests, Rhino is another
* JSON, Ajax, & Web Sockets
  * JSON still requires restraint, can't go stuffing tonnes of data into it
  * Ajax vs. Web Sockets
    * Ajax is a full request taking up extra resources, not heavy but heavier
    * web sockets create one initial http cycle, then upgrades to web socket to get a persistent socket
      * less overhead from this point forward. web socket packet is 8 bytes 
      * 2 way communication
      * not truly realtime, but a lot less latency

#### The Front-End: Resource Loading
* Preloading Images
  * I know I'm going to need something later so give it to me now
  * Effectively saying that this something is at least as important as what we're doing now
  * <link rel="prefetch"> is a hint to the browser to load something
  * need to send cache headers too
  * DNS prefetching can be turned off
* Lazy loading
  * opposite of preloading
  * don't download anything until you need it
  * risk the 100ms, or even 1000ms barriers
  * both are valid techniques that require understanding how your user feels about your site
  * dynamically append a script element to the dom
* Parallel Loading
  * presserve execution order
  * src.async is true by default, order is preserved in markup?
  * labjs does dynamic loading -> assuming that no script does document.write
  * avoid document.write, browsers have to assume it might be present and wait in case the dom might change

### The Front-End: Abstractions & Animcation
* OO is Slow(er)
 * OO js in the browser is different and slower than compiled languages
 * in general you tend to create too much abstraction
 * deciding for the critical path (3%) consider not OO there
 * Batch Operations
  * often OO does not consider operations that you need to do in batch
  * eg. reporting 
 * dynamic language, live link, lots of function calls that cannot be optimised away like in a compiled language
* Javascript Animations
  * if you can, offload to CSS engine for performance
  * setTimeout doesn't guarantee when it will fire
  * requestAnimationFrame is HTML5 attempt to solve setTimeout, call this code before you paint next (60hz ~ 16.7 seconds)
  * timeouts keep happening when tabs inactive but requestAnimationFrame does not because the browser knows this is animation related code
* CSS: Transition vs. Animation
  *  transition is starting value and ending value, change it and take this amount of time, you figure it out
  *  just updateElement once in js + css with transition: to set timing
