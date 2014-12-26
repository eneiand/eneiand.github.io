#### Introduction
* Paint.net
  * free
  * basic image editing
* Corel PaintShop Pro
  * intermediate
  * easy photo enhancements
* Image Types
  * raster/bitmap
    * rectangular grid of single color pixels
    * color-depth (bits per pixel)
    * 8bit is 256 colors
    * 24bit is 16.8 million colors ("truecolor")
    * often referred to as wifth * height ( 1024 * 768 )
    * can't zoom or scale up without distortion
  * vector
    * defined by mathematical equations
    * no distortion, redrawn according to the equation
* JPEG
  * Joint Photographic Experts Group ( 1992)
  * best format for photos
  * lossy compression
    * continous edit and save reduces quality
    * often cut 50+% from original sizes with no visible impact
  * supports progressive quality
  * can trade-off quality and size by playing with compression
* GIF
  * Graphics Interchange format (Compuserve, 1987)
  * Lossless compression
  * 8 bits per pixel (256 colors)
  * animated GIFs
  * logos, non-photos
* PNG
  * Portable Network Graphics (1996)
  * designed to replace GIF (patents)
  * lossless compression
  * 8 bit (good GIF replacement)
  * 24 bit and 32 bit also
  * transparency, choose colors to be see through, how much etc.
  * interlaced
  * does not support animation
* WebP
  * Google 2010
  * designed to replace JPEG
  * Lossy and lossless compression
  * animation, transparency
  * supported by Chrome and Opera
  * need to add a MIME type for IIS (image/webp)
* SVG
  * Scalable Vector Graphics (W3C 1999)
  * XML format
  * 2D Graphics
* <img>
   * alt - alternative text if image cannot be displayed
   * title - most often displayed as tooltip
   * longdex - link to URL with long description of the image
   * width/height -> important, faster perceived rendering (no reflow, the browser doesn't have to figure out layout more than once)
     * never scale (lose clarity or waste bandwidth)
   * url case sensitive for caching

#### jQuery Plugins and CSS 3
* jQuery Cycle Plugin
  * rotate through various images with transitions  
* jQuery Carousel Plugin
  * a portion of a set of images with previous and next navigation
  * can contain any html
  * sometimes requires you to set the images to be invisible at first to avoid all appearing
* jQuery Zoom Plugin
  * see a zoomed in version of the portion under the mouse, like zooming in on an item of clothing
  * provide two resolution images
* jQuery Overlays Plugin
  * overlay content, "more info" when hover over an image
  * hover and a title appears
* jQuery LazyLoad Plugin
  * performance concerns, don't want to download all the images until needed
  * uses data dash attributes from HTML5 to store the actual url of the img
  * uses a small clear gif as the image initially
* Disable Right Click
  * turn off the right click menu so people can't download image
  * disable the contextmenu event, return false from the handler
* CSS 3
  * series of modules
  * some are considered part of CSS Core
  * www.w3.org/Style/CSS
* Browser/Vendor Prefixes
  * CSS3 support is being provided by some prefixed properties until supported
  * list the actual CSS3 property last for fallback
* Fallbacks
  * feature detection is preferable over what user-agent are you
  * modernizr
* Polyfills and Shims
  * shim is a small lib that intercepts PI calls, can implement or pass on
  * polyfill - a shim that implements new functionality in older browsers
  * list -> http://tinyurl.com/3o67jqp
* Rounded Corners
  * used to be a massive pain, various jquery-ui plugins
  * border-radius in CSS3 is builtin
* Opacity
  * how opaque or transparent an element is
  * from 0 (full transparent) to 1 (fully opaque)
* Multiple Backgrounds
  * standard background properties with comma seperated values
* Icon Fonts
  * resolution independent, vector based
  * fonts, so can color and use other CSS styles
  * text chars from a font instead of images
  * modernpictograms
  * fontsquirrel.com

#### Performance
* Fiddler
  * optimised for HTTP level as opposed to wireshark TCP
  * good for performance reviews
  * galary extension
* Image Optimization
  * a large portion of webpages today are images
  * jpegtran - removes metadata
* Content Expirations
  * client asks if-modified-since (has this image been modified since I put it in the cache)
  * for small images it is just as expensive to see if modified as to receive content
  * setup expiration times for content folders to avoid lookups
  * rename the file if need to override browser caching
* CSS Sprites
  * combine small images into a single image, make one request, use CSS to "index" into the larger image
  * reduce the number of requests, best for combining lots of small images
* link to multiple destinations from within a single image
  * a single image, define certain areas to be links to elsewhere, like a single image with multiple icons in it
  * map and area elements are used
* Data URI
  * embed small files directly into a URL
  * reduces requests, can't set expiration
  * only usable on object, img, link and in CSS
  * maximum size is 32K
  * img src=data:image/gif;base64blahblah
* CDN
  * akamai, limelight, internap, amazon
  * geographically closer to users
  * typically used for static files
  * offloads some work form your servers
  * most cdn allow us to use a subdomain on our own domain to point at it
* Multiple domains
  * browsers open multiple connections, using different domains/subdomains increases the number of connections the browser can use
  * tradeoff is time taken for multiple DNS lookups.
* Favicon Caching
  * use <link> to specify where the favicon is and override default behaviour
  * means we can treat it like any other resource

#### Miscellaneous
* Aspect Ratios
  * proportional relationship between width and height
  * keep them the same when resizing
* Responsive Images
  * http://tinyurl.com/3aj4zhy
  * fluid grids, css3 media queries, fluid images
  * don't want to just download large images and scale down
  * how to efficiently download the most appropriate image for the situation?
    * server side -> UA Sniffing, cookie with screen size
    * client side -> CSS3 Media Queries, jQuery with data-* attributes
    * future -> <picture> tag with mutiple srcs for different sizes
  * setting max width to 100% for img tag will resize images
  * server side techniques don't play well with caching
  * client side, replace the src of an img with data-small or data-large attribute
  * media queries can be used to determine which css to use according to the size of the screen
* High Pixel Density Displays
  * retina displays
  * icon fonts, css3 gradients, SVG, fonts, vector graphics
  * more pixels in a smaller amount of space, standard images don't look good
  * basic solution is to use double the image size (size more than doubles), specify original width and height
* Design Placeholders
  * placehold.it
  * request an image size
  * placehold.it/350x150
* Watermarks
  * IIS Copyright Handler, inserts a copyright/watermark message when jpg requests come in
* Upload Images
* Where to get images
* Chart Controls
  * Web forms char controls, creates pngs
* System.Net.Drawing
  * draw files on the server
* HTML5 Canvas
  * only 2d at the moment, upper left is 0,0, positive x to right, positive y down
  * can respond to events, create games
  * explorerCanvas.js is a decent polyfill
* Windows 7 Snipping Tool
* Flickr
  * flickrnet on codeplex
* Cool
  * MS DeepZoom
  * MS PhotoSynth -> navigate around some images
  * Lytro, focus free cameras, change the focus by clicking on the image
