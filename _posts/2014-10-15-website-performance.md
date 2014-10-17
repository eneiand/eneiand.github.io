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


#### The Middle-End: Resources

#### The Middle-End: Architecture and Communication

#### The Front-End: Resource Loading

### The Front-End: Abstractions
