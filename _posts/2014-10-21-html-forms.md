#### HTML forms fundamentals

* Form Basics
  * creating content
  * make purchases
  * allow us to interact with the server in two-way comms
  * markup to display
  * data is entered
  * name-value pairs sent to server
  * form
    * input, name and type attributes 
    * type="submit" gives submission button
* Form settings
  * action -> uri to send the data to
  * method -> HTTP method (GET -> idempotent!/POST) to use
  * enctype -> how to encode the data, multipart etc

#### HTML form inputs

* Text Inputs
  * input with type="text", or type="password"
  * textarea is a multi-line text box
  * input with type="hidden" -> control values that get sent
  * HTML5 : email, phone, url, date ,time ,datetime, month, week, local date time, number, range, color 
* Selections
  * select list (single or multi)
  * radio buttons
  * check boxes
* Input Attributes
  * size, maxLength, checked, multiple/selected, rows/cols, disabled/readonly (won't get sent)  
* Input commands
  *  input with type of reset 
  *  input with type of submit -> sends form to the server
  *  button, or button tag with type="submit"
  *  image button

#### Organizing HTML forms
* Labels
  * text explicitly associated with an input
  * interaction with label, focus on field
  * label tag with for attribute, or label wrapped around input element
* Fieldsets
  * groups form input fields together
  * optionally label the group
  * fieldset, legend tags
  * legend is the label for the fieldset
* Tab index
  * tabindex attribute to control the order they should be tabbed to
  * 1 based index
  * default is the order they appear in the document
* Access Key
  * keyboard shortcut to go to a particular label or input
  * "activate" so focus an input, follow an anchor
  * accesskey attribute

#### HTML form scenarios
* Scripting forms
  *  set the onclick handler of a button
  *  get the form element by id, call submit()
  *  onsubmit on the form lets you handle it too
* Handling multiple forms
  * when a form is submitted, the key value pairs are sent
  * the name attached to the submit button is included
  * check for different names to determine which form was submitted
  * or same key, check value instead
  * also could change the action to use different end points
* Uploading files
  * input type of file -> filepicker
  * change the encoding type to multipart/form-data to actually send the data
  * default doesn't send file, just gets the filename in key-value pairs

#### HTML form server processing
* Accessing Data
  * ASP.net has Request object
  * PHP has special $_ functions/collections, $_POST, $_GET
  * Ruby has Request object too
  * often name-value pairs
* Uploading files
  * ASP.net has files collection
  * $_Files collection in PHP
  * Ruby params collection but the object we get out is a file with data
* Required Processing!
  * HTML encoding -> take user and display it safely
  * cross site scripting
  * input validation
  * SSL
* Model View Controller
  * View is presentation -> HTML example
  * Model represents the data
  * Controller coordinates the model and the view
