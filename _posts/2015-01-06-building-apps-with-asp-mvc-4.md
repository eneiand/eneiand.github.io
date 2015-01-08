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
