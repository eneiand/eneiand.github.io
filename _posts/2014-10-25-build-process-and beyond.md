#### Introduction

* Web Apps
  *  1 Modern workflow ,2 grunt and friends, 3 dev tools
  *  traditional heavy app mixes frontend with server side workflow
  *  rich client uses templates, ajax, json, service back-end
* Tooling
  *  frontend second class citizen traditionally
  *  split out front end tooling, easier to switch projects
  *  lots of tools built on top of node
    * need to consider where this js will run
  * npm -> node packaged modules
    * package.json -> metadata about package, dependencies etc.
    * dependencies -> npm install will pull htese things down
    * dev-dependencies -> only required for development, odn't publish
    * npm install --save or --save-dev will wriet to the package.json
 
* Grunt
 * grunt 
   * npm install -g grunt-cli
   * command line + gruntfile.js
    * defines all the pieces of the workflow that grunt is going to execute 
    * coffee file also supported
  * workflow
    * all the bits of work we need to do
    * minify + compress js
    * minify + compress css
    * optimise images
    * html
 
* Project Setup
  * some nice aliases like 'git hist'
  
* Starting Point

#### Working with Grunt

* NPM Init and Grunt
* Gruntfile.js
* Globs and CoffeeScript
* Grunt Watch
* CSS Preprocessors
* LESS Mixins
* LESS Watch Tasks
* Grunt Documentation
* Splittin Concerns and Using Copy
* Custom Server Tasks
* Finishing the Custom Task
* Using Express Compress
* Live Reload
* Live Reload Alternative
* Chrome Workspaces
* Grunt Clean and Grunt LESS
* The DIST Workflow
* Minifying Javscript
* Grunt Open
* Match Depenedencies
* Simulating Production Assets
* Vendor JavaScript Libraries and CoffeeScript
* Compiling CoffeeScript

#### Beyond Grunt

* Bower
* Reorganizing the Application
* Sourcemaps
* Backbone
* Yeoman Introduction
* Browserify
* Yeoman Workflow
* Lineman Workflow
* Lineman Spec and Build
* Test-Driven Development Questions
* End-to-End Testing
* Push State Simulation
* Integrating with Rails
* Unit Testing Grunt Plugins
* Writing a Blog With Lineman
* Wrap-Up
