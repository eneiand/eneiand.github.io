#### Introduction to ASP.NET MVC 4
* Models, Views, Controllers
  *  Controller receives a request
  *  Controller builds the model
  *  Controller selects the view to present the model
  *  Goals for the MVC framework
    *  Embrace the Web and run on the ASP.NET runtime, be extensible
    *  testable
* Making Changes
  *  request ultimately ends up in a class inside the Controllers folder
  *  methods inside a controller are "actions"
  *  A View() is a type of ActionResult
  *  naming conventions allow returning a View from a controller Action hooks into a similarly named View
  *  ViewBag is a dynamically typed object, available in the razor view
  *  Can use a strongly type model to pass data to the view too
  *  return the View with the model as a parameter
  *  @model directive to inform the view about the model
* Unit Testing
  * .Tests project
  * Testing the controller, MSTest framework comes in VS
  * Arrange, Act (call an action on a controller directly), Assert
* Javascript and CSS
  * js in Scripts folder
  * CSS in content folder
  
#### Controllers in ASP.NET MVC 4
* Routes and Controllers
  * routing engine uses the maproute to figure out where to send the http request
  * Global.asax contains Application_Start which registers routes, called once
  * RouteData.Values["controller"] extracts current value from the RouteData structure 
* Actions and Parameters
  * can alter the routes to do custom things
  * the order that routes are added to the collection is important, first one wins
  * MapRoute matches a route and tells MVC what controller and action to use
  * adding a parameter to an action, the framework will look for something from the request that it should use
  * Server.HTMLEncode to avoid CSS
* ActionResult
  * ContentResult, EmptyResult, FileContentResult/FilePathResult/FileStreamResult, HttpUnauthorizedResult, JavaScriptResult, JsonResult, RedirectResult, RedirectToRouteResut, ViewResult, PartialViewResult 
* Action Selectors
  *  ActionName -> alias the name of the method
  *  AcceptVerbs -> only accessible via a particular HTTP message type [HttpPost] or [HttpGet]
* Action Filters
  *  pre and post processing logic
  *  Caching, authorization etc.
  *  [Authorize] on action or controller -> user must be logged in
  *  global filters can be run on app startup, eg what to do when an error occurs
  *  extend ActionFilterAttribute to make a custom Action Filter

#### Razor Views
* templates, cshtml
* Razor Basics
  * strongly typed views know what model or collection of model you are displaying 
* Code Expressions
  * @ sign -> C# code to evaluate and insert the output into the view
  * ~ means the root of the application
  * Razor automatically HTMLEncodes anything that comes from an @ expression
  * use HTML.Raw to override the encoding behaviour
  * Razor makes an effort to figure out C# vs markup, use explicit brackets where it gets confused
* Code Blocks
  * @{}, @foreach(){} 
  * @: means the content following is literal
* Layout Views
  * UI structure
  * RenderBody, RenderSection are called to plugin the custom body or section views
  * _Layout.cshtml
  * _ViewStart.cshtml defines what the layout view is, hierarchical and can be overriden in code
  * @section can define a section that will appear somewhere on the layout page
* HTML Helpers
  * Create inputs, links, forms
  * @Html.EditorFor
  * @Html.ActionLink
  * keep views simplie
* Partial Views
  * re-use a view 
  * simplify views
  * Shared folder makes it available everywhere
  * @Html.Partial(nameOfView, modeltoRender)
  * @Html.Action() => call another controller from this one, place the ouput here, like a subrequest
    * BestReview on Reviews controller to appear on Layout
    * return a PartialView
    * make it a child action only to disable direct url access

#### Working with Data
* The Entity Framework
  * access a relational database with strongly-type LINQ queries
  * Schema First => point to a db and it will import it
  * Model First -> draw a model and generate
  * Code First => write C# classes and EF will create a database
  * Supports a lot of different databases
* Building Entities 
  * "database class" to derive from DbContext
  * DbSet properties contain the entities we want to query
  * instantiating the DbContext -> it will look for a db and create one if doesn't exist
  * creates database in LocalDB
* Database Migrations
  * call into the base DbContext constructor to give it a connection string
  * Web.config holds connection strings
  * base("name=DefaultConnection") uses web.config connection string
  * Migrations track and change the database as you code
    * Seed -> populates the database with data on each update
    * _migrationHistory is created in the database
    * run Update-Database -Verbose at the package manager console
* Using LINQ
  * select comes at the end
  * Comprehension Query Syntax -> starts with from, where, orderby, select
  * Extension Method Syntax -> .Where.OrderBy.Skip -> extra options, no C# keywords
  * ViewModel -> carrying information just for the View, eg aggregates
* A Search Filter
  * add a Where clause to the LINQ

#### Working With Data (Part II)

* A Restaurant Controller
  *  CRUD, need an area for restaurant
  *  Choose template with read/write and select the model
  *  views etc. are created in the scaffolding
  *  Details action -> accepts an ID and tries to find it in the DB, checks for null and returns a 404 if s
* Listing Reviews
  *  watch out for htmlAttributes overload by accident
  *  reviews index takes the id of the restaurant
  *  use Bind to alias a parameter in the Action
  *  use a partial view to extract the list
  *  EF doesn't load up the child relationships automatically
  *  add the virtual keyword to the collection property do it behind the scenes lazily (2 queries)
* Create a Review
  *  Create New -> Create action, restaurantID that this review is for
  *  place BeginForm in a using statement to emit to end form tag automatically
  *  does a post to Create with a RestaurantReview
  *  check that the ModelState.IsValid before saving in the database (_db.SaveChanges())
  *  redirect to the index to see the review
*  Editing a Review
  *  EditView with the Edit scaffold
  *  look up the model using the id
  *  hidden input in the field for the id in the form
  *  change the state of the review to modified in the edit post action
* Mass Assignment (overposting)
  * Watch out for auto binding of data
  * the model binder will look for and assign as many values as it can
  * Can use Bind to include or exclude the values 
  * or define a viewmodel that only has the values you require
* Validation Annotations
  *  on the model attributes Range, Required, StringLength
  *  putting these attributes on the model will require migrations to alter the database
  *  editorFor will put the validation logic on the client as well as server (model binder enforces them)
  *  also display annotations to describe what a field should be described as in the ui
  *  System.ComponentModel.DataAnnotations
* Custom Validations
  * extend the ValidationAttribute eg. MaxWords
  * implement IsValid, allows custom error message
  * also can have model implement IValidatableObject and implement Validate for deep model inspection
  * ValidationSummary shows errors when not associated with any particular field

#### AJAX and ASP.NET MVC
* The Scripts
   * _references.js tells VS what files you commonly use to provide intellisense
   * jquery intellisense js is just to help VS, never gets sent
   * ASP.NET MVC 4 can auto-minify
   * knockout and modernizer included
* Managing Scripts
    * Scripts.Render -> scripts tag referencing the library, some like modernizer require being added at the top
    * Scripts and Syles.Render -> can minify and bundle the js
    * Global.asax -> BundleConfig.RegisterBundles 
      * create bundles, can use placeholders/wildcards etc. to be used in Scripts.Render or Stlyes.Render
      * debug mode outputs all files, release has them bundled together and minified
* AJAX Helpers
  *  Ajax.BeginForm -> async request to the server and redraw an area of the screen
  *  InsertionMode eg replace, UpdateArea -> what div to replace?
  *  in the controller -> Request.IsAjaxRequest? and if it is then just return the partial, otherwise return the whole view
* An Async Search
  *  @Ajax.ActionLink
  *  all uses unobtrusive javascript, data-ajax attributes attach events that degrade when no js available
  *  js looks for the data dash attributes and attaches the appropriate handlers etc.
* Autocompletion
  * action on the controller that receives a term and returns JSON
  * JSON returned should have a label property
* Paging Results
  * nuget package PagedList.MVC
  * extension method to call .ToPagedList with a page number and number of results
  * model becomes IPagedList<T>
  * Web.Config in the Views folder has list of default namespaces
  * @Html.PagedListPager to generate links, previous and next etc.

#### Security and ASP.NET MVC 4
* Authentication
  * What's the user's identity?
  * Forms Auth -> website provides an input form to provide password, SSL, 
  * OpenID/OAuth -> 3rd party authenticates, no credential management
  * Windows Auth -> internal apps using windows domain/desktop details
* Windows Authentication
  * Intranet application
  * enable windows auth on IIS
  * tell IE to consider localhost to be an intranet site
  * you get a User object
* Forms Authentication
  * anonymous user gets redirected to a login page
  * once authenticated they are directed to the members only area
  * AccountController, Views etc.
  * WebSecurity from WebMatrix -> talks to SimpleMembershipProvider
* Taking Control of Membership
  * Filters folder -> InitializeSimpleMembership, InitializeDatabaseConnection defines where to put users
  * delete the InitialSimpleMembership and put the InitializeDatabaseConnection in the Init instead
  * take control of the User model to add custom fields etc.
* Forms Authentication in Action
  *  WebSecurity takes care of crypto etc.
  *  webpages_ tables are used by WebSecurity
  *  WebSecurity stores hash
  *  attribute [RequireHttps] to enforce secure connection
* Authorize
  * [Authorize] attribute says that the user must be logged in to visit this URL
  * decorate the Action or Controller 
  * [AllowAnonymous] permits users despite the Authorize
  * Specify particular users or roles that can access certain controllers
* Seeding Membership
  * Seed method of Configuration.cs
  * Roles.Provider and Membership.Provider
  * create roles, check for users and membership 
  * User.IsInRole to check and determine if certain UI elements should be displayed
* CSRF
  * masquerade as a user by submitting the form from another site
  * browser sends the logged in user's auth token
  * make sure the form is the one you served, not a malicious one
  * [ValidateAntiForgeryToken] attribute on the controller
  * add verification token to the form -> a crypto value @HTML.AntiForgeryToken()
* OpenID and OAuth
  * dotnetopenauth project
  * during app startup AuthConfig.RegisterAuth
  * register your application with Facebook etc.
  * Google doesn't require setup
 
#### ASP.NET MVC 4 Infrastructure
* Caching
  * [OutputCache] -> action filter to determine when an action should be cached
    * Duration (how long to cache the response), good for SQL queries
    * Can also cache child actions
* Cache Settings
  * ASP.NET cache engine settings
  * VaryByParam -> choose params to cache by eg. cache a response for page 1, page 2 etc.
  * Location -> server, client, client and server
  * VaryByHeader -> vary on an HTTP header
  * VaryByCustom
  * SqlDependency -> cache until data in a table changes
* Cache Profiles
  * stored in the web.config and can use that instead of hard coding across the board
* Localization
  * Thread.CurrentCulture property impacts formatting
  * Thread.CurrentUICulture impacts resouce loading
  * ASP.net can set cultures according to HTTP Headers
  * add a globalization section in system.web with culture and ui culture set to auto
* Resources
  * resx files can store localized text and binary assets
  * create a resource file for a language, dynamically change which one is used
* Diagnostics
  * log4net, elmah, healthMonitoring
  * web.config in the .net folder
  * nuget elmah.mvc -> shows logs through the web interface
  * configure elmah to require authentication etc.
