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
