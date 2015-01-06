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
